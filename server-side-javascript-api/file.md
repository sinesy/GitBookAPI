# CSV-Text File

## Create a text file and fill in with the passed content <a href="#createtextfile" id="createtextfile"></a>

**Syntax**

```javascript
var outcome = utils.createTextFile(String fileName, String fileContent, Boolean overwrite, Long directoryId);
```

**Details**

| Argument    | Description                                                                                                                                                              |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|             | fileName -file name; it can includes a subpath to append to the base path specified through directoryId                                                                  |
| fileContent | text content to save                                                                                                                                                     |
| overwrite   | true to overwrite the file content if already exists, falseto ignore this operation and returns false as result                                                          |
| directoryId | directory identifier, used to define the absolute path, in the central server, where the file will be stored; if null, there must be one only entry for this application |
| outcome     | true in case of the operation has beenexecuted successfully, an exception otherwise                                                                                      |

## Create a text file with specify charset and fill in with the passed content <a href="#getcsvcontent" id="getcsvcontent"></a>

**Syntax**

```javascript
var outcome = utils.createTextFile(String fileName, String fileContent, 
    Boolean overwrite, Long directoryId, String charsetName
);
```

**Details**

| Argument    | Description                                                                                                                                                              |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|             | fileName -file name; it can includes a subpath to append to the base path specified through directoryId                                                                  |
| fileContent | text content to save                                                                                                                                                     |
| overwrite   | true to overwrite the file content if already exists, falseto ignore this operation and returns false as result                                                          |
| directoryId | directory identifier, used to define the absolute path, in the central server, where the file will be stored; if null, there must be one only entry for this application |
| outcome     | true in case of the operation has beenexecuted successfully, an exception otherwise                                                                                      |
| charsetName | name charset                                                                                                                                                             |

## Writing a very long text file on the server file system <a href="#getcsvcontent" id="getcsvcontent"></a>

**From 5.3.1 version**

Write a very long text file on the server file system, through a 3 steps approach:

* first, open the output stream, through the "opeTextFile" method
* next, add as many rows as you need, by invoking the "writeTotextFile" method multiple times, for each row to add
* finally, close the output stream, by invoking the "closeTextFile"

Data could be retrieved from a SQL query, through the **executeQueryWithCallback** method, since this will ensure a limited amount of memory consumption.

**Syntax for openTextFile method**

```javascript
var fileId = utils.openTextFile(fileName, overwrite, directoryId, fileAppend);
```

or&#x20;

```javascript
var fileId = utils.openTextFile(fileName, overwrite, directoryId, fileAppend, charsetName);
```

**Details**

| Argument |
| -------- |

|             | Description                                                                                                                                                              |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| fileName    | text file name to create within the specified directory                                                                                                                  |
| overwrite   | flag true\|false used to define whether the file must overwrite a previous one                                                                                           |
| directoryId | directory identifier, used to define the absolute path, in the central server, where the file will be stored; if null, there must be one only entry for this application |
| fileAppend  | flag true\|false used to define if rows to add must be appneded at the end of  an already existing file                                                                  |
| fileId      | a text id, representing the output stream, to refer in the next two methods.                                                                                             |
| charsetName | name charset                                                                                                                                                             |

**Syntax for writeToTextFile method**

```javascript
var fileId = utils.writeToTextFile(fileId, row)
```

**Details**

| Argument | Description                                                                                                                     |
| -------- | ------------------------------------------------------------------------------------------------------------------------------- |
| fileId   | a text id, representing the output stream, needed to work qwith the correct output stream                                       |
| row      | a text to write; this text does NOT contain a return carriage, so it is up to the programmer to add it, if needed (e.g. "\r\n") |

**Syntax for closeTextFile method**

| Argument | Description                                                                               |
| -------- | ----------------------------------------------------------------------------------------- |
| fileId   | a text id, representing the output stream, needed to work qwith the correct output stream |

**Example**

```javascript
// open the text file, in order to write into it
var fileId = utils.openTextFile(
    "abc.txt",true,9, true
);

// declare a callback function, invoked by a SQL query, used to write a single line into the text file
var processRow = function(jsonRow) {
    var row = jsonRow.userCodeId+","+jsonRow.description+"\r\n"; // or any other custom logic to use to produce a text content
    utils.writeToTextFile(fileId,row);
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

// close the text file, after reading all records from the query
utils.closeTextFile(fileId);
```

## Read a text file located on the server <a href="#readtextfile" id="readtextfile"></a>

```javascript
var textString = utils.readTextFile(filePath);
```

**Important note**: please do not use this method in case of a very long text file (e.g. > 10MB), since it can consume an excessive amount of memory on the server and reduce the scalability of your application. In case of very long files, use the method described below.

**Details**

| Argument   | Description                             |
| ---------- | --------------------------------------- |
| filePath   | Filepath + Filename of the file to read |
| textString | The content of the read file            |

## Read a text file located on the server with a specific charset

A text file can be saved with different charset formats. You have to know in advance which format to use. Examples of formats are: UTF-8 or Windows-1252

```javascript
var textString = utils.readTextFile(filePath, charSet);
```

**Important note**: please do not use this method in case of a very long text file (e.g. > 10MB), since it can consume an excessive amount of memory on the server and reduce the scalability of your application. In case of very long files, use the method described below.

**Details**

| Argument   | Description                                   |
| ---------- | --------------------------------------------- |
| filePath   | Filepath + Filename of the file to read       |
| charSet    | the charset to use when reading the text file |
| textString | The content of the read file                  |

## Read a very long text file

**From 5.3.1 version**

In case of a very long text file, it would be better to read it row by row, in order to limit the amount of data stored in the server.

The following method requires a callback function, which will be invoked automatically, for each line read from the file. The current line (string) will be passed forward to the callback method.

```javascript
utils.readTextFile(String fileName,Long directoryId,String callbackFunName);
```

**Details**

| Argument        | Description                                                                                                         |
| --------------- | ------------------------------------------------------------------------------------------------------------------- |
| fileName        | text file name to read                                                                                              |
| directoryId     | directory id, identifying where the file is located; can work both with server file system and Google Cloud Storage |
| callbackFunName | callback function name, invoked by this one for each row                                                            |

## Read a very long text file with charset

**From 5.3.1 version**

In case of a very long text file, it would be better to read it row by row, in order to limit the amount of data stored in the server.

The following method requires a callback function, which will be invoked automatically, for each line read from the file. The current line (string) will be passed forward to the callback method.

```javascript
utils.readTextFile(String fileName,Long directoryId,String callbackFunName,String charset);
```

**Details**

| Argument        | Description                                                                                                         |
| --------------- | ------------------------------------------------------------------------------------------------------------------- |
| filePath        | text file name to read                                                                                              |
| directoryId     | directory id, identifying where the file is located; can work both with server file system and Google Cloud Storage |
| callbackFunName | callback function name, invoked by this one for each row                                                            |
| charset         | charset to use when reading file; e.g. UTF-8                                                                        |

## Read a very long text file located on the server with charset

**From 5.3.1 version**

In case of a very long text file, it would be better to read it row by row, in order to limit the amount of data stored in the server.

The following method requires a callback function, which will be invoked automatically, for each line read from the file. The current line (string) will be passed forward to the callback method.

```javascript
utils.readTextFile(String filePath,String callbackFunName,String charset);
```

**Details**

| Argument        | Description                                                              |
| --------------- | ------------------------------------------------------------------------ |
| filePath        | absolute path on the server file system, including the file name to read |
| callbackFunName | callback function name, invoked by this one for each row                 |
| charset         | charset to use when reading file; e.g. UTF-8                             |

## Delete a file previously stored in a specific path <a href="#deletefile" id="deletefile"></a>

**Syntax**

```javascript
var outcome = utils.deleteFile(String fileName,Long directoryId);
```

**Details**

| Argument    | Description                                                                                                                                                              |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| fileName    | it can includes a subpath to append to the base path specified through directoryId                                                                                       |
| directoryId | directory identifier, used to define the absolute path, in the central server, where the file will be stored; if null, there must be one only entry for this application |
| outcome     | true in case of the operation has beenexecuted successfully, an exception otherwise                                                                                      |

## Read the specified URL and convert the HTML content to an image and save it to the server file system.

**Syntax**

```javascript
utils.convertUrlToImage(String url, String imagePath);
```

**Details**

```
url: URL to read, related to HTML content 
imagePath: absolute path + image file name where saving the image 
fire an exception in case of errors.
```

## Reading the HTML content and convert it to an image and save the image to the server file system.

**Syntax**

```javascript
utils.convertHtmlToImage(String html, String imagePath);
```

**Details**

```
html: HTML content to read 
imagePath: absolute path + image file name where saving the image 
fire an exception in case of errors.
```

## Reading a csv file stored in the specified path <a href="#getcsvcontent" id="getcsvcontent"></a>

Read up to the specified number of rows, starting from the specified index (0..x) from the csv file stored in the specified path and get back the content of a specific folder

dirId path identifier\
fileName name of the csv file\
attributeNames, list of attributes, assigned to each column, starting from leftmost column to the right

**Syntax**

```javascript
var list = utils.getCsvContent(String sep,String dirId,String fileName,Integer startRow,Integer blockSize,Boolean removeEmptyValues,String... attributeNames);
```

**Important note**: this method should NOT be used in case of very long CSV files, since it can consume a large amount of memory on the server. In case of a very long CSV file, please refer the next method.

**Details**

```
 sep tokens separator: ; or ,
 dirId: path identifier; optional and helpful for files stored in the cloud; you can set it to null, to save temporarelly the uploaded file in the tmp dir of the application server
 fileName: name of the csvfile
```

startRow row index; if null it is the first row, i.e. 0

blockSize max number of rows to read, if available; if null it is set to 10000

attributeNames, list of attributes, assigned to each column, starting from leftmost column to the right

```
 return a list of js objects, where each object is expressed as a set of couples <attributename, related value>
```

A list of js objects, where each object is expressed as a set of couples \<attributename, related value>; a 0 length list in case of no more rows available.\
It supports also nested objects and list of objects: it depends on the definition of the attribute lists.\
A few examples of attributes:\
\[ "attr1", "subobject.attrsub1", "subobject.attrsub2", "sublist\[0].subattr3","sublist\[0].subattr4","sublist\[1].subattr5" ]

## Reading a very long csv file stored in the specified path <a href="#getcsvcontent" id="getcsvcontent"></a>

**From 5.3.2 version**

In case of very long CSV files to read (e.g. > 1MB), it would be better to avoid reading the whole content and maintain it in the server memory, until the end of its processing: this could lead to an excessive amount of memory consumption.

The best approach consists of reading that file row by row and maintain in memory only one row per time. The following method allows to do it: a callback function is used to process a single row and it is invoked automatically when reading the CSV file.

**Syntax**

```javascript
utils.readCSVFile(
  fileName,
  directoryId,
  sep,
  skipFirstRow,
  callbackFunName,
  attributeNames
);
```

**Details**

| Argument         | Description                                                                                                                                                                                                                                             |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| filenName        | CSV file name to read from the specified directory                                                                                                                                                                                                      |
| directoryId      | directory identifier, used to define the absolute path, in the central server, where the file is already located                                                                                                                                        |
| sep              | field separator; allowed values: , or ;                                                                                                                                                                                                                 |
| skipFirstRowflag | true\|false, indicating whether the first row in the file should me skipped, for instance because it contains the column header names.                                                                                                                  |
| callbackFunName  | callback function name which will be invoked for each row read from the CSV file. Such a function must be declared before the invocation of this one, and must include and argument used to pass forward the js object representing data read for theCS |
| attributeNames   | will be created and filled with the values coming from the fields, each with the specified attribute name                                                                                                                                               |

**Example**

```javascript
var processRow = function(row) {
    utils.log(
        row.userCodeId+"-"+row.password+"-"+row.rowVersion+"-"+row.dateExpirationPassword,
        "INFO"
    );
}

utils.readCSVFile(
    "myfile.csv", // file name
    9, // data source id
    ",", // separator
    false, 
    "processRow", // callback function name
    ["userCodeId","password","rowVersion","dateExpirationPassword"]
);
```

## Reading a very long csv file stored in the specified path and write it directly to a database table <a href="#getcsvcontent" id="getcsvcontent"></a>

**From 5.3.2 version**

In case of very long CSV files to read (e.g. > 1MB), it would be better to avoid reading the whole content and maintain it in the server memory, until the end of its processing: this could lead to an excessive amount of memory consumption.

The best approach consists of reading that file row by row and maintain in memory only one row per time. The following method allows to do it; moreover, this method is optimized in case you need to load data into a database table.

This methods allows to read part of data from the CSV file and part from default values. You can also read only a part of the columns provided in the CSV file.

**Syntax**

```javascript
var processedRows = utils.readCSVFileAndWriteToTable( 
  fileName,
  directoryId,
  sep,
  skipFirstRow,
  datastoreId,
  tableName,
  defaultFieldNames,
  csvFields
);
```

**Details**

| Argument          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| filenName         | CSV file name to read from the specified directory                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| directoryId       | directory identifier, used to define the absolute path, in the central server, where the file is already located; can be null                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| sep               | field separator; allowed values: , or ;                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| skipFirstRowflag  | true or false, indicating whether the first row in the file should me skipped, for instance because it contains the column header names.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| datastoreId       | data source id which identifies where the table to load is located                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| tableName         | name of the table where data will be loaded                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| defaultFieldNames | javascript object containing the list of additional table fields to fill in, expressed as field name + value; example: { STATUS: "E", CREATE\_DATE: new java.sql.Date() }                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| csvFields         | list of javascript objects, one for each CSV column; the object structure can contains optionally these attributes: { fieldName: "....", convertToSqlDate: "yyyy-MM-dd", convertToSqlTimestamp: "yyyy-MM-dd HH:mm:ss" }. This object allows to define whether the CSV column must be used to fill in the corresponding table field specified through "fieldName" attribute; if this attribute is omitted, the CSV column is ignored when importing the row; the other two attributes (convertXXXX) are optional and must be used in case a CSV column must be mapped to a DATE or DATETIME table field. Another property is trim: true\|false, used to remove spaces from text type fields. |

**Example**

```javascript
var processedRows = utils.readCSVFileAndWriteToTable(
    "myproducts.csv", // file name
    9, // data source id
    ",", // separator
    false, 
    null, // data source id: default database schema
    "MY_TABLE", // table name where inserting data
    { // these are the default values to include in every INSERT
       STATUS: "E", 
       CREATE_DATE: new java.sql.Timestamp(),
       USER_ID_CREATE: userInfo.username,
       ROW_VERSION: 1
    },
    [ // this is the list of CSV columns
    { fieldName: "PRODUCT_CODE" },
    {}, // second CSV column ignored, since it does not contain the "fieldName" attribute
    { fieldName: "DESCRIPTION" },
    { fieldName: "START_DATE", convertToSqlDate: "yyyy-MM-dd" } // we suppose that this column contains a date expressed in such format
    ]
);
```

## Writing a csv file on the server file system <a href="#getcsvcontent" id="getcsvcontent"></a>

Write a CSV file on the server file system, starting from a list of data provided in input.

Data could be retrieved from a SQL query, through the executeQuery method.

**Syntax**

```javascript
var outcome = utils.createCSVFile(
  fileName,
  overwrite,
  directoryId, 
  data, 
  sep,
  languageId,
  exportAttributes,
  exportColumns,
  formatColumns,
  printTitles,
  fileAppend
);
```

**Important note**: this method should NOT be used in case of very long CSV files, since it can consume a large amount of memory on the server. In case of a very long CSV file, please refer the next method.

**Details**

| Argument         | Description                                                                                                                                                              |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| filenName        | CSV file name to create within the specified directory                                                                                                                   |
| directoryId      | directory identifier, used to define the absolute path, in the central server, where the file will be stored; if null, there must be one only entry for this application |
| data             | list of js objects, one for each row to save into the CSV file                                                                                                           |
| sep              | field separator; allowed values: , or ;                                                                                                                                  |
| languageId       | IT, EN, ...                                                                                                                                                              |
| exportAttributes | list of attribute names to export into the CSV file                                                                                                                      |
| exportColums     | list of column headers to include as the first row in the CSV file                                                                                                       |
| formatColumns    | optional list of formatters to apply to the data defined in each js object, in order to convert data to text (e.g. "0.00" to covnert a number to string)                 |
| printTitles      | flag true\|false, indicating whether the column headers must be included as the first row in the CSV file                                                                |
| outcome          | "" in case of the operation has been executed successfully, the error message otherwise                                                                                  |

## Writing a very long csv file on the server file system <a href="#getcsvcontent" id="getcsvcontent"></a>

**From 5.3.2 version**

Write a very long CSV file on the server file system, through a 3 steps approach:

* first, open the output stream, through the "openCSVFile" method
* next, add as many rows as you need, by invoking the "writeToCSVFile" method multiple times, for each row to add
* finally, close the output stream, by invoking the "closeCSVFile"

Data could be retrieved from a SQL query, through the **executeQueryWithCallback** method, since this will ensure a limited amount of memory consumption.

**Syntax for openCSVFile method**

```javascript
var fileId = utils.openCSVFile(fileName, overwrite, directoryId, sep, fileAppend, attributesToWrite, formatters)
```

**Details**

| Argument          | Description                                                                                                                                                              |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| fileName          | CSV file name to create within the specified directory                                                                                                                   |
| overwrite         | flag true\|false used to define whether the file must overwrite a previous one                                                                                           |
| directoryId       | directory identifier, used to define the absolute path, in the central server, where the file will be stored; if null, there must be one only entry for this application |
| sep               | field separator; allowed values: , or ;                                                                                                                                  |
| fileAppend        | flag true\|false used to define if rows to add must be appneded at the end of  an already existing file                                                                  |
| attributesToWrite | list of attribute names to export into the CSV file                                                                                                                      |
| formatters        | optional list of formatters to apply to the data defined in each js object, in order to convert data to text (e.g. "0.00" to covnert a number to string)                 |
| fileId            | a text id, representing the output stream, to refer in the next two methods.                                                                                             |

**Syntax for writeToCSVFile method**

```javascript
var fileId = utils.writeToCSVFile(fileId, obj)
```

**Details**

| Argument | Description                                                                                                                                                         |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| fileId   | a text id, representing the output stream, needed to work qwith the correct output stream                                                                           |
| obj      | javascript object, containing data to write as a row in the CSV file; data contains attributes referred in the previous method through "attributrstoWrite" argument |

**Syntax for closeCSVFile method**

```javascript
var fileId = utils.closeCSVFile(fileId)
```

**Details**

| Argument | Description                                                                               |
| -------- | ----------------------------------------------------------------------------------------- |
| fileId   | a text id, representing the output stream, needed to work qwith the correct output stream |

**Example**

```javascript
// open the CSV file, in order to write into it
var fileId = utils.openCSVFile(
    "ab.csv",true,9, ",",true,
    ["userCodeId","password","rowVersion","dateExpirationPassword"],
    [null,null,null,null]
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

## Writing a very long csv file on the server file system from a SQL query <a href="#getcsvcontent" id="getcsvcontent"></a>

**From 5.3.2 version**

Write a very long CSV file on the server file system, starting from a SQL query.

```javascript
var errorMsg = utils.createCSVFileFromSQLQuery(
   fileName, overwrite, directoryId, sep, languageId, printTitles, fileAppend, formatColumns,
   datasourceId,
   sqlQuery,
   pars
);
```

**Details**

| Argument      | Description                                                                                                                                                              |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| fileName      | CSV file name to create within the specified directory                                                                                                                   |
| overwrite     | flag true/false used to define whether the file must overwrite a previous one                                                                                            |
| directoryId   | directory identifier, used to define the absolute path, in the central server, where the file will be stored; if null, there must be one only entry for this application |
| sep           | field separator; allowed values: , or ;                                                                                                                                  |
| languageId    | language to use when formatting date values                                                                                                                              |
| printTitles   | flag true/false used to incude a first row within the CSV file related to the SELECT field names                                                                         |
| fileAppend    | flag true/false used to define if rows to add must be appneded at the end of  an already existing file                                                                   |
| formatColumns | optional list of formatters to apply to the data defined in each js object, in order to convert data to text (e.g. "0.00" to covnert a number to string)                 |
| datasourceId  | datasource id which identifies the database schema where reading data                                                                                                    |
| sqlQuery      | SQL query to execute, in order to fill in the CSV file                                                                                                                   |
| pars          | list of javascript values, related to binding variables expressed as ?                                                                                                   |

**Example**

```javascript
var errors = utils.createCSVFileFromSQLQuery(
   "mycsffile.csv", 
   false, // overwrite, 
   xyz, // directoryId where the file csv will be created
   ";", // separator to use among the CSV fields
   "IT", // languageId
   true, // printTitles
   false, //  fileAppend
   null, // formatColumns
   datasourceId,
   "SELECT FIELD1,FIELD2,FIELD3 FROM MYTABLE WHERE FIELDX=?",
   ["VALUEFORFIELDX"]
);
```

## Writing data to CloudSQL from a CSV file stored in Google Cloud Storage <a href="#getcsvcontent" id="getcsvcontent"></a>

**From 5.3.2 version**

Starting from a CSV file stored in Google Cloud Storage, this method allows to load the whole content to a CloudSQL instance, in the specified table/schema, always in append mode.

In order to use this function, a Google cloud administrator must set the correct grants to the GCS and CloudSQL services.

```javascript
utils.importDataInCloudSQL(instance, bucketPath, dbSchema, dataSourceId, tableName, where, timeout, columns);
```

**Details**

| Argument     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| instance     | CloudSQL instance name; this value is reported within the Google Cloud Console                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| bucketPath   | GCS bucket name + subpath + file name for the CSV, expressed as gs://bucketname/filename.csv                                                                                                                                                                                                                                                                                                                                                                                                                         |
| dbSchema     | database schema where the table to load is located                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| dataSourceId | datasource id related to the schema specified with the previous argument                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| tableName    | table where saving data coming from the CSV file                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| where        | can be null; optional WHERE condition to include in the SQL query automatically executed (every 2 seconds) in order to check out if the data to import has been loaded. In null, it is assumed that the table is empty and the executed query would be "SELECT COUNT(\*) FROM tablename". This method terminates when the returned value is > 0. If this argument is filled in, the query would be "SELECT COUNT(\*) from tablename WHERE yourwhere". Again, the method terminates when there is at least one record |
| timeout      | max number of seconds to wait before a timeout is fired, waiting from the completition of data loading on the table                                                                                                                                                                                                                                                                                                                                                                                                  |
| columns      | list of table fields where the CSV data will be saved: these fields must be as many as the number of columns in the CSV file                                                                                                                                                                                                                                                                                                                                                                                         |

**Example**

```
var processedRows = utils.importDataInCloudSQL(
    "cloudsqlinstancename",
    "gs://mybucket/myfile.csv",
    "mydatabaseschema",
    mydatasourceid,
    "mytable",
    "MYFIELD = 'XYZ' ",
    50,// max number of seconds to wait
    ["STATISTICS","VALUE","POSITION","DDS","TOTALE","PERCENTUALE"] // table field names/CSV columns
);
utils.debug("Processed Rows: " + processedRows);
```

```javascript
var response = utils.importDataInCloudSQL(
    "cloudsqlinstancename",
    "gs://mybucket/myfile.csv",
    "mydatabaseschema",
    mydatasourceid,
    "mytable",
    "MYFIELD = 'XYZ' ",
    50,// max number of seconds to wait
    ["STATISTICS","VALUE","POSITION","DDS","TOTALE","PERCENTUALE"] // table field names/CSV columns
);
utils.debug("Processed Id: " + response.name);
utils.debug("Rows: " + response.processedRows);
utils.debug("Status: " + response.status);
utils.debug("Start: " + response.startTime);
utils.debug("End: " + response.endTime);
utils.debug("Operation Type: " + response.operationType)
```

##





