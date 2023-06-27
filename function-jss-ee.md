# Function JSS EE

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.protectPdf(String passwordRestriction,String passwordOwner,String fullPathSrc,String fullPathDst);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCatalog(Long datasourceId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSql(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.textToInt(String text);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendEmail(String smtpHost,String smtpPort,String useTLS,String protocol,String smtpUsername,String smtpPassword,String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendEmail(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendEmail(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.zipFiles(String baseDir,String[] files,String zipFile,Boolean deleteFilesAfterZip);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.zipFiles(Long baseDirId,String zipFile,Boolean deleteFilesAfterZip);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.saveEml(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String folderName,String[] messageIds,String[] fileNames,Long directoryId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendGmail(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeTime(Date date);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.parseXML(String xmlDocument);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendFiles(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String toDir,String[] filePaths);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendFiles(String host,Integer port,Boolean useSSL,String username,String password,String toDir,String[] filePaths);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendFiles(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String toDir,Integer sessionTimeout,String[] filePaths);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String destFile,String sourceFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendFile(String host,Integer port,Boolean useSSL,String username,String password,String destFile,String sourceFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String destFile,Long directoryId,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendFile(String host,Integer port,Boolean useSSL,String username,String password,String destFile,Long directoryId,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String destFile,Long directoryId,String fileName,Integer sessionTimeout);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFiles(Long dirId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFiles(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFiles(String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFiles(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter,Integer sessionTimeout);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEmails(String server,Integer port,String username,String password,String protocol,Boolean useTLS,Integer maxMessagesToRead,Boolean notReadFilter,Date startSendDateFilter,Date endSendDateFilter,Date startReceiveDateFilter,Date endReceiveDateFilter,String fromAddressFilter,String subjectFilter,String bodyFilter,Boolean withAttachments,String attachmentsPath,String folderName,String moveToFolderOnceRead,Boolean setAsSeen,Boolean deleteEmailWhenRead,Boolean debug);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEmails(String server,Integer port,String username,String password,String protocol,Boolean useTLS,Integer maxMessagesToRead,Boolean notReadFilter,Date startDateFilter,String fromAddressFilter,String subjectFilter,String bodyFilter,Boolean withAttachments,String attachmentsPath,String folderName,String moveToFolderOnceRead,Boolean setAsSeen,Boolean deleteEmailWhenRead,Boolean debug);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyFile(String inBaseDir,String inFileName,String destPathFileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyFile(String srcFile,String destFile,Boolean replaceExistingFile,Boolean deleteSourceFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.camel(String fieldName,Boolean firstCharUpper);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uncamel(String attributeName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.debugAll);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setSiteId(Long siteId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.isOffLine);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.existUser(String companyId,Long siteId,String userCodeId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createRole(String companyId,Long siteId,String roleId,String description);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createUser(String companyId,Long siteId,String userCodeId,String description,String password,String languageId,Map user,Map[] roles);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateUser(String companyId,Long siteId,String userCodeId,String languageId,Map user);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.renameFile(Long directoryId,String oldFileName,String newFileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.unzip(Long directoryId,String zipFile,Long directoryIdOut,Boolean deleteZipFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.stringify(Object o);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.parseJSON(String json);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.md5(String text);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sha256(String text);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.logInCon60(String logType,String msg,String messageTag);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.rPad(String value,char fillChar,int length);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.lPad(String value,char fillChar,int length);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.saveBlob(Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.fileExists(String filePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertStringToUTCDate(String date);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createDbTableMetadata(Long datasourceId,String tableName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateDbTableMetadata(Long dbTableId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createValueImports(Long dbTableId,Long directoryId,String fileName,String description,String note,String inputData,Long breakOnColumnsEmpty,Long breakOnRowsEmpty);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateValueImports(Long valueImportId,Long directoryId,String fileName,String description,String note,String inputData,Long breakOnColumnsEmpty,Long breakOnRowsEmpty,Boolean ignoreSheet);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateValueImports(Long valueImportId,Long directoryId,String fileName,String description,String note,String inputData,Long breakOnColumnsEmpty,Long breakOnRowsEmpty);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importCellsFromExcelFile(Long directoryId,String fileName,Long valueImportId,Map fieldsData,Map inputData,Boolean separatedTransaction);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportFromExcelFile(Long sourceDirId,String sourceFileName,Long destDirId,String destFileName,List areas);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteValueImport(Long valueImportId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.disableValueImport(Long valueImportId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSqlBatch(Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setImagesInXls(Long dirId,String srcFileName,String destFileName,String sheetName,Map> images);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getSheetListFromExcelFile(Long dirId,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyImportRowsFromFile(Long importId,String newDescription);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importRowsFromFile(Long dirId,String fileName,Long importId,boolean insert,Long maxErrors,Long maxRowErrors,Map inputData,Long destErrorsFileDirId,String destErrorsFileName,boolean rollbackIfErrors,boolean async);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importRowsFromFile(Long dirId,String fileName,Long importId,boolean insert,Long maxErrors,Long maxRowErrors,Map inputData,Long destErrorsFileDirId,String destErrorsFileName,boolean rollbackIfErrors,boolean async,String sheetTitle);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getExcelRowsBlock(Long dirId,String fileName,Long sheetIndex,Long fromRow,Long toRow,String[] attributeNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEnvironment);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCachedProgressive(Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFileLength(String fileAbsolutePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enqueueActionsFromSqlQuery(String queueName,String payload,Long actionId,Long datasourceId,String sqlQuery,Object[] params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getColumnsInQuery(Long datastoreId,String query);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readCsvAndLoadTable(Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.mapClobFieldToTable(Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.validateCode(Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyDataFromBorderTable(Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.writeToCSVFile(String uuid,Map obj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.writeToCSVFile(String uuid,Map obj,String rowSeparator);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createCSVFileFromSQLQuery(String fileName,Boolean overwrite,Long directoryId,String sep,String languageId,Boolean printTitles,Boolean fileAppend,String[] formatColumns,Long datasourceId,String sqlQuery,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createCSVFileFromSQLQuery(String fileName,Boolean overwrite,Long directoryId,String sep,String languageId,Boolean printTitles,Boolean fileAppend,String charset,String[] formatColumns,Long datasourceId,String sqlQuery,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.openCSVFile(String fileName,Boolean overwrite,Long directoryId,String sep,Boolean fileAppend,String[] attributesToWrite,String[] formatters);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.forceCompanyId(String companyId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCustomApplUserVars(String code);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setUsername(String username);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.callBusinessComponent(Long compId,Map additionalReqParams,Map decodedReqParams,Map decodedFilterNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setPassword(String pwd);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setContextValue(String varName,String varValue);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.debugVariable(String variableName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addCustomApplUserVars(String code,String value);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createTextFile(String fileName,String fileContent,Boolean overwrite,Long directoryId,String charset);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createTextFile(String fileName,String fileContent,Boolean overwrite,Long directoryId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createCSVFile(String fileName,Boolean overwrite,Long directoryId,List data,String sep,String languageId,String[] exportAttributes,String[] exportColumns,String[] formatColumns,boolean printTitles,Boolean fileAppend);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createCSVFile(String fileName,Boolean overwrite,Long directoryId,List data,String sep,String languageId,String[] exportAttributes,String[] exportColumns,String[] formatColumns,boolean printTitles);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getColumnsInTable(Long datastoreId,String tableName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getRelation(Long dataStoreId,String fkTable,String pkTable);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObject(Map obj,String tableName,Long dataSourceId,Boolean separatedTransaction,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.saveGridExportInCSV(String appId,String companyId,Long siteId,String username,String password,String platformBaseUrl,String functionId,Long panelId,List filters,List orders,List attributes,List titles,String title,String toFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteMappedObject(Map neutralObject,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteMappedObject(Map neutralObject,String tableName,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObject(Map obj,Boolean emptyAsNull,Boolean forceAttributesToNull,String tableName,Long dataSourceId,Boolean separatedTransaction,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getTablesInDataStore(Long datastoreId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateMappedObject(Map neutralObject,Boolean emptyAsNull,Boolean forceAttributesToNull,String tableName,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateMappedObject(Map neutralObject,Boolean emptyAsNull,Boolean forceAttributesToNull,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils._deleteMappedObject(Con14DataModel model,Long decodedDataStoreId,Con111MappedDatabase mdb,Long dataStoreId,Map neutralObject,String tableName,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils._updateMappedObject(Con14DataModel model,Long decodedDataStoreId,Con111MappedDatabase mdb,Long dataStoreId,Map neutralObject,Boolean emptyAsNull,Boolean forceAttributesToNull,String tableName,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enqueueShellCommand(String queueName,String cmd,String priority,Long processWaitTime,Boolean logExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getLanguageIdFromEmail(String email);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.forceStartProcess(String queueName,Long progressive);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSqlFile(String sqlFile,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEncodedRtk(String[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.dequeueProcess(String queueName,Long progressive);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enqueueWebService(String queueName,String url,Map params,String priority,Long processWaitTime,Boolean logExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getLanguageIdFromUsername(String username);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.waitAnyElement(String queueName,Long actionId,Long[] elementIds);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.waitAllElements(String queueName,Long actionId,Long[] elementIds);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.startThreadedAction(Long actionId,Long waitTime,Map args);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.blockingWaitAllElements(Long timeout,String[] elementIdsStr);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enqueueAction(String queueName,Long actionId,Map params,String priority,Long processWaitTime,Boolean logExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertStringToNumber(String number);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readBase64File(String filePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enqueueActionWithNote(String queueName,Long actionId,Map params,String priority,Long processWaitTime,Boolean logExecution,String note);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObject(Map obj,String tableName,Long dataSourceId,Boolean separatedTransaction,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertMappedObject(Map neutralObject,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertMappedObject(Map neutralObject,String tableName,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readTextFile(String fullPathName,String callbackFunName,String charSet);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readTextFile(String fileName,Long directoryId,String callbackFunName,String charSet);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readTextFile(String filePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readTextFile(String fileName,Long directoryId,String callbackFunName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readTextFile(String filePath,String charSet);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.writeBase64File(String filePath,String base64Content);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setReturnValue(Object returnValue);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getDataStoreId(Long dataStoreId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSqlReplaceVariables(String sql,String variablePrefix,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSqlNoLog(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQuery(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryWithCallback(String callbackFunName,String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryWithAlias(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Long dataModelId,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeMappedQuery(String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getQueryColumns(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDecodeField(String attributeName,String fieldName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDecodeOperator(String attributeName,String operator);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDecodeUpperCase(String attributeName,Boolean uppercase);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResult(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResult(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,String> attributesMap,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResult(String select,String from,String where,String orderBy,String groupBy,String having,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultNoCount(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Long totalCount,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultNoCount(String select,String from,String where,String orderBy,String groupBy,String having,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Long totalCount,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getMappedPartialResult(String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String> attributesMap,Long totalCount,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeStoredFunction(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getResourceByLanguageId(String entry,String languageId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCustomResource(String entry);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.numberToText(Number num,Number decimals,String languageId,Boolean showDecimals,String sep);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setCompanyId(String companyId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getInitialValue);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getBasePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendEmailWithTemplate(String subject,Long templateId,Map jsObj,String from,String to,String cc,String bcc,String priority,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Long dirId,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getDirectoryPath(Long directoryId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendEmailWithSMTPSettings(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendEmailWithSMTPSettings(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getProgressive(String tableName,String columnName,Boolean separatedTransaction,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCurrentDate);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCurrentDateAndTime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertStringToDate(String dateAsString,String format);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertUTCStringToDate(String utcDateAsString);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertDateToString(Date date,String format);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertDateToSqlDate(Date date);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertDateToTimestamp(Date date);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendChatMessage(String from,String message,String destinations,String priority,Long conversationId,String messageTag);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendChatMessage(String from,String message,String destinations,String priority);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertMessage(String from,String message,String destinations,String priority);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertMessage(String from,String message,String destinations,String priority,Long conversationId,String messageTag);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendJavascriptMessage(String from,Map obj,String destinations,String functionName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmail(String from,String subject,String message,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,boolean returnReceipt,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmail(String from,String subject,String message,String destinations,String priority,boolean isHtmlContent,boolean returnReceipt,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplate(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplate(String from,Number templateId,String destinations,String priority,boolean isHtmlContent,Map jsObj,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplate(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeShellCommand(String command,String[] arguments);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWebContent(String uri,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWebContent(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWebContentWithHeaders(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,String charSet,Map headers);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWebContentWithSettings(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,String charSet,Map headers,Number timeout,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getBinaryContent(String toFile,String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.findTagsByPath(Map[] xmlDoc,String path);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.findTagsByNames(Map[] nodes,String[] tagNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.generateXML(Map jsonObj,String header,String rootNode,Long dirId,String fileName,String> attrMapping,Map listMapping,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getJSONString(Map obj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getJSONObject(Map obj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getJSONList(Map[] aux);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeAttribute(String host,Integer port,String filterDN,String ldapUsername,String ldapPassword,String attributeNameToRemove,String attributeValueToRemove);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEntriesList(String host,Integer port,String baseDN,String ldapUsername,String ldapPassword,String searchAttributes,String> attributesListToRead);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getMultipleValuesList(String host,Integer port,String baseDN,String ldapUsername,String ldapPassword,String searchAttributes,String attributeName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createEntry(String host,Integer port,String ldapUsername,String ldapPassword,String baseDN,String entryName,String entryType,String entryDescription,String[] attributeNamesValues);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getListResponse(Map[] list,Number resultSetLength,Boolean moreRows);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.formatNumber(Number value,Boolean grouping,String groupingSymbol,Number decimals,String decimalSymbol);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createAllowedUrl(String baseUrl,Long actionId,String aName,String aValue,String rName,String rValue,String params,Long expirationDays,Long maxTimes,String message);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createAllowedLink(Long expirationDays,Long maxTimes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createAllowedLinkWithRtk(Long expirationDays,Long maxTimes,String rtk);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.saveDocument(String reportName,String dirReports,Long datastoreId,Long compId,String reportFormat,Object> reportParams,String savePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.printDocument(String printerName,int copies,Integer mediaSize,Object> printParams,String reportName,String dirReports,Long datastoreId,String reportFormat,Object> reportParams);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPrintServices);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.encodePassword(String password);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.decodePassword(String encriptedPassword);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getConversation(Long conversationId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getConversationFromTag(String messageTag);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCertMessageFromPdf(Long srcDirectoryId,Long destDirectoryId,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCertMessage(Long srcDirectoryId,Long destDirectoryId,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCertMessage(String srcFileName,String destFolder);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.moveMessages(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String[] messageIds,String folderName,String moveToFolder,Boolean setAsSeen,Boolean debug);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.markMessagesAsSeen(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String[] messageIds,String folderName,Boolean setAsSeen,Boolean debug);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteMessages(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String[] messagesToDelete,Date startSendDateFilter,Date endSendDateFilter,Date startReceiveDateFilter,Date endReceiveDateFilter,String folderName,String trashName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteMessages(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String[] messageIdsToDelete,Integer[] messageNumbersToDelete,String folderName,String trashName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.forwardEmail(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String to,String subject,String text,String messageId,String smtpHost,String smtpPort,String smtpProtocol,String smtpUsername,String smtpPassword);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setAttributeValue(String attributeName,Object value);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setVariable(String attributeName,Object value);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyCompanyId(String startingCompanyId,String newCompanyId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyCompanyId(String startingCompanyId,String newCompanyId,String newCorporateName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.camelToSnake(String str,boolean toUpperCase);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.openPDFFile(String fileName,Long directoryId,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addPageToPDFFile(String uuid);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addLineToPDFFile(String uuid,String line,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.movePDFPage(String uuid,int page);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPDFPageCount(String uuid);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPDFOrientation(String uuid);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setLineToPDFFile(String uuid,int x,int y,String line,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.closePDFFile(String uuid);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addBackgroundToPdf(Long dirId,String pdfFile,String background,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.stringifyForDatabaseField(Object obj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getTxtFileCharset(String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCellsValue(Long directoryId,String fileName,List coordinates,List functions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeValueImportFunction(String function,String sheetName,Map values);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.decodeBase64(String plainText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.closeCSVFile(String uuid);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.openTextFile(String fileName,Boolean overwrite,Long directoryId,Boolean fileAppend);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.openTextFile(String fileName,Boolean overwrite,Long directoryId,Boolean fileAppend,String charset);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.writeToTextFile(String uuid,String text);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.closeTextFile(String uuid);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readCSVFile(String fileName,Long directoryId,String sep,Boolean skipFirstRow,String callbackFunName,String[] attributeNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readCSVFile(String fileName,Long directoryId,String sep,Boolean skipFirstRow,String callbackFunName,String[] attributeNames,String charSet);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.readCSVFileAndWriteToTable(String fileName,Long directoryId,String sep,Boolean skipFirstRow,Long datastoreId,String tableName,Map defaultFieldNames,Map[] csvFields);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeLinkedDevices);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createChatGroup(String groupName,String myPhoneNumber,String> contactNames,String> contactPhoneNumbers);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addMembersToChatGroup(String groupId,String myPhoneNumber,String> contactNames,String> contactPhoneNumbers);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeMembersFromChatGroup(String groupId,String myPhoneNumber,String> contactPhoneNumbers);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createChatContact(Con89ChatContact person);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getXlsContent(String dirId,String fileName,int sheetIndex,int fromRow,String[] attributeNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getXlsContentWithEncoding(String dirId,String fileName,String encoding,int sheetIndex,int fromRow,String[] attributeNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCsvContent(String sep,String dirId,String fileName,Integer startRow,Integer blockSize,Boolean removeEmptyValues,String[] attributeNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getVariable(String varName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFilesInPath(String path);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createRoleForApplication(String appId,String companyId,Long siteId,String roleId,String description);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCompanyApplParameter(String companyId,Long siteId,String paramId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addUserRole(String companyId,Long siteId,String userCodeId,Map[] roles);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updatePeopleData(String companyId,Long siteId,String userCodeId,Map data);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getUserRoles(String companyId,Long siteId,String userCodeId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addUserRoleForApplication(String appId,String companyId,Long siteId,String userCodeId,Map[] roles);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateUserRole(String companyId,Long siteId,String userCodeId,Map[] roles);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.userRoleActive(String companyId,Long siteId,String userCodeId,String roleId,Date activeDate);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getDataModelAttrTypes(Long dataModelId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.backupDirFiles(Long baseDirId,Long toDirId,String ftpHost,Long ftpPort,String ftpUseSSL,String ftpUsername,String ftpPassword,String ftpDestination,String suffixZipFile,Long availbaleBackup);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.applicationExportBackup(Long toDirId,String ftpHost,Long ftpPort,String ftpUseSSL,String ftpUsername,String ftpPassword,String ftpDestination,Long availbaleBackup);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.renameFTPFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String fromFileName,String toFileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.renameFTPFile(String host,Integer port,Boolean useSSL,String username,String password,String fromFileName,String toFileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFTPFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileName,Integer sessionTimeout);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFTPFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFTPFile(String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createFTPDirectories(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String directories);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addResponseHeader(String headerName,String headerValue);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.checkFunctionId(String functionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.checkRoleId(String roleId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.decodeEncToken(String encToken);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEncToken(String[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertXMLToHTML(Long xmlDirId,String xmlFileName,Long xslDirId,String xslFileName,Long htmlDirId,String htmlFileName,Boolean namespaceAware,Boolean validating);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getSchedNextActivationTime(Long schedId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setHttpResponseCode(int httpResponseCode);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getHttpResponseCode);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.logServiceElaboration(String logType,String logMessage,String messageCode,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.logServiceElaborationTag(Long tagNumber,String tagValue);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setElaborationState(String elaborationState,String result);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.terminateElaborationState(String elaborationState,String result,String logType,String logMessage,String messageCode);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.logServiceFileElaboration(String operation,Boolean elaborated,String fileName,Long directoryId,String backupFilename,Long backupDirectoryId,String note);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.logServiceFileElaboration(String operation,Boolean elaborated,String fileName,Long directoryId,String backupFilename,Long backupDirectoryId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.logServiceFileElaboration(String operation,String state,String fileName,Long directoryId,String backupFilename,Long backupDirectoryId,String note);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getBlobAsBase64(Long datastoreId,String sql,Object[] params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateBlobInPRM17(String appId,String fromCompanyId,String toCompanyId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getMimeType(String filename);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCurrentTime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getObjectTime(int hours,int minutes,int seconds);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWindowPanelsNavigateTree(Long windowId,String treeTranslation,String[] excludedProperties);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.checkCellsWithMetadataForImport(Long directoryId,String fileName,Long valueImportId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importSubFolderInWebContext(String appId,String subfolderName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryReplaceVariables(String sql,String variablePrefix,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeMappedQueryWithCallback(String callbackFunName,String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getMappedPartialResultWithFieldsToOmit(String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String> attributesMap,Long totalCount,String[] fieldsToOmit,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getMappedPartialResultWithFieldsToInclude(String select,String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String> attributesMap,Long totalCount,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendEmailWithMessageTemplate(String subject,String messageTemplate,Map jsObj,String from,String to,String cc,String bcc,String priority,Boolean isHtmlContent,Boolean returnReceipt,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Boolean zipFiles,Long dirId,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendEmailWithMessageTemplateWithSettings(String subject,String messageTemplate,Map jsObj,String from,String to,String cc,String bcc,String priority,Boolean isHtmlContent,Boolean returnReceipt,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Boolean zipFiles,Map additionalSettings,Long dirId,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getProgressiveForApplicationId(String appId,String tableName,String columnName,Boolean separatedTransaction,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertUTCStringToTimeZoneDate(String utcDateAsString,int hrs);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailWithConversation(String from,String subject,String message,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailWithConversation(String from,String subject,String message,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailWithConversation(String from,String subject,String message,String destinations,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailWithEmailAddresses(String fromEmail,String subject,String message,String destinationsEmail,String priority,boolean isHtmlContent,boolean returnReceipt,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithConversation(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithConversation(String from,Number templateId,String destinations,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithConversation(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWebContentWithHeadersAndCookies(String uri,boolean replaceVariables,String httpMethod,String contentType,Object requestBody,String user,String pwd,String charSet,Map headers,Number timeout,boolean cookie,Long dirId,String sendFileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWebContentWithHeadersAndCookies(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,String charSet,Map headers,Number timeout);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getBinaryContentWithSettings(String toFile,String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enqueueActionWithNoteAsString(String queueName,Long actionId,Map params,String priority,Long processWaitTime,Boolean logExecution,String note,Integer maxRetries);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.saveGridExportInExtendedCSV(String appId,String companyId,Long siteId,String username,String password,String platformBaseUrl,String functionId,Long panelId,List filters,List orders,List attributes,List titles,String title,String toFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getDriverNameDefaultConnection);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertSecondToHoursMinutesSeconds(Long seconds);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailWithEmailAddressesWithConversation(String fromEmail,String subject,String message,String destinationsEmail,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailWithEmailAddressesWithConversation(String fromEmail,String subject,String message,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddresses(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddresses(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithConversationAndSMTPSettings(String from,Number templateId,String destinations,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithConversationAndSMTPSettings(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithConversationAndSMTPSettings(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversation(String fromEmail,Number templateId,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversation(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversation(String fromEmail,Number templateId,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddressesWithSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddressesWithSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversationAndSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversationAndSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversationAndSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String[] filesToAttach);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.log(String msg,String logType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.replaceAll(String text,String pattern,String changedValue);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.trim(String text);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.info(String msg);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getResource(String entry);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.debug(String msg);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.suspend(String suspendingId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.suspend);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.resume);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String ftpDir,String ftpFileName,String localFile,Integer sessionTimeout);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String ftpDir,String ftpFileName,String localFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFile(String host,Integer port,Boolean useSSL,String username,String password,String ftpDir,String ftpFileName,String localFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.round(Number num,int decimals);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.error(String msg);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.mkdir(String path);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.warn(String msg);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addAttribute(String host,Integer port,String filterDN,String ldapUsername,String ldapPassword,String attributeNameToAdd,String attributeValueToAdd);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGroup(String host,Integer port,String ldapUsername,String ldapPassword,String baseDN,String folderDN,String groupName,String[] additionalAttributeNamesValues);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCount(String tableName,String valueColumnName,String incrementValue,String where,Boolean separatedTransaction,Boolean interruptExecution,Long dataSourceId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getCount(String tableName,String valueColumnName,String incrementValue,String where,Boolean separatedTransaction,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addDate(String date,String format,String field,Number amount);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addDate(Long currentTimeMillis,String field,Number amount);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addDate(String field,Number amount);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setContentType(String contentType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getParameter(String paramName);
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
utils.deleteDir(Long dirId,String subFolder);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addISO8601(Date dt,String period);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.encodeJWT(Map dataToSend,String sharedKey);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.mergeDocx(Long srcDirId,String[] docxNames,Long destDirId,String mergedDocxName,Boolean deleteFilesAfterMerge);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImport(Long sourceDirId,Long destDirId,Long backupDirId,Long dataSourceId,String tableName,String csvFileName,String csvFileNameField,String csvUniqueIdField,String csvSep,Object> defaultValues,String> mapping,String nullString,Boolean skipWithErrors,Boolean skipFileNotInCSV,Long beforeInsertActionId,Long afterInsertActionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.unzipFile(Long zipDirId,String zipFileName,String serverFileSystemDir);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getUUID);
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
utils.updateCard(Long dataModelId,Long panelId,Map vo);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteCard(Long dataModelId,Long panelId,Map vo);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDatasetId(String datasetId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setBlockSize(int blockSize);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setStartIndex(int startIndex);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertListWithMapper(String json,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleTokenResponse(String token);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getValueInCache(String varName,String alternativeFunctionName);
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
utils.addValueInCache(String varName,Object value);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addValueInCache(String varName,Object value,Long expirationTime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertISO8601(String period);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleCalendarEvent(String title,Date beginDate,Date endDate);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.modifyGoogleCalendarEvent(String calendarEventId,String title,Date beginDate,Date endDate);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleCalendarEvent(String calendarEventId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleContactsFiltered(Integer pages,Integer maxPageResults,String searchString,Boolean splitEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleContact(String name,String surname,String email,String phone,Boolean shared);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateGoogleContact(String contactId,String name,String surname,String email,String phone,Boolean shared);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleContact(String contactId,Boolean shared);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sharedContatctsSync);
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
utils.createGoogleDriveFolder(String userId,String folderName,String> parents,String description);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleDriveFolder(String folderName,String> parents,String description);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFile(String userId,String fileId,boolean skipTrash);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFile(String fileId,boolean skipTrash);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileInfo(String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileInfo(String userId,String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileOpenURL(String fileId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileProperty(String userId,String fileId,String key,String visibility);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileProperty(String fileId,String key,String visibility);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.moveGoogleDriveFile(String fileId,String newParent,boolean addToRevision);
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
utils.moveGoogleDriveFile(String fileId,String newParents);
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
utils.updateGoogleDriveFile(String userId,String fileId,String title,String description,String mimeType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateGoogleDriveFile(String fileId,String title,String description,String mimeType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateGoogleDriveFile(String userId,String sourceFolderId,String destinationFolderId,String newFileName,Boolean copyPermissions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.searchInGoogleDrive(String userId,Integer maxPageResults,Integer pages,String nextPageToken,String folderId,Boolean recursive,String query,Boolean trashed);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.searchInGoogleDrive(Integer maxPageResults,Integer pages,String nextPageToken,String folderId,Boolean recursive,String query,Boolean trashed);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setPublicLink(String bucketName,String objectName,Boolean publicLink);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleOAuth2AccessToken(String[] scopes);
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
utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities,Long expirationTime);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearDatastoreEntities(String entityName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeValueInCache(String varName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearAllDatastoreEntities);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnMongoDb(String where,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnMongoDb(String where,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.startActivitiProcess(String appId,String processDefinitionId,Map params,Map processVariables);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.completeActivitiTask(String processInstanceId,Map params,Map processVariables);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getProcessDefinition(String processDefinitionId,Map params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getAlfrescoDocument(String id,String fileName,String destPath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getAlfrescoWebScript(String uri,boolean replaceVariables,String httpMethod,String bodyRequest);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getAlfrescoWebScript(String uri,boolean replaceVariables,String httpMethod,String bodyRequest,String charSet);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.generateDocx(Long reportId,Object> args,String langId,String path,String fileName);
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
utils.sendSmsMessage(String fromPhoneNr,String toPhoneNr,String text,Boolean logMessage);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getShortUrl(String realUrl);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertUrlToImage(String url,String imagePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertHtmlToImage(String html,String imagePath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeAction(Long actionId,Map vo,Map params,Map headers);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addFileToMobileDevices(String fullPathName,String fileName,String username);
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
utils.scaleJpgFile(Long srcJpgDirId,String srcJpgFileName,Long destDirId,String destFileName,Long scale);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.scaleJpgFile(Long srcJpgDirId,String srcJpgFileName,Long destDirId,String destFileName,Long maxWidth,Long maxHeight);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importFileInCMS(String path,Long destDirId,Long dataSourceId,String tableName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importFileInCMS(Long sourceDirId,String fileName,Long destDirId,Long dataSourceId,String tableName);
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
utils.deleteFileFromCMS(String uuid);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImportFromFTP(String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter,Long destDirId,Long backupDirId,Long dataSourceId,String tableName,String csvFileName,String csvFileNameField,String csvUniqueIdField,String csvSep,Object> defaultValues,String> mappingCsvToFields,String nullString,Boolean skipWithErrors,Boolean skipFileNotInCSV,Long beforeInsertActionId,Long afterInsertActionId);
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
utils.getKeysFromCache(String keyPrefix);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeValuesFromCache(String keyPrefix);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getInfoFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive,Boolean removeEmptyDir);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createConDbForCurrentUser(String companyId,Long siteId,String username);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGooglePrivateKeyString(String key);
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
utils.sendPushNotification(String appId,String[] userCodeIds,String title,String shortMessage,Long actionId,String json,Long badgeNr);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendSinglePushNotification(String appId,String firebaseId,String title,String shortMessage,Long actionId,String json,Long badgeNr,Map rootOptions,Map dataOptions,Map notificationOptions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createXlsContent(Long dirId,String fileName,String sheetName,Integer sheetIndex,Integer fromRow,Object>[] vos,String[] attributeNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getModifiedPks(String tableName,String field,Date changedStardDate,Date changedEndDate);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheetData(String userId,Long dataModelId,String spreadsheetId,String range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheetData(String userId,Long dataModelId,String spreadsheetId,String> range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheetData(String userId,String spreadsheetId,String> range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSheetData(String userId,String spreadsheetId,String range,String valueRenderOption,String dateTimeRenderOption);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleSpreadsheets(String userId,String spreadsheetTitle,String[] sheets);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleSheets(String userId,String spreadsheetId,String[] sheets);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleSheets(String userId,String spreadsheetId,Integer[] sheetIds);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateGoogleSheet(String userId,String spreadsheetId,Integer sourceSheetId,Integer insertSheetIndex,Integer newSheetId,String newSheetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyGoogleSheet(String userId,String spreadsheetId,Integer sheetId,String destinationSpreadsheetId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.appendRangeGoogleSheet(String userId,String spreadsheetId,String range,String valueInputOption,String insertDataOption,Object[][] vos);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateRangeGoogleSheet(String userId,String spreadsheetId,String range,String valueInputOption,Object[][] vos);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearRangeGoogleSheet(String userId,String spreadsheetId,String range);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createCsvFromSqlQuery(String sql,Long dataSourceId,Boolean includeRowNum,String replaceNullWith,Long fromRow,Long maxRowsToRead,String firstRow,String sep,Long dirId,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendTensorFlowCsvFromCsv(String csvFilePath,Boolean includeFirstRow,Boolean includeRowNum,int resultValuesNr,Long dirId,String topic,String cmd,Long pkIndex,Map jsObj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.matchTensorFlowCsvResults(Long dirId,Long dataSourceId,String tableName,Map jsObj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.analyzeSentiment(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.analyzeEntitySentiment(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.analyzeEntities(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.analyzeSyntax(String text,String encodingType,Boolean htmlText);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.classifyText(String text,Boolean htmlText);
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
utils.executeAllExports(String queryType,Map paramValues);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.callGaeAction(Long actionId,Boolean async);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enqueueGaeAction(String queueName,Long actionId,Map params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getElementFromQueueByNote(String note,String namespace);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryDataset(String datasetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteBigQueryDataset(String datasetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryTable(String datasetName,String tableName,Map> columns);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteBigQueryTable(String datasetName,String tableName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeBigQuerySaveOnTable(String destinationDataset,String destinationTable,String defaultDataset,String sqlQuery,Object[] params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.extractBigQueryData(String datasetName,String tableName,String format,String gcsUrl,Boolean deleteTableAfterExport,Boolean exportHeaders);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getBigQueryDataset);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setBigQueryDataset(String bigQueryDataset);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryDataFromGCS(String datasetName,String tableName,String format,String sourceUri,String encoding,String separator);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertBigQueryObject(String datasetName,String tableName,Map obj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateBigQueryObject(String datasetName,String tableName,Map obj,String[] pks);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteBigQueryObject(String datasetName,String tableName,Map obj,String[] pks);
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
utils.createXLSXFileFromSQLQuery(Long templateDirectoryId,String templateFileName,String sheetName,Long outDirectoryId,String outFileName,Map[] formatHeaderColumns,Map[] formatColumns,Map grouping,Map additionalSettings,Long datastoreId,String sqlQuery,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.backupEntitiesInGCS(String[] entityNames,Long directoryId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setDatastoreNamespace(String namespace);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getDetailOnArchiflow(Long dataModelId,String cardId,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertCards(Long dataModelId,Long panelId,Map[] vos,Integer archiveId,Map additionalSettings,Long actionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertCards(Long dataModelId,Long panelId,Map[] vos,Integer archiveId,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateCards(Long dataModelId,Long panelId,Map[] vos);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteCards(Long dataModelId,Long panelId,Map[] vos);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadArchiflowDocument(Long dirId,String fileNameSrc,String cardId,String fileName,String documentTitle,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.downloadArchiflowDocument(Long dirId,String fileName,String cardId,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.validateAlexaRequest(String signingCertificateChainUrl,String baseEncoded64Signature,String requestBody);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportUsersToDatastore(String companyId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportUsersToDatastore);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.convertObjectWithMapper(String json,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteProcessInstance(String processInstanceId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getActivitiProcessAsJson(String id,Boolean includeSubProcesses,Map tasksDueDates);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.enquiryTasks(HashMap pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setTaskAssignee(String taskId,String assignee);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.closeActivitiTask(String processInstanceId,String taskDefinitionKey,String assignee,Map map);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.closeActivitiTask(String taskInstanceId,Map map);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendWhatsappMessage(String accountId,String secretKey,String fromNr,String toNumber,String message,String publicUrl);
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
utils.sendWhatsappMessage(String accountId,String secretKey,String fromNr,String toNumber,String message,String bucketName,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createStripeCustomer(String apiKey,Map customerData);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.prepareStripePayment(String apiKey,String publicKey,Long priceWithCents,String currency,String customerId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeStripePayment(String apiKey,Long priceWithCents,String currency,String customerId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGCPAuthToken(String user,String serviceAccountEmail,String privateKeyString,String[] _scopes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.generateGCPAuthToken(String user,String serviceAccountEmail,String privateKeyString,String redirectUri,String[] _scopes);
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
utils.mergeObjectOnGoogleSpanner(Map attributesToSet,String[] attributesToSetToNull,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSpannerDdl(String[] scripts);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImportFromDSToSpanner(String gql,Long datastoreDataModelId,boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeSpannerSql(String sql);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnBigQuery(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnBigQuery(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectsOnBigQuery(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectOnBigQuery(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectsOnBigQuery(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObjectOnBigQuery(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkImportFromDSToBigQuery(String gql,Long datastoreDataModelId,String location,String bigQueryTable,boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.maybeStartProcess(Long schedId,Boolean forceRunning,Boolean startNextProcesses);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.reinsertElements(String companyId,Long actionId,String queueName,String status,String id);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getWebContentWithNTLM(String url,String contentType,String httpMethod,String bodyRequest,String username,String password,String workstation,String domain,Map settings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGroupMembers(String userId,String groupId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.checkGoogleSSOToken(String ssoAuthToken);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleCalendarEventWithSettings(String serviceAccountEmail,String privateKeyString,String userId,String title,Date beginDate,Date endDate,String description,String location,String calendarId,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.addGoogleCalendarEventWithConference(String serviceAccountEmail,String privateKeyString,String userId,String title,Date beginDate,Date endDate,String description,String location,String calendarId,String type,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.modifyGoogleCalendarEventWithSettings(String calendarEventId,String title,Date beginDate,Date endDate,String description,String location,String creatorEmail,String[] attendeeEmails);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleCalendarEventWithSettings(String serviceAccountEmail,String privateKeyString,String userId,String calendarEventId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleSharedContactsFiltered(Integer pages,Integer maxPageResults,String searchString,Boolean splitEmails);
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
utils.deleteGoogleDriveFileProperty(String userId,String fileId,String key);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteGoogleDriveFileProperty(String fileId,String key);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDriveFileDownloadURL(String fileId);
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
utils.modifyGoogleDriveFileParents(String userId,String fileId,String parentsToAdd,String parentsToRemove);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.modifyGoogleDriveFileParents(String fileId,String parentsToAdd,String parentsToRemove);
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
utils.setGoogleDriveFileAttributes(String fileId,FileAttributes fileAttributes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFileAttributes(String userId,String fileId,FileAttributes fileAttributes);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFilePermissions(String fileId,String type,String value,String role,String> additionalRoles,boolean sendNotifications,String message);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleDriveFilePermissions(String userId,String fileId,String type,String value,String role,String> additionalRoles,boolean sendNotifications,String message);
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
utils.uploadGoogleDriveFileFromFS(String userId,String fsPath,String parentId,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleDriveFileFromFS(String fsPath,String parentId,boolean deleteFsFile);
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
utils.duplicateGoogleDriveFolderAndContents(String sourceFolderId,String newFolderName,String newFolderDescription,String destinationFolderId,String titlePrefix,Boolean copyPermissions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.duplicateGoogleDriveFolderAndContents(String userId,String sourceFolderId,String newFolderName,String newFolderDescription,String destinationFolderId,String titlePrefix,Boolean copyPermissions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.downloadFileFromGoogleDrive(String userId,String fileId,String localPath,String fileName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createGoogleCloudStorageBucket(String project,String bucketName,String bucketLocation,String storageClass);
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
utils.setGoogleCloudStorageBucketVersioning(String bucketName,Boolean versioning);
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
utils.downloadGoogleCloudStorageObject(String bucketName,String objectName,String destPath);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.listGoogleCloudStorageObjects(String bucketName,Long maxPageResults,Integer pages,String nextPageToken,String prefix,String delimiter);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.listGoogleCloudStorageObjects(String bucketName,String prefix,String delimiter);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.copyGoogleCloudStorageObject(String sourceBucketName,String sourceObjectName,Long sourceObjectVersion,String destinationBucketName,String destinationObjectName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleCloudStorageObjectFromFS(String fsPath,String bucketName,String objectName,Boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleCloudStoragePublicObjectFromFS(String fsPath,String bucketName,String objectName,Boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleCloudStorageObjectFromString(String textContent,String bucketName,String objectName,String contentType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.rewriteGoogleCloudStorageObject(String sourceBucketName,String sourceObjectName,Long sourceObjectVersion,String destinationBucketName,String destinationObjectName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getGoogleDomainContactsFiltered(Integer pages,Integer maxPageResults,String query,String orderBy,String sortOrder);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeCachedQueryOnGoogleDatastore(int maxCachedEntities,String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnGoogleDatastoreWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnGoogleDatastore(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnGoogleDatastore(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
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
utils.updateObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.mergeObjectOnGoogleDatastore(Map attributesToSet,String[] attributesToSetToNull,Long dataModelId,Boolean interruptExecution);
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
utils.bulkUpdateOnGoogleDatastore(String gql,Map attributesToSet,Map attributesToRemove,Long actionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.bulkDeleteOnGoogleDatastore(String gql);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeActionSameTransaction(Long actionId,Map vo,Map params,Map headers);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getButtonsAuthorizationOfUser);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getFunctionAuthorizationOfUser(String functionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getLastSynchronizationDevice);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.setGoogleServiceAccountEmail(String email);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendPushNotificationWithOptions(String appId,String[] userCodeIds,String title,String shortMessage,Long actionId,String json,Long badgeNr,Map rootOptions,Map dataOptions,Map notificationOptions);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.sendTensorFlowCsvFromSqlQuery(String sql,Long dataSourceId,Long fromRow,Long maxRowsToRead,String fieldName,Integer resultValuesNr,Long dirId,String fileName,Map jsObj);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeBigQueryWithCallback(String processRowFunName,String defaultDataset,String sqlQuery,Object[] params);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryDataFromLocalDatasource(String datasetName,String tableName,String location,String format,String csvPath,String encoding,String separator,Integer maxBadRecords,Boolean truncate,Boolean deleteSrcFileAfterImport);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importMultipleDataFromLocalDatasource(String datasetName,String[] tableNames,String location,String format,String dirPath,String[] csvFiles,String encoding,String separator,Integer maxBadRecords,Boolean truncate,Boolean deleteSrcFileAfterImport);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.importBigQueryThroughStreaming(String datasetName,String tableName,Object[] objectsForBQ);
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
utils.createTablesFromDatastoreBackup(String[] entityNames,String gcsURI,String datasetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.createBigQueryTableFromDatastoreEntities(String[] entityNames,Long directoryId,String datasetName);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnArchiflow(Long dataModelId,Map[] filters,Integer[] archiveIds,Boolean cardsWithAttachedDoc,Integer searchTypes,Map additionalSettings);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getActivitiLastVersionProcessId(String id);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getInvolvedNotAssignedTasks(HashMap pars,String username);
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
utils.getActivitiProcessInstancesVariables(String processInstanceId,String processDefinitionId);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportFromExcelFileToGSheet(Long sourceDirId,String sourceFileName,String spreadsheetId,List areas);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.exportFromExcelFileToGSheet(String userId,Long sourceDirId,String sourceFileName,String spreadsheetId,List areas);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeGoogleDriveFilePermissions(String fileId,String emailUser);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.removeGoogleDriveFilePermissions(String userId,String fileId,String emailUser);
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
utils.getPartialResultOnGoogleSpanner(String sql,Long dataModelId,Boolean interruptExecution,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.insertObjectsOnGoogleSpanner(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.updateObjectsOnGoogleSpanner(Map[] objs,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.deleteObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeQueryOnBigQueryWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map map,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnBigQueryWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
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
utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(String userId,String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,String fileName,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,String fileName,boolean deleteFsFile);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.uploadGoogleCloudStoragePublicObjectFromString(String textContent,String bucketName,String objectName,String contentType);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.executeCachedQueryOnGoogleDatastoreWithSetting(int maxCachedEntities,String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnGoogleDatastoreWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.getPartialResultOnGoogleSpannerWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object[] pars);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearCache(String varNames);
```
{% endcode %}

{% code overflow="wrap" lineNumbers="true" %}
```js
utils.clearCache(String varNames,String keys);
```
{% endcode %}
