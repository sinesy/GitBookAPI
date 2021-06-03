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
      null, // priority: not managed
      null, // process wait time: not managed
      false, // log execution: not managed
      null, // optional payload, expressed as a String
      null  // optional: max retries as a number
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

## Checking for element termination

When enqueuing an element in AppEngine, the "**enqueueActionWithNoteAsString**" method returns an uuid identifying the specific element appended to the queue.

Optionally, you can pass forward any payload \(for example a unique identifier as String or a JSON String\) to such method, using the "note" argument. You can later use this information to check for the element termination, using the "**getElementFromQueueByNote**" method, which enquiry the queue management system, searching from an element having the specified payload.

**Syntax**

```javascript
var json = utils.getElementFromQueueByNote(String payload,String namespace);
```

The payload argument is used to search for an element still inside the queue, having that payload bounded.

If it exists, the method returns the element in queue \(a JSON String representing the enqueued element\). 

An example of returned JSON is:

```javascript
{
  "appId": "GAE",
  "companyId": "00000",
  "siteId": 100,
  "queueName": "queue1",
  "actionId": 119,
  "note": "123",
  "status": "ERROR",
  "createDate": "Jun 3, 2021 3:59:53 PM",
  "json": "{\"userInfo\":{\"applicationId\":\"GAE\",\"companyId\":\"00000\",\"siteId\":100,\"useGridSuffix\":false,\"prm40ApplUserPars\":{},\"customApplUserVars\":{},\"useFormSuffix\":false,\"username\":\"ADMIN\",\"languageId\":\"EN\"},\"internalState\":{\"appParams\":{},\"enabledFunctionIds\":{},\"customTraslations\":{},\"syncAlfrescoUsers\":false,\"syncAlfrescoUserRoles\":false,\"syncAlfrescoRoles\":false,\"password\":\"admin\",\"showRoleId\":false,\"showSiteId\":false,\"editUserSiteId\":false,\"googleServiceAccountEmail\":\"711439762495-38h1rs18fbp4scgt4th1gqok4qjltb2u@developer.gserviceaccount.com\",\"googlePrivateKeyString\":\"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 hHvg2NS9+Oc03CU6KVfsSPsbAgIEAA\\u003d\\u003d\",\"googleServiceAccountAdminUser\":\"lorenzo.zimolo@sinesy.it\",\"googleClientSecret\":\"j6tPwEOOlmePBmkdJImga3Vc\",\"showAlertMenuItem\":false,\"showChatPopupMessage\":false,\"hideChatToastMessage\":false,\"autoDefineUploadFileName\":false,\"disableGoogleaMapLibs\":false,\"hidePlatformLogo\":false,\"maxNumberOfExportableRows\":100000,\"menuButtonsCols\":5,\"menuButtonsAutosize\":true,\"menuButtonsWidth\":150,\"menuButtonsHeight\":50,\"menuButtonsImageWidth\":32,\"menuButtonsImageHeight\":32,\"menuButtonsRoundBorder\":0,\"menuButtonsTextUpperCase\":false,\"hideImagesInTabsMenu\":false,\"menuButtonsShowBack\":false,\"menuButtonsNoEsc\":false,\"encriptPasswords\":false,\"duplicatePerCompany\":true,\"checkFunctionIdsWhenReadingData\":false,\"autoEncriptData\":true,\"reshowButtonsMenu\":false,\"windowPanesToHide\":{},\"exportUsingHSSF\":false,\"datasetId\":\"sinesy4wsplatform\",\"licensed\":true,\"fileStorage\":\"FILE_SYSTEM\",\"googleCloudStorageLocation\":\"US\",\"googleCloudProjectId\":\"sinesy4wsplatform\",\"googleSpeechVoiceFlag\":false,\"twilioAccountId\":\"AC8acaec2fc5eaf209a18f05e50a8b2675\",\"twilioAuthToken\":\"449958d1458f8852ed183a64c40ec5d1\",\"sdi\":false,\"createCompanySite\":true,\"aliasesRequestNum\":{},\"enabledMenuFunctionIds\":{},\"namespace\":\"SVIL\",\"enabledComponentIds\":[],\"headersLowercase\":true,\"removeSession\":false,\"autoEncriptParams\":false,\"bigQueryDataset\":\"test_mauro\",\"userInfo\":{\"applicationId\":\"GAE\",\"companyId\":\"00000\",\"siteId\":100,\"useGridSuffix\":false,\"prm40ApplUserPars\":{},\"customApplUserVars\":{},\"useFormSuffix\":false,\"username\":\"ADMIN\",\"languageId\":\"EN\"}},\"vo\":{\"id\":123}}"
}
```

There are two possibilities for having still and element returned:

* the element is still in queue; in such a case, the "status" attribute is set to "ENQUEUED"
* the element has been dequeued but not processed correctly and error was fired during the elaboration; in such a case, the "status" attribute is set to "ERROR"

If the method returns null, it means the element has been already processed and removed from the queue.

\*\*\*\*

**Example**

Thread where the element is enqueued:

```javascript
var myDocumentId = "...";
var documentToProcess = {
  id: myDocumentId,
  ...
};

var uuid = utils.enqueueActionWithNoteAsString(
      "QueueName",
      actionIdInvokedByTheQueue,
      documentToProcess, // parameters to pass forward to the enqueued action
      null, // priority: not managed
      null, // process wait time: not managed
      false, // log execution: not managed
      myDocumentId, // payload, expressed as a String
      null  // optional: max retries as a number
);





```

Another thread, checking for element termination

```javascript
var myDocumentId = "..."; // the same value used in the firdt thread
var namespace = "...";

var element = utils.getElementFromQueueByNote(myDocumentId, namespace);
if (element!=null) {
    // the enqueued element can be in queue or dequeued and terminated with errors
    var outcome = JSON.parse(element);
    if (outcome.status=="ENQUEUED") {
      // element still enqueued...
    } 
    else {
      // what to do in such a case?
    }
}
else {
    // the element has been dequeued and processed correctly and no more in queue
}
```



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

