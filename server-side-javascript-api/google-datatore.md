# Google Datastore

## Execute a GQL query into a Google Datastore

The datastore must be already configured as a global parameter.Once done that, it is possible to execute a query statement, in order to fetch a list of entities.  
The query language is GQL: filtering and sorting conditions are strinctly ruled by the Google datastore. That means that additional indexes could be defined before executing the query. For instance, = operators can be used without additional indexes, but it is not so for sorting conditions or filtering conditions having not equal operators \(e.g. &lt;, &lt;=, etc.\).  
See Datastore syntaxto get detail information about the syntax to use when filtering entities.

**Syntax**

```javascript
var json = utils.executeQueryOnGoogleDatastore(gql,dataModelId,interruptExecution, params);
```

**Details**

| Argument | Description |
| :--- | :--- |
| gql | string value: GQL queryto execute; it can contain ? or :XXX |
| dataModelId | it identifies the data model having "datastore" type, related to the entity to enquiry, so the GQL query must refer the same entity name related to the specified data model |
| interruptExecution | boolean value; if true, an erroneous GQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| params | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma \(do not use \[\]\); these additional parameters represent values which replace ? symbols in the sql statement. |
|  | XXX variable can be replaced by vo or params values |

Example

```javascript
var json = utils.executeQueryOnGoogleDatastore(
"SELECT * FROM Products WHERE companyId=:COMPANY_ID AND enabled='Y' ",
XXX, // XXX must be the data model id
true, // fire an Execution in case of error
[]
);
```

Note: every GQL instruction will be logged.

Note: in case of a data model where there are attributes having type **Array**, this method will get back also the array value, expressed as a String whose values are separated by a comma.

## Execute a GQL query into a Google Datastore: only a block of data is fetched

**This method can be coupled with a grid panel where the data loading is limited to a block of data. Optional filtering/sorting conditions coming from the grid are automatically applied to the base GQL query. Note that filterable/sortable columns should be carefully defined according to the limits come with the Google Datastore and custom indexes must be defined in the Datastore first.**

The datastore must be already configured as a global parameter.Once done that, it is possible to execute a query statement, in order to fetch a list of entities.  
The query language is GQL: filtering and sorting conditions are strinctly ruled by the Google datastore. That means that additional indexes could be defined before executing the query. For instance, = operators can be used without additional indexes, but it is not so for sorting conditions or filtering conditions having not equal operators \(e.g. &lt;, &lt;=, etc.\).  
See Datastore syntaxto get detail information about the syntax to use when filtering entities.

**Syntax**

```javascript
var json = utils.getPartialResultOnGoogleDatastore(gql,dataModelId,interruptExecution, params)
```

**Details**

| Argument | Description |
| :--- | :--- |
| gql | string value: GQL queryto execute; it can contain ? or :XXX |
| dataModelId | it identifies the data model having "datastore" type, related to the entity toinsert |
| interruptExecution | boolean value; if true, an erroneous insertinstruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| params | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma \(do not use \[\]\); these additional parameters represent values which replace ? symbols in the sql statement. |
|  | XXX variable can be replaced by vo or params values |

**Example**

```javascript
var json = utils.getPartialResultOnGoogleDatastore(
"select * from Products where companyId=:COMPANY_ID and enabled='Y' ",
XXX, // XXX must be the data model id
true, // fire an Execution in case of error
[]
);
```

Note: every GQL instruction will be logged.

Note: in case of a data model where there are attributes having type **Array**, this method will get back also the array value, expressed as a String whose values are separated by a comma.

## Get a single entity from Google Datastore

Reading and writing data on Google Datastore is costly, so it is important to limit the amount of queries to execute. A best practice is to cache single entity reading in the internal Platform cache and maintain it for a little time, like a minute or 10 minutes.

An ad hoc method is provided in order to do it:

```javascript
var jsonString = utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities,long expirationTime);
```

**Syntax**

| Argument | Description |
| :--- | :--- |
| entityName | entity name identifying the table in Datastore \(it is case sensitive\) |
| key | primary key value |
| maxCachedEntities | max number of cached objects for this entity; this is helpful to reduce the cost involved with the reading operation; set it to 0 to by-pass the cache and get a freshed object \(not recommended\) |
| expirationTime | expiration time, expressed in minutes; after that time, the object is removed from cache |
| jsonString | a string representation \(JSON format\) of the returned object; a Date value is returned with this format: yyyy-MM-dd HH:mm:ss a null value is returned in case no object is retrieved startingfrom the specified pk value |

## Insert a single entity into the Google Datastore

The entity is expressed as a Javascript object.

The datastore must be already configured as a global parameter.Once done that, it is possible to execute operations on the Google Datastore.

**Syntax**

```javascript
var json = utils.insertObjectOnGoogleDatastore(obj, dataModelId, interruptExecution);
```

**Details**

| Argument | Description |
| :--- | :--- |
| obj | a Javascript object containing the data to save in the specified Datastoreentity |
| dataModelId | it identifies the data model having "datastore" type, related to the entity to insert |
| interruptExecution | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of the operation |
| ok | true in case of the operation has been executed successfully, an exception otherwise |

Note: in case of a data model where there are attributes having type **Array**, this method will get back also the array value, expressed as a String whose values are separated by a comma.

## Insert multiple entities into the Google Datastore

The datastore must be already configured as a global parameter. Once done that, it is possible to execute operations on the Google Datastore.

**Syntax**

```javascript
var json = utils.insertObjectsOnGoogleDatastore(objects, dataModelId, interruptExecution);
```

**Details**

| Argument | Description |
| :--- | :--- |
| objects | a Javascript array containing a list of objects to save in the specified Datastore entity; insert is transactional |
| dataModelId | it identifies the data model having "datastore" type, related to the entities to insert |
| interruptExecution | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of the operation |
| ok | true in case of the operation has been executed successfully, an exception otherwise |

Note: in case of a data model where there are attributes having type **Array**, this method will get back also the array value, expressed as a String whose values are separated by a comma.

## Update a single entity into the Google Datastore

The entity is expressed as a Javascript object

The datastore must be already configured as a global parameter.Once done that, it is possible to execute operations on the Google Datastore.

**Syntax**

```javascript
var json = utils.updateObjectOnGoogleDatastore(obj, dataModelId, interruptExecution);
```

**Details**

| Argument | Description |
| :--- | :--- |
| obj | a Javascript object containing the data to save in the specified Datastore entity |
| dataModelId | it identifies the data model having "datastore" type, related to the entity to update |
| interruptExecution | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of the operation |
| ok | true in case of the operation has been executed successfully, an exception otherwise |

Note: in case of a data model where there are attributes having type **Array**, this method will get back also the array value, expressed as a String whose values are separated by a comma.

## Update multiple entities into the Google Datastore

Entities are expressed as Javascript objects.

The datastore must be already configured as a global parameter. Once done that, it is possible to execute operations on the Google Datastore.

**Syntax**

```javascript
var json = utils.updateObjectsOnGoogleDatastore(objects, dataModelId, interruptExecution);
```

**Details**

| Argument | Description |
| :--- | :--- |
| objects | a Javascript array containing a list of objects to save in the specified Datastore entity. Update is transactional. |
| dataModelId | it identifies the data model having "datastore" type, related to the entities to update |
| interruptExecution | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of the operation |
| ok | true in case of the operation has been executed successfully, an exception otherwise |

Note: in case of a data model where there are attributes having type **Array**, this method will get back also the array value, expressed as a String whose values are separated by a comma.

## Delete a single entity from the Google Datastore

The entity is expressed as a Javascript object.

The datastore must be already configured as a global parameter.Once done that, it is possible to execute operations on the Google Datastore.

**Syntax**

```javascript
var json = utils.deleteObjectOnGoogleDatastore(obj, dataModelId, interruptExecution);
```

**Details**

| Argument | Description |
| :--- | :--- |
| obj | a Javascript object related to the entity stored in the Datastore and to remove |
| dataModelId | it identifies the data model having "datastore" type, related to the entity to remove |
| interruptExecution | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of the  operation |
| ok | true in case of the operation has been executed successfully, an exception otherwise |

## Bulk update on Google Datastore

The datastore must be already configured as a global parameter.Once done that, it is possible to execute operations on the Google Datastore.

This method updates already existing entities in Datastore, starting from a GQL query on that kind of Entity and for all fetched entities, apply an update.

It is possibile to specify new attributes/attributes to change, through the "valuesToSet" argument.

It is possible to remove already existing attributes, through the "valuesToRemove" map \(e.g. { "attrName": true }

It is possible, optionally, to specify an action id, related to an action to execute for each fetched entity: it can be used to execute additional business logic and decide how to fill every entity. If specified, the bulk update will be slower.

**Syntax**

```javascript
utils.bulkUpdateOnGoogleDatastore(gql, valuesToSet, valuesToRemove, actionId);
```

**Details**

| Argument | Description |
| :--- | :--- |
| gql | GQL query, used to read records to update; bulk update will be applied only of the records filtered in this query |
| valuesToSet | map of attributes+values to set; here it is possible to specifiy new attributes or already existing attributes; |
| valuesToRemove | map of attributes+useless values; only attribute names are used here, in order to remove them form the entity |
| actionId | not managed yet; set to null |

## Bulk delete on Google Datastore

The datastore must be already configured as a global parameter.Once done that, it is possible to execute operations on the Google Datastore.

This method delete already existing entities in Datastore, starting from a GQL query on that kind of Entity and it removes from Datastore all fetched entities.

**Syntax**

```javascript
utils.bulkDeleteOnGoogleDatastore(gql);
```

**Details**

| Argument | Description |
| :--- | :--- |
| gql | GQL query, used to read records to delete; bulk delete will be applied only of the records filtered in this query |

## Move data from Datastore to BigQuery

The datastore must be already configured as a global parameter.Once done that, it is possible to execute operations on the Google Datastore.

This method delete already existing entities in Datastore, starting from a GQL query on that kind of Entity and it removes from Datastore all fetched entities.

**Syntax**

```javascript
utils.createBigQueryTableFromDatastoreEntities(
        String[] entityNames,
        Long directoryId,
        String datasetName
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| entityNames | list of Datastore entities to extract as is and move to BigQuery |
| directoryId | directory identifier in Google Cloud Storage, where saving temporarely the exported data |
| datasetName | dataset name in the BigQuery repostiroy where re-creating the same tables |

## Move users definition form Platform Standard to Datastore

In case there is a Platform Standard installation used to manage a Platform for GAE application, it can be helpful to move all users from the standard to GAE, i.e. within the Users entity of a Google Datastore NOSQL database.

**Syntax**

```javascript
utils.exportUsersToDatastore();
```

This method moves users to Datastore Users entity \(for all company ids\).

