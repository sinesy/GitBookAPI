# Function JSS EE

## addFileToMobileDevices

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addFileToMobileDevices(String fullPathName,String fileName,String username);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| fullPathName | \[description...] |
| fileName     | \[description...] |
| username     | \[description...] |

## addGoogleCalendarEvent

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return CalendarEvent type
var risp = utils.addGoogleCalendarEvent(String title,Date beginDate,Date endDate);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| title     | \[description...] |
| beginDate | \[description...] |
| endDate   | \[description...] |

## addGoogleCalendarEventWithConference

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return CalendarEvent type
var risp = utils.addGoogleCalendarEventWithConference(String serviceAccountEmail,String privateKeyString,String userId,String title,Date beginDate,Date endDate,String description,String location,String calendarId,String type,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| serviceAccountEmail | \[description...] |
| privateKeyString    | \[description...] |
| userId              | \[description...] |
| title               | \[description...] |
| beginDate           | \[description...] |
| endDate             | \[description...] |
| description         | \[description...] |
| location            | \[description...] |
| calendarId          | \[description...] |
| type                | \[description...] |
| creatorEmail        | \[description...] |
| attendeeEmails      | \[description...] |

## addGoogleCalendarEventWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return CalendarEvent type
var risp = utils.addGoogleCalendarEventWithSettings(String serviceAccountEmail,String privateKeyString,String userId,String title,Date beginDate,Date endDate,String description,String location,String calendarId,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| serviceAccountEmail | \[description...] |
| privateKeyString    | \[description...] |
| userId              | \[description...] |
| title               | \[description...] |
| beginDate           | \[description...] |
| endDate             | \[description...] |
| description         | \[description...] |
| location            | \[description...] |
| calendarId          | \[description...] |
| creatorEmail        | \[description...] |
| attendeeEmails      | \[description...] |

## addGoogleContact

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Contact type
var risp = utils.addGoogleContact(String name,String surname,String email,String phone,Boolean shared);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| name     | \[description...] |
| surname  | \[description...] |
| email    | \[description...] |
| phone    | \[description...] |
| shared   | \[description...] |

## addGoogleDriveFileProperty

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleDriveFileProperty(String fileId,String key,String value,String visibility);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| fileId     | \[description...] |
| key        | \[description...] |
| value      | \[description...] |
| visibility | \[description...] |

## addGoogleDriveFileProperty

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleDriveFileProperty(String userId,String fileId,String key,String value,String visibility);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| userId     | \[description...] |
| fileId     | \[description...] |
| key        | \[description...] |
| value      | \[description...] |
| visibility | \[description...] |

## addISO8601

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Date type
var risp = utils.addISO8601(Date dt,String period);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| dt       | \[description...] |
| period   | \[description...] |

## addPermissionsToGoogleDriveFolder

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.addPermissionsToGoogleDriveFolder(String folderId,String type,String value,String fileRole,String folderRole,String> additionalRoles,Boolean updateBaseFolder,Boolean recursive,Boolean sendNotifications,String message);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| folderId          | \[description...] |
| type              | \[description...] |
| value             | \[description...] |
| fileRole          | \[description...] |
| folderRole        | \[description...] |
| additionalRoles   | \[description...] |
| updateBaseFolder  | \[description...] |
| recursive         | \[description...] |
| sendNotifications | \[description...] |
| message           | \[description...] |

## addPermissionsToGoogleDriveFolder

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.addPermissionsToGoogleDriveFolder(String userId,String folderId,String type,String value,String fileRole,String folderRole,String> additionalRoles,Boolean updateBaseFolder,Boolean recursive,Boolean sendNotifications,String message);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| userId            | \[description...] |
| folderId          | \[description...] |
| type              | \[description...] |
| value             | \[description...] |
| fileRole          | \[description...] |
| folderRole        | \[description...] |
| additionalRoles   | \[description...] |
| updateBaseFolder  | \[description...] |
| recursive         | \[description...] |
| sendNotifications | \[description...] |
| message           | \[description...] |

## addValueInCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addValueInCache(String varName,Object value);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| varName  | \[description...] |
| value    | \[description...] |

## addValueInCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addValueInCache(String varName,Object value,Long expirationTime);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| varName        | \[description...] |
| value          | \[description...] |
| expirationTime | \[description...] |

## analyzeEntities

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.analyzeEntities(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| text         | \[description...] |
| encodingType | \[description...] |
| htmlText     | \[description...] |

## analyzeEntitySentiment

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.analyzeEntitySentiment(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| text         | \[description...] |
| encodingType | \[description...] |
| htmlText     | \[description...] |

## analyzeSentiment

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.analyzeSentiment(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| text         | \[description...] |
| encodingType | \[description...] |
| htmlText     | \[description...] |

## analyzeSyntax

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.analyzeSyntax(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| text         | \[description...] |
| encodingType | \[description...] |
| htmlText     | \[description...] |

## appendRangeGoogleSheet

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Integer type
var risp = utils.appendRangeGoogleSheet(String userId,String spreadsheetId,String range,String valueInputOption,String insertDataOption,Object[][] vos);
```
{% endcode %}

Details

| Argument         | Description       |
| ---------------- | ----------------- |
| userId           | \[description...] |
| spreadsheetId    | \[description...] |
| range            | \[description...] |
| valueInputOption | \[description...] |
| insertDataOption | \[description...] |
| vos              | \[description...] |

## backupEntitiesInGCS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.backupEntitiesInGCS(String[] entityNames,Long directoryId);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| entityNames | \[description...] |
| directoryId | \[description...] |

## bulkDeleteOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkDeleteOnGoogleDatastore(String gql);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| gql      | \[description...] |

## bulkImport

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String[] type
var risp = utils.bulkImport(Long sourceDirId,Long destDirId,Long backupDirId,Long dataSourceId,String tableName,String csvFileName,String csvFileNameField,String csvUniqueIdField,String csvSep,Object> defaultValues,String> mapping,String nullString,Boolean skipWithErrors,Boolean skipFileNotInCSV,Long beforeInsertActionId,Long afterInsertActionId);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| sourceDirId          | \[description...] |
| destDirId            | \[description...] |
| backupDirId          | \[description...] |
| dataSourceId         | \[description...] |
| tableName            | \[description...] |
| csvFileName          | \[description...] |
| csvFileNameField     | \[description...] |
| csvUniqueIdField     | \[description...] |
| csvSep               | \[description...] |
| defaultValues        | \[description...] |
| mapping              | \[description...] |
| nullString           | \[description...] |
| skipWithErrors       | \[description...] |
| skipFileNotInCSV     | \[description...] |
| beforeInsertActionId | \[description...] |
| afterInsertActionId  | \[description...] |

## bulkImportFromDSToBigQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImportFromDSToBigQuery(String gql,Long datastoreDataModelId,String location,String bigQueryTable,boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| gql                  | \[description...] |
| datastoreDataModelId | \[description...] |
| location             | \[description...] |
| bigQueryTable        | \[description...] |
| interruptExecution   | \[description...] |
| pars                 | \[description...] |

## bulkImportFromDSToSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImportFromDSToSpanner(String gql,Long datastoreDataModelId,boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| gql                  | \[description...] |
| datastoreDataModelId | \[description...] |
| interruptExecution   | \[description...] |
| pars                 | \[description...] |

## bulkImportFromFTP

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String[] type
var risp = utils.bulkImportFromFTP(String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter,Long destDirId,Long backupDirId,Long dataSourceId,String tableName,String csvFileName,String csvFileNameField,String csvUniqueIdField,String csvSep,Object> defaultValues,String> mappingCsvToFields,String nullString,Boolean skipWithErrors,Boolean skipFileNotInCSV,Long beforeInsertActionId,Long afterInsertActionId);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| host                 | \[description...] |
| port                 | \[description...] |
| useSSL               | \[description...] |
| username             | \[description...] |
| password             | \[description...] |
| remoteDir            | \[description...] |
| fileFilter           | \[description...] |
| destDirId            | \[description...] |
| backupDirId          | \[description...] |
| dataSourceId         | \[description...] |
| tableName            | \[description...] |
| csvFileName          | \[description...] |
| csvFileNameField     | \[description...] |
| csvUniqueIdField     | \[description...] |
| csvSep               | \[description...] |
| defaultValues        | \[description...] |
| mappingCsvToFields   | \[description...] |
| nullString           | \[description...] |
| skipWithErrors       | \[description...] |
| skipFileNotInCSV     | \[description...] |
| beforeInsertActionId | \[description...] |
| afterInsertActionId  | \[description...] |

## bulkUpdateOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkUpdateOnGoogleDatastore(String gql,Map attributesToSet,Map attributesToRemove,Long actionId);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| gql                | \[description...] |
| attributesToSet    | \[description...] |
| attributesToRemove | \[description...] |
| actionId           | \[description...] |

## callGaeAction

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.callGaeAction(Long actionId,Boolean async);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| actionId | \[description...] |
| async    | \[description...] |

## checkGoogleSSOToken

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.checkGoogleSSOToken(String ssoAuthToken);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| ssoAuthToken | \[description...] |

## classifyText

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.classifyText(String text,Boolean htmlText);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| text     | \[description...] |
| htmlText | \[description...] |

## clearAllDatastoreEntities

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearAllDatastoreEntities);
```
{% endcode %}

Details

## clearCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.clearCache(String varNames);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| varNames | \[description...] |

## clearCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.clearCache(String varNames,String keys);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| varNames | \[description...] |
| keys     | \[description...] |

## clearDatastoreEntities

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearDatastoreEntities(String entityName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| entityName | \[description...] |

## clearRangeGoogleSheet

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.clearRangeGoogleSheet(String userId,String spreadsheetId,String range);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| userId        | \[description...] |
| spreadsheetId | \[description...] |
| range         | \[description...] |

## closeActivitiTask

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.closeActivitiTask(String processInstanceId,String taskDefinitionKey,String assignee,Map map);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| processInstanceId | \[description...] |
| taskDefinitionKey | \[description...] |
| assignee          | \[description...] |
| map               | \[description...] |

## closeActivitiTask

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.closeActivitiTask(String taskInstanceId,Map map);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| taskInstanceId | \[description...] |
| map            | \[description...] |

## completeActivitiTask

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.completeActivitiTask(String processInstanceId,Map params,Map processVariables);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| processInstanceId | \[description...] |
| params            | \[description...] |
| processVariables  | \[description...] |

## convertDocxToOtherFormat

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertDocxToOtherFormat(String docxFile,String newFile,Boolean deleteDocxFile,String format);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| docxFile       | \[description...] |
| newFile        | \[description...] |
| deleteDocxFile | \[description...] |
| format         | \[description...] |

## convertDocxToPdf

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertDocxToPdf(String docxFile,String pdfFile,Boolean deleteDocxFile);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| docxFile       | \[description...] |
| pdfFile        | \[description...] |
| deleteDocxFile | \[description...] |

## convertHtmlToImage

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertHtmlToImage(String html,String imagePath);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| html      | \[description...] |
| imagePath | \[description...] |

## convertISO8601

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.convertISO8601(String period);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| period   | \[description...] |

## convertListWithMapper

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.convertListWithMapper(String json,Map settings);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| json     | \[description...] |
| settings | \[description...] |

## convertObjectWithMapper

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.convertObjectWithMapper(String json,Map settings);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| json     | \[description...] |
| settings | \[description...] |

## convertPdfToImage

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.convertPdfToImage(Long pdfDirId,String pdfFileName,Long imgDirId,String imgExtension,Float scale);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| pdfDirId     | \[description...] |
| pdfFileName  | \[description...] |
| imgDirId     | \[description...] |
| imgExtension | \[description...] |
| scale        | \[description...] |

## convertTifToJpg

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertTifToJpg(Long tifDirId,String tifFileName,Long jpgDirId,String jpgFileName,Float compressionFactor);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| tifDirId          | \[description...] |
| tifFileName       | \[description...] |
| jpgDirId          | \[description...] |
| jpgFileName       | \[description...] |
| compressionFactor | \[description...] |

## convertUrlToImage

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertUrlToImage(String url,String imagePath);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| url       | \[description...] |
| imagePath | \[description...] |

## copyGoogleCloudStorageObject

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.copyGoogleCloudStorageObject(String sourceBucketName,String sourceObjectName,Long sourceObjectVersion,String destinationBucketName,String destinationObjectName);
```
{% endcode %}

Details

| Argument              | Description       |
| --------------------- | ----------------- |
| sourceBucketName      | \[description...] |
| sourceObjectName      | \[description...] |
| sourceObjectVersion   | \[description...] |
| destinationBucketName | \[description...] |
| destinationObjectName | \[description...] |

## copyGoogleSheet

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.copyGoogleSheet(String userId,String spreadsheetId,Integer sheetId,String destinationSpreadsheetId);
```
{% endcode %}

Details

| Argument                 | Description       |
| ------------------------ | ----------------- |
| userId                   | \[description...] |
| spreadsheetId            | \[description...] |
| sheetId                  | \[description...] |
| destinationSpreadsheetId | \[description...] |

## createBigQueryDataset

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryDataset(String datasetName);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |

## createBigQueryTable

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryTable(String datasetName,String tableName,Map> columns);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |
| tableName   | \[description...] |
| columns     | \[description...] |

## createBigQueryTableFromDatastoreEntities

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryTableFromDatastoreEntities(String[] entityNames,Long directoryId,String datasetName);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| entityNames | \[description...] |
| directoryId | \[description...] |
| datasetName | \[description...] |

## createConDbForCurrentUser

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createConDbForCurrentUser(String companyId,Long siteId,String username);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| companyId | \[description...] |
| siteId    | \[description...] |
| username  | \[description...] |

## createCsvFromSqlQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createCsvFromSqlQuery(String sql,Long dataSourceId,Boolean includeRowNum,String replaceNullWith,Long fromRow,Long maxRowsToRead,String firstRow,String sep,Long dirId,String fileName);
```
{% endcode %}

Details

| Argument        | Description       |
| --------------- | ----------------- |
| sql             | \[description...] |
| dataSourceId    | \[description...] |
| includeRowNum   | \[description...] |
| replaceNullWith | \[description...] |
| fromRow         | \[description...] |
| maxRowsToRead   | \[description...] |
| firstRow        | \[description...] |
| sep             | \[description...] |
| dirId           | \[description...] |
| fileName        | \[description...] |

## createGoogleCloudStorageBucket

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return FileContainer type
var risp = utils.createGoogleCloudStorageBucket(String project,String bucketName,String bucketLocation,String storageClass);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| project        | \[description...] |
| bucketName     | \[description...] |
| bucketLocation | \[description...] |
| storageClass   | \[description...] |

## createGoogleDriveFolder

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.createGoogleDriveFolder(String userId,String folderName,String> parents,String description);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| userId      | \[description...] |
| folderName  | \[description...] |
| parents     | \[description...] |
| description | \[description...] |

## createGoogleDriveFolder

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.createGoogleDriveFolder(String folderName,String> parents,String description);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| folderName  | \[description...] |
| parents     | \[description...] |
| description | \[description...] |

## createGoogleSheets

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.createGoogleSheets(String userId,String spreadsheetId,String[] sheets);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| userId        | \[description...] |
| spreadsheetId | \[description...] |
| sheets        | \[description...] |

## createGoogleSpreadsheets

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.createGoogleSpreadsheets(String userId,String spreadsheetTitle,String[] sheets);
```
{% endcode %}

Details

| Argument         | Description       |
| ---------------- | ----------------- |
| userId           | \[description...] |
| spreadsheetTitle | \[description...] |
| sheets           | \[description...] |

## createStripeCustomer

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.createStripeCustomer(String apiKey,Map customerData);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| apiKey       | \[description...] |
| customerData | \[description...] |

## createTablesFromDatastoreBackup

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createTablesFromDatastoreBackup(String[] entityNames,String gcsURI,String datasetName);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| entityNames | \[description...] |
| gcsURI      | \[description...] |
| datasetName | \[description...] |

## createXLSXFileFromSQLQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Long type
var risp = utils.createXLSXFileFromSQLQuery(Long templateDirectoryId,String templateFileName,String sheetName,Long outDirectoryId,String outFileName,Map[] formatHeaderColumns,Map[] formatColumns,Map grouping,Map additionalSettings,Long datastoreId,String sqlQuery,Object[] pars);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| templateDirectoryId | \[description...] |
| templateFileName    | \[description...] |
| sheetName           | \[description...] |
| outDirectoryId      | \[description...] |
| outFileName         | \[description...] |
| formatHeaderColumns | \[description...] |
| formatColumns       | \[description...] |
| grouping            | \[description...] |
| additionalSettings  | \[description...] |
| datastoreId         | \[description...] |
| sqlQuery            | \[description...] |
| pars                | \[description...] |

## createXlsContent

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createXlsContent(Long dirId,String fileName,String sheetName,Integer sheetIndex,Integer fromRow,Object>[] vos,String[] attributeNames);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| dirId          | \[description...] |
| fileName       | \[description...] |
| sheetName      | \[description...] |
| sheetIndex     | \[description...] |
| fromRow        | \[description...] |
| vos            | \[description...] |
| attributeNames | \[description...] |

## deleteBigQueryDataset

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteBigQueryDataset(String datasetName);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |

## deleteBigQueryObject

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Long type
var risp = utils.deleteBigQueryObject(String datasetName,String tableName,Map obj,String[] pks);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |
| tableName   | \[description...] |
| obj         | \[description...] |
| pks         | \[description...] |

## deleteBigQueryTable

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteBigQueryTable(String datasetName,String tableName);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |
| tableName   | \[description...] |

## deleteCard

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.deleteCard(Long dataModelId,Long panelId,Map vo);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| dataModelId | \[description...] |
| panelId     | \[description...] |
| vo          | \[description...] |

## deleteCards

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map[] type
var risp = utils.deleteCards(Long dataModelId,Long panelId,Map[] vos);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| dataModelId | \[description...] |
| panelId     | \[description...] |
| vos         | \[description...] |

## deleteDir

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Boolean type
var risp = utils.deleteDir(Long dirId,String subFolder);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| dirId     | \[description...] |
| subFolder | \[description...] |

## deleteFileFromCMS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFileFromCMS(String uuid);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| uuid     | \[description...] |

## deleteFiles

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Boolean type
var risp = utils.deleteFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive,Boolean removeEmptyDir);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| dirId          | \[description...] |
| subFolder      | \[description...] |
| operator       | \[description...] |
| fileName       | \[description...] |
| caseSensitive  | \[description...] |
| removeEmptyDir | \[description...] |

## deleteFiles

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Boolean type
var risp = utils.deleteFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| dirId         | \[description...] |
| subFolder     | \[description...] |
| operator      | \[description...] |
| fileName      | \[description...] |
| caseSensitive | \[description...] |

## deleteGoogleCalendarEvent

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleCalendarEvent(String calendarEventId);
```
{% endcode %}

Details

| Argument        | Description       |
| --------------- | ----------------- |
| calendarEventId | \[description...] |

## deleteGoogleCalendarEventWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleCalendarEventWithSettings(String serviceAccountEmail,String privateKeyString,String userId,String calendarEventId);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| serviceAccountEmail | \[description...] |
| privateKeyString    | \[description...] |
| userId              | \[description...] |
| calendarEventId     | \[description...] |

## deleteGoogleCloudStorageBucket

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return FileContainer type
var risp = utils.deleteGoogleCloudStorageBucket(String bucketName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |

## deleteGoogleCloudStorageObject

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.deleteGoogleCloudStorageObject(String bucketName,String objectName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |
| objectName | \[description...] |

## deleteGoogleContact

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleContact(String contactId,Boolean shared);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| contactId | \[description...] |
| shared    | \[description...] |

## deleteGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.deleteGoogleDriveFile(String userId,String fileId,boolean skipTrash);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| userId    | \[description...] |
| fileId    | \[description...] |
| skipTrash | \[description...] |

## deleteGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.deleteGoogleDriveFile(String fileId,boolean skipTrash);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| fileId    | \[description...] |
| skipTrash | \[description...] |

## deleteGoogleDriveFileProperty

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFileProperty(String userId,String fileId,String key);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| userId   | \[description...] |
| fileId   | \[description...] |
| key      | \[description...] |

## deleteGoogleDriveFileProperty

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFileProperty(String fileId,String key);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| fileId   | \[description...] |
| key      | \[description...] |

## deleteGoogleSheets

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.deleteGoogleSheets(String userId,String spreadsheetId,Integer[] sheetIds);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| userId        | \[description...] |
| spreadsheetId | \[description...] |
| sheetIds      | \[description...] |

## deleteObjectOnBigQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.deleteObjectOnBigQuery(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## deleteObjectOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.deleteObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## deleteObjectOnGoogleSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.deleteObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## deleteObjectOnMongoDb

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.deleteObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## deleteProcessInstance

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteProcessInstance(String processInstanceId);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| processInstanceId | \[description...] |

## downloadArchiflowDocument

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.downloadArchiflowDocument(Long dirId,String fileName,String cardId,Map additionalSettings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| dirId              | \[description...] |
| fileName           | \[description...] |
| cardId             | \[description...] |
| additionalSettings | \[description...] |

## downloadFileFromGoogleDrive

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.downloadFileFromGoogleDrive(String userId,String fileId,String localPath,String fileName);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| userId    | \[description...] |
| fileId    | \[description...] |
| localPath | \[description...] |
| fileName  | \[description...] |

## downloadGoogleCloudStorageObject

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.downloadGoogleCloudStorageObject(String bucketName,String objectName,String destPath);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |
| objectName | \[description...] |
| destPath   | \[description...] |

## duplicateGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.duplicateGoogleDriveFile(String userId,String sourceFolderId,String destinationFolderId,String newFileName,Boolean copyPermissions);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| userId              | \[description...] |
| sourceFolderId      | \[description...] |
| destinationFolderId | \[description...] |
| newFileName         | \[description...] |
| copyPermissions     | \[description...] |

## duplicateGoogleDriveFolderAndContents

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.duplicateGoogleDriveFolderAndContents(String userId,String sourceFolderId,String newFolderName,String newFolderDescription,String destinationFolderId,String titlePrefix,Boolean copyPermissions);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| userId               | \[description...] |
| sourceFolderId       | \[description...] |
| newFolderName        | \[description...] |
| newFolderDescription | \[description...] |
| destinationFolderId  | \[description...] |
| titlePrefix          | \[description...] |
| copyPermissions      | \[description...] |

## duplicateGoogleDriveFolderAndContents

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.duplicateGoogleDriveFolderAndContents(String sourceFolderId,String newFolderName,String newFolderDescription,String destinationFolderId,String titlePrefix,Boolean copyPermissions);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| sourceFolderId       | \[description...] |
| newFolderName        | \[description...] |
| newFolderDescription | \[description...] |
| destinationFolderId  | \[description...] |
| titlePrefix          | \[description...] |
| copyPermissions      | \[description...] |

## duplicateGoogleSheet

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.duplicateGoogleSheet(String userId,String spreadsheetId,Integer sourceSheetId,Integer insertSheetIndex,Integer newSheetId,String newSheetName);
```
{% endcode %}

Details

| Argument         | Description       |
| ---------------- | ----------------- |
| userId           | \[description...] |
| spreadsheetId    | \[description...] |
| sourceSheetId    | \[description...] |
| insertSheetIndex | \[description...] |
| newSheetId       | \[description...] |
| newSheetName     | \[description...] |

## encodeJWT

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.encodeJWT(Map dataToSend,String sharedKey);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| dataToSend | \[description...] |
| sharedKey  | \[description...] |

## enqueueGaeAction

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.enqueueGaeAction(String queueName,Long actionId,Map params);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| queueName | \[description...] |
| actionId  | \[description...] |
| params    | \[description...] |

## enquiryTasks

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.enquiryTasks(HashMap pars);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| pars     | \[description...] |

## executeAction

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeAction(Long actionId,Map vo,Map params,Map headers);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| actionId | \[description...] |
| vo       | \[description...] |
| params   | \[description...] |
| headers  | \[description...] |

## executeActionSameTransaction

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeActionSameTransaction(Long actionId,Map vo,Map params,Map headers);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| actionId | \[description...] |
| vo       | \[description...] |
| params   | \[description...] |
| headers  | \[description...] |

## executeAllExports

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return long type
var risp = utils.executeAllExports(String queryType,Map paramValues);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| queryType   | \[description...] |
| paramValues | \[description...] |

## executeBigQueryDmlStatement

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Long type
var risp = utils.executeBigQueryDmlStatement(String datasetName,String sql,Object[] pars);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |
| sql         | \[description...] |
| pars        | \[description...] |

## executeBigQuerySaveOnLocalTable

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return long type
var risp = utils.executeBigQuerySaveOnLocalTable(Long datastoreId,String localTableName,Map defaultFieldNames,Map[] csvFields,String defaultDataset,String sqlQuery,Object[] params);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| datastoreId       | \[description...] |
| localTableName    | \[description...] |
| defaultFieldNames | \[description...] |
| csvFields         | \[description...] |
| defaultDataset    | \[description...] |
| sqlQuery          | \[description...] |
| params            | \[description...] |

## executeBigQuerySaveOnTable

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeBigQuerySaveOnTable(String destinationDataset,String destinationTable,String defaultDataset,String sqlQuery,Object[] params);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| destinationDataset | \[description...] |
| destinationTable   | \[description...] |
| defaultDataset     | \[description...] |
| sqlQuery           | \[description...] |
| params             | \[description...] |

## executeBigQueryWithCallback

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeBigQueryWithCallback(String processRowFunName,String defaultDataset,String sqlQuery,Object[] params);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| processRowFunName | \[description...] |
| defaultDataset    | \[description...] |
| sqlQuery          | \[description...] |
| params            | \[description...] |

## executeCachedQueryOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeCachedQueryOnGoogleDatastore(int maxCachedEntities,String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| maxCachedEntities  | \[description...] |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## executeCachedQueryOnGoogleDatastoreWithSetting

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeCachedQueryOnGoogleDatastoreWithSetting(int maxCachedEntities,String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| maxCachedEntities  | \[description...] |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |
| pars               | \[description...] |

## executeExport

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return long type
var risp = utils.executeExport(Long exportId,String queryType,Map paramValues);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| exportId    | \[description...] |
| queryType   | \[description...] |
| paramValues | \[description...] |

## executeExportsInGroup

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return long type
var risp = utils.executeExportsInGroup(String groupName,String queryType,Map paramValues);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| groupName   | \[description...] |
| queryType   | \[description...] |
| paramValues | \[description...] |

## executeQueryOnBigQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeQueryOnBigQuery(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## executeQueryOnBigQueryWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeQueryOnBigQueryWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map map,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| map                | \[description...] |
| pars               | \[description...] |

## executeQueryOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeQueryOnGoogleDatastore(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## executeQueryOnGoogleDatastoreWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeQueryOnGoogleDatastoreWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |
| pars               | \[description...] |

## executeQueryOnGoogleSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeQueryOnGoogleSpanner(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## executeQueryOnGoogleSpannerWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeQueryOnGoogleSpannerWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |
| pars               | \[description...] |

## executeQueryOnMongoDb

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeQueryOnMongoDb(String where,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| where              | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## executeSpannerDdl

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeSpannerDdl(String[] scripts);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| scripts  | \[description...] |

## executeSpannerSql

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSpannerSql(String sql);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| sql      | \[description...] |

## executeStripePayment

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.executeStripePayment(String apiKey,Long priceWithCents,String currency,String customerId);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| apiKey         | \[description...] |
| priceWithCents | \[description...] |
| currency       | \[description...] |
| customerId     | \[description...] |

## exportFromExcelFileToGSheet

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.exportFromExcelFileToGSheet(String userId,Long sourceDirId,String sourceFileName,String spreadsheetId,List areas);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| userId         | \[description...] |
| sourceDirId    | \[description...] |
| sourceFileName | \[description...] |
| spreadsheetId  | \[description...] |
| areas          | \[description...] |

## exportFromExcelFileToGSheet

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.exportFromExcelFileToGSheet(Long sourceDirId,String sourceFileName,String spreadsheetId,List areas);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| sourceDirId    | \[description...] |
| sourceFileName | \[description...] |
| spreadsheetId  | \[description...] |
| areas          | \[description...] |

## exportUsersToDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportUsersToDatastore(String companyId);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| companyId | \[description...] |

## exportUsersToDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportUsersToDatastore);
```
{% endcode %}

Details

## extractBigQueryData

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.extractBigQueryData(String datasetName,String tableName,String format,String gcsUrl,Boolean deleteTableAfterExport,Boolean exportHeaders);
```
{% endcode %}

Details

| Argument               | Description       |
| ---------------------- | ----------------- |
| datasetName            | \[description...] |
| tableName              | \[description...] |
| format                 | \[description...] |
| gcsUrl                 | \[description...] |
| deleteTableAfterExport | \[description...] |
| exportHeaders          | \[description...] |

## generateDocx

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.generateDocx(Long reportId,Object> args,String langId,String path,String fileName);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| reportId | \[description...] |
| args     | \[description...] |
| langId   | \[description...] |
| path     | \[description...] |
| fileName | \[description...] |

## generateGCPAuthToken

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.generateGCPAuthToken(String user,String serviceAccountEmail,String privateKeyString,String redirectUri,String[] _scopes);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| user                | \[description...] |
| serviceAccountEmail | \[description...] |
| privateKeyString    | \[description...] |
| redirectUri         | \[description...] |
| \_scopes            | \[description...] |

## getActivitiLastVersionProcessId

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getActivitiLastVersionProcessId(String id);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| id       | \[description...] |

## getActivitiProcessAsJson

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getActivitiProcessAsJson(String id,Boolean includeSubProcesses,Map tasksDueDates);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| id                  | \[description...] |
| includeSubProcesses | \[description...] |
| tasksDueDates       | \[description...] |

## getActivitiProcessInstancesVariables

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getActivitiProcessInstancesVariables(String processInstanceId,String processDefinitionId);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| processInstanceId   | \[description...] |
| processDefinitionId | \[description...] |

## getActivitiUserAssignedTasks

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getActivitiUserAssignedTasks(String assignee,String processInstanceId,String taskDefinitionKey);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| assignee          | \[description...] |
| processInstanceId | \[description...] |
| taskDefinitionKey | \[description...] |

## getActivitiUserCandidateTasks

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getActivitiUserCandidateTasks(String candidate,String processInstanceId,String taskDefinitionKey);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| candidate         | \[description...] |
| processInstanceId | \[description...] |
| taskDefinitionKey | \[description...] |

## getAlfrescoDocument

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.getAlfrescoDocument(String id,String fileName,String destPath);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| id       | \[description...] |
| fileName | \[description...] |
| destPath | \[description...] |

## getAlfrescoWebScript

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getAlfrescoWebScript(String uri,boolean replaceVariables,String httpMethod,String bodyRequest);
```
{% endcode %}

Details

| Argument         | Description       |
| ---------------- | ----------------- |
| uri              | \[description...] |
| replaceVariables | \[description...] |
| httpMethod       | \[description...] |
| bodyRequest      | \[description...] |

## getAlfrescoWebScript

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getAlfrescoWebScript(String uri,boolean replaceVariables,String httpMethod,String bodyRequest,String charSet);
```
{% endcode %}

Details

| Argument         | Description       |
| ---------------- | ----------------- |
| uri              | \[description...] |
| replaceVariables | \[description...] |
| httpMethod       | \[description...] |
| bodyRequest      | \[description...] |
| charSet          | \[description...] |

## getBigQueryDataset

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getBigQueryDataset);
```
{% endcode %}

Details

## getButtonsAuthorizationOfUser

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.getButtonsAuthorizationOfUser);
```
{% endcode %}

Details

## getDetailOnArchiflow

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getDetailOnArchiflow(Long dataModelId,String cardId,Map additionalSettings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| dataModelId        | \[description...] |
| cardId             | \[description...] |
| additionalSettings | \[description...] |

## getElementFromQueueByNote

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getElementFromQueueByNote(String note,String namespace);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| note      | \[description...] |
| namespace | \[description...] |

## getEntities

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map[] type
var risp = utils.getEntities(String entityName,Object[] entityKeys);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| entityName | \[description...] |
| entityKeys | \[description...] |

## getEntitiesAsJSON

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getEntitiesAsJSON(String entityName,Object[] entityKeys);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| entityName | \[description...] |
| entityKeys | \[description...] |

## getEntity

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.getEntity(String entityName,Object key,int maxCachedEntities,Long expirationTime);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| entityName        | \[description...] |
| key               | \[description...] |
| maxCachedEntities | \[description...] |
| expirationTime    | \[description...] |

## getEntity

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.getEntity(String entityName,Object key,int maxCachedEntities);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| entityName        | \[description...] |
| key               | \[description...] |
| maxCachedEntities | \[description...] |

## getEntityAsJSON

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| entityName        | \[description...] |
| key               | \[description...] |
| maxCachedEntities | \[description...] |

## getEntityAsJSON

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities,Long expirationTime);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| entityName        | \[description...] |
| key               | \[description...] |
| maxCachedEntities | \[description...] |
| expirationTime    | \[description...] |

## getFunctionAuthorizationOfUser

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.getFunctionAuthorizationOfUser(String functionId);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| functionId | \[description...] |

## getGCPAuthToken

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGCPAuthToken(String user,String serviceAccountEmail,String privateKeyString,String[] _scopes);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| user                | \[description...] |
| serviceAccountEmail | \[description...] |
| privateKeyString    | \[description...] |
| \_scopes            | \[description...] |

## getGoogleCloudStorageBucket

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return FileContainer type
var risp = utils.getGoogleCloudStorageBucket(String bucketName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |

## getGoogleCloudStorageBucketVersioning

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Boolean type
var risp = utils.getGoogleCloudStorageBucketVersioning(String bucketName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |

## getGoogleCloudStorageObject

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.getGoogleCloudStorageObject(String bucketName,String objectName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |
| objectName | \[description...] |

## getGoogleCloudStorageObjectVersions

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleCloudStorageObjectVersions(String bucketName,String objectName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |
| objectName | \[description...] |

## getGoogleCloudStorageSignedURL

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleCloudStorageSignedURL(String verb,Long expiration,String bucketName,String objectName,String mime);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| verb       | \[description...] |
| expiration | \[description...] |
| bucketName | \[description...] |
| objectName | \[description...] |
| mime       | \[description...] |

## getGoogleContactsFiltered

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleContactsFiltered(Integer pages,Integer maxPageResults,String searchString,Boolean splitEmails);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| pages          | \[description...] |
| maxPageResults | \[description...] |
| searchString   | \[description...] |
| splitEmails    | \[description...] |

## getGoogleDomainContactsFiltered

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleDomainContactsFiltered(Integer pages,Integer maxPageResults,String query,String orderBy,String sortOrder);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| pages          | \[description...] |
| maxPageResults | \[description...] |
| query          | \[description...] |
| orderBy        | \[description...] |
| sortOrder      | \[description...] |

## getGoogleDriveFileDownloadURL

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleDriveFileDownloadURL(String fileId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| fileId   | \[description...] |

## getGoogleDriveFileInfo

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.getGoogleDriveFileInfo(String userId,String fileId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| userId   | \[description...] |
| fileId   | \[description...] |

## getGoogleDriveFileInfo

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.getGoogleDriveFileInfo(String fileId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| fileId   | \[description...] |

## getGoogleDriveFileOpenURL

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleDriveFileOpenURL(String fileId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| fileId   | \[description...] |

## getGoogleDriveFileProperty

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleDriveFileProperty(String userId,String fileId,String key,String visibility);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| userId     | \[description...] |
| fileId     | \[description...] |
| key        | \[description...] |
| visibility | \[description...] |

## getGoogleDriveFileProperty

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleDriveFileProperty(String fileId,String key,String visibility);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| fileId     | \[description...] |
| key        | \[description...] |
| visibility | \[description...] |

## getGoogleDriveFileRevisions

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleDriveFileRevisions(String fileId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| fileId   | \[description...] |

## getGoogleDriveFileRevisions

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleDriveFileRevisions(String userId,String fileId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| userId   | \[description...] |
| fileId   | \[description...] |

## getGoogleDriveFolderContents

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleDriveFolderContents(String userId,String folderId,String query,Boolean trashed);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| userId   | \[description...] |
| folderId | \[description...] |
| query    | \[description...] |
| trashed  | \[description...] |

## getGoogleDriveFolderContents

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleDriveFolderContents(String folderId,String query,Boolean trashed);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| folderId | \[description...] |
| query    | \[description...] |
| trashed  | \[description...] |

## getGoogleDriveFolderContentsIds

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleDriveFolderContentsIds(String userId,String folderId,String query,boolean trashed);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| userId   | \[description...] |
| folderId | \[description...] |
| query    | \[description...] |
| trashed  | \[description...] |

## getGoogleDriveFolderContentsIds

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleDriveFolderContentsIds(String folderId,String query,boolean trashed);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| folderId | \[description...] |
| query    | \[description...] |
| trashed  | \[description...] |

## getGoogleOAuth2AccessToken

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleOAuth2AccessToken(String projectId,String[] scopes);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| projectId | \[description...] |
| scopes    | \[description...] |

## getGoogleOAuth2AccessToken

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleOAuth2AccessToken(String[] scopes);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| scopes   | \[description...] |

## getGoogleOAuth2AccessToken

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleOAuth2AccessToken(String projectId,String serviceAccountEmail,String privateKeyString,String[] scopes);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| projectId           | \[description...] |
| serviceAccountEmail | \[description...] |
| privateKeyString    | \[description...] |
| scopes              | \[description...] |

## getGoogleSharedContactsFiltered

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.getGoogleSharedContactsFiltered(Integer pages,Integer maxPageResults,String searchString,Boolean splitEmails);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| pages          | \[description...] |
| maxPageResults | \[description...] |
| searchString   | \[description...] |
| splitEmails    | \[description...] |

## getGoogleSheetData

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleSheetData(String userId,String spreadsheetId,String> range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| userId               | \[description...] |
| spreadsheetId        | \[description...] |
| range                | \[description...] |
| valueRenderOption    | \[description...] |
| dateTimeRenderOption | \[description...] |

## getGoogleSheetData

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleSheetData(String userId,String spreadsheetId,String range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| userId               | \[description...] |
| spreadsheetId        | \[description...] |
| range                | \[description...] |
| valueRenderOption    | \[description...] |
| dateTimeRenderOption | \[description...] |

## getGoogleSheetData

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleSheetData(String userId,Long dataModelId,String spreadsheetId,String> range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| userId               | \[description...] |
| dataModelId          | \[description...] |
| spreadsheetId        | \[description...] |
| range                | \[description...] |
| valueRenderOption    | \[description...] |
| dateTimeRenderOption | \[description...] |

## getGoogleSheetData

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleSheetData(String userId,Long dataModelId,String spreadsheetId,String range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| userId               | \[description...] |
| dataModelId          | \[description...] |
| spreadsheetId        | \[description...] |
| range                | \[description...] |
| valueRenderOption    | \[description...] |
| dateTimeRenderOption | \[description...] |

## getGoogleSheets

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleSheets(String userId,String spreadsheetId);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| userId        | \[description...] |
| spreadsheetId | \[description...] |

## getGoogleSheets

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGoogleSheets(String spreadsheetId);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| spreadsheetId | \[description...] |

## getGroupMembers

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getGroupMembers(String userId,String groupId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| userId   | \[description...] |
| groupId  | \[description...] |

## getInfoFiles

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return ArrayList type
var risp = utils.getInfoFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| dirId         | \[description...] |
| subFolder     | \[description...] |
| operator      | \[description...] |
| fileName      | \[description...] |
| caseSensitive | \[description...] |

## getInvolvedNotAssignedTasks

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getInvolvedNotAssignedTasks(HashMap pars,String username);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| pars     | \[description...] |
| username | \[description...] |

## getKeysFromCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String[] type
var risp = utils.getKeysFromCache(String keyPrefix);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| keyPrefix | \[description...] |

## getLastSynchronizationDevice

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Timestamp type
var risp = utils.getLastSynchronizationDevice);
```
{% endcode %}

Details

## getModifiedPks

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return ArrayList type
var risp = utils.getModifiedPks(String tableName,String field,Date changedStardDate,Date changedEndDate);
```
{% endcode %}

Details

| Argument         | Description       |
| ---------------- | ----------------- |
| tableName        | \[description...] |
| field            | \[description...] |
| changedStardDate | \[description...] |
| changedEndDate   | \[description...] |

## getPartialResultOnArchiflow

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getPartialResultOnArchiflow(Long dataModelId,Map[] filters,Integer[] archiveIds,Boolean cardsWithAttachedDoc,Integer searchTypes,Map additionalSettings);
```
{% endcode %}

Details

| Argument             | Description       |
| -------------------- | ----------------- |
| dataModelId          | \[description...] |
| filters              | \[description...] |
| archiveIds           | \[description...] |
| cardsWithAttachedDoc | \[description...] |
| searchTypes          | \[description...] |
| additionalSettings   | \[description...] |

## getPartialResultOnBigQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getPartialResultOnBigQuery(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## getPartialResultOnBigQueryWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getPartialResultOnBigQueryWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |
| pars               | \[description...] |

## getPartialResultOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getPartialResultOnGoogleDatastore(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## getPartialResultOnGoogleDatastoreWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getPartialResultOnGoogleDatastoreWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |
| pars               | \[description...] |

## getPartialResultOnGoogleSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getPartialResultOnGoogleSpanner(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## getPartialResultOnGoogleSpannerWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getPartialResultOnGoogleSpannerWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| sql                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |
| pars               | \[description...] |

## getPartialResultOnMongoDb

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getPartialResultOnMongoDb(String where,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| where              | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| pars               | \[description...] |

## getProcessDefinition

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getProcessDefinition(String processDefinitionId,Map params);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| processDefinitionId | \[description...] |
| params              | \[description...] |

## getShortUrl

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getShortUrl(String realUrl);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| realUrl  | \[description...] |

## getUUID

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getUUID);
```
{% endcode %}

Details

## getValueInCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Object type
var risp = utils.getValueInCache(String varName,String alternativeFunctionName);
```
{% endcode %}

Details

| Argument                | Description       |
| ----------------------- | ----------------- |
| varName                 | \[description...] |
| alternativeFunctionName | \[description...] |

## getValueInCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Object type
var risp = utils.getValueInCache(String varName,String alternativeFunctionName,Long expirationTime);
```
{% endcode %}

Details

| Argument                | Description       |
| ----------------------- | ----------------- |
| varName                 | \[description...] |
| alternativeFunctionName | \[description...] |
| expirationTime          | \[description...] |

## getValueInCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Object type
var risp = utils.getValueInCache(String varName);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| varName  | \[description...] |

## getWebContentWithNTLM

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.getWebContentWithNTLM(String url,String contentType,String httpMethod,String bodyRequest,String username,String password,String workstation,String domain,Map settings);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| url         | \[description...] |
| contentType | \[description...] |
| httpMethod  | \[description...] |
| bodyRequest | \[description...] |
| username    | \[description...] |
| password    | \[description...] |
| workstation | \[description...] |
| domain      | \[description...] |
| settings    | \[description...] |

## importBigQueryDataFromGCS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryDataFromGCS(String datasetName,String tableName,String format,String sourceUri,String encoding,String separator);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |
| tableName   | \[description...] |
| format      | \[description...] |
| sourceUri   | \[description...] |
| encoding    | \[description...] |
| separator   | \[description...] |

## importBigQueryDataFromLocalDatasource

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryDataFromLocalDatasource(String datasetName,String tableName,String location,String format,String csvPath,String encoding,String separator,Integer maxBadRecords,Boolean truncate,Boolean deleteSrcFileAfterImport);
```
{% endcode %}

Details

| Argument                 | Description       |
| ------------------------ | ----------------- |
| datasetName              | \[description...] |
| tableName                | \[description...] |
| location                 | \[description...] |
| format                   | \[description...] |
| csvPath                  | \[description...] |
| encoding                 | \[description...] |
| separator                | \[description...] |
| maxBadRecords            | \[description...] |
| truncate                 | \[description...] |
| deleteSrcFileAfterImport | \[description...] |

## importBigQueryThroughStreaming

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryThroughStreaming(String datasetName,String tableName,Object[] objectsForBQ);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| datasetName  | \[description...] |
| tableName    | \[description...] |
| objectsForBQ | \[description...] |

## importDataInCloudSQL

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Long type
var risp = utils.importDataInCloudSQL(String instance,String bucketPath,String dbSchema,Long dataSourceId,String tablename,String where,Integer timeout,String[] columns);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| instance     | \[description...] |
| bucketPath   | \[description...] |
| dbSchema     | \[description...] |
| dataSourceId | \[description...] |
| tablename    | \[description...] |
| where        | \[description...] |
| timeout      | \[description...] |
| columns      | \[description...] |

## importDataInCloudSQL

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return HashMap type
var risp = utils.importDataInCloudSQL(String instance,String bucketPath,String dbSchema,Long dataSourceId,String tablename,String where,String[] columns);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| instance     | \[description...] |
| bucketPath   | \[description...] |
| dbSchema     | \[description...] |
| dataSourceId | \[description...] |
| tablename    | \[description...] |
| where        | \[description...] |
| columns      | \[description...] |

## importFileInCMS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.importFileInCMS(String path,Long destDirId,Long dataSourceId,String tableName);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| path         | \[description...] |
| destDirId    | \[description...] |
| dataSourceId | \[description...] |
| tableName    | \[description...] |

## importFileInCMS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.importFileInCMS(Long sourceDirId,String fileName,Long destDirId,Long dataSourceId,String tableName);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| sourceDirId  | \[description...] |
| fileName     | \[description...] |
| destDirId    | \[description...] |
| dataSourceId | \[description...] |
| tableName    | \[description...] |

## importMultipleDataFromLocalDatasource

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importMultipleDataFromLocalDatasource(String datasetName,String[] tableNames,String location,String format,String dirPath,String[] csvFiles,String encoding,String separator,Integer maxBadRecords,Boolean truncate,Boolean deleteSrcFileAfterImport);
```
{% endcode %}

Details

| Argument                 | Description       |
| ------------------------ | ----------------- |
| datasetName              | \[description...] |
| tableNames               | \[description...] |
| location                 | \[description...] |
| format                   | \[description...] |
| dirPath                  | \[description...] |
| csvFiles                 | \[description...] |
| encoding                 | \[description...] |
| separator                | \[description...] |
| maxBadRecords            | \[description...] |
| truncate                 | \[description...] |
| deleteSrcFileAfterImport | \[description...] |

## insertBigQueryObject

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Long type
var risp = utils.insertBigQueryObject(String datasetName,String tableName,Map obj);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |
| tableName   | \[description...] |
| obj         | \[description...] |

## insertCard

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.insertCard(Long dataModelId,Long panelId,Map vo,Integer archiveId,Map additionalSettings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| dataModelId        | \[description...] |
| panelId            | \[description...] |
| vo                 | \[description...] |
| archiveId          | \[description...] |
| additionalSettings | \[description...] |

## insertCard

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.insertCard(Long dataModelId,Long panelId,Map vo,Integer archiveId,Map additionalSettings,Long actionId);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| dataModelId        | \[description...] |
| panelId            | \[description...] |
| vo                 | \[description...] |
| archiveId          | \[description...] |
| additionalSettings | \[description...] |
| actionId           | \[description...] |

## insertCards

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map[] type
var risp = utils.insertCards(Long dataModelId,Long panelId,Map[] vos,Integer archiveId,Map additionalSettings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| dataModelId        | \[description...] |
| panelId            | \[description...] |
| vos                | \[description...] |
| archiveId          | \[description...] |
| additionalSettings | \[description...] |

## insertCards

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map[] type
var risp = utils.insertCards(Long dataModelId,Long panelId,Map[] vos,Integer archiveId,Map additionalSettings,Long actionId);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| dataModelId        | \[description...] |
| panelId            | \[description...] |
| vos                | \[description...] |
| archiveId          | \[description...] |
| additionalSettings | \[description...] |
| actionId           | \[description...] |

## insertObjectOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.insertObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## insertObjectOnGoogleSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.insertObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## insertObjectOnMongoDb

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.insertObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## insertObjectsOnBigQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.insertObjectsOnBigQuery(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## insertObjectsOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.insertObjectsOnGoogleDatastore(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## insertObjectsOnGoogleDatastoreWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.insertObjectsOnGoogleDatastoreWithSettings(Map[] objs,Long dataModelId,Boolean interruptExecution,Map settings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |

## insertObjectsOnGoogleSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.insertObjectsOnGoogleSpanner(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## invalidateAll

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.invalidateAll);
```
{% endcode %}

Details

## invalidateAllCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.invalidateAllCache(String varName);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| varName  | \[description...] |

## listGoogleCloudStorageObjects

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return GooglePaginatedList type
var risp = utils.listGoogleCloudStorageObjects(String bucketName,Long maxPageResults,Integer pages,String nextPageToken,String prefix,String delimiter);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| bucketName     | \[description...] |
| maxPageResults | \[description...] |
| pages          | \[description...] |
| nextPageToken  | \[description...] |
| prefix         | \[description...] |
| delimiter      | \[description...] |

## listGoogleCloudStorageObjects

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return List type
var risp = utils.listGoogleCloudStorageObjects(String bucketName,String prefix,String delimiter);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |
| prefix     | \[description...] |
| delimiter  | \[description...] |

## matchTensorFlowCsvResults

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.matchTensorFlowCsvResults(Long dirId,Long dataSourceId,String tableName,Map jsObj);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| dirId        | \[description...] |
| dataSourceId | \[description...] |
| tableName    | \[description...] |
| jsObj        | \[description...] |

## maybeStartProcess

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.maybeStartProcess(Long schedId,Boolean forceRunning,Boolean startNextProcesses);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| schedId            | \[description...] |
| forceRunning       | \[description...] |
| startNextProcesses | \[description...] |

## mergeDocx

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.mergeDocx(Long srcDirId,String[] docxNames,Long destDirId,String mergedDocxName,Boolean deleteFilesAfterMerge);
```
{% endcode %}

Details

| Argument              | Description       |
| --------------------- | ----------------- |
| srcDirId              | \[description...] |
| docxNames             | \[description...] |
| destDirId             | \[description...] |
| mergedDocxName        | \[description...] |
| deleteFilesAfterMerge | \[description...] |

## mergeObjectOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.mergeObjectOnGoogleDatastore(Map attributesToSet,String[] attributesToSetToNull,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument              | Description       |
| --------------------- | ----------------- |
| attributesToSet       | \[description...] |
| attributesToSetToNull | \[description...] |
| dataModelId           | \[description...] |
| interruptExecution    | \[description...] |

## mergeObjectOnGoogleSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.mergeObjectOnGoogleSpanner(Map attributesToSet,String[] attributesToSetToNull,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument              | Description       |
| --------------------- | ----------------- |
| attributesToSet       | \[description...] |
| attributesToSetToNull | \[description...] |
| dataModelId           | \[description...] |
| interruptExecution    | \[description...] |

## modifyGoogleCalendarEvent

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return CalendarEvent type
var risp = utils.modifyGoogleCalendarEvent(String calendarEventId,String title,Date beginDate,Date endDate);
```
{% endcode %}

Details

| Argument        | Description       |
| --------------- | ----------------- |
| calendarEventId | \[description...] |
| title           | \[description...] |
| beginDate       | \[description...] |
| endDate         | \[description...] |

## modifyGoogleCalendarEventWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return CalendarEvent type
var risp = utils.modifyGoogleCalendarEventWithSettings(String calendarEventId,String title,Date beginDate,Date endDate,String description,String location,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

Details

| Argument        | Description       |
| --------------- | ----------------- |
| calendarEventId | \[description...] |
| title           | \[description...] |
| beginDate       | \[description...] |
| endDate         | \[description...] |
| description     | \[description...] |
| location        | \[description...] |
| creatorEmail    | \[description...] |
| attendeeEmails  | \[description...] |

## modifyGoogleDriveFileParents

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.modifyGoogleDriveFileParents(String fileId,String parentsToAdd,String parentsToRemove);
```
{% endcode %}

Details

| Argument        | Description       |
| --------------- | ----------------- |
| fileId          | \[description...] |
| parentsToAdd    | \[description...] |
| parentsToRemove | \[description...] |

## modifyGoogleDriveFileParents

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.modifyGoogleDriveFileParents(String userId,String fileId,String parentsToAdd,String parentsToRemove);
```
{% endcode %}

Details

| Argument        | Description       |
| --------------- | ----------------- |
| userId          | \[description...] |
| fileId          | \[description...] |
| parentsToAdd    | \[description...] |
| parentsToRemove | \[description...] |

## moveGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.moveGoogleDriveFile(String fileId,String newParent,boolean addToRevision);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| fileId        | \[description...] |
| newParent     | \[description...] |
| addToRevision | \[description...] |

## moveGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.moveGoogleDriveFile(String userId,String fileId,String newParents);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| userId     | \[description...] |
| fileId     | \[description...] |
| newParents | \[description...] |

## moveGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.moveGoogleDriveFile(String userId,String fileId,String newParent,boolean addToRevision);
```
{% endcode %}

Details

| Argument      | Description       |
| ------------- | ----------------- |
| userId        | \[description...] |
| fileId        | \[description...] |
| newParent     | \[description...] |
| addToRevision | \[description...] |

## moveGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.moveGoogleDriveFile(String fileId,String newParents);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| fileId     | \[description...] |
| newParents | \[description...] |

## patchGoogleDriveFileProperty

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.patchGoogleDriveFileProperty(String userId,String fileId,String key,String value,String visibility);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| userId     | \[description...] |
| fileId     | \[description...] |
| key        | \[description...] |
| value      | \[description...] |
| visibility | \[description...] |

## patchGoogleDriveFileProperty

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.patchGoogleDriveFileProperty(String fileId,String key,String value,String visibility);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| fileId     | \[description...] |
| key        | \[description...] |
| value      | \[description...] |
| visibility | \[description...] |

## prepareStripePayment

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.prepareStripePayment(String apiKey,String publicKey,Long priceWithCents,String currency,String customerId);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| apiKey         | \[description...] |
| publicKey      | \[description...] |
| priceWithCents | \[description...] |
| currency       | \[description...] |
| customerId     | \[description...] |

## recoverGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.recoverGoogleDriveFile(String userId,String fileId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| userId   | \[description...] |
| fileId   | \[description...] |

## recoverGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.recoverGoogleDriveFile(String fileId);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| fileId   | \[description...] |

## reinsertElements

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return int type
var risp = utils.reinsertElements(String companyId,Long actionId,String queueName,String status,String id);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| companyId | \[description...] |
| actionId  | \[description...] |
| queueName | \[description...] |
| status    | \[description...] |
| id        | \[description...] |

## removeGoogleDriveFilePermissions

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeGoogleDriveFilePermissions(String userId,String fileId,String emailUser);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| userId    | \[description...] |
| fileId    | \[description...] |
| emailUser | \[description...] |

## removeGoogleDriveFilePermissions

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeGoogleDriveFilePermissions(String fileId,String emailUser);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| fileId    | \[description...] |
| emailUser | \[description...] |

## removeValueInCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeValueInCache(String varName);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| varName  | \[description...] |

## removeValuesFromCache

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeValuesFromCache(String keyPrefix);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| keyPrefix | \[description...] |

## rewriteGoogleCloudStorageObject

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.rewriteGoogleCloudStorageObject(String sourceBucketName,String sourceObjectName,Long sourceObjectVersion,String destinationBucketName,String destinationObjectName);
```
{% endcode %}

Details

| Argument              | Description       |
| --------------------- | ----------------- |
| sourceBucketName      | \[description...] |
| sourceObjectName      | \[description...] |
| sourceObjectVersion   | \[description...] |
| destinationBucketName | \[description...] |
| destinationObjectName | \[description...] |

## scaleJpgFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.scaleJpgFile(Long srcJpgDirId,String srcJpgFileName,Long destDirId,String destFileName,Long maxWidth,Long maxHeight);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| srcJpgDirId    | \[description...] |
| srcJpgFileName | \[description...] |
| destDirId      | \[description...] |
| destFileName   | \[description...] |
| maxWidth       | \[description...] |
| maxHeight      | \[description...] |

## scaleJpgFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.scaleJpgFile(Long srcJpgDirId,String srcJpgFileName,Long destDirId,String destFileName,Long scale);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| srcJpgDirId    | \[description...] |
| srcJpgFileName | \[description...] |
| destDirId      | \[description...] |
| destFileName   | \[description...] |
| scale          | \[description...] |

## searchInGoogleDrive

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return GooglePaginatedList type
var risp = utils.searchInGoogleDrive(String userId,Integer maxPageResults,Integer pages,String nextPageToken,String folderId,Boolean recursive,String query,Boolean trashed);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| userId         | \[description...] |
| maxPageResults | \[description...] |
| pages          | \[description...] |
| nextPageToken  | \[description...] |
| folderId       | \[description...] |
| recursive      | \[description...] |
| query          | \[description...] |
| trashed        | \[description...] |

## searchInGoogleDrive

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return GooglePaginatedList type
var risp = utils.searchInGoogleDrive(Integer maxPageResults,Integer pages,String nextPageToken,String folderId,Boolean recursive,String query,Boolean trashed);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| maxPageResults | \[description...] |
| pages          | \[description...] |
| nextPageToken  | \[description...] |
| folderId       | \[description...] |
| recursive      | \[description...] |
| query          | \[description...] |
| trashed        | \[description...] |

## sendPushNotification

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendPushNotification(String appId,String[] userCodeIds,String title,String shortMessage,Long actionId,String json,Long badgeNr);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| appId        | \[description...] |
| userCodeIds  | \[description...] |
| title        | \[description...] |
| shortMessage | \[description...] |
| actionId     | \[description...] |
| json         | \[description...] |
| badgeNr      | \[description...] |

## sendPushNotificationWithOptions

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendPushNotificationWithOptions(String appId,String[] userCodeIds,String title,String shortMessage,Long actionId,String json,Long badgeNr,Map rootOptions,Map dataOptions,Map notificationOptions);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| appId               | \[description...] |
| userCodeIds         | \[description...] |
| title               | \[description...] |
| shortMessage        | \[description...] |
| actionId            | \[description...] |
| json                | \[description...] |
| badgeNr             | \[description...] |
| rootOptions         | \[description...] |
| dataOptions         | \[description...] |
| notificationOptions | \[description...] |

## sendSinglePushNotification

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendSinglePushNotification(String appId,String firebaseId,String title,String shortMessage,Long actionId,String json,Long badgeNr,Map rootOptions,Map dataOptions,Map notificationOptions);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| appId               | \[description...] |
| firebaseId          | \[description...] |
| title               | \[description...] |
| shortMessage        | \[description...] |
| actionId            | \[description...] |
| json                | \[description...] |
| badgeNr             | \[description...] |
| rootOptions         | \[description...] |
| dataOptions         | \[description...] |
| notificationOptions | \[description...] |

## sendSmsMessage

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendSmsMessage(String fromPhoneNr,String toPhoneNr,String text,Boolean logMessage);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| fromPhoneNr | \[description...] |
| toPhoneNr   | \[description...] |
| text        | \[description...] |
| logMessage  | \[description...] |

## sendTensorFlowCsvFromCsv

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendTensorFlowCsvFromCsv(String csvFilePath,Boolean includeFirstRow,Boolean includeRowNum,int resultValuesNr,Long dirId,String topic,String cmd,Long pkIndex,Map jsObj);
```
{% endcode %}

Details

| Argument        | Description       |
| --------------- | ----------------- |
| csvFilePath     | \[description...] |
| includeFirstRow | \[description...] |
| includeRowNum   | \[description...] |
| resultValuesNr  | \[description...] |
| dirId           | \[description...] |
| topic           | \[description...] |
| cmd             | \[description...] |
| pkIndex         | \[description...] |
| jsObj           | \[description...] |

## sendTensorFlowCsvFromSqlQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendTensorFlowCsvFromSqlQuery(String sql,Long dataSourceId,Long fromRow,Long maxRowsToRead,String fieldName,Integer resultValuesNr,Long dirId,String fileName,Map jsObj);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| sql            | \[description...] |
| dataSourceId   | \[description...] |
| fromRow        | \[description...] |
| maxRowsToRead  | \[description...] |
| fieldName      | \[description...] |
| resultValuesNr | \[description...] |
| dirId          | \[description...] |
| fileName       | \[description...] |
| jsObj          | \[description...] |

## sendWhatsappMessage

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendWhatsappMessage(String toNumber,String message,String bucketName,String fileName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| toNumber   | \[description...] |
| message    | \[description...] |
| bucketName | \[description...] |
| fileName   | \[description...] |

## sendWhatsappMessage

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendWhatsappMessage(String accountId,String secretKey,String fromNr,String toNumber,String message,String bucketName,String fileName);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| accountId  | \[description...] |
| secretKey  | \[description...] |
| fromNr     | \[description...] |
| toNumber   | \[description...] |
| message    | \[description...] |
| bucketName | \[description...] |
| fileName   | \[description...] |

## sendWhatsappMessage

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendWhatsappMessage(String toNumber,String message,String publicUrl);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| toNumber  | \[description...] |
| message   | \[description...] |
| publicUrl | \[description...] |

## sendWhatsappMessage

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return String type
var risp = utils.sendWhatsappMessage(String accountId,String secretKey,String fromNr,String toNumber,String message,String publicUrl);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| accountId | \[description...] |
| secretKey | \[description...] |
| fromNr    | \[description...] |
| toNumber  | \[description...] |
| message   | \[description...] |
| publicUrl | \[description...] |

## setBigQueryDataset

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setBigQueryDataset(String bigQueryDataset);
```
{% endcode %}

Details

| Argument        | Description       |
| --------------- | ----------------- |
| bigQueryDataset | \[description...] |

## setBlockSize

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setBlockSize(int blockSize);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| blockSize | \[description...] |

## setDatasetId

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDatasetId(String datasetId);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| datasetId | \[description...] |

## setDatastoreNamespace

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDatastoreNamespace(String namespace);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| namespace | \[description...] |

## setGoogleClientId

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleClientId(String id);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| id       | \[description...] |

## setGoogleClientSecret

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleClientSecret(String pwd);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| pwd      | \[description...] |

## setGoogleCloudStorageBucketVersioning

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return FileContainer type
var risp = utils.setGoogleCloudStorageBucketVersioning(String bucketName,Boolean versioning);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |
| versioning | \[description...] |

## setGoogleDriveFileAttributes

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFileAttributes(String userId,String fileId,FileAttributes fileAttributes);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| userId         | \[description...] |
| fileId         | \[description...] |
| fileAttributes | \[description...] |

## setGoogleDriveFileAttributes

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFileAttributes(String fileId,FileAttributes fileAttributes);
```
{% endcode %}

Details

| Argument       | Description       |
| -------------- | ----------------- |
| fileId         | \[description...] |
| fileAttributes | \[description...] |

## setGoogleDriveFilePermissions

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFilePermissions(String userId,String fileId,String type,String value,String role,String> additionalRoles,boolean sendNotifications,String message);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| userId            | \[description...] |
| fileId            | \[description...] |
| type              | \[description...] |
| value             | \[description...] |
| role              | \[description...] |
| additionalRoles   | \[description...] |
| sendNotifications | \[description...] |
| message           | \[description...] |

## setGoogleDriveFilePermissions

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFilePermissions(String fileId,String type,String value,String role,String> additionalRoles,boolean sendNotifications,String message);
```
{% endcode %}

Details

| Argument          | Description       |
| ----------------- | ----------------- |
| fileId            | \[description...] |
| type              | \[description...] |
| value             | \[description...] |
| role              | \[description...] |
| additionalRoles   | \[description...] |
| sendNotifications | \[description...] |
| message           | \[description...] |

## setGooglePrivateKeyString

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGooglePrivateKeyString(String key);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| key      | \[description...] |

## setGoogleServiceAccountEmail

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleServiceAccountEmail(String email);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| email    | \[description...] |

## setGoogleTokenResponse

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleTokenResponse(String token);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| token    | \[description...] |

## setPublicLink

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setPublicLink(String bucketName,String objectName,Boolean publicLink);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| bucketName | \[description...] |
| objectName | \[description...] |
| publicLink | \[description...] |

## setStartIndex

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setStartIndex(int startIndex);
```
{% endcode %}

Details

| Argument   | Description       |
| ---------- | ----------------- |
| startIndex | \[description...] |

## setTaskAssignee

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setTaskAssignee(String taskId,String assignee);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| taskId   | \[description...] |
| assignee | \[description...] |

## sharedContatctsSync

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sharedContatctsSync);
```
{% endcode %}

Details

## startActivitiProcess

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.startActivitiProcess(String appId,String processDefinitionId,Map params,Map processVariables);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| appId               | \[description...] |
| processDefinitionId | \[description...] |
| params              | \[description...] |
| processVariables    | \[description...] |

## unzipFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.unzipFile(Long zipDirId,String zipFileName,String serverFileSystemDir);
```
{% endcode %}

Details

| Argument            | Description       |
| ------------------- | ----------------- |
| zipDirId            | \[description...] |
| zipFileName         | \[description...] |
| serverFileSystemDir | \[description...] |

## updateBigQueryObject

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Long type
var risp = utils.updateBigQueryObject(String datasetName,String tableName,Map obj,String[] pks);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| datasetName | \[description...] |
| tableName   | \[description...] |
| obj         | \[description...] |
| pks         | \[description...] |

## updateCard

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.updateCard(Long dataModelId,Long panelId,Map vo);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| dataModelId | \[description...] |
| panelId     | \[description...] |
| vo          | \[description...] |

## updateCards

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map[] type
var risp = utils.updateCards(Long dataModelId,Long panelId,Map[] vos);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| dataModelId | \[description...] |
| panelId     | \[description...] |
| vos         | \[description...] |

## updateFileInCMS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateFileInCMS(String uuid,String path);
```
{% endcode %}

Details

| Argument | Description       |
| -------- | ----------------- |
| uuid     | \[description...] |
| path     | \[description...] |

## updateFileInCMS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateFileInCMS(String uuid,Long sourceDirId,String fileName);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| uuid        | \[description...] |
| sourceDirId | \[description...] |
| fileName    | \[description...] |

## updateGoogleContact

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Contact type
var risp = utils.updateGoogleContact(String contactId,String name,String surname,String email,String phone,Boolean shared);
```
{% endcode %}

Details

| Argument  | Description       |
| --------- | ----------------- |
| contactId | \[description...] |
| name      | \[description...] |
| surname   | \[description...] |
| email     | \[description...] |
| phone     | \[description...] |
| shared    | \[description...] |

## updateGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.updateGoogleDriveFile(String userId,String fileId,String title,String description,String mimeType);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| userId      | \[description...] |
| fileId      | \[description...] |
| title       | \[description...] |
| description | \[description...] |
| mimeType    | \[description...] |

## updateGoogleDriveFile

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.updateGoogleDriveFile(String fileId,String title,String description,String mimeType);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| fileId      | \[description...] |
| title       | \[description...] |
| description | \[description...] |
| mimeType    | \[description...] |

## updateGoogleDriveFileFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.updateGoogleDriveFileFromFS(String fileId,String fsPath,boolean deleteFsFile,boolean newRevision);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| fileId       | \[description...] |
| fsPath       | \[description...] |
| deleteFsFile | \[description...] |
| newRevision  | \[description...] |

## updateGoogleDriveFileFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.updateGoogleDriveFileFromFS(String userId,String fileId,String fsPath,boolean deleteFsFile,boolean newRevision);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| userId       | \[description...] |
| fileId       | \[description...] |
| fsPath       | \[description...] |
| deleteFsFile | \[description...] |
| newRevision  | \[description...] |

## updateObjectOnBigQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.updateObjectOnBigQuery(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## updateObjectOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.updateObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## updateObjectOnGoogleSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.updateObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## updateObjectOnMongoDb

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Map type
var risp = utils.updateObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## updateObjectsOnBigQuery

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.updateObjectsOnBigQuery(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## updateObjectsOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.updateObjectsOnGoogleDatastore(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## updateObjectsOnGoogleDatastoreWitSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.updateObjectsOnGoogleDatastoreWitSettings(Map[] objs,Long dataModelId,Boolean interruptExecution,Map settings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |

## updateObjectsOnGoogleDatastoreWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.updateObjectsOnGoogleDatastoreWithSettings(Map[] objs,Long dataModelId,Boolean interruptExecution,Map settings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |

## updateObjectsOnGoogleSpanner

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.updateObjectsOnGoogleSpanner(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## updateRangeGoogleSheet

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Integer type
var risp = utils.updateRangeGoogleSheet(String userId,String spreadsheetId,String range,String valueInputOption,Object[][] vos);
```
{% endcode %}

Details

| Argument         | Description       |
| ---------------- | ----------------- |
| userId           | \[description...] |
| spreadsheetId    | \[description...] |
| range            | \[description...] |
| valueInputOption | \[description...] |
| vos              | \[description...] |

## uploadAndRenameGoogleDriveFileFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadAndRenameGoogleDriveFileFromFS(String userId,String fsPath,String parentId,String fileName,boolean deleteFsFile);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| userId       | \[description...] |
| fsPath       | \[description...] |
| parentId     | \[description...] |
| fileName     | \[description...] |
| deleteFsFile | \[description...] |

## uploadAndRenameGoogleDriveFileFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadAndRenameGoogleDriveFileFromFS(String fsPath,String parentId,String fileName,boolean deleteFsFile);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| fsPath       | \[description...] |
| parentId     | \[description...] |
| fileName     | \[description...] |
| deleteFsFile | \[description...] |

## uploadAndRenameGoogleDriveFileInNamedFolderFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(String userId,String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,String fileName,boolean deleteFsFile);
```
{% endcode %}

Details

| Argument                | Description       |
| ----------------------- | ----------------- |
| userId                  | \[description...] |
| fsPath                  | \[description...] |
| baseFolderId            | \[description...] |
| folderName              | \[description...] |
| createFolderIfNotExists | \[description...] |
| fileName                | \[description...] |
| deleteFsFile            | \[description...] |

## uploadAndRenameGoogleDriveFileInNamedFolderFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,String fileName,boolean deleteFsFile);
```
{% endcode %}

Details

| Argument                | Description       |
| ----------------------- | ----------------- |
| fsPath                  | \[description...] |
| baseFolderId            | \[description...] |
| folderName              | \[description...] |
| createFolderIfNotExists | \[description...] |
| fileName                | \[description...] |
| deleteFsFile            | \[description...] |

## uploadArchiflowDocument

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return Boolean type
var risp = utils.uploadArchiflowDocument(Long dirId,String fileNameSrc,String cardId,String fileName,String documentTitle,Map additionalSettings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| dirId              | \[description...] |
| fileNameSrc        | \[description...] |
| cardId             | \[description...] |
| fileName           | \[description...] |
| documentTitle      | \[description...] |
| additionalSettings | \[description...] |

## uploadGoogleCloudStorageObjectFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadGoogleCloudStorageObjectFromFS(String fsPath,String bucketName,String objectName,Boolean deleteFsFile);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| fsPath       | \[description...] |
| bucketName   | \[description...] |
| objectName   | \[description...] |
| deleteFsFile | \[description...] |

## uploadGoogleCloudStorageObjectFromString

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadGoogleCloudStorageObjectFromString(String textContent,String bucketName,String objectName,String contentType);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| textContent | \[description...] |
| bucketName  | \[description...] |
| objectName  | \[description...] |
| contentType | \[description...] |

## uploadGoogleCloudStoragePublicObjectFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadGoogleCloudStoragePublicObjectFromFS(String fsPath,String bucketName,String objectName,Boolean deleteFsFile);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| fsPath       | \[description...] |
| bucketName   | \[description...] |
| objectName   | \[description...] |
| deleteFsFile | \[description...] |

## uploadGoogleCloudStoragePublicObjectFromString

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadGoogleCloudStoragePublicObjectFromString(String textContent,String bucketName,String objectName,String contentType);
```
{% endcode %}

Details

| Argument    | Description       |
| ----------- | ----------------- |
| textContent | \[description...] |
| bucketName  | \[description...] |
| objectName  | \[description...] |
| contentType | \[description...] |

## uploadGoogleDriveFileFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadGoogleDriveFileFromFS(String fsPath,String parentId,boolean deleteFsFile);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| fsPath       | \[description...] |
| parentId     | \[description...] |
| deleteFsFile | \[description...] |

## uploadGoogleDriveFileFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadGoogleDriveFileFromFS(String userId,String fsPath,String parentId,boolean deleteFsFile);
```
{% endcode %}

Details

| Argument     | Description       |
| ------------ | ----------------- |
| userId       | \[description...] |
| fsPath       | \[description...] |
| parentId     | \[description...] |
| deleteFsFile | \[description...] |

## uploadGoogleDriveFileInNamedFolderFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadGoogleDriveFileInNamedFolderFromFS(String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,boolean deleteFsFile);
```
{% endcode %}

Details

| Argument                | Description       |
| ----------------------- | ----------------- |
| fsPath                  | \[description...] |
| baseFolderId            | \[description...] |
| folderName              | \[description...] |
| createFolderIfNotExists | \[description...] |
| deleteFsFile            | \[description...] |

## uploadGoogleDriveFileInNamedFolderFromFS

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return File type
var risp = utils.uploadGoogleDriveFileInNamedFolderFromFS(String userId,String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,boolean deleteFsFile);
```
{% endcode %}

Details

| Argument                | Description       |
| ----------------------- | ----------------- |
| userId                  | \[description...] |
| fsPath                  | \[description...] |
| baseFolderId            | \[description...] |
| folderName              | \[description...] |
| createFolderIfNotExists | \[description...] |
| deleteFsFile            | \[description...] |

## upsertObjectOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.upsertObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| obj                | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## upsertObjectsOnGoogleDatastore

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.upsertObjectsOnGoogleDatastore(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |

## upsertObjectsOnGoogleDatastoreWithSettings

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.upsertObjectsOnGoogleDatastoreWithSettings(Map[] objs,Long dataModelId,Boolean interruptExecution,Map settings);
```
{% endcode %}

Details

| Argument           | Description       |
| ------------------ | ----------------- |
| objs               | \[description...] |
| dataModelId        | \[description...] |
| interruptExecution | \[description...] |
| settings           | \[description...] |

## validateAlexaRequest

Syntax

{% code overflow="wrap" lineNumbers="true" %}
```js
//return boolean type
var risp = utils.validateAlexaRequest(String signingCertificateChainUrl,String baseEncoded64Signature,String requestBody);
```
{% endcode %}

Details | Argument | Description | | -- | -- | | signingCertificateChainUrl | \[description...] | | baseEncoded64Signature | \[description...] | | requestBody | \[description...] |

End
