# MongoDB

## Execute a query into a Mongo DB

The Mongo DBmust be already configured through theglobal parameters. Once done that, it is possible to execute a query statement, in order to fetch a list of documents.  
The query language must fit the Mongo DB syntax: filtering and sorting conditions are as powerful as the ones available with the standard SQL language, but expressed with a different syntax. In order to get quick responses when executing enquires, it is important to define special indexes. These can be defined in the "Indexes" folder of the data model definition.  
SeeMongo DB syntaxto get detail information about the syntax to use when filtering documents.

**Syntax**

```javascript
var json = utils.executeQueryOnMongoDb(where,dataModelId,interruptExecution, params);
```

**Details**

| Argument | Description |
| :--- | :--- |
| where | string value: it represents only the where part of the query; it can contain ? or :XXX |
| dataModelId | it identifies the data model having "Mongo DB" type, related to the collectionto enquiry, so the query must refer the same collectionname related to the specified data model |
| interruptExecution | boolean value; if true, an erroneous instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| params | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma \(do not use \[\]\); these additional parameters represent values which replace ? symbols in the sql statement. |
| An | XXX variable can be replaced by vo or params values |

**Example**

```javascript
var json = utils.executeQueryOnMongoDb(
"{ companyId: :COMPANY_ID }, { price: { gt: 1234.5 } } ",
XXX, // XXX must be the data model id
true, // fire an Execution in case of error
[]
);
```

Note: every query instruction will be logged.

## Execute a query into a Mongo DB: only a block of data is got back

_This method can be coupled with a grid panel where the data loading is limited to a block of data. Optional filtering/sorting conditions coming from the grid are automatically applied to the base query_.

The Mongo DBmust be already configured through theglobal parameters. Once done that, it is possible to execute a query statement, in order to fetch a list of documents.  
The query language must fit the Mongo DB syntax: filtering and sorting conditions are as powerful as the ones available with the standard SQL language, but expressed with a different syntax. In order to get quick responses when executing enquires, it is important to define special indexes. These can be defined in the "Indexes" folder of the data model definition.  
SeeMongo DB syntaxto get detail information about the syntax to use when filtering documents.

**Syntax**

```javascript
var json = utils.getPartialResultOnMongoDb(where,dataModelId,interruptExecution, params)
```

**Details**

| Argument | Description |
| :--- | :--- |
| where | string value: it represents only the where part of the query; it can contain ? or :XXX |
| dataModelId | it identifies the data model having "Mongo DB" type, related to the collectionto enquiry, so the query must refer the same collectionname related to the specified data model |
| interruptExecution | boolean value; if true, an erroneous instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| params | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma \(do not use \[\]\); these additional parameters represent values which replace ? symbols in the sql statement. |
| An | XXX variable can be replaced by vo or params values |

**Example**

```javascript
var json = utils.getPartialResultOnMongoDb(
"{ companyId: :COMPANY_ID},{ enabled: "Y" } ",
XXX, // XXX must be the data model id
true, // fire an Execution in case of error
[]
);
```

Note: every queryinstruction will be logged.

## Insert a single document into the Mongo DB

The document is expressed as a Javascript object

The Mongo DBmust be already configured through theglobal parameters.Once done that, it is possible to executeoperations on it.

**Syntax**

```javascript
var returnedObj = utils.insertObjectOnMongoDb(obj,dataModelId,interruptExecution);
```

**Details**

| Argument | Description |
| :--- | :--- |
| obj | a Javascript object containing the data to saveas a document in the Mongo DB collection specified through the data store id |
| dataModelId | it identifies the data model having "Mongo DB" type, related to the collection whereinserting data |
| interruptExecution | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of theoperation |
|  | returnedObj: the object passed as argumentin case of the operation has beenexecuted successfully, an exception otherwise |

Note that the returned objectcontains additional data: the "id" atttribute represents the primary key of any document in Mongo DB and it is automatically generated by the database and got back by this method.

In case the defined data model includes unique keys, these are checked out before executing the instruction and an exception is fired in case of a unique key violation.

In case the defined data model includes a counter \(e.g. internal counter\), this is automatically reckoned internally and got back to the returned object, which would contained it as well.

## Update a single document into the Mongo DB

The document is expressed as a Javascript object

The Mongo DBmust be already configured through theglobal parameters.Once done that, it is possible to executeoperations on it.

**Syntax**

```javascript
var ok = utils.updateObjectOnMongoDb(obj,dataModelId,interruptExecution);
```

**Details**

| Argument | Description |
| :--- | :--- |
| obj | a Javascript object containing the data to saveas a document in the Mongo DB collection specified through the data store id |
| dataModelId | it identifies the data model having "Mongo DB" type, related to the collection where updatingdata |
| interruptExecution | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of theoperation |
|  | ok: true in case of the operation has beenexecuted successfully, an exception otherwise |

In case the defined data model includes unique keys, these are checked out before executing the instruction and an exception is fired in case of a unique key violation.

## Delete an already existing document from the Mongo DB

The document is expressed as a Javascript object.

The Mongo DBmust be already configured through theglobal parameters.Once done that, it is possible to executeoperations on it.

**Syntax**

```javascript
var returnedObj = utils.deleteObjectOnMongoDb(obj,dataModelId,interruptExecution);
```

**Details**

| Argument | Description |
| :--- | :--- |
| obj | a Javascript object containing the data to removefromthe Mongo DB collection specified through the data store id |
| dataModelId | it identifies the data model having "Mongo DB" type, related to the collection where deletingdata |
| interruptExecution | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of theoperation |
|  | ok: true in case of the operation has beenexecuted successfully, an exception otherwise |

