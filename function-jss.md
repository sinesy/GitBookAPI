# Function JSS

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

## Convert a javascript object to its JSON representation

**Syntax**

```javascript
var json = utils.getJSONString(obj);
```

**Details**

| Argument | Description                                             |
| -------- | ------------------------------------------------------- |
| obj      | javascript object to convert to its JSON representation |

## Add an attribute (e.g. "member of") to the entry identified by "filterDN"

**Syntax**

```javascript
var num = utils.addAttribute(host, port, filterDN, ldapUsername, ldapPassword, attributeNameToAdd, attributeValueToAdd);
```

**Details**

| Argument | Description                                              |
| -------- | -------------------------------------------------------- |
| host     | LDAP host                                                |
| port     | LDAP port (optional: if not specified, 389 will be used) |

```
 filterDN - base DN to apply as a filter
```

| Argument            | Description                                                        |
| ------------------- | ------------------------------------------------------------------ |
| ldapUsername        | username to use to authenticate to the LDAP server                 |
| ldapPassword        | password to use to authenticate to the LDAP server                 |
| attributeNameToAdd  | attribute name to add to every entry matching the search criteria  |
| attributeValueToAdd | attribute value to add to every entry matching the search criteria |

```
Returns the number of entries found and updated
```

## Remove an attribute (e.g. "memberOf") from the entry identified by "filterDN"

**Syntax**

```javascript
utils.removeAttribute(host, port, filterDN, ldapUsername, ldapPassword, attributeNameToRemove, attributeValueToRemove);
```

**Details**

| Argument | Description                                              |
| -------- | -------------------------------------------------------- |
| host     | LDAP host                                                |
| port     | LDAP port (optional: if not specified, 389 will be used) |

```
 filterDN - base DN to apply as a filter
```

| Argument               | Description                                                             |
| ---------------------- | ----------------------------------------------------------------------- |
| ldapUsername           | username to use to authenticate to the LDAP server                      |
| ldapPassword           | password to use to authenticate to the LDAP server                      |
| attributeNameToRemove  | attribute name to remove from every entry matching the search criteria  |
| attributeValueToRemove | attribute value to remove from every entry matching the search criteria |

```
Returns number of entries found and updated
```

## Create entry

```
utils.createEntry(String host,Integer port,String ldapUsername,String ldapPassword,String baseDN,String entryName,String entryType,String entryDescription,String[] attributeNamesValues)
```

| Argument             |                                                          |
| -------------------- | -------------------------------------------------------- |
| host                 | LDAP host                                                |
| port                 | LDAP port (optional: if not specified, 389 will be used) |
| ldapUsername         | username to use to authenticate to the LDAP server       |
| ldapPassword         | password to use to authenticate to the LDAP server       |
| baseDN               | base DN to apply as a filter                             |
| entryName            |                                                          |
| entryType            |                                                          |
| entryDescription     |                                                          |
| attributeNamesValues |                                                          |

## Create group

```
utils.createGroup(String host,Integer port,String ldapUsername,String ldapPassword,String baseDN,String folderDN,String groupName,String[] additionalAttributeNamesValues)
```

**tails**

| Argument | Description                                              |
| -------- | -------------------------------------------------------- |
| host     | LDAP host                                                |
| port     | LDAP port (optional: if not specified, 389 will be used) |

| ldapUsername                  | username to use to authenticate to the LDAP server |
| ----------------------------- | -------------------------------------------------- |
| ldapPassword                  | password to use to authenticate to the LDAP server |
| baseDN                        |                                                    |
| folderDN                      |                                                    |
| groupName                     |                                                    |
| additionalAttributeNameValues |                                                    |

## Convert a list of javascript objects into its JSON representation and embed it to a “Ext.grid.GridPanel like” data representation

based on “valueObjectList”, “resultSetLength” and “moreRows” attributes

**Syntax**

```javascript
var json = utils.getListResponse(jsObjectsList, resultSetLength, moreRows);
```

**Details**

| Argument        | Description                                          |
| --------------- | ---------------------------------------------------- |
| jsObjectsList   | list of javascript objects to convert to JSON format |
| resultSetLenght | a number : list of objects (can be list.length)      |
| moreRows        | flag used to specify                                 |
| _return value_  | returns a JSON content compatible with Ext grids     |

## Format Number

```
utils.formatNumber(Number value,Boolean grouping,String groupingSymbol,Number decimals,String decimalSymbol)
```

| Argument       | Description                                                 |
| -------------- | ----------------------------------------------------------- |
| value          |                                                             |
| grouping       |                                                             |
| groupingSymbol |                                                             |
| decimals       | number of decimals that the final number must be rounded to |
| decimalSymbol  |                                                             |

## create an URL which can be invoked later from another client <a href="#createallowedurl" id="createallowedurl"></a>

(e.g. from an email message as a link) and which will be accepted by Platform, since it contains an authentication token; this URL can be used to invoke a server-side javascript action identified by the specific action id. The URL will show the approve.jsp web page containing the Accept/Reject buttons used to confirm or deny an action invoked when pressing the related button.

**Syntax**

```javascript
createAllowedUrl(baseUrl, actionId, aName, aValue, rName, rValue, params, expirationDays, maxTimes, message);
```

**Details**

| Argument       | Description                                                                                                                                                                    |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| baseUrl        | base URL to pass, related to the host name and web context; it will represent the first part of the final URL (e.g. [http://host:port/platform/](http://host/:port/platform/)) |
| actionId       | action identifier to execute when pressing the Accept/Reject button on the web page opened when clicking of the returning URL                                                  |
| aName          | parameter name related to the accept event, i.e. parameter passed to the js action when pressing the Accept button                                                             |
| aValue         | parameter value related to the accept event, i.e. parameter value passed to the js action when pressing the Accept button                                                      |
| rName          | parameter name related to the reject event, i.e. parameter passed to the js action when pressing the Reject button                                                             |
| rValue         | parameter name related to the accept event, i.e. parameter value passed to the js action when pressing the Reject button                                                       |
| params         | additional parameters to pass to the js action, for instance to identify a specific record to work with                                                                        |
| expirationDays | optional parameter (can be set to 0); if set, it represents the maximum number of days the URL is valid, starting from the URL creation date                                   |
| maxTimes       | it represents the maximum number of times the URL can be used before it expires                                                                                                |
| message        | text to show on the approve.jsp web page, just above the Accept/Reject buttons.                                                                                                |

## Create a link to access the web app from an email or other external media

In case you need to create a dynamic link which allows you to access a Platform web application, linked to a specific username, you can use this method:

```javascript
utils.createAllowedLink(
  expirationDays, // expirationDays = 0 for no expiration
  maxTimes
);
```

The required arguments are:

* **expirationDays** – optional: it defines the validity of this link, expressed as number of days; if not specified, the link is always valid
* **maxTimes** – optional: it defines the validity of this link, expressed as the number of times it can be used; after reaching this number, the link cannot be used anymore; if not specified, the link is always valid.

This method returns a token, which is a dynamically generated text you can include when logging on the web app.

Note: the link can become invalid either if it reaches the expiration time or when it has been used the max number of times.

**Important note:** it is strongly recommended to always specify at least one of the 2 arguments, so that the link will expire: this will make your Platform web application more secure.

## Create a link to access the web app from an email or other external media with additional data

In case you need to create a dynamic link which allows you to access a Platform web application, linked to a specific username and you also need to pass forward additional data, you can use this method:

```javascript
var token = utils.createAllowedLinkWithRtk(
  expirationDays, // expirationDays = 0 for no expiration
  maxTimes,
  rtk
);
```

The required arguments are:

* **expirationDays** – optional: it defines the validity of this link, expressed as number of days; if not specified, the link is always valid
* **maxTimes** – optional: it defines the validity of this link, expressed as the number of times it can be used; after reaching this number, the link cannot be used anymore; if not specified, the link is always valid
* **rtk** - additional data to include, expressed as a String. You can get this content through the **getEncodedRtk.**

This method returns a token, which is a dynamically generated text you can include when logging on the web app.

Note: the link can become invalid either if it reaches the expiration time or when it has been used the max number of times.

**Important note:** it is strongly recommended to always specify at least one of the 2 first arguments, so that the link will expire: this will make your Platform web application more secure.

## Generate a report starting from a .jasper report template and save it to the server file system, in the specified path.

**Syntax**

```javascript
var json = utils.saveDocument(
    reportName,
    dirReports, 
    datastoreId, 
    compId,r
    eportFormat, 
    reportParams,
    savePath
);
```

**Details**

| **Argument** | Description                                                                                                                                                          |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| reportName   | .jasper report name                                                                                                                                                  |
| dirReports   | optional folder where the .jasper file is located; this is a relative path and it is always contained within the subfolder \<application-context-path>/reports/      |
| datastoreId  | optional data source id used by the .jasper template to read data from the database                                                                                  |
| compId       | optional value: business component id to use to fill in the report                                                                                                   |
| reportFormat | report format to use when creating the report; allowed values are: PDF, XLS, DOCX                                                                                    |
| reportParams | input parameters required by the report template                                                                                                                     |
| savePath     | path where the generated report will be saved; it must includes the file name error message, in case of errors; "" if the generation has been successfully completed |

It returns a JSON string containing:\
{ "success": true }\
if the report has been created successfully, or a JSON string having this format otherwise:\
{ "success": false, "message": "..."}

**Example**

and the database schema to pass forward to the report is the Platform repository schema:

```javascript
var reportParams = new Object();

reportParams.paramxyz = "...";
...
var json = utils.saveDocument(
    "mytemplate.jasper",
    null, 
    null, 
    null,
    "PDF", 
    reportParams,
    "pathwheresavingthepdf/myreport.pdf"
);
utils.setReturnValue('{ "success": true, "fileName": "myreport.pdf", "dirId": ' + dirId + ' }');
```

If you want showing the report you can create a javascript action

```javascript
if(response!==null && response!=='') {
    var risp = Ext.decode(response);
    if(risp.success) {
        mydesktop.createWindow({
          title: 'uploadfilesgrid.preview.text',
          width: 800,
          height: 600,
          manager: mydesktop.getManager(),
          modal: true,
          plain: true,
          layout: 'fit',
          items: 
            new Ext.Panel({
              html: '<iframe src="' + contextPath + 
                '/filemanager/downloadfile?dirId='+ risp.dirId + '&fileName='+ risp.fileName +
                '&appId='+applicationId+'&applicationId='+applicationId+
                '&preview=true" width="100%" height="100%"/>'
            })
        }).show();    
    } else {
       showMessageDialog("Error",risp.msg,function() {}, true);
    }
}
```

## How to print a report directly to a printer

**Syntax**

```javascript
var response = utils.printDocument( printerName, copies, mediaSize, printParams, reportName,dirReports, datastoreId, reportFormat, reportParams);
```

**Details**

| Argument    | Description                                                                                    |
| ----------- | ---------------------------------------------------------------------------------------------- |
| printerName | printer name                                                                                   |
| copies      | number of copies; e.g. 1                                                                       |
| mediaSize   | dimernsion of the paper, expressed as 1-10 values (i.e. A0-A10); can be null                   |
| printParams | js object containing parameters specific for the selected printer; if not needed, set it to {} |
| reportName  | .jasper file name, which must be stored with the folder                                        |

```
 /reports
```

| Argument     | Description                                                                                                                                                                                                                                                                                                                                                                       |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dirReports   | optional subfolder where the .jasper file is located; it is a subfolder of the one described above; if not needed, you have to set it to ‘’                                                                                                                                                                                                                                       |
| datastoreId  | optional, related to the data source used by the .jasper report to get data from the database; if the default repository is used, then set it to null                                                                                                                                                                                                                             |
| reportFormat | report format, e.g. PDF                                                                                                                                                                                                                                                                                                                                                           |
| reportParams | input parameters required vy the .jasper report file; if not needed, set it to {}                                                                                                                                                                                                                                                                                                 |
| result       | outcome; it could contain an error message if no printers has been configured or if the specified printer name has not been recognized or if the .jasper file is not located in the required path or in case of a generic print error. If the report has been successfully genrated and it has been sent to the printer spooler, then the ""Report printed." message is sent back |

## Get Print services

```
utils.getPrintServices
```

## Encode Password

```
utils.encodePassword(String password)
```

| Argument | Description       |
| -------- | ----------------- |
| password | encoding password |

## Decode Password

```
utils.decodePassword(String encriptedpassword)
```

| Argument          | Description |
| ----------------- | ----------- |
| encriptedpassword |             |

## Get conversation

```
utils.getConversation(Long conversationId)
```

| Argument      | Description                                                                                                                                       |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| convesationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |

## Get conversation from tag

```
utils.getConversationFromTag(String messageTag)
```

| Argument   | Description                                                                                                        |
| ---------- | ------------------------------------------------------------------------------------------------------------------ |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history. |

### &#x20;Read a signed PDF file and extract data coming from the embedded certificate <a href="#getcsvcontent" id="getcsvcontent"></a>

The source PDF file is identified starting from the source directory id + fileName.The specified PDF file is signed file, i.e. it contains a certificate; this certificate is then extracted and saved in the destination directory. The certificate file, if recognized with a MIME type, is renamed to a name having the original name + its real extension. Otherwise, it is saved with the original source file name.**Syntax**var obj = utils.getCertMessageFromPdf(Long srcDirectoryId,Long destDirectoryId,String fileName);**Details**

| Argument        | Description                                                                                                        |
| --------------- | ------------------------------------------------------------------------------------------------------------------ |
| srcDirectoryId  | id used to identify a source folder in the server file system where the PDF signed file to read has been stored    |
| destDirectoryId | id used to identify a folder in the server file system when the extracted document (the certificate) will be saved |
| fileName        | file name inside the specified folder                                                                              |
| obj             | embedded document, expressed as a javascript object                                                                |

The returned javascript object contains the following attributes:

* expirationDate
* firstName
* lastName
* personId
* signerCountry
* signerId
* signerOrganization
* personalVatNumber
* corporateVatNumber
* corporateName
* personCountry
* mimeType - MIME type for the embedded file; e.g. application/xml, application/pdf, etc.
* destFilePath - absolute path + file name, related to the embedded file
* signDate - the sign date, expressed as a javascript Date

## Read the specified file from the source directory and extract signed data and the embedded document

The source file is identified starting from the source directory id + fileName.

The embedded document is then saved in the destination directory. The embedded file, if recognized with a MIME type, is renamed to a name having the original name + its real extension. Otherwise, it is saved with the original source file name.

**Syntax**

```javascript
utils.getCertMessage(srcDirectoryId, destDirectoryId, fileName);
```

**Details**

| Argument        | Description                                                                                          |
| --------------- | ---------------------------------------------------------------------------------------------------- |
| srcDirectoryId  | id used to identify a source folder in the server file system where the file to read has been stored |
| destDirectoryId | id used to identify a folder in the server file system when the extracted document will be saved     |
| fileName        | file name inside the specified folder                                                                |
| obj             | embedded document, expressed as a javascript object                                                  |

The returned javascript object contains the following attributes:

* expirationDate
* firstName
* lastName
* personId
* signerCountry
* signerId
* signerOrganization
* personalVatNumber
* corporateVatNumber
* corporateName
* personCountry
* mimeType - MIME type for the embedded file; e.g. application/xml, application/pdf, etc.
* destFilePath - absolute path + file name, related to the embedded file

## Move a list of email messages to another folder <a href="#movemessages" id="movemessages"></a>

**Syntax**

```javascript
utils.moveMessages(server,port, username, password, protocol, useTLS, messageIds,folderName, moveToFolder, setAsSeen, debug);
```

**Details**

```
server - server host
port - server port
username - username to use when connecting to the email server
password - password to use when connecting to the email server
protocol - protocol to use when connecting to the email server
```

| Argument     | Description                                                     |
| ------------ | --------------------------------------------------------------- |
| useTLS       | flag used to enabled the TLS mode                               |
| messageIds   | list of email message identifiers, related to emails to move    |
| folderName   | source folder (e.g. INBOX), where the email messages are stored |
| moveToFolder | destination folder (e.g. Archivio)                              |
| setAsSeen    | flag used to mark the email as seen                             |

```
debug - flag used to debug the process
```

## Mark a list of email messages as seen or not seen <a href="#markmessagesasseen" id="markmessagesasseen"></a>

**Syntax**

```javascript
var ok = utils.markMessagesAsSeen(server,port, username, password, protocol, useTLS, messageIds,folderName, setAsSeen, debug);
```

**Details**

```
 server -server host
 port - server port
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server
```

| Argument   | Description                                                    |
| ---------- | -------------------------------------------------------------- |
| useTLS     | flag used to enabled the TLS mode                              |
| messageIds | list of email message identifiers, related to emails to move   |
| folderName | source folder (e.g. INBOX), where the email messages arestored |
| setAsSeen  | flag used to mark the email as seen or not seen                |

```
 debug - flag used to debug the process
```

## Delete a list of email messages starting from filtering conditions

Delete a list of email messages from the specified folder by moving them to the trash folder, starting from a filtering condition. At least one filtering condition is required (one of the four date filters)

**Syntax**

```javascript
utils.deleteMessages(server,port, username, password, protocol, useTLS, startSendDateFilter, endSendDateFilter, startReceiveDateFilter, endReceiveDateFilter,  messagesNumbersToDelete, folderName, trashName);
```

**Details**

```
 server -server host
 port - server port
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server
```

| Argument                            | Description                                                                                    |
| ----------------------------------- | ---------------------------------------------------------------------------------------------- |
| useTLS                              | flag used to enabled the TLS mode                                                              |
| startSendDateFilter-optional filter | if specified, only messages sent after the specified date will be deleted                      |
| endSendDateFilter                   | optional filter: if specified, only messages sent beforethe specified date will be deleted     |
| startReceiveDateFilter              | optional filter: if specified, only messages receviedafter the specified date will be deleted  |
| endReceiveDateFilter                | optional filter: if specified, only messages received beforethe specified date will be deleted |

```
 trashName-identifier of the Trash folder; since this name changes according to the specific email provider, it is not necessarely the value "Trash". If you don't know it, you can try with "Trash" and in case of errors, Platform would log the whole list of folders supported by the email provider.
 folderName-folder name where themessages to delete are located (e.g. INBOX)
```

## Forward an email to the specified destination <a href="#forwardemail" id="forwardemail"></a>

**Syntax**

```javascript
utils.forwardEmail(server,port, username, password, protocol, useTLS,to, subject subject, text, messageId);
```

**Details**

```
 server -server host
 port - server port
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server
```

| Argument  | Description                                     |
| --------- | ----------------------------------------------- |
| useTLS    | flag used to enabled the TLS mode               |
| to        | destination address                             |
| subject   | additional title to add to the original one     |
| text      | additional text to add to the body of the email |
| messageId | list of email message identifiers to delete     |

## Setting a value in a value object to save from a server-side js action

In case you are saving data from a grid or form, using the standard Platform saving system (form Save button on the UI), you can inject new attributes or change attribute values just before saving data on the server. Using the "before saving data on insert/update" event, you can link a server-side js action. Here you can execute any kind of business logic and the use calculated data and inject it in the "vo" which is just to be saved, through the following method:

```javascript
utils.setAttributeValue(String attrName,Object value);
```

**Details**

| Argument | Description                                                           |
| -------- | --------------------------------------------------------------------- |
| attrName | attribute name to set in the "vo" Platform is working on to save data |
| value    | value to set for this attribute                                       |

## Set variable

```
utils.setVariable(String attributeName,Object value)
```

| Argument      | Description           |
| ------------- | --------------------- |
| attributeName | name of the variable  |
| value         | value of the variable |

## Copy company id

```
utils.copyCompanyId(String startingCompanyId,String newCompanyId,String newCorporateName)
```

| Argument          | Description                     |
| ----------------- | ------------------------------- |
| startingCompanyId | starting company identification |
| newCompanyId      | new company identification      |
| newCorporatename  | new corporate name              |

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

## Write base 64 file

```
utils.writeBase64File(String filePath,String base64Content)
```

| Argument      | Description                                                                                                      |
| ------------- | ---------------------------------------------------------------------------------------------------------------- |
| filePath      | list of files stored in the server side file system (expressed with absolute path) to copy within the FTP server |
| base64Content |                                                                                                                  |

## Read base 64 file

```
utils.readBase64File(String filePath)
```

| Argument | Description                                                                                                      |
| -------- | ---------------------------------------------------------------------------------------------------------------- |
| filePath | list of files stored in the server side file system (expressed with absolute path) to copy within the FTP server |

## Execute a series of SQL statements, stored in the specified file.

**Syntax**

```javascript
var rows = utils.executeSqlFile(
  sqlFile,
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
| sqlFile              | absolute path + file name, related to the SQL script to execute                                                                                                                                                      |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                           |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)                                                              |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                       |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql statement. |

An :XXX variable can be replaced by vo or params values

## Convert string to number

```
utils.convertStringToNumber(String number)
```

| Argument | Description       |
| -------- | ----------------- |
| number   | number to convert |

## Get lenguage id from email

```
utils.getLanguageIdFromEmail(String email)
```

| Argument | Description                   |
| -------- | ----------------------------- |
| email    | email to get lenguage id from |

## Get language id for a specific username

**Syntax**

```javascript
var languageId = utils.getLanguageIdFromUsername(userId)
```

**Details**

| Argument   | Description                                              |
| ---------- | -------------------------------------------------------- |
| languageId | string value: the language id expressed like (IT,EN,...) |
| userId     | string value: the username to use to get language id     |

## Blocking wait all elements

**Syntax**

```javascript
utils.blockingWaitAllElements(Long timeout,String[] elementIdsStr)
```

**Details**

| Argument     | Description |
| ------------ | ----------- |
| timeout      |             |
| elementIdStr |             |

## Wait all elements

**Syntax**

```javascript
utils.waitAllElements(String queueName,Long actionId,Long[] elementIds)
```

**Details**

| queueName    | name of the queue |
| ------------ | ----------------- |
| timeout      |                   |
| elementIdStr |                   |

## Wait any elements

**Syntax**

```javascript
utils.waitAnyElement(String queueName,Long actionId,Long[] elementIds)
```

**Details**

| queueName  | name of the queue                                   |
| ---------- | --------------------------------------------------- |
| actionId   | server-side javascript action identifier to execute |
| elementIds |                                                     |

## **Enqueuing server-side js actions**

```
enqueueAction(queueName, actionId, params, priority, processWaitTime, logExecution);
```

The arguments are:

* **queueName**– optional: queue name; if not specified, the process will be enqueued in the DEFAULT queue
* **actionId**– server-side javascript action identifier to execute
* **param**– javascript object containing parameters to pass to the action
* **priority**– optional; if specified, processes within the same queue will be sorted according to the priority rathe than to the enqueuing time
* **processWaitTime**– optional; if specified, the process will not be started before that time, expressed in seconds
* **logExecution**– true to log in the predefined table LOG60\_LOGS the execution of the process

Note: the javascript object specified through the "param" can accept an optional attribute named "**queueTimeout**": when the action execution time overpasses that value, (expressed in minutes), the element is marked as "timeout" in the queue and the queue is then unlocked, in order to allow extracting new elements from it. Note that the current action is still under execution and this could create drawbacks in case of actions which should be executed sequentially, since the work on the same set of data,by writing them.

There is a variant of the method described above, having one more argument:

```
enqueueActionWithNote(queueName, actionId, params, priority, processWaitTime, logExecution, note);
```

where **note** is a string value which will be saved in the NOTE field of the CON77\_QUEUES table. This field can be helpful to carry out custom logic on the enqueued elements, for instance to execute statistics about the amount of data not processed yet.

## **Adding a web service invocation as a process to a specific queue**

```javascript
utils.enqueueWebService(queueName, url, params, priority, processWaitTime, logExecution);
```

The required arguments are:

* **queueName**– optional: queue name; if not specified, the process will be enqueued in the DEFAULT queue
* **url**– shell command to execute
* **param**– js object containing parameters to pass to the web service
* **priority**– optional; if specified, processes within the same queue will be sorted according to the priority rathe than to the enqueing time
* **processWaitTime**– optional; if specified, the process will not be started before that time, expressed in seconds
* **logExecution**– true to log in LOG60\_LOGS the execution of the process

## Force start process

**Syntax**

```javascript
utils.forceStartProcess(String queueName,Long progressive)
```

**Details**

| queueName   | name of the queue                                   |
| ----------- | --------------------------------------------------- |
| progressive | server-side javascript action identifier to execute |

## Dequeue process

**Syntax**

```javascript
utils.dequeueProcess(String queueName,Long progressive)
```

**Details**

| queueName   | name of the queue                                   |
| ----------- | --------------------------------------------------- |
| progressive | server-side javascript action identifier to execute |

## Enconding data to send externally

In case you need to encode data which you need to send outside, for instance in a link, you can use this method:

```javascript
var token = utils.getEncodedRtk(String data);
```

The required arguments are:

* **data** – data list to encode

This method returns a String object, that can be used for instance in the method **createAllowedLinkWithRtk**.

Note: this method will NOT encrypt data: it only obfuscates data, by not makes it visible in plain text.

If you need more protection and encrypt data, use the method **getEncToken** instead.

## Execute a SQL insert instruction, starting from a javascript object, instead of defining explicitelly the SQL script. <a href="#insertobject" id="insertobject"></a>

**Syntax**

```javascript
utils.insertObject(obj, tableName, dataSourceId, separatedTransaction, interruptExecution);
```

**Details**

| Argument             | Description                                                                                                                                                                                                                                                                                                                     |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| obj                  | a Javascript object containing the data to save in the specified table; data is related to the table fields and each object attribute name is expressed in "camel" format, i.e. if the table field has name PRODUCT\_CODE, the attribute name must be productCode                                                               |
| tableName            | table name to use when creating the SQL insert instruction; field names as retrieved starting from the data model linked to the current table name: that means that it is mandatory to define a (writable) data model for that table, before invoking this javascript method; values are fechted starting from the obj argument |
| dataSourceId         | optional parameter (can be null); it defines the additional datastore to use when executing the SQL insert                                                                                                                                                                                                                      |
| separatedTransaction | boolean flag used to define if the SQL query must be execute on a separated transation or not                                                                                                                                                                                                                                   |
| interruptExecution   | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an error during the execution of the SQL query                                                                                                                                                        |
| ok                   | true in case of SQL instruction executed correctly, an exception otherwise                                                                                                                                                                                                                                                      |

## Execute a SQL update instruction, starting from a javascript object, instead of defining explicitelly the SQL script <a href="#updateobject" id="updateobject"></a>

**Syntax**

```javascript
utils.updateObject(obj, emptyAsNull, forceAttributesToNull, tableName, dataSourceId, separatedTransaction, interruptExecution);
```

**Details**

| Argument              | Description                                                                                                                                                                                                                                                                                                                     |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| obj                   | a Javascript object containing the data to save in the specified table; data is related to the table fields and each object attribute name is expressed in "camel" format, i.e. if the table field has name PRODUCT\_CODE, the attribute name must be productCode                                                               |
| tableName             | table name to use when creating the SQL update instruction; field names as retrieved starting from the data model linked to the current table name: that means that it is mandatory to define a (writable) data model for that table, before invoking this javascript method; values are fechted starting from the obj argument |
| emptyAsNull           | this boolean flag can be set to true to force the conversion of ‘’ string values to null; it can be helpful to clear up some table fields                                                                                                                                                                                       |
| forceAttributesToNull | this boolean flag can be used to force to null every table field not referred in the javascript object but defined in the linked data model                                                                                                                                                                                     |
| dataSourceId          | optional parameter (can be null); it defines the additional datastore to use when executing the SQL update                                                                                                                                                                                                                      |
| separatedTransaction  | boolean flag used to define if the SQL query must be execute on a separated transation or not                                                                                                                                                                                                                                   |
| interruptExecution    | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an errore during the execution of the SQL query                                                                                                                                                       |
| ok                    | true in case of SQL instruction executed correctly, an exception otherwise                                                                                                                                                                                                                                                      |

## Execute a SQL delete instruction, starting from a javascript object, instead of defining explicitelly the SQL script <a href="#deleteobject" id="deleteobject"></a>

**Syntax**

```javascript
utils.deleteObject(obj, tableName, dataSourceId, separatedTransaction, interruptExecution);
```

**Details**

| Argument             | Description                                                                                                                                                                                                                                                                                                                                                                                  |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| obj                  | a Javascript object containing the data to delete in the specified table; data is related to the table fields and each object attribute name is expressed in "camel" format, i.e. if the table field has name PRODUCT\_CODE, the attribute name must be productCode; only fields which are part of the primary key will be taken into account                                                |
| tableName            | table name to use when creating the SQL delete instruction; field names as retrieved starting from the data model linked to the current table name: that means that it is mandatory to define a (writable) data model for that table, before invoking this javascript method; values are fechted starting from the obj argument: only the attributes related to the primary key will be used |
| dataSourceId         | optional parameter (can be null); it defines the additional datastore to use when executing the SQL delete                                                                                                                                                                                                                                                                                   |
| separatedTransaction | boolean flag used to define if the SQL query must be execute on a separated transation or not                                                                                                                                                                                                                                                                                                |
| interruptExecution   | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an errore during the execution of the SQL query                                                                                                                                                                                                                    |
| ok                   | true in case of SQL instruction executed correctly, an exception otherwise                                                                                                                                                                                                                                                                                                                   |











