# Google Spanner

## Google Spanner: execute a SQL query&#x20;

It is possible to execute a SQL query on a single Spanner table and get the whole result set as a JSON string.

**Syntax**

```javascript
var json = utils.executeQueryOnGoogleSpanner(
  String sql,
  Long dataModelId,
  Boolean interruptExecution,
  Object... pars
);
```

| Argument           | Description                                                                                                                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| sql                | SQL query to execute; the constraint is that the query must retrieve all fields of the table identified by the data model id; you can make the WHERE condition as complex as needed. |
| dataModelId        | a data model identifying a Spanner already existing table                                                                                                                            |
| interruptException | flag used to fire an exception in case of SQL errors                                                                                                                                 |

**Important note:** do NOT use this method to retrieve a long result se (more than a hundred records).

## Google Spanner: execute a SQL query **and retrieve a block of data**

It is possible to execute a SQL query on a single Spanner table and get a partial result set, a block of data to fill in a grid. This method is helpful within a server-side javascript business component bounded to a grid.

**Syntax**

```javascript
var json = utils.getPartialResultOnGoogleSpanner(
  String sql,
  Long dataModelId,
  Boolean interruptExecution,
  Object... pars
);
```

**Details**

| Argument           | Description                                                                                                                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| sql                | SQL query to execute; the constraint is that the query must retrieve all fields of the table identified by the data model id; you can make the WHERE condition as complex as needed. |
| dataModelId        | a data model identifying a Spanner already existing table                                                                                                                            |
| interruptException | flag used to fire an exception in case of SQL errors                                                                                                                                 |

This method also parses the HTTP request parameters passed forward by the calling grid (current block of data and block size) as well as filtering and sorting conditions coming from the grid.

## Google Spanner: insert records in a table from a list of javascript objects

This method is helpful when you need to insert one or more records in a Spanner table, starting from the data model id related to such a table.

**Syntax**

```javascript
var ok = utils.insertObjectsOnGoogleSpanner(
  Map[] objects,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument           | Description                                                                                                                                                           |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| objects            | a javascript array of objects, where each object represents a record to insert; the object attributes must be the same defined as fields in the data model definition |
| dataModelId        | a data model identifying a Spanner already existing table                                                                                                             |
| interruptException | flag used to fire an exception in case of SQL errors                                                                                                                  |

## Google Spanner: update a single record in a table from a javascript object

This method is helpful when you need to update a record in a Spanner table, starting from the data model id related to such a table.

**Syntax**

```javascript
var ok = utils.updateObjectOnGoogleSpanner(
  Map object,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument           | Description                                                                                                                                  |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| object             | a javascript object representing the record to update; the object attributes must be the same defined as fields in the data model definition |
| dataModelId        | a data model identifying a Spanner already existing table                                                                                    |
| interruptException | flag used to fire an exception in case of SQL errors                                                                                         |

## Google Spanner: merge a single record in a table from a javascript object

This method is helpful when you need to update a record in a Spanner table, starting from the data model id related to such a table and a javascript object. The performed operation is a "merge", i.e. only attributes passed forward through the input objects are updated: the ones not passed are ignored and their previous values are maintained. Behind the scene, a select is first needed in order to get the whole record and this is then "updated" for the attributes passed as input: the merging object is finally saved on the table.

**Syntax**

```javascript
var ok = utils.mergeObjectOnGoogleSpanner(
  Map object,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument           | Description                                                                                                                                          |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| object             | a javascript object representing the record to update (merge); the object attributes must be the same defined as fields in the data model definition |
| dataModelId        | a data model identifying a Spanner already existing table                                                                                            |
| interruptException | flag used to fire an exception in case of SQL errors                                                                                                 |

## Google Spanner: update multiple records in a table from a list of javascript objects

This method is helpful when you need to update one or more records in a Spanner table, starting from the data model id related to such a table.

**Syntax**

```javascript
var ok = utils.updateObjectsOnGoogleSpanner(
  Map[] objects,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument           | Description                                                                                                                                                           |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| objects            | a javascript array of objects, where each object represents a record to update; the object attributes must be the same defined as fields in the data model definition |
| dataModelId        | a data model identifying a Spanner already existing table                                                                                                             |
| interruptException | flag used to fire an exception in case of SQL errors                                                                                                                  |

## Google Spanner: delete one or more records starting from a list of javascript objects

This method is helpful when you need to update one or more records in a Spanner table, starting from the data model id related to such a table.

**Syntax**

```javascript
var ok = utils.deleteObjectOnGoogleSpanner(
  Map object,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument           | Description                                                                                                                                |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| object             | a javascript object representing a record to delete; the object attributes must be the same defined as fields in the data model definition |
| dataModelId        | a data model identifying a Spanner already existing table                                                                                  |
| interruptException | flag used to fire an exception in case of SQL errors                                                                                       |

\
Google Spanner: insert/update a large number of records in a table from Google Datastore
----------------------------------------------------------------------------------------

This method is helpful when you need to execute a bulk import of records in a Spanner table, starting from records coming from Google Datastore. Records can be inserted or updated.

**Syntax**

```javascript
var ok = utils.bulkImportFromDSToSpanner(
  String gql,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument           | Description                                                                                                                                                                                                                                                                        |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| gql                | a GQL query to execute on Google Datastore: for each record read, a corresponding record is inserted/updated in the Spanner table (the Spanner table must be a duplicate of the one in Datastore, created through the Data Model -> Duplicate object from Datastore functionality) |
| dataModelId        | a data model identifying a Spanner already existing table                                                                                                                                                                                                                          |
| interruptException | flag used to fire an exception in case of SQL errors                                                                                                                                                                                                                               |

