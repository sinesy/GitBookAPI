# Sql

## Generic SQL execution (NO SQL queries) <a href="executesql" id="executesql"></a>

**Syntax**

```javascript
var rows = utils.executeSql(sql, dataSourceId, separatedTransaction, interruptExecution, params)
```

**Details**

| Argument             | Description                                                                                                                                                                                                          |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| rows                 | int value: number of processed rows                                                                                                                                                                                  |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                              |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                           |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE_NEW EJB directive)                                                               |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                       |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql statement. |

An :XXX variable can be replaced by vo or params values

**Example**

```javascript
var updatedRowsNr = utils.executeSql(
"UPDATE PRM01_USERS SET USER_CODE_ID=:USER_CODE_ID, DESCRIPTION=:USER_CODE_ID WHERE COMPANY_ID= :COMPANY_ID AND STATUS=? AND LOCKED=?",
null, // no additional datastore!
false, // do it on a separated transaction
true, // fire an Exception in case of error
["E", "N"]
);
```

Note: every SQL instruction will be logged.

## Generic SQL execution (NO SQL queries) without logging it

**Syntax**

```javascript
var rows = utils.executeSqlNoLog(
sql,
dataSourceId,
separatedTransaction,
interruptExecution,
params
)
```

**Details**

| Argument             | Description                                                                                                                                                                                                          |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| rows                 | int value: number of processed rows                                                                                                                                                                                  |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                              |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                           |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE_NEW EJB directive)                                                               |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                       |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql statement. |

An :XXX variable can be replaced by vo or params values

**Example**

```javascript
var updatedRowsNr = utils.executeSql(
"UPDATE PRM01_USERS SET USER_CODE_ID=:USER_CODE_ID, DESCRIPTION=:USER_CODE_ID WHERE COMPANY_ID= :COMPANY_ID AND STATUS=? AND LOCKED=?",
null, // no additional datastore!
false, // do it on a separated transaction
true, // fire an Execution in case of error
"E",
"N"
);
```

Note: the SQL operation will not be logged. This method csan be useful with bulk operations, whose execution could slow down if a log message were produced for each execution.

## SQL query execution <a href="executequery" id="executequery"></a>

**Syntax**

```javascript
var jsonList = utils.executeQuery(
sql,
dataSourceId,
separatedTransaction,
interruptExecution,
params
)
```

**Details**

| Argument             | Description                                                                                                                                                                                                      |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| jsonList             | string value: list of json objects, i.e. the result of the query execution                                                                                                                                       |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                          |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                       |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE_NEW EJB directive)                                                           |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                   |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql query. |

An :XXX variable can be replaced by vo or params values

**Example**

```javascript
var rows = utils.executeQuery(
"SELECT USER_CODE_ID,DESCRIPTION FROM PRM01_USERS WHERE COMPANY_ID=:COMPANY_ID AND STATUS=? AND LOCKED=?",
null, // no additional datastore!
false, // do it on a separated transaction
true, // fire an Execution in case of error
"E",
"N"
);
var username = rows[0].userCodeId;
```

## SQL query execution with very long result sets <a href="executequery" id="executequery"></a>

**From 5.4.0 version**

In case of a SQL query returning a very long result set, it is NOT recommended to use the previous method, since it gives back the whole result set at once, which is dangerous because it can consume a large amount of memory on the server.

A better solution is represented by the following method, where the result set is read row by row: for each row, a callback function is invoked, in order to process it.

Consequently, this method cannot be coupled to the user interface, since it would mean that all data would be read in the end. This approach is good when the row processing does not involve the UI, but some other operation on the server side, like writing a text file, starting from the result set.

**Syntax**

```javascript
utils.executeQueryWithCallback(
  callbackFunName,
  sql,
  dataStoreId,
  separatedTransaction,
  interruptExecution,
  params
)
```

**Details**

| Argument             | Description                                                                                                                                                                                                                             |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| callbackFunName      | string value: the name of a callback function, defined inside the action, which will be automatically invoked for each record read from the SQL query. This method must have an argument, which is a js object, representing the record |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                                                 |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                                              |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE_NEW EJB directive)                                                                                  |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                                          |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql query.                        |

An :XXX variable can be replaced by vo or params values

**Example**

```javascript
var processRow = function(record) {
  utils.log(record.userCodeId+" "+record.description,"INFO");
}

utils.executeQueryWithCallback(
"processRow",
"SELECT USER_CODE_ID,DESCRIPTION FROM PRM01_USERS WHERE COMPANY_ID=:COMPANY_ID AND STATUS=? AND LOCKED=?",
null, // no additional datastore!
false, // do it on a separated transaction
true, // fire an Execution in case of error
"E",
"N"
);
```

A more complex example is the one reported as follows, where the SQL query result set is coupled with the export of records to a CSV file on the server file system. The CSV file is built by writing row by row, using an optimized approach based on 3 steps: opening the output stream, writing multiple lines, closing the output stream:

**Example of an optimized approach for reading data from a SQL query + writing data on a CSV file**

```javascript
// open the CSV file, in order to write into it
var fileId = utils.openCSVFile(
    "ab.csv",
    true,
    9, // data source id
    ",",
    true,
    ["userCodeId","password","rowVersion","dateExpirationPassword"], // attributes coming from a row, to manage and export
    [null,null,null,null] // optional data converters (es. from number to text: "0.00")
);

// declare a callback function, invoked by a SQL query, used to write a single line into the CSV file
var processRow = function(jsonRow) {
    utils.writeToCSVFile(fileId,jsonRow);
}

// execute the SQL query, whose result set will be read row by row, by invoking each time the specified callback
utils.executeQueryWithCallback(
    "processRow", // callback function, invoked for each record coming from the query, whose argument will receive a JSON object representing the record
    "SELECT U.USER_CODE_ID,U.DESCRIPTION,U.PASSWORD,U.DATE_EXPIRATION_PASSWORD,U.ROW_VERSION FROM PRM01_USERS U",
    null,
    false,
    true,
    []
);

// close the CSV file, after reading all records from the query
utils.closeCSVFile(fileId);
```

## Execute the specified SQL query and enrich it by adding filtering/sorting and pagination settings <a href="getpartialresult" id="getpartialresult"></a>

These settings can be defined through ListCommand object automatically created when this method is invoked through a "Server JS business component" connected to a grid panel.

**Syntax**

```
var json = utils.getPartialResult(sql, dataStoreId, separatedTransaction, interruptExecution, pars);
```

**Details**

| Argument             | Description                                                                                                  |
| -------------------- | ------------------------------------------------------------------------------------------------------------ |
| Details              |                                                                                                              |
| sql                  | base SQL query                                                                                               |
| dataStoreId          | optional data source id (a number)                                                                           |
| separatedTransaction | flag used to define if this query has to be perfomed in a separated transaction                              |
| interruptExecution   | flag used to defined if the whole server side transation must be interruped and roolbacked in case of errors |
| pars                 | optional (can be expressed as \[] in js) list of parameters binded to ? variables in the SQL query           |

```
 Returns a list of records, expressed in JSON format, which also includes "valueObjectList", "moreRows" and "resultSetLength" attributes.
```

In case of a complex SQL query including aliases, it could be needed to decode the field (to filter/sort) from the grid panel into an alias. You can do it through a specific utility method:setDecodeField(fieldToDecode, decodedField).

In this way, you can control exactly which fields to apply in case of filtering or sorting conditions.

**Example**

```javascript
utils.setDecodeField("ROW_VERSION*ROW_VERSION AS RV","RV");
var json = utils.getPartialResult(
    "SELECT USER_CODE_ID,DESCRIPTION,ROW_VERSION*ROW_VERSION AS RV "+
    "FROM PRM01_USERS "+
    "WHERE STATUS='E'",
    null,
    false,
    true,
    []
);

utils.setReturnValue(json);
```

## Stored SQL function execution <a href="executestoredfunction" id="executestoredfunction"></a>

**Syntax**

```javascript
var json = utils.executeStoredFunction( sql, dataSourceId, separatedTransaction, interruptExecution, params)
```

**Details**

| Argument     | Description                                                                                                                          |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| json         | string value: the result of the function execution                                                                                   |
| sql          | string value: stored function to execute, including its parameters between parenthesis (see example below); it can contains ? or XXX |
| dataSourceId | num value; it can be null and used to specify a different db to                                                                      |

```
 use with the sql statement
```

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE_NEW EJB directive)         |
| interruptedExecution | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| params               | array value: can be \[]; it represents values which replace ? symbols in sql                                                                                   |

**Example **

```javascript
var returnedValue = utils.executeStoredFunction("usercheck1(?, ?)",....
```

## Progressive <a href="getprogressive" id="getprogressive"></a>

**Syntax**

```javascript
var value = utils.getProgressive(String tableName, String columnName,Boolean separatedTransaction, Boolean interruptExecution)
```

**Details**

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| tableName            | String: name of table for calculating progressive                                                                                                              |
| columnName           | String: column name of field to calculating progressive                                                                                                        |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE_NEW EJB directive)         |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |

## Counter

**Syntax**

```javascript
var value = utils.getCount(String tableName, String valueColumnName, String incrementValue, String where, Boolean separatedTransaction, Boolean interruptExecution, Long dataSourceId)
```

**Details**

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| value                | Long: new value of counter                                                                                                                                     |
| tableName            | String: name of table for calculating counter                                                                                                                  |
| valueColumnName      | String: column name of field to calculating counter                                                                                                            |
| incrementValue       | String: increment value for counter                                                                                                                            |
| where                | String: where condition for query                                                                                                                              |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE_NEW EJB directive)         |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| dataSourceId         | additional data source to use when executing this SQL statement; if set to null, the default database connection will be used                                  |

## Get the current date <a href="getcurrentdate" id="getcurrentdate"></a>

helpful when executing a SQL query and a bind variable should be filled out by a dynamic value which is the current date.

**Syntax**

```javascript
var currentDate = utils.getCurrentDate();
```

## Execute synchronously a server-side JS action <a href="executeaction" id="executeaction"></a>

A new SQL transaction is created for this action.

**Syntax**

```javascript
var json = utils.executeAction(Long actionId,Map vo,Map params,Map headers);
```

**Details**

| Argument | Description                                                              |
| -------- | ------------------------------------------------------------------------ |
| actionId | action id related to the action to execute                               |
| vo       | value object to pass                                                     |
| params   | request parameters to pass; read on the other side through reqParams.xxx |
| header   | request headers; read on the other side through reqHeaders.xxx           |

## Execute synchronously a server-side JS action on the same transaction <a href="executeaction" id="executeaction"></a>

The same SQL transaction is reused for this action. This method is recommended in case of database locks when executing the action: a lock usually means that the logic executed here works on the same data managed by the calling action and both are trying to write the same records. In such cases, it is not correct to execute a second action on another transaction, so this second method is the right one to use.

Bear in mind that errors (javascript exceptions) fired during the execution of this action will be affect the main action too, since it is the same transaction. If you do not want that data written by the main action will not be rollbacked, use try-catch keywords to surround the executeActionSameTransaction instruction.

**Syntax**

```javascript
var json = utils.executeActionSameTransaction(Long actionId,Map vo,Map params,Map headers);
```

**Details**

| Argument | Description                                                              |
| -------- | ------------------------------------------------------------------------ |
| actionId | action id related to the action to execute                               |
| vo       | value object to pass                                                     |
| params   | request parameters to pass; read on the other side through reqParams.xxx |
| header   | request headers; read on the other side through reqHeaders.xxx           |

## How to get the field names and types for every fields in the select clause of a SQL query to execute

This can be helpful when creating programmatically a grid and there is the need to know how to format data.

**Syntax**

```javascript
var jsonList = utils.getQueryColumns(sql, dataStoreId, separatedTransaction, interruptExecution, pars);
```

**Details**

| Argument             | Description                                                                                                                                                                                                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sql                  | SQL query to execute, in order to fetch information about each field in the select clause                                                                                                                                                         |
| dataStoreId          | optional parameter (can be null); it defines the additional datastore to use when executing the query                                                                                                                                             |
| separatedTransaction | boolean flag used to define if the SQL query must be execute on a separated transation or not                                                                                                                                                     |
| interruptExecution   | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an errore during the execution of the SQL query                                                                         |
| pars                 | list of parameters required by the SQL query, one for each binding variable; if not needed, set to \[]                                                                                                                                            |
| jsonList             | the list of select fields is expressed as a JSON string, having the following format: \[ { "fieldName": "FIELDXX", "fieldType": 1\|2\|... }, { … } , …] where the fieldType reports the field type according to the JDBC Java.sql.Types notation. |

## Execute a SQL insert instruction, starting from a javascript object, instead of defining explicitelly the SQL script. <a href="insertobject" id="insertobject"></a>

**Syntax**

```javascript
var ok = utils.insertObject(obj, tableName, dataSourceId, separatedTransaction, interruptExecution);
```

**Details**

| Argument             | Description                                                                                                                                                                                                                                                                                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| obj                  | a Javascript object containing the data to save in the specified table; data is related to the table fields and each object attribute name is expressed in "camel" format, i.e. if the table field has name PRODUCT_CODE, the attribute name must be productCode                                                                |
| tableName            | table name to use when creating the SQL insert instruction; field names as retrieved starting from the data model linked to the current table name: that means that it is mandatory to define a (writable) data model for that table, before invoking this javascript method; values are fechted starting from the obj argument |
| dataSourceId         | optional parameter (can be null); it defines the additional datastore to use when executing the SQL insert                                                                                                                                                                                                                      |
| separatedTransaction | boolean flag used to define if the SQL query must be execute on a separated transation or not                                                                                                                                                                                                                                   |
| interruptExecution   | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of the SQL query                                                                                                                                                        |
| ok                   | true in case of SQL instruction executed correctly, an exception otherwise                                                                                                                                                                                                                                                      |

## Execute a SQL update instruction, starting from a javascript object, instead of defining explicitelly the SQL script <a href="updateobject" id="updateobject"></a>

**Syntax**

```javascript
var ok = utils.updateObject(obj, emptyAsNull, forceAttributesToNull, tableName, dataSourceId, separatedTransaction, interruptExecution);
```

**Details**

| Argument              | Description                                                                                                                                                                                                                                                                                                                     |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| obj                   | a Javascript object containing the data to save in the specified table; data is related to the table fields and each object attribute name is expressed in "camel" format, i.e. if the table field has name PRODUCT_CODE, the attribute name must be productCode                                                                |
| tableName             | table name to use when creating the SQL update instruction; field names as retrieved starting from the data model linked to the current table name: that means that it is mandatory to define a (writable) data model for that table, before invoking this javascript method; values are fechted starting from the obj argument |
| emptyAsNull           | this boolean flag can be set to true to force the conversion of ‘’ string values to null; it can be helpful to clear up some table fields                                                                                                                                                                                       |
| forceAttributesToNull | this boolean flag can be used to force to null every table field not referred in the javascript object but defined in the linked data model                                                                                                                                                                                     |
| dataSourceId          | optional parameter (can be null); it defines the additional datastore to use when executing the SQL update                                                                                                                                                                                                                      |
| separatedTransaction  | boolean flag used to define if the SQL query must be execute on a separated transation or not                                                                                                                                                                                                                                   |
| interruptExecution    | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an errore during the execution of the SQL query                                                                                                                                                       |
| ok                    | true in case of SQL instruction executed correctly, an exception otherwise                                                                                                                                                                                                                                                      |

## Execute a SQL delete instruction, starting from a javascript object, instead of defining explicitelly the SQL script <a href="deleteobject" id="deleteobject"></a>

**Syntax**

```javascript
var ok = utils.deleteObject(obj, tableName, dataSourceId, separatedTransaction, interruptExecution);
```

**Details**

| Argument             | Description                                                                                                                                                                                                                                                                                                                                                                                  |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| obj                  | a Javascript object containing the data to delete in the specified table; data is related to the table fields and each object attribute name is expressed in "camel" format, i.e. if the table field has name PRODUCT_CODE, the attribute name must be productCode; only fields which are part of the primary key will be taken into account                                                 |
| tableName            | table name to use when creating the SQL delete instruction; field names as retrieved starting from the data model linked to the current table name: that means that it is mandatory to define a (writable) data model for that table, before invoking this javascript method; values are fechted starting from the obj argument: only the attributes related to the primary key will be used |
| dataSourceId         | optional parameter (can be null); it defines the additional datastore to use when executing the SQL delete                                                                                                                                                                                                                                                                                   |
| separatedTransaction | boolean flag used to define if the SQL query must be execute on a separated transation or not                                                                                                                                                                                                                                                                                                |
| interruptExecution   | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an errore during the execution of the SQL query                                                                                                                                                                                                                    |
| ok                   | true in case of SQL instruction executed correctly, an exception otherwise                                                                                                                                                                                                                                                                                                                   |

## How to extract a binary object from a BLOB field

In case you need to extract the binary content from a BLOB data field of a relational database, you can use the following server-side javascript function, which allows you to get its content and convert it to a Base64 String.

This String value can be easily passed forward to the web UI or to a Jasper Report template, for example as a JSON attribute and later refer it within the report and map it to an Image.

**Syntax**:

```javascript
var base64String = utils.getBlobAsBase64(
   datastoreId,
   sql,
   params
);
```

| Argument    | Description                                                                                                                                                                                                                   |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| datastoreId | identifier for a data source; it can be set to null (default Platform repository scheme)                                                                                                                                      |
| sql         | SQL query to execute, in order to extract the BLOB field value; the query should always include a single field in the SELECT clause, the BLOB type field and can include in the WHERE clause variables expressed as :XXX or ? |
| params      | javascript list containing the values for the bind variables reported in the SQL query and expressed as ?                                                                                                                     |

This method returns a String whose content is the Base64 representation of the BLOB field content.

## Call a business component from a server-side js business component

It is available a js function to invoke from within a server-side js b.c. (not from an action) to call another business component. 

Basically, it can be used to pass forward all request parameters received in input from the starting b.c and get a response to use as the final result to pass back.

**Syntax**

```javascript
callBusinessComponent(
  Long compId,
  Map additionalReqParams,
  Map decodedReqParams,
  Map decodedFilterNames
)
```



| Argument            | Description                                                                                                                                                                                                                                                                                                                                                               |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| compId              | identifier for the b.c. to call; bear in mind that all request parameters received from the current b.c. are automatically passed forward to the one specified here; optionally, you can replace request names through the other function arguments                                                                                                                       |
| additionalReqParams | it can be null; if specified, it is a js object containing additional request parameters to pass forward; for example, if you wanna call a b.c. for a detail, input parameters a required (the ones expressed as :XXX in the called b.c.); you can use this argument to specify these input parameters, if not already available in the starting b.c. input               |
| decodedReqParams    | it can be null: if specified, it is a js object containing mappings between request parameters in input and the new request parameter name which must replace the one mapped; e.g. { itemCode: "codice", description: "desc" } in case the UI passes itemCode and description request parameters and you need to pass foward to the called b.c. different parameter names |
| decodedFilterNames  | it can be null: if specified, it is a js object to use ONLY in case of a b.c. for lists; it represents a sub-case of the previous argument: it works only on quickFilterNames and filterNames request attributes and it goes into depth to these values and replace attribute names with new ones                                                                         |

**Example of a server-side js b.c. invoking a b.c. for grids**

```javascript
var json = utils.callBusinessComponent(109,{},{},{
     codice: "uid", // replace "codice" input req param with "uid"
     descrizione: "companyTitle"
});
var res = JSON.parse(json);
// scroll all results returned by the called b.c. and create a new 
// response, containing the data needed
var list = [];
for(var i=0;i<res.valueObjectList.length;i++) {
    list.push({
        codice: res.valueObjectList[i].uid,
        descrizione: res.valueObjectList[i].companyTitle
    });
}

var _res = {
    valueObjectList: list,
    moreRows: res.moreRows
};
utils.setReturnValue(JSON.stringify(_res));
```

 

**Example of a server-side js b.c. invoking a b.c. for a form**

```javascript
var params = new Object();
params["cliente.uid"] = "00109801-de92-4e5e-85a4-108aa6b63387"; // for example
var json = utils.callBusinessComponent(119,params,{},{}); // here the required "pk" for the b.c. for a form is passed forward through "params"
...
```



## Execute bulk insert/update from a SQL query <a href="insertobject" id="insertobject"></a>

Use this method when you need to copy data from one table to another, having the same structure (in terms of field types and mandatory constraints), for example from one SQL schema to another.

This is the fastest method to execute inserts or updates (or both), it can save up to 300.000 records in 30 seconds.

**Syntax**

```javascript
var processedRows = utils.executeSqlBatch(Map settings);
```

**Details**

The javascript object "settings" contains a few attributes:

* **selectSql**: a mandatory String type attribute, containing the SQL query to execute in the source schema; this SQL query can contain aliases and bind variables
* **selectParameters**: an optional java.util.ArrayList  containing the values for the bind variables specified in the SQL query
* **srcDataStoreId**: an optional numeric type attribute, identifying the source database schema by its datasource id
* **insertSql**: this String type attribute defines the INSERT statement to execute, expressed with biding variables and in-line values (e.g. NOW(), 'INSERT_USER', 1, etc.); for each field reported in the SQL query, there must be a corresponding bind variable for this INSERT statement and exactly in the same position; you are free to include additional fields in the INSERT clause, whose values do not coming from the SQL query, but they must be filled with in-line values
* **updateSql**: this String type attribute defines the UPDATE statement to execute, expressed with biding variables and in-line values (e.g. NOW(), 'UPDATE_USER', etc.); for each field reported in the SQL query, there must be a corresponding bind variable for this UPDATE statement and exactly in the same position; you are free to include additional fields in the INSERT clause, whose values do not coming from the SQL query, but they must be filled with in-line values. The UPDATE statement ends with the WHERE clause which must be defined with bind variables and must always refer a single record to update. When defining the "updateSql" attribute, you have also to specify the "pk" attribute
* **pk**: this java.util.ArrayList type attribute must be specified as long as you have defined the "updateSql" attribute and it reports the name of the fields in the SELECT clause which are used to fill in the binding variables of the WHERE clause for the UPDATE statement
* **blockSize**: optional numeric type attribute; it defines the amount of records to enqueue before executing all of them and commit such block; if not specified, the default value is 10.000 records
* **destDataStoreId**: an optional numeric type attribute, identifying the destination database schema by its datasource id

**Important note: **when appending writing operations, these are collected through the JDBC driver in use; it is up to the driver to either pass appended data to the database server or accumulate it on the client side; in the latter case, the memory consumption can increase significantly on the application server and a memory heap error could happen because of that. In order to prevent such a critical error, it is a good practice to limit the amount of collected data to a lower value, so it is better to** set the blockSize property to a relatively lower value**, like 100 o 500 and pay attention to the memory consumption: do not increase it if you note a potentially critical amount of memory consumed (e.g. hundreds of MB).



Executes once the specified SQL query and for each fetched record:

* if updateSql has been specified:
  * execute massively N updates, where N is 10k (or blockSize if specified)
  * execute a commit
  * if there are 0 records updated, only for those ones, execute the insertSql (if specified)
  * continue until the end of the result set
* otherwise, the insertSql must be specified, therefore:
  * execute massively N inserts, where N is 10k (or blockSize if specified)
  * execute a commit
  * continue until the end of the result set

**Insert only example**

```javascript
var selectParameters = new java.util.ArrayList();
// selectParameters.add(...);

utils.executeSqlBatch({
    selectSql: "SELECT ID_CLIENTE, ETA, SESSO, PROV, TOTALE, CHECK_ACQ, PREDIZIONE, USER_CODE_ID, LAST_UPDATE FROM CLIENTI_BOGGI",
    selectParameters: selectParameters,
    srcDataStoreId: null,
    destDataStoreId: 319,
    insertSql: "INSERT INTO CLIENTI(ID_CLIENTE, ETA, SESSO, PROV, TOTAL, CHECK_ACQ, PREDIZIONE, USER_CODE_ID, LAST_UPDATE) VALUES(?,?,?,?,?,?,?,?,?)"
});
```

Note that the select fields MUST be in the same order of ? variables in the insertSql statement



**Update only example**

```javascript
var selectParameters = new java.util.ArrayList();
// selectParameters.add(...);

var pk = new java.util.ArrayList();
pk.add("ID_CLIENTE");

utils.executeSqlBatch({
    selectSql: "SELECT ID_CLIENTE, ETA, SESSO, PROV, TOTALE, CHECK_ACQ, PREDIZIONE, USER_CODE_ID, LAST_UPDATE FROM CLIENTI_BOGGI",
    selectParameters: selectParameters,
    srcDataStoreId: null,
    destDataStoreId: 319,
    updateSql: "UPDATE CLIENTI set ID_CLIENTE=?, ETA=?, SESSO=?, PROV=?, TOTAL=?, CHECK_ACQ=?, PREDIZIONE=?, USER_CODE_ID=?, LAST_UPDATE=? WHERE ID_CLIENTE=?",
    pk: pk
});
```

Note that select fields MUST be in the same order of ? variables in the updateSql statement (there must be as many SET clauses as the number of fields in the select clause)

Note that the "pk" attribute is mandatory in case of "updateSql" and it must contains the field names (or alias) of the select clause field**.**

****

**Update + Insert example**

```javascript
var selectParameters = new java.util.ArrayList();
// selectParameters.add(...);

var pk = new java.util.ArrayList();
pk.add("ID_CLIENTE");

utils.executeSqlBatch({
    selectSql: "SELECT ID_CLIENTE, ETA, SESSO, PROV, TOTALE, CHECK_ACQ, PREDIZIONE, USER_CODE_ID, LAST_UPDATE FROM CLIENTI_BOGGI",
    selectParameters: selectParameters,
    srcDataStoreId: null,
    destDataStoreId: 319,
    insertSql: "INSERT INTO CLIENTI(ID_CLIENTE, ETA, SESSO, PROV, TOTAL, CHECK_ACQ, PREDIZIONE, USER_CODE_ID, LAST_UPDATE) VALUES(?,?,?,?,?,?,?,?,?)",
    updateSql: "UPDATE CLIENTI set ID_CLIENTE=?, ETA=?, SESSO=?, PROV=?, TOTAL=?, CHECK_ACQ=?, PREDIZIONE=?, USER_CODE_ID=?, LAST_UPDATE=? WHERE ID_CLIENTE=?",
    pk: pk
});
```

In this example, a block of 10.000 records are updated; for those records not updated (because they do not exist yet), a bulk insert is performed; in any case, the commit is execute at the end of this block. Then process the next 10.000 records and so on.



### Cached progressive calculation

In case you have a progressives table used to calculate a progressive and it is  invoked a very high amount of times concurrently, it is likely to have locks or a low performance.

This method can be used to increase the progressives table a lower number of times, since the update is performed on the table rarely, since the writing operation would increase the current value not by 1, but by an "increment" value.

Every time this method is invoked, a new increment is returned without any update operation, since the current value is cached and incremented programatically in the cache, until the max "increment" value is reach: only at that point the update operation is called again.

The operation of Insert a new record in progressives table is also supported.

**Example:**

* progressives table already contains the record with current value 1
* the method is invoked for the first time with increment value = 1000
* the method updates the record with 1+1000 = 1001 and returns 2; cached incremented value is now 2
* the method is invoked again and the cached current value is incremented to 3; 3 is returned

      ...

* the method is invoked for the 1000th time:  cached current value is 1001: no more increments can be done;
* the record is updated to 1001+1000 = 2001 and returns 1002; cached incremented value is now 1002

      ..

      

      **Arguments**: settings - a javascript object, containing a series of attributes, all mandatory

|              |                                                       |
| ------------ | ----------------------------------------------------- |
| datasourceId | data source id where the progressives table is stored |
| tableName    |                                                       |
|              |                                                       |

      **datasourceId** - 

      **tableName** - string representing the name of the progressives table

      pkFields - javascript array containing the list of fields composing the PK

      pkValues - javascript array containing the values of the PK fields

      updateFields - additional fields to update when increasing the current value on the progressives table

      updateValues - values for the additional fields to update when increasing the current value on the progressives table

      currentValueField - field name in the progressives table containing the current value

      incrementValue - how much to increase the current value (number)

      initialValue - initial value to set, when inserting the record because not found yet

      insertFields - list of fields in the progressives table to insert; DO NOT include the currentValueField

      insertValues - list of values for the fields to insert in the progressives table

      

      Example:

      

      var settings = {

            datasourceId: null,

            tableName: "INI21\_GLOBAL_SEQUENCES",

            pkFields: \["TABLE_NAME","FIELD_NAME"],

            pkValues: \["AAAA","PROG_ID"],

            updateFields: \["USER_ID_UPDATE","LAST_UPDATE"],

            updateValues: \[userInfo.username,utils.getCurrentDateAndTime()],

            currentValueField: "CURRENT_VALUE",

            incrementValue: 2,

            initialValue: utils.getInitialValue(),

            insertFields: \["INITIAL_VALUE","INCREMENT_VALUE","IS_CYCLE","MAX_NUMBER","USER_ID_CREATE","CREATE_DATE","ROW_VERSION","STATUS"],

            insertValues: \[utils.getInitialValue(),2,"F",null,userInfo.username,utils.getCurrentDateAndTime(),0,"E"]

      };

      var p = utils.getCachedProgressive(settings);

###

