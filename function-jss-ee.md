# Function JSS EE

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addFileToMobileDevices(String fullPathName,String fileName,String username);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleCalendarEvent(String title,Date beginDate,Date endDate);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleCalendarEventWithConference(String serviceAccountEmail,String privateKeyString,String userId,String title,Date beginDate,Date endDate,String description,String location,String calendarId,String type,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleCalendarEventWithSettings(String serviceAccountEmail,String privateKeyString,String userId,String title,Date beginDate,Date endDate,String description,String location,String calendarId,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleContact(String name,String surname,String email,String phone,Boolean shared);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleDriveFileProperty(String userId,String fileId,String key,String value,String visibility);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleDriveFileProperty(String fileId,String key,String value,String visibility);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addISO8601(Date dt,String period);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addPermissionsToGoogleDriveFolder(String folderId,String type,String value,String fileRole,String folderRole,String> additionalRoles,Boolean updateBaseFolder,Boolean recursive,Boolean sendNotifications,String message);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addPermissionsToGoogleDriveFolder(String userId,String folderId,String type,String value,String fileRole,String folderRole,String> additionalRoles,Boolean updateBaseFolder,Boolean recursive,Boolean sendNotifications,String message);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addValueInCache(String varName,Object value,Long expirationTime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addValueInCache(String varName,Object value);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.analyzeEntities(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.analyzeEntitySentiment(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.analyzeSentiment(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.analyzeSyntax(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.appendRangeGoogleSheet(String userId,String spreadsheetId,String range,String valueInputOption,String insertDataOption,Object[][] vos);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.backupEntitiesInGCS(String[] entityNames,Long directoryId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkDeleteOnGoogleDatastore(String gql);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImport(Long sourceDirId,Long destDirId,Long backupDirId,Long dataSourceId,String tableName,String csvFileName,String csvFileNameField,String csvUniqueIdField,String csvSep,Object> defaultValues,String> mapping,String nullString,Boolean skipWithErrors,Boolean skipFileNotInCSV,Long beforeInsertActionId,Long afterInsertActionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImportFromDSToBigQuery(String gql,Long datastoreDataModelId,String location,String bigQueryTable,boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImportFromDSToSpanner(String gql,Long datastoreDataModelId,boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImportFromFTP(String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter,Long destDirId,Long backupDirId,Long dataSourceId,String tableName,String csvFileName,String csvFileNameField,String csvUniqueIdField,String csvSep,Object> defaultValues,String> mappingCsvToFields,String nullString,Boolean skipWithErrors,Boolean skipFileNotInCSV,Long beforeInsertActionId,Long afterInsertActionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkUpdateOnGoogleDatastore(String gql,Map attributesToSet,Map attributesToRemove,Long actionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.callGaeAction(Long actionId,Boolean async);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.checkGoogleSSOToken(String ssoAuthToken);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.classifyText(String text,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearAllDatastoreEntities);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearCache(String varNames,String keys);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearCache(String varNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearDatastoreEntities(String entityName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearRangeGoogleSheet(String userId,String spreadsheetId,String range);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.closeActivitiTask(String taskInstanceId,Map map);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.closeActivitiTask(String processInstanceId,String taskDefinitionKey,String assignee,Map map);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.completeActivitiTask(String processInstanceId,Map params,Map processVariables);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertDocxToOtherFormat(String docxFile,String newFile,Boolean deleteDocxFile,String format);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertDocxToPdf(String docxFile,String pdfFile,Boolean deleteDocxFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertHtmlToImage(String html,String imagePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertISO8601(String period);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertListWithMapper(String json,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertObjectWithMapper(String json,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertPdfToImage(Long pdfDirId,String pdfFileName,Long imgDirId,String imgExtension,Float scale);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertTifToJpg(Long tifDirId,String tifFileName,Long jpgDirId,String jpgFileName,Float compressionFactor);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertUrlToImage(String url,String imagePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyGoogleCloudStorageObject(String sourceBucketName,String sourceObjectName,Long sourceObjectVersion,String destinationBucketName,String destinationObjectName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyGoogleSheet(String userId,String spreadsheetId,Integer sheetId,String destinationSpreadsheetId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryDataset(String datasetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryTable(String datasetName,String tableName,Map> columns);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryTableFromDatastoreEntities(String[] entityNames,Long directoryId,String datasetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createConDbForCurrentUser(String companyId,Long siteId,String username);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createCsvFromSqlQuery(String sql,Long dataSourceId,Boolean includeRowNum,String replaceNullWith,Long fromRow,Long maxRowsToRead,String firstRow,String sep,Long dirId,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleCloudStorageBucket(String project,String bucketName,String bucketLocation,String storageClass);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleDriveFolder(String folderName,String> parents,String description);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleDriveFolder(String userId,String folderName,String> parents,String description);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleSheets(String userId,String spreadsheetId,String[] sheets);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleSpreadsheets(String userId,String spreadsheetTitle,String[] sheets);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createStripeCustomer(String apiKey,Map customerData);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createTablesFromDatastoreBackup(String[] entityNames,String gcsURI,String datasetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createXLSXFileFromSQLQuery(Long templateDirectoryId,String templateFileName,String sheetName,Long outDirectoryId,String outFileName,Map[] formatHeaderColumns,Map[] formatColumns,Map grouping,Map additionalSettings,Long datastoreId,String sqlQuery,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createXlsContent(Long dirId,String fileName,String sheetName,Integer sheetIndex,Integer fromRow,Object>[] vos,String[] attributeNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteBigQueryDataset(String datasetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteBigQueryObject(String datasetName,String tableName,Map obj,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteBigQueryTable(String datasetName,String tableName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteCard(Long dataModelId,Long panelId,Map vo);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteCards(Long dataModelId,Long panelId,Map[] vos);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteDir(Long dirId,String subFolder);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFileFromCMS(String uuid);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive,Boolean removeEmptyDir);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleCalendarEvent(String calendarEventId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleCalendarEventWithSettings(String serviceAccountEmail,String privateKeyString,String userId,String calendarEventId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleCloudStorageBucket(String bucketName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleCloudStorageObject(String bucketName,String objectName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleContact(String contactId,Boolean shared);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFile(String fileId,boolean skipTrash);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFile(String userId,String fileId,boolean skipTrash);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFileProperty(String fileId,String key);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFileProperty(String userId,String fileId,String key);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleSheets(String userId,String spreadsheetId,Integer[] sheetIds);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObjectOnBigQuery(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteProcessInstance(String processInstanceId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.downloadArchiflowDocument(Long dirId,String fileName,String cardId,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.downloadFileFromGoogleDrive(String userId,String fileId,String localPath,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.downloadGoogleCloudStorageObject(String bucketName,String objectName,String destPath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateGoogleDriveFile(String userId,String sourceFolderId,String destinationFolderId,String newFileName,Boolean copyPermissions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateGoogleDriveFolderAndContents(String userId,String sourceFolderId,String newFolderName,String newFolderDescription,String destinationFolderId,String titlePrefix,Boolean copyPermissions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateGoogleDriveFolderAndContents(String sourceFolderId,String newFolderName,String newFolderDescription,String destinationFolderId,String titlePrefix,Boolean copyPermissions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateGoogleSheet(String userId,String spreadsheetId,Integer sourceSheetId,Integer insertSheetIndex,Integer newSheetId,String newSheetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.encodeJWT(Map dataToSend,String sharedKey);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enqueueGaeAction(String queueName,Long actionId,Map params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enquiryTasks(HashMap pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeAction(Long actionId,Map vo,Map params,Map headers);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeActionSameTransaction(Long actionId,Map vo,Map params,Map headers);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeAllExports(String queryType,Map paramValues);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeBigQueryDmlStatement(String datasetName,String sql,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeBigQuerySaveOnLocalTable(Long datastoreId,String localTableName,Map defaultFieldNames,Map[] csvFields,String defaultDataset,String sqlQuery,Object[] params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeBigQuerySaveOnTable(String destinationDataset,String destinationTable,String defaultDataset,String sqlQuery,Object[] params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeBigQueryWithCallback(String processRowFunName,String defaultDataset,String sqlQuery,Object[] params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeCachedQueryOnGoogleDatastore(int maxCachedEntities,String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeCachedQueryOnGoogleDatastoreWithSetting(int maxCachedEntities,String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeExport(Long exportId,String queryType,Map paramValues);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeExportsInGroup(String groupName,String queryType,Map paramValues);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnBigQuery(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnBigQueryWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map map,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnGoogleDatastore(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnGoogleDatastoreWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnGoogleSpanner(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnGoogleSpannerWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnMongoDb(String where,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSpannerDdl(String[] scripts);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSpannerSql(String sql);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeStripePayment(String apiKey,Long priceWithCents,String currency,String customerId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportFromExcelFileToGSheet(String userId,Long sourceDirId,String sourceFileName,String spreadsheetId,List areas);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportFromExcelFileToGSheet(Long sourceDirId,String sourceFileName,String spreadsheetId,List areas);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportUsersToDatastore);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportUsersToDatastore(String companyId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.extractBigQueryData(String datasetName,String tableName,String format,String gcsUrl,Boolean deleteTableAfterExport,Boolean exportHeaders);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.generateDocx(Long reportId,Object> args,String langId,String path,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.generateGCPAuthToken(String user,String serviceAccountEmail,String privateKeyString,String redirectUri,String[] _scopes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getActivitiLastVersionProcessId(String id);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getActivitiProcessAsJson(String id,Boolean includeSubProcesses,Map tasksDueDates);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getActivitiProcessInstancesVariables(String processInstanceId,String processDefinitionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getActivitiUserAssignedTasks(String assignee,String processInstanceId,String taskDefinitionKey);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getActivitiUserCandidateTasks(String candidate,String processInstanceId,String taskDefinitionKey);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getAlfrescoDocument(String id,String fileName,String destPath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getAlfrescoWebScript(String uri,boolean replaceVariables,String httpMethod,String bodyRequest,String charSet);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getAlfrescoWebScript(String uri,boolean replaceVariables,String httpMethod,String bodyRequest);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getBigQueryDataset);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getButtonsAuthorizationOfUser);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getDetailOnArchiflow(Long dataModelId,String cardId,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getElementFromQueueByNote(String note,String namespace);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEntities(String entityName,Object[] entityKeys);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEntitiesAsJSON(String entityName,Object[] entityKeys);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEntity(String entityName,Object key,int maxCachedEntities);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEntity(String entityName,Object key,int maxCachedEntities,Long expirationTime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities,Long expirationTime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFunctionAuthorizationOfUser(String functionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGCPAuthToken(String user,String serviceAccountEmail,String privateKeyString,String[] _scopes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleCloudStorageBucket(String bucketName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleCloudStorageBucketVersioning(String bucketName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleCloudStorageObject(String bucketName,String objectName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleCloudStorageObjectVersions(String bucketName,String objectName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleCloudStorageSignedURL(String verb,Long expiration,String bucketName,String objectName,String mime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleContactsFiltered(Integer pages,Integer maxPageResults,String searchString,Boolean splitEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDomainContactsFiltered(Integer pages,Integer maxPageResults,String query,String orderBy,String sortOrder);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileDownloadURL(String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileInfo(String userId,String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileInfo(String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileOpenURL(String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileProperty(String fileId,String key,String visibility);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileProperty(String userId,String fileId,String key,String visibility);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileRevisions(String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileRevisions(String userId,String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFolderContents(String folderId,String query,Boolean trashed);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFolderContents(String userId,String folderId,String query,Boolean trashed);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFolderContentsIds(String folderId,String query,boolean trashed);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFolderContentsIds(String userId,String folderId,String query,boolean trashed);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleOAuth2AccessToken(String projectId,String serviceAccountEmail,String privateKeyString,String[] scopes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleOAuth2AccessToken(String projectId,String[] scopes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleOAuth2AccessToken(String[] scopes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSharedContactsFiltered(Integer pages,Integer maxPageResults,String searchString,Boolean splitEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheetData(String userId,Long dataModelId,String spreadsheetId,String> range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheetData(String userId,String spreadsheetId,String range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheetData(String userId,String spreadsheetId,String> range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheetData(String userId,Long dataModelId,String spreadsheetId,String range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheets(String userId,String spreadsheetId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheets(String spreadsheetId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGroupMembers(String userId,String groupId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getInfoFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getInvolvedNotAssignedTasks(HashMap pars,String username);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getKeysFromCache(String keyPrefix);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getLastSynchronizationDevice);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getModifiedPks(String tableName,String field,Date changedStardDate,Date changedEndDate);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnArchiflow(Long dataModelId,Map[] filters,Integer[] archiveIds,Boolean cardsWithAttachedDoc,Integer searchTypes,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnBigQuery(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnBigQueryWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnGoogleDatastore(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnGoogleDatastoreWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnGoogleSpanner(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnGoogleSpannerWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnMongoDb(String where,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getProcessDefinition(String processDefinitionId,Map params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getShortUrl(String realUrl);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getUUID);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getValueInCache(String varName,String alternativeFunctionName,Long expirationTime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getValueInCache(String varName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getValueInCache(String varName,String alternativeFunctionName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWebContentWithNTLM(String url,String contentType,String httpMethod,String bodyRequest,String username,String password,String workstation,String domain,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryDataFromGCS(String datasetName,String tableName,String format,String sourceUri,String encoding,String separator);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryDataFromLocalDatasource(String datasetName,String tableName,String location,String format,String csvPath,String encoding,String separator,Integer maxBadRecords,Boolean truncate,Boolean deleteSrcFileAfterImport);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryThroughStreaming(String datasetName,String tableName,Object[] objectsForBQ);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importDataInCloudSQL(String instance,String bucketPath,String dbSchema,Long dataSourceId,String tablename,String where,String[] columns);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importDataInCloudSQL(String instance,String bucketPath,String dbSchema,Long dataSourceId,String tablename,String where,Integer timeout,String[] columns);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importFileInCMS(Long sourceDirId,String fileName,Long destDirId,Long dataSourceId,String tableName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importFileInCMS(String path,Long destDirId,Long dataSourceId,String tableName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importMultipleDataFromLocalDatasource(String datasetName,String[] tableNames,String location,String format,String dirPath,String[] csvFiles,String encoding,String separator,Integer maxBadRecords,Boolean truncate,Boolean deleteSrcFileAfterImport);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertBigQueryObject(String datasetName,String tableName,Map obj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertCard(Long dataModelId,Long panelId,Map vo,Integer archiveId,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertCard(Long dataModelId,Long panelId,Map vo,Integer archiveId,Map additionalSettings,Long actionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertCards(Long dataModelId,Long panelId,Map[] vos,Integer archiveId,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertCards(Long dataModelId,Long panelId,Map[] vos,Integer archiveId,Map additionalSettings,Long actionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectsOnBigQuery(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectsOnGoogleDatastore(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectsOnGoogleDatastoreWithSettings(Map[] objs,Long dataModelId,Boolean interruptExecution,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectsOnGoogleSpanner(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.invalidateAll);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.invalidateAllCache(String varName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.listGoogleCloudStorageObjects(String bucketName,String prefix,String delimiter);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.listGoogleCloudStorageObjects(String bucketName,Long maxPageResults,Integer pages,String nextPageToken,String prefix,String delimiter);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.matchTensorFlowCsvResults(Long dirId,Long dataSourceId,String tableName,Map jsObj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.maybeStartProcess(Long schedId,Boolean forceRunning,Boolean startNextProcesses);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.mergeDocx(Long srcDirId,String[] docxNames,Long destDirId,String mergedDocxName,Boolean deleteFilesAfterMerge);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.mergeObjectOnGoogleDatastore(Map attributesToSet,String[] attributesToSetToNull,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.mergeObjectOnGoogleSpanner(Map attributesToSet,String[] attributesToSetToNull,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.modifyGoogleCalendarEvent(String calendarEventId,String title,Date beginDate,Date endDate);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.modifyGoogleCalendarEventWithSettings(String calendarEventId,String title,Date beginDate,Date endDate,String description,String location,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.modifyGoogleDriveFileParents(String fileId,String parentsToAdd,String parentsToRemove);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.modifyGoogleDriveFileParents(String userId,String fileId,String parentsToAdd,String parentsToRemove);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.moveGoogleDriveFile(String fileId,String newParent,boolean addToRevision);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.moveGoogleDriveFile(String fileId,String newParents);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.moveGoogleDriveFile(String userId,String fileId,String newParent,boolean addToRevision);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.moveGoogleDriveFile(String userId,String fileId,String newParents);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.patchGoogleDriveFileProperty(String userId,String fileId,String key,String value,String visibility);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.patchGoogleDriveFileProperty(String fileId,String key,String value,String visibility);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.prepareStripePayment(String apiKey,String publicKey,Long priceWithCents,String currency,String customerId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.recoverGoogleDriveFile(String userId,String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.recoverGoogleDriveFile(String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.reinsertElements(String companyId,Long actionId,String queueName,String status,String id);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeGoogleDriveFilePermissions(String userId,String fileId,String emailUser);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeGoogleDriveFilePermissions(String fileId,String emailUser);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeValueInCache(String varName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeValuesFromCache(String keyPrefix);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.rewriteGoogleCloudStorageObject(String sourceBucketName,String sourceObjectName,Long sourceObjectVersion,String destinationBucketName,String destinationObjectName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.scaleJpgFile(Long srcJpgDirId,String srcJpgFileName,Long destDirId,String destFileName,Long maxWidth,Long maxHeight);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.scaleJpgFile(Long srcJpgDirId,String srcJpgFileName,Long destDirId,String destFileName,Long scale);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.searchInGoogleDrive(Integer maxPageResults,Integer pages,String nextPageToken,String folderId,Boolean recursive,String query,Boolean trashed);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.searchInGoogleDrive(String userId,Integer maxPageResults,Integer pages,String nextPageToken,String folderId,Boolean recursive,String query,Boolean trashed);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendPushNotification(String appId,String[] userCodeIds,String title,String shortMessage,Long actionId,String json,Long badgeNr);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendPushNotificationWithOptions(String appId,String[] userCodeIds,String title,String shortMessage,Long actionId,String json,Long badgeNr,Map rootOptions,Map dataOptions,Map notificationOptions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendSinglePushNotification(String appId,String firebaseId,String title,String shortMessage,Long actionId,String json,Long badgeNr,Map rootOptions,Map dataOptions,Map notificationOptions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendSmsMessage(String fromPhoneNr,String toPhoneNr,String text,Boolean logMessage);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendTensorFlowCsvFromCsv(String csvFilePath,Boolean includeFirstRow,Boolean includeRowNum,int resultValuesNr,Long dirId,String topic,String cmd,Long pkIndex,Map jsObj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendTensorFlowCsvFromSqlQuery(String sql,Long dataSourceId,Long fromRow,Long maxRowsToRead,String fieldName,Integer resultValuesNr,Long dirId,String fileName,Map jsObj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendWhatsappMessage(String accountId,String secretKey,String fromNr,String toNumber,String message,String publicUrl);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendWhatsappMessage(String accountId,String secretKey,String fromNr,String toNumber,String message,String bucketName,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendWhatsappMessage(String toNumber,String message,String publicUrl);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendWhatsappMessage(String toNumber,String message,String bucketName,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setBigQueryDataset(String bigQueryDataset);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setBlockSize(int blockSize);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDatasetId(String datasetId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDatastoreNamespace(String namespace);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleClientId(String id);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleClientSecret(String pwd);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleCloudStorageBucketVersioning(String bucketName,Boolean versioning);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFileAttributes(String userId,String fileId,FileAttributes fileAttributes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFileAttributes(String fileId,FileAttributes fileAttributes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFilePermissions(String userId,String fileId,String type,String value,String role,String> additionalRoles,boolean sendNotifications,String message);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFilePermissions(String fileId,String type,String value,String role,String> additionalRoles,boolean sendNotifications,String message);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGooglePrivateKeyString(String key);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleServiceAccountEmail(String email);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleTokenResponse(String token);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setPublicLink(String bucketName,String objectName,Boolean publicLink);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setStartIndex(int startIndex);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setTaskAssignee(String taskId,String assignee);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sharedContatctsSync);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.startActivitiProcess(String appId,String processDefinitionId,Map params,Map processVariables);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.unzipFile(Long zipDirId,String zipFileName,String serverFileSystemDir);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateBigQueryObject(String datasetName,String tableName,Map obj,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateCard(Long dataModelId,Long panelId,Map vo);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateCards(Long dataModelId,Long panelId,Map[] vos);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateFileInCMS(String uuid,Long sourceDirId,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateFileInCMS(String uuid,String path);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateGoogleContact(String contactId,String name,String surname,String email,String phone,Boolean shared);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateGoogleDriveFile(String fileId,String title,String description,String mimeType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateGoogleDriveFile(String userId,String fileId,String title,String description,String mimeType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateGoogleDriveFileFromFS(String fileId,String fsPath,boolean deleteFsFile,boolean newRevision);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateGoogleDriveFileFromFS(String userId,String fileId,String fsPath,boolean deleteFsFile,boolean newRevision);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectOnBigQuery(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectsOnBigQuery(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectsOnGoogleDatastore(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectsOnGoogleDatastoreWitSettings(Map[] objs,Long dataModelId,Boolean interruptExecution,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectsOnGoogleDatastoreWithSettings(Map[] objs,Long dataModelId,Boolean interruptExecution,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectsOnGoogleSpanner(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateRangeGoogleSheet(String userId,String spreadsheetId,String range,String valueInputOption,Object[][] vos);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadAndRenameGoogleDriveFileFromFS(String fsPath,String parentId,String fileName,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadAndRenameGoogleDriveFileFromFS(String userId,String fsPath,String parentId,String fileName,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,String fileName,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(String userId,String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,String fileName,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadArchiflowDocument(Long dirId,String fileNameSrc,String cardId,String fileName,String documentTitle,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleCloudStorageObjectFromFS(String fsPath,String bucketName,String objectName,Boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleCloudStorageObjectFromString(String textContent,String bucketName,String objectName,String contentType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleCloudStoragePublicObjectFromFS(String fsPath,String bucketName,String objectName,Boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleCloudStoragePublicObjectFromString(String textContent,String bucketName,String objectName,String contentType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleDriveFileFromFS(String fsPath,String parentId,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleDriveFileFromFS(String userId,String fsPath,String parentId,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleDriveFileInNamedFolderFromFS(String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleDriveFileInNamedFolderFromFS(String userId,String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.upsertObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.upsertObjectsOnGoogleDatastore(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.upsertObjectsOnGoogleDatastoreWithSettings(Map[] objs,Long dataModelId,Boolean interruptExecution,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.validateAlexaRequest(String signingCertificateChainUrl,String baseEncoded64Signature,String requestBody);
```
{% endcode %}
