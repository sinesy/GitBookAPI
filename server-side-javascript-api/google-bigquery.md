# Google BigQuery

## Google BigQuery: create a dataset

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Create a new dataset into Google BigQuery; a dataset is a group of BigQuery tables logically dependent with each other.

**Syntax**

```javascript
utils.createBigQueryDataset(datasetName);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset to create |

## Google BigQuery: delete a dataset

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Delete an already existing dataset into Google BigQuery.

**Syntax**

```javascript
utils.deleteBigQueryDataset(datasetName);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset to delete |

## Google BigQuery: create a table

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Create a new table in the specified dataset of Google BigQuery. When creating a table in BigQuery, you need to specify a list of fields, each expressed with a name and a type.

**Syntax**

```javascript
utils.createBigQueryTable(datasetName, tableName, columns);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset containing the new table |
| tableName | table name to create |
| columns | javascript list of objects, each related to a field to define; such a list must have the following format: \[{ name: "FIELD1", type: "..."},...\] where supported types are: INT, DEC, DATE, DATE\_TIME or TEXT |

## Google BigQuery: delete a table

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Delete an already existing table from the specified dataset.

**Syntax**

```javascript
utils.deleteBigQueryTable(datasetName, tableName);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset containing the table to delete |
| tableName | table name to delete |

## Google BigQuery: execute a SQL query and get results one row a time

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Execute the specified SQL query on the BigQuery service and get back the result, a record a time.

**Syntax**

```javascript
utils.executeBigQueryWithCallback(processRowFunName, defaultDataset, sqlQuery, params);
```

**Details**

| Argument | Description |
| :--- | :--- |
| processRowFunName | name of a javascript function locally defined in the js action, which will be automatically invoked for each row read from the query; such a function must define an argument which will be filled with the data read from the current record; data is expressed as a javascript list, where each element is related to a field in the SELECT clause of the SQL query |
| defaultDataset | name of the dataset containing the table to delete |
| sqlQuery | SQL query used to fetch data; it can contain binding variables; for each of these variables, a corresponding value must be provided through the "params" argument; the argument massed to the callback js function will contain a js list having as many elements as the number of fields specified in the SELECT clause |
| params | javascript list of binding values |

## Google BigQuery: execute a SQL query and save results in a BigQuery table

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Execute the specified SQL query on the BigQuery service and save the result on a BigQuery table, created automatically.

**Syntax**

```javascript
utils.executeBigQuerySaveOnTable(destinationDataset, destinationTable, defaultDatset, sqlQuery, params);
```

**Details**

| Argument | Description |
| :--- | :--- |
| destinationDataset | dataset name where the destination table is located |
| destinationTable | table name where the results will be saved; if not defined, it will be automatically created |
| defaultDataset | name of the dataset where the SQL query will be carried out |
| sqlQuery | SQL query used to fetch data; it can contain binding variables; for each of these variables, a corresponding value must be provided through the "params" argument |
| params | javascript list of binding values |

## Google BigQuery: execute a SQL query and save results in a relational db table

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Execute the specified SQL query on the BigQuery service and save the result on a local table, stored in the relational database.

**Syntax**

```javascript
utils.executeBigQuerySaveOnLocalTable(
  datastoreId, 
  localTableName,
  defaultFieldNames, 
  csvFields,
  defaultDataset,
  sqlQuery,
  params
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datastoreId | datastore id defining where the local table is located |
| localTableName | table name where the results will be saved in the relational database |
| defaultFieldNames | collection of &lt;fieldname,defaultvalue&gt; used to fill in table fields not starting from the input 8CSV file\); used to populate oadditional fields like CREATE\_DATE, USER\_ID\_CREATE, etc. |
| csvFields | list of js objects, one for each CSV column; this list allows to define the mapping between CSV columns and table fields; not necessarely all CSV columns must be mapped to table fields; |
| defaultDataset | name of the dataset where the SQL query will be carried out |
| sqlQuery | SQL query used to fetch data; it can contain binding variables; for each of these variables, a corresponding value must be provided through the "params" argument |
| params | javascript list of binding values |

**Example**

```javascript
utils.executeBigQuerySaveOnLocalTable(
  null, // datastoreId, null for default db schema
  "MYTABLE",
  { 
    USER_ID_CREATE_DATE: userInfo.username,
    ROW_VERSION: 1
  }, // default values
  [
    { fieldName: "CODE" },
    {}, // no mapping to a field
    { fieldName: "DESCRIPTION" }
  ], // csv fields
  "MYBIGQUERY_DATASET", // defaultDataset,
  "SELECT CODE,DESCRIPTION FROM MYBIGQUERYTABLE WHERE COMPANY_ID=? ", // SQL BigQuery
  [userInfo.companyId] // values for bind variables
);
```

## Google BigQuery: execute a SQL query and save results in a text file in GCS

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Extract data from the specified BigQuery table to a Google Cloud Storage file. Fields separator is always the comma \(,\)

* You can export up to 1 GB of table data to a single file. 
* If you are exporting more than 1 GB of data, use a wildcard to export the data into multiple files. 
* When you export data to multiple files, the size of the files will vary.
* You cannot export nested and repeated data in CSV format. Nested and repeated data is supported for Avro and JSON exports.
* You cannot export data from multiple tables in a single export job.

**Syntax**

```javascript
utils.extractBigQueryData(datasetName, tableName, format, gcsUrl, deleteTableAfterExport, printHeaders);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset where the table is located |
| tableName | table name whose content will be extracted and save to a text file in Google Cloud Storage |
| format | text file format; supported values: CSV \(with comma separator\), JSON, Avro |
| gsUrl | GCS URI representing the bucket+subpath+filename where the table content will be saved |
| deleteTableAfterExport | true to delete the BigQuery table afer exporting data, false to maintain it |
| printHeaders | true to include a first line in the CSV file, false to omit it. In case you are going to use the CSV to import data to CloudSQL, you have to omit the first line. |

Examples for gcsUrl:

gs://my-bucket/file-name.json

gs://my-bucket/file-name-\*.json

gs://my-bucket/path-component-\* /file-name.json

## Google BigQuery: import data from a local text file to BigQuery table

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Import a text file stored in the server file system to a BigTable table.

When you load CSV or JSON data, values in DATE columns must use the dash \(-\) separator and the date must be in the following format: YYYY-MM-DD \(year-month-day\).

When you load JSON or CSV data, values in TIMESTAMP columns must use a dash \(-\) separator for the date portion of the timestamp, and the date must be in the following format: YYYY-MM-DD \(year-month-day\).

The hh:mm:ss \(hour-minute-second\) portion of the timestamp must use a colon \(:\) separator.

**Syntax**

```javascript
var numberOfImportedRows = utils.importBigQueryDataFromLocalDatasource(
  datasetName, tableName, location,
  format, csvPath, encoding, separator, maxBadErrors, truncate, deleteSrcFileAfterImport
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset where the table is located |
| tableName | table name where saving data coming from a local text file |
| location | GCS location; allowed values are EU, US, etc; see: [https://cloud.google.com/bigquery/docs/locations\#specifying\_your\_location](https://cloud.google.com/bigquery/docs/locations#specifying_your_location) |
| format | text file format; supported values: CSV \(with comma separator\), JSON |
| csvPath | absolute path + file name of the text file to read; such file must be in the server file system |
| encoding | can be null; if specified, it represents the text file encoding; if not specified it is assumed the text file is expressed in UTF-8; other values: ISO-8859-1, ASCII |
| separator | separator used among field, in case of CSV file; e.g. comma \(,\) or semi-colon \(;\) |
| maxBadErrors | maximum number of error on reading data |
| truncate | true to truncate \(clear up\) the table before importing data, false to append data to already existing data |
| deleteSrcFileAfterImport | true to delete the original file on the local file system, after importing it to BigQuery |

## Google BigQuery: import multiple local files to BigQuery tables

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Import a text file stored in the server file system to a BigTable table.

When you load CSV or JSON data, values in DATE columns must use the dash \(-\) separator and the date must be in the following format: YYYY-MM-DD \(year-month-day\).

When you load JSON or CSV data, values in TIMESTAMP columns must use a dash \(-\) separator for the date portion of the timestamp, and the date must be in the following format: YYYY-MM-DD \(year-month-day\).

The hh:mm:ss \(hour-minute-second\) portion of the timestamp must use a colon \(:\) separator.

**Syntax**

```javascript
var numberOfImportedRows = utils.importMultipleDataFromLocalDatasource(
  datasetName, tableNames, location,
  format, baseDir, csvFiles, encoding, separator, maxBadErrors, truncate, deleteSrcFileAfterImport
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset where the table is located |
| tableNames | list of table names where saving data coming from the CSV files to read; e.g. \["table1","table2"\]; there must be a table for each input file, defined positionally |
| location | GCS location; allowed values are EU, US, etc; see: [https://cloud.google.com/bigquery/docs/locations\#specifying\_your\_location](https://cloud.google.com/bigquery/docs/locations#specifying_your_location) |
| format | text file format; supported values: CSV \(with comma separator\), JSON |
| baseDir | absolute path on the server file system where all files to import are located |
| csvFiles | list of CSV file names to import; e.g. \["file1.csv","file2.csv"\] |
| encoding | can be null; if specified, it represents the text file encoding; if not specified it is assumed the text file is expressed in UTF-8; other values: ISO-8859-1, ASCII |
| separator | separator used among field, in case of CSV file; e.g. comma \(,\) or semi-colon \(;\) |
| maxBadErrors | maximum number of error on reading data |
| truncate | true to truncate \(clear up\) the table before importing data, false to append data to already existing data |
| deleteSrcFileAfterImport | true to delete the original file on the local file system, after importing it to BigQuery |

## Google BigQuery: import data from a GCS text file to BigQuery table

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Import a text file stored in GCS to a BigTable table.

When you load CSV or JSON data, values in DATE columns must use the dash \(-\) separator and the date must be in the following format: YYYY-MM-DD \(year-month-day\).

When you load JSON or CSV data, values in TIMESTAMP columns must use a dash \(-\) separator for the date portion of the timestamp, and the date must be in the following format: YYYY-MM-DD \(year-month-day\).

The hh:mm:ss \(hour-minute-second\) portion of the timestamp must use a colon \(:\) separator.

**Syntax**

```javascript
var numberOfImportedRows = utils.importBigQueryDataFromGCS(
  datasetName, tableName, format, 
  sourceUri, encoding, separator
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset where the table is located |
| tableName | table name where saving data coming from a GCS text file |
| format | text file format; supported values: CSV \(with comma separator\), JSON |
| sourceUri | GCS URI, related to the bucket + subpath + filename of a text file stored in GCS |
| encoding | can be null; if specified, it represents the text file encoding; if not specified it is assumed the text file is expressed in UTF-8; other values: ISO-8859-1, ASCII |
| separator | separator used among field, in case of CSV file; e.g. comma \(,\) or semi-colon \(;\) |

Examples for gcsUrl:

gs://my-bucket/file-name.json

gs://my-bucket/file-name-\*.json

## Google BigQuery: import data as a streaming to BigQuery table

In order to work with BigQuery, you need to setup Google settings and assign to the auth key permissions about BigQuery.

Import a single record as a streaming.

When you load CSV or JSON data, values in DATE columns must use the dash \(-\) separator and the date must be in the following format: YYYY-MM-DD \(year-month-day\).

When you load JSON or CSV data, values in TIMESTAMP columns must use a dash \(-\) separator for the date portion of the timestamp, and the date must be in the following format: YYYY-MM-DD \(year-month-day\).

The hh:mm:ss \(hour-minute-second\) portion of the timestamp must use a colon \(:\) separator.

**Syntax**

```javascript
var errorsString = utils.importBigQueryThroughStreaming(datasetName, tableName, record);
```

**Details**

| Argument | Description |
| :--- | :--- |
| datasetName | name of the dataset where the table is located |
| tableName | table name where saving data |
| record | a javascript object, containing data to import |

Return errors during import, expressed as a JSON map; null if there are NOT errors

## Google BigQuery: execute a SQL query 

It is possible to execute a SQL query on a single BigQuery table and get the whole result set as a JSON string.

**Syntax**

```javascript
var json = utils.executeQueryOnBigQuery(
  String sql,
  Long dataModelId,
  Boolean interruptExecution,
  Object... pars
);
```

| Argument | Description |
| :--- | :--- |
| sql | SQL query to execute; the constraint is that the query must retrieve all fields of the table identified by the data model id; you can make the WHERE condition as complex as needed. |
| dataModelId | a data model identifying a BigQuery already existing table |
| interruptException | flag used to fire an exception in case of SQL errors |

**Important note:** do NOT use this method to retrieve a long result se \(more than a hundred records\).

## Google BigQuery: execute a SQL query **and retrieve a block of data**

It is possible to execute a SQL query on a single BigQuery table and get a partial result set, a block of data to fill in a grid. This method is helpful within a server-side javascript business component bounded to a grid.

**Syntax**

```javascript
var json = utils.getPartialResultOnBigQuery(
  String sql,
  Long dataModelId,
  Boolean interruptExecution,
  Object... pars
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| sql | SQL query to execute; the constraint is that the query must retrieve all fields of the table identified by the data model id; you can make the WHERE condition as complex as needed. |
| dataModelId | a data model identifying a BigQuery already existing table |
| interruptException | flag used to fire an exception in case of SQL errors |

This method also parses the HTTP request parameters passed forward by the calling grid \(curernt block of data and block size\) as well as filtering and sorting conditions coming from the grid.

## Google BigQuery: insert records in a table from a list of javascript objects

This method is helpful when you need to insert one or more records in a BigQuery table, starting from the data model id related to such a table.

**Syntax**

```javascript
var ok = utils.insertObjectsOnBigQuery(
  Map[] objects,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| objects | a javascript array of objects, where each object represents a record to insert; the object attributes must be the same defined as fields in the data model definition |
| dataModelId | a data model identifying a BigQuery already existing table |
| interruptException | flag used to fire an exception in case of SQL errors |

## Google BigQuery: update a single record in a table from a javascript object

This method is helpful when you need to update a record in a BigQuery table, starting from the data model id related to such a table.

**Syntax**

```javascript
var ok = utils.updateObjectOnBigQuery(
  Map object,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| object | a javascript object representing the record to update; the object attributes must be the same defined as fields in the data model definition |
| dataModelId | a data model identifying a BigQuery already existing table |
| interruptException | flag used to fire an exception in case of SQL errors |

## Google BigQuery: update multiple records in a table from a list of javascript objects

This method is helpful when you need to update one or more records in a BigQuery table, starting from the data model id related to such a table.

**Syntax**

```javascript
var ok = utils.updateObjectsOnBigQuery(
  Map[] objects,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| objects | a javascript array of objects, where each object represents a record to update; the object attributes must be the same defined as fields in the data model definition |
| dataModelId | a data model identifying a BigQuery already existing table |
| interruptException | flag used to fire an exception in case of SQL errors |

## Google BigQuery: delete one or more records starting from a list of javascript objects

This method is helpful when you need to update one or more records in a BigQuery table, starting from the data model id related to such a table.

**Syntax**

\*\*\*\*

```javascript
var ok = utils.deleteObjectOnBigQuery(
  Map object,
  Long dataModelId,
  Boolean interruptExecution
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| object | a javascript object representing a record to delete; the object attributes must be the same defined as fields in the data model definition |
| dataModelId | a data model identifying a BigQuery already existing table |
| interruptException | flag used to fire an exception in case of SQL errors |

  


bulkImportFromDSToBigQuery\(String gql,Long datastoreDataModelId,String location,String bigQueryTable,**boolean** interruptExecution,Object...pars\)







