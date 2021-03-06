# Using Sql

## deleteObject\(object, tableName, fireWhenErrors\) <a id="deleteobject"></a>

generate a SQL delete instruction in the specified table, starting from the javascript object passed as argument: the record having the object pk will be deleted; fireWhenErrors: true\|false

## updateObject\(object, tableName, fireWhenErrors\) <a id="updateobject"></a>

generate a SQL update instruction in the specified table, starting from the javascript object passed as argument; fireWhenErrors: true\|false

## insertObject\(object, tableName, fireWhenErrors\) <a id="insertobject"></a>

generate a SQL insert instruction in the specified table, starting from the javascript object passed as argument; fireWhenErrors: true\|false

## executeQuery\(query, dbType, fireWhenErrors, params\) <a id="executequery"></a>

executeSql\(query, dbType, fireWhenErrors, params\)  
execute the specified SQL query on the specified database; allowed values for dbType are: "DBCON" \(platform tables\), "DBRW" \(readonly+readwrite tables\), "DBNOSYNC" \(only mobile db, managed manually by user\) ; fireWhenErrors: true\|false, params: a list of parameters, expressed with ?; returned value is a list of objects. Each object has value identifiers defined as attributes \(select fields in camel mode\)  
NOTE: Use executeQuery to select values, and executeSql to update/insert records!

**Example**

```javascript
var list = executeQuery(
  "SELECT ...", 
  "DBRW", 
  true, 
  []
);
var json = convertToListResponseJson(list); 
return json;
```

## getPartialResult\(query, dbType, fireWhenErrors, params\) <a id="getpartialresult"></a>

execute the specified SQL query on the specified database; when linked to a grid, it inherits filtering, sorting and pagination conditions from the grid, so that it can apply automatically filters, sortings and read a block of data instead of the whole result set.  
Allowed values for dbType are: "DBCON" \(platform tables\), "DBRW" \(readonly+readwrite tables\), "DBNOSYNC" \(only mobile db, managed manually by user\) ; fireWhenErrors: true\|false, params: a list of parameters, expressed with ?; returned value is a list of objects. Each object has value identifiers defined as attributes \(select fields in camel mode\)

**Example**

```javascript
var listResponse = getPartialResult(
  "SELECT ...", 
  "DBRW", 
  true, 
  []
);
var json = convertToListResponseJson(listResponse.rows,listResponse.rows.length,listResponse.moreRows);
return json;
```

## addFilter\(fieldName,op,value\)

adda filtering condition to the filter panel search. Typically, this instruction is added to a js action linked to the "before search" event of the Search button in a filter panel.  
Required parameters:

```text
 fieldName - physical field name; the table name is not required
 op - the SQL operator, like: =, &lt;, &gt;, etc.
 value - a string representing the filter value
```

## setPanelParameter\(name,value\)

Store a parameter value within the current panel scope. It can be referred in SQL instructions or js instructions as :PARAMETERNAME variables.  
Required parameters are:

```text
 name-parameter name
 value-parameter value
```

## syncSqlInstruction\(\)

Send to server the sql instractions of data modified. This operation not is a total sync.

