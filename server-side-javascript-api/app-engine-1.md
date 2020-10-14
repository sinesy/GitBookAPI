# Google App Engine

## Checking for authorizations

GAE javascript actions are stateless web services, that is to say, they do not store conversational state among different calls. 

These actions can be invoked directly or, even better, through an alias \(api?cmd=...\).

In any case, an authentication process is required, in order to successfully invoke an action.

Authentication can be performed in 2 alternative ways:

* by invoking "**login**" standard ws first, get a token and use it for any subsequent invocation of a GAE action by pass the token along with the other input parameters
* by invoking directly a GAE action an **pass credentials** along with the other input parameters

In any case, credentials are required and must be provided always as request headers.

Moreover, in the first case the needTmpToken is required too, in order to ask Platform for GAE to get back a token to use in the next requests.

Optionally, it is possible to ask Platform to fetch authorizations as well, when carrying out the authentication process. Authorizations are the list of granted roles associated to the specified user.

This can be carried out b y including in the request the "**loadRoles=Y**" header parameter.

Finally, the **utils.checkRoles\(roleId\)** method can be included in any GAE action, in order to force Platform for GAE to check for that role as a role bound to the current user. This checking is performed ONLY IF "loadRoles=Y" has been previously included in the authentication request.

## Reading data from Datastore

When there is the need to read a sigle entity, **it is strongly recommended to use the following method to read a single record by key** instead of executing a query where the filter condition limits the number of record, since reading a single record by key is cheaper.

**Syntax**

```javascript
var json = utils.getEntityAsJSON(entityName, key, maxCachedEntities);
utils.setReturnValue(json);
```

Parameters

| Pararamer | Meaning |
| :--- | :--- |
| entityName | data model name, where the record to read is stored |
| key | the id which identifies the record to read |
| maxCachedEntities | total amount of records for this entity which will be cached in order to reduce the number of real readings and hence reduce the reading costs. It is recommended to always set this value &gt;0. **A 0 value is allowed when it is essential to get always a freshed version of the record** \(never for read only entities...\), i.e. for objects written concurrently. |

## Reading data from Datastore

When there is the need to read a sigle entity, **it is strongly recommended to use the following method to read a single record by key** instead of executing a query where the filter condition limits the number of record, since reading a single record by key is cheaper.

**Syntax**

```javascript
var json = utils.getEntityAsJSON(entityName, key, maxCachedEntities, expirationTime);
utils.setReturnValue(json);
```

Parameters

| Pararamer | Meaning |
| :--- | :--- |
| entityName | data model name, where the record to read is stored |
| key | the id which identifies the record to read |
| maxCachedEntities | total amount of records for this entity which will be cached in order to reduce the number of real readings and hence reduce the reading costs. It is recommended to always set this value &gt;0. **A 0 value is allowed when it is essential to get always a freshed version of the record** \(never for read only entities...\), i.e. for objects written concurrently. |
| expirationTime | expiration time, expressed in minutes |

## Execute a long HTTP\(s\) requestExecute a long HTTP\(s\) request

AppEngine is a high scalable web container, used to run web services.

In order to provide scalability, it limits all HTTP requests to 30 seconds only. It goes without saying that in case of longer operations, like in case of a sequence of writing operations, there is the need for a queue and the real operations must be postponed to the queue execution.

The best approach is to enqueue operations in a GAE action, using something like:

```javascript
var uuid = utils.enqueueActionWithNoteAsString(
      "QueueName",
      actionIdInvokedByTheQueue,
      { /* parameters to pass forward to the enqueued action*/ },
      null,
      null,
      false,
      null
);
```

This method gets back a unique identifier for the element in queue.

At this point, there are two possible scenarios:

* the client invoking the current action does not need a feedback: that's all
* the client needs a feedback and this action must wait for the termination of the enqueued action

In the latter case, since the HTTP request launched by the client will terminate in 30 seconds \(because GAE will force its termination\), we can wait after the **enqueueActionWithNoteAsString** command, but not for more than 30 seconds. It can be helpful this method:

```javascript
var json = utils.blockingWaitAllElements(20,[uuid]);
utils.setReturnValue(json);
```

In this example, this method will wait up to 20 seconds, until all enqueued elements specified in list will be terminated.

If after the specified timeout \(expressed in seconds\), not all of the elements are still finished, the method ends gracefully and get back the list of not terminated element ids, which can be provided to the client.

Consequently, the client should invoked a second request, to a third action which should contain only the previous instructions, so that it can determine when the actions are terminated.

## Capturing enqueued action outcome

The enqueued action can also provide a feedback to the invoking action or to any other action; the action return value \(JSON content\) is automatically cached internally, referred by the enqueued action uuid. That means that if the enqueued action terminates by providing some content \(either a successful or a wrong outcome\), like in this scenario:

```javascript
var response = { success: true, someData: "..." };
if (somethingWrong) {
 response = { success: false, message: "..." };
}
utils.setReturnValue(JSON.stringify(response));
```

this content can be accessed, for example from the calling action, through the uuid:

```javascript
var uuid = utils.enqueueActionWithNoteAsString(
      "QueueName",
      actionIdInvokedByTheQueue,
      { /* parameters to pass forward to the enqueued action*/ },
      null,
      null,
      false,
      null
);
var json = utils.blockingWaitAllElements(20,[uuid]);
if (json=="[]") {
  // enqueued action has terminated on time...
  var json = utils.getValueInCache(uuid); // this value automatically expires in 1 minute
  var response = JSON.parse(json); // { success: ..., ...}
}
utils.setReturnValue(json);
```

Bear in mind that cached response for an enqueued action is available up to 1 minute, after that time, the content is automatically removed from the cache.

## Concurrent writing operations

As long as the **updateObject/updateObjects** are used, the Google Datastore automatically provides a checking which avoids the possibility to update the same object multiple times, starting from old states of the object: it means that if concurrent requests to writing operations are performed, only the ones starting from a consistent state from the Datastore will be allowed. The others will fire an exception, **which must be captured and managed appropriately** by the GAE javascript code.

Let's take the classical example of a counter table "Counters" whose purpose is to reckon the next value for a counter. A Datastore object used for that goal would be something like:

| Field | Type / PK |
| :--- | :--- |
| id \(companyId\_siteId\_docType\_year\_sectional\) | TEXT |
| companyId | TEXT |
| siteId | NUM |
| docType | TEXT |
| year | NUM |
| sectional | TEXT |
| currentValue | NUM |

The right GAE javascript action should manage the possibility of a concurrent access exception and attempt multiple times to get the next value:

```javascript
var todayStr = new Date().toISOString().substring(0, 10);
var sectional = reqParams.ente+"_"+reqParams.filiale+"_"+todayStr+"_"+reqParams.registerNr;
var key = userInfo.companyId+"_"+userInfo.siteId+"_"+reqParams.docType+"_"+new Date().getFullYear()+"_"+sectional;
var attempts = 0;
var currentValue = null;
var json = utils.getEntityAsJSON("Counters",key, 0); // always set to 0 the cache, so that the record is always read

if (json==null) {
  // insert record...
  currentValue = 1;
  try {
    // ...
  }
  catch(e) {
    // insert failed, because in the meantime another concurrent request has inserted the same record:
    // let's convert the insert to update, i.e. let's go on
    json = utils.getEntityAsJSON("Counters", key, 0); // always set to 0 the cache, so that the record is aways read
  }
}

if (json!=null) {
  // update record concurrently
  do {
    try {
      attempts++;
      vo = JSON.parse(json);
      vo.currentValue = vo.currentValue+1;
      utils.updateObject(vo,...);
      currentValue = vo.currentValue;
      break;
    }
    catch(e) {
      // concurrent exception: reload a freshed version of the record
      json = utils.getEntityAsJSON("Counters", key, 0); // always set to 0 the cache, so that the record is aways read
    }
  }
  while(attempts<100);
  if (currentValue==null)
    throw "Update not performed: try later";
}

utils.setReturnValue(JSON.stringify({ success: true, currentValue: currentValue }));
```

## How to manage distributed transactions and SAGA

Since Google Datastore is a NoSQL database, the ACID \(atomic, concurrent, isolated, durable\) properties supported by a relational database cannot be applied.

Consequently, when multiple writing operations on different entity types are required, it is not possible to count on the Database behavior. The best way to manage a distributed transaction over multiple entity types, is to manage it as for a micro-service architecture, based on the SAGA pattern \(see for example: [https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part-2\](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part-2%29\), using the "**command-orchestration sequencing logic**", where a main javascript action would orchestrate all operations, by invoking each of them sequentially.

In case of an error fired by any of the invoked actions, the main javascript action has the duty to "undo" any writing operation already carried out, by deleting them. That means that every invoking object should not only provide a "writing operation" but also an "undo" operation, to clean up any writing operation already done.

![](https://i1.wp.com/blog.couchbase.com/wp-content/uploads/2018/01/Screen-Shot-2018-01-11-at-7.40.54-PM.png?resize=1300%2C796&ssl=1)

When comparing Platform with the schema above:

* the "Order Service" represents the GAE javascript action invoked by a web/mobile client
* the "Order Saga Orchestrator" is the GAE javascript action enqueued by the previous one, which is invoked asynchronously
* "Payment Service", "Stock Service" and "Delivery Service" represent additional GAE javascript actions which can be called by the previous enqueued action. **In the easiest case**, **we can embed this logic as a sequence of writing operations within the "Order Saga Orchestrator" action,** which has the purpose of managing the "rollback" operations as well, in case of errors during the sequence of writing operations. In the most complex scenario, these 3 additional actions are enqueued too by the "Order Saga Orchestrator" into:
  * 3 distinct queues, if it makes sense to parallelize these 3 operations; a **blockingWaitAllElements** is required, in order to check out if all operations completed correctly or to manage the undo task
  * a unique queue, where the "Payment Service" is enqueued, waiting for its termination through the **blockingWaitAllElements** method; when completed correctly, the second actions is enqueued; same approach for the third. Undo operations are managed after each **blockingWaitAllElements** termination, if needed.

