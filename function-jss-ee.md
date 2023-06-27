# Function JSS EE

utils.protectPdf(String passwordRestriction,String passwordOwner,String fullPathSrc,String fullPathDst);

utils.getCatalog(Long datasourceId);

utils.executeSql(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.textToInt(String text);

utils.sendEmail(String smtpHost,String smtpPort,String useTLS,String protocol,String smtpUsername,String smtpPassword,String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String\[] filesToAttach);

utils.sendEmail(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,Long dirId,String fileName,String\[] filesToAttach);

utils.sendEmail(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String\[] filesToAttach);

utils.zipFiles(String baseDir,String\[] files,String zipFile,Boolean deleteFilesAfterZip);

utils.zipFiles(Long baseDirId,String zipFile,Boolean deleteFilesAfterZip);

utils.saveEml(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String folderName,String\[] messageIds,String\[] fileNames,Long directoryId);

utils.sendGmail(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String\[] filesToAttach);

utils.removeTime(Date date);

utils.parseXML(String xmlDocument);

utils.sendFiles(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String toDir,String\[] filePaths);

utils.sendFiles(String host,Integer port,Boolean useSSL,String username,String password,String toDir,String\[] filePaths);

utils.sendFiles(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String toDir,Integer sessionTimeout,String\[] filePaths);

utils.sendFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String destFile,String sourceFile);

utils.sendFile(String host,Integer port,Boolean useSSL,String username,String password,String destFile,String sourceFile);

utils.sendFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String destFile,Long directoryId,String fileName);

utils.sendFile(String host,Integer port,Boolean useSSL,String username,String password,String destFile,Long directoryId,String fileName);

utils.sendFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String destFile,Long directoryId,String fileName,Integer sessionTimeout);

utils.getFiles(Long dirId);

utils.getFiles(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter);

utils.getFiles(String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter);

utils.getFiles(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter,Integer sessionTimeout);

utils.getEmails(String server,Integer port,String username,String password,String protocol,Boolean useTLS,Integer maxMessagesToRead,Boolean notReadFilter,Date startSendDateFilter,Date endSendDateFilter,Date startReceiveDateFilter,Date endReceiveDateFilter,String fromAddressFilter,String subjectFilter,String bodyFilter,Boolean withAttachments,String attachmentsPath,String folderName,String moveToFolderOnceRead,Boolean setAsSeen,Boolean deleteEmailWhenRead,Boolean debug);

utils.getEmails(String server,Integer port,String username,String password,String protocol,Boolean useTLS,Integer maxMessagesToRead,Boolean notReadFilter,Date startDateFilter,String fromAddressFilter,String subjectFilter,String bodyFilter,Boolean withAttachments,String attachmentsPath,String folderName,String moveToFolderOnceRead,Boolean setAsSeen,Boolean deleteEmailWhenRead,Boolean debug);

utils.copyFile(String inBaseDir,String inFileName,String destPathFileName);

utils.copyFile(String srcFile,String destFile,Boolean replaceExistingFile,Boolean deleteSourceFile);

utils.camel(String fieldName,Boolean firstCharUpper);

utils.uncamel(String attributeName);

utils.debugAll);

utils.setSiteId(Long siteId);

utils.isOffLine);

utils.existUser(String companyId,Long siteId,String userCodeId);

utils.createRole(String companyId,Long siteId,String roleId,String description);

utils.createUser(String companyId,Long siteId,String userCodeId,String description,String password,String languageId,Map user,Map\[] roles);

utils.updateUser(String companyId,Long siteId,String userCodeId,String languageId,Map user);

utils.renameFile(Long directoryId,String oldFileName,String newFileName);

utils.unzip(Long directoryId,String zipFile,Long directoryIdOut,Boolean deleteZipFile);

utils.stringify(Object o);

utils.parseJSON(String json);

utils.md5(String text);

utils.sha256(String text);

utils.logInCon60(String logType,String msg,String messageTag);

utils.rPad(String value,char fillChar,int length);

utils.lPad(String value,char fillChar,int length);

utils.saveBlob(Map settings);

utils.fileExists(String filePath);

utils.convertStringToUTCDate(String date);

utils.createDbTableMetadata(Long datasourceId,String tableName);

utils.updateDbTableMetadata(Long dbTableId);

utils.createValueImports(Long dbTableId,Long directoryId,String fileName,String description,String note,String inputData,Long breakOnColumnsEmpty,Long breakOnRowsEmpty);

utils.duplicateValueImports(Long valueImportId,Long directoryId,String fileName,String description,String note,String inputData,Long breakOnColumnsEmpty,Long breakOnRowsEmpty,Boolean ignoreSheet);

utils.duplicateValueImports(Long valueImportId,Long directoryId,String fileName,String description,String note,String inputData,Long breakOnColumnsEmpty,Long breakOnRowsEmpty);

utils.importCellsFromExcelFile(Long directoryId,String fileName,Long valueImportId,Map fieldsData,Map inputData,Boolean separatedTransaction);

utils.exportFromExcelFile(Long sourceDirId,String sourceFileName,Long destDirId,String destFileName,List areas);

utils.deleteValueImport(Long valueImportId);

utils.disableValueImport(Long valueImportId);

utils.executeSqlBatch(Map settings);

utils.setImagesInXls(Long dirId,String srcFileName,String destFileName,String sheetName,Map> images);

utils.getSheetListFromExcelFile(Long dirId,String fileName);

utils.copyImportRowsFromFile(Long importId,String newDescription);

utils.importRowsFromFile(Long dirId,String fileName,Long importId,boolean insert,Long maxErrors,Long maxRowErrors,Map inputData,Long destErrorsFileDirId,String destErrorsFileName,boolean rollbackIfErrors,boolean async);

utils.importRowsFromFile(Long dirId,String fileName,Long importId,boolean insert,Long maxErrors,Long maxRowErrors,Map inputData,Long destErrorsFileDirId,String destErrorsFileName,boolean rollbackIfErrors,boolean async,String sheetTitle);

utils.getExcelRowsBlock(Long dirId,String fileName,Long sheetIndex,Long fromRow,Long toRow,String\[] attributeNames);

utils.getEnvironment);

utils.getCachedProgressive(Map settings);

utils.getFileLength(String fileAbsolutePath);

utils.enqueueActionsFromSqlQuery(String queueName,String payload,Long actionId,Long datasourceId,String sqlQuery,Object\[] params);

utils.getColumnsInQuery(Long datastoreId,String query);

utils.readCsvAndLoadTable(Map settings);

utils.mapClobFieldToTable(Map settings);

utils.validateCode(Map settings);

utils.copyDataFromBorderTable(Map settings);

utils.writeToCSVFile(String uuid,Map obj);

utils.writeToCSVFile(String uuid,Map obj,String rowSeparator);

utils.createCSVFileFromSQLQuery(String fileName,Boolean overwrite,Long directoryId,String sep,String languageId,Boolean printTitles,Boolean fileAppend,String\[] formatColumns,Long datasourceId,String sqlQuery,Object\[] pars);

utils.createCSVFileFromSQLQuery(String fileName,Boolean overwrite,Long directoryId,String sep,String languageId,Boolean printTitles,Boolean fileAppend,String charset,String\[] formatColumns,Long datasourceId,String sqlQuery,Object\[] pars);

utils.openCSVFile(String fileName,Boolean overwrite,Long directoryId,String sep,Boolean fileAppend,String\[] attributesToWrite,String\[] formatters);

utils.forceCompanyId(String companyId);

utils.getCustomApplUserVars(String code);

utils.setUsername(String username);

utils.callBusinessComponent(Long compId,Map additionalReqParams,Map decodedReqParams,Map decodedFilterNames);

utils.setPassword(String pwd);

utils.setContextValue(String varName,String varValue);

utils.debugVariable(String variableName);

utils.addCustomApplUserVars(String code,String value);

utils.createTextFile(String fileName,String fileContent,Boolean overwrite,Long directoryId,String charset);

utils.createTextFile(String fileName,String fileContent,Boolean overwrite,Long directoryId);

utils.createCSVFile(String fileName,Boolean overwrite,Long directoryId,List data,String sep,String languageId,String\[] exportAttributes,String\[] exportColumns,String\[] formatColumns,boolean printTitles,Boolean fileAppend);

utils.createCSVFile(String fileName,Boolean overwrite,Long directoryId,List data,String sep,String languageId,String\[] exportAttributes,String\[] exportColumns,String\[] formatColumns,boolean printTitles);

utils.getColumnsInTable(Long datastoreId,String tableName);

utils.getRelation(Long dataStoreId,String fkTable,String pkTable);

utils.deleteObject(Map obj,String tableName,Long dataSourceId,Boolean separatedTransaction,Boolean interruptExecution);

utils.saveGridExportInCSV(String appId,String companyId,Long siteId,String username,String password,String platformBaseUrl,String functionId,Long panelId,List filters,List orders,List attributes,List titles,String title,String toFile);

utils.deleteMappedObject(Map neutralObject,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String\[] pks);

utils.deleteMappedObject(Map neutralObject,String tableName,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String\[] pks);

utils.updateObject(Map obj,Boolean emptyAsNull,Boolean forceAttributesToNull,String tableName,Long dataSourceId,Boolean separatedTransaction,Boolean interruptExecution);

utils.getTablesInDataStore(Long datastoreId);

utils.updateMappedObject(Map neutralObject,Boolean emptyAsNull,Boolean forceAttributesToNull,String tableName,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution,String\[] pks);

utils.updateMappedObject(Map neutralObject,Boolean emptyAsNull,Boolean forceAttributesToNull,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution,String\[] pks);

utils.\_deleteMappedObject(Con14DataModel model,Long decodedDataStoreId,Con111MappedDatabase mdb,Long dataStoreId,Map neutralObject,String tableName,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String\[] pks);

utils.\_updateMappedObject(Con14DataModel model,Long decodedDataStoreId,Con111MappedDatabase mdb,Long dataStoreId,Map neutralObject,Boolean emptyAsNull,Boolean forceAttributesToNull,String tableName,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution,String\[] pks);

utils.enqueueShellCommand(String queueName,String cmd,String priority,Long processWaitTime,Boolean logExecution);

utils.getLanguageIdFromEmail(String email);

utils.forceStartProcess(String queueName,Long progressive);

utils.executeSqlFile(String sqlFile,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.getEncodedRtk(String\[] pars);

utils.dequeueProcess(String queueName,Long progressive);

utils.enqueueWebService(String queueName,String url,Map params,String priority,Long processWaitTime,Boolean logExecution);

utils.getLanguageIdFromUsername(String username);

utils.waitAnyElement(String queueName,Long actionId,Long\[] elementIds);

utils.waitAllElements(String queueName,Long actionId,Long\[] elementIds);

utils.startThreadedAction(Long actionId,Long waitTime,Map args);

utils.blockingWaitAllElements(Long timeout,String\[] elementIdsStr);

utils.enqueueAction(String queueName,Long actionId,Map params,String priority,Long processWaitTime,Boolean logExecution);

utils.convertStringToNumber(String number);

utils.readBase64File(String filePath);

utils.enqueueActionWithNote(String queueName,Long actionId,Map params,String priority,Long processWaitTime,Boolean logExecution,String note);

utils.insertObject(Map obj,String tableName,Long dataSourceId,Boolean separatedTransaction,Boolean interruptExecution);

utils.insertMappedObject(Map neutralObject,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution);

utils.insertMappedObject(Map neutralObject,String tableName,Long dataModelId,Map additionalAttributes,Boolean separatedTransaction,Boolean interruptExecution);

utils.readTextFile(String fullPathName,String callbackFunName,String charSet);

utils.readTextFile(String fileName,Long directoryId,String callbackFunName,String charSet);

utils.readTextFile(String filePath);

utils.readTextFile(String fileName,Long directoryId,String callbackFunName);

utils.readTextFile(String filePath,String charSet);

utils.writeBase64File(String filePath,String base64Content);

utils.setReturnValue(Object returnValue);

utils.getDataStoreId(Long dataStoreId);

utils.executeSqlReplaceVariables(String sql,String variablePrefix,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.executeSqlNoLog(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.executeQuery(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.executeQueryWithCallback(String callbackFunName,String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.executeQueryWithAlias(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Long dataModelId,Object\[] pars);

utils.executeMappedQuery(String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.getQueryColumns(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.setDecodeField(String attributeName,String fieldName);

utils.setDecodeOperator(String attributeName,String operator);

utils.setDecodeUpperCase(String attributeName,Boolean uppercase);

utils.getPartialResult(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.getPartialResult(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,String> attributesMap,Object\[] pars);

utils.getPartialResult(String select,String from,String where,String orderBy,String groupBy,String having,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.getPartialResultNoCount(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Long totalCount,Object\[] pars);

utils.getPartialResultNoCount(String select,String from,String where,String orderBy,String groupBy,String having,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Long totalCount,Object\[] pars);

utils.getMappedPartialResult(String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String> attributesMap,Long totalCount,Object\[] pars);

utils.executeStoredFunction(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.getResourceByLanguageId(String entry,String languageId);

utils.getCustomResource(String entry);

utils.numberToText(Number num,Number decimals,String languageId,Boolean showDecimals,String sep);

utils.setCompanyId(String companyId);

utils.getInitialValue);

utils.getBasePath);

utils.sendEmailWithTemplate(String subject,Long templateId,Map jsObj,String from,String to,String cc,String bcc,String priority,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Long dirId,String\[] filesToAttach);

utils.getDirectoryPath(Long directoryId);

utils.sendEmailWithSMTPSettings(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String\[] filesToAttach);

utils.sendEmailWithSMTPSettings(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String\[] filesToAttach);

utils.getProgressive(String tableName,String columnName,Boolean separatedTransaction,Boolean interruptExecution);

utils.getCurrentDate);

utils.getCurrentDateAndTime);

utils.convertStringToDate(String dateAsString,String format);

utils.convertUTCStringToDate(String utcDateAsString);

utils.convertDateToString(Date date,String format);

utils.convertDateToSqlDate(Date date);

utils.convertDateToTimestamp(Date date);

utils.sendChatMessage(String from,String message,String destinations,String priority,Long conversationId,String messageTag);

utils.sendChatMessage(String from,String message,String destinations,String priority);

utils.sendAlertMessage(String from,String message,String destinations,String priority);

utils.sendAlertMessage(String from,String message,String destinations,String priority,Long conversationId,String messageTag);

utils.sendJavascriptMessage(String from,Map obj,String destinations,String functionName);

utils.sendAlertEmail(String from,String subject,String message,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,boolean returnReceipt,String\[] filesToAttach);

utils.sendAlertEmail(String from,String subject,String message,String destinations,String priority,boolean isHtmlContent,boolean returnReceipt,String\[] filesToAttach);

utils.sendAlertEmailFromTemplate(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,String\[] filesToAttach);

utils.sendAlertEmailFromTemplate(String from,Number templateId,String destinations,String priority,boolean isHtmlContent,Map jsObj,String\[] filesToAttach);

utils.sendAlertEmailFromTemplate(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long dirId,String fileName,String\[] filesToAttach);

utils.executeShellCommand(String command,String\[] arguments);

utils.getWebContent(String uri,Map settings);

utils.getWebContent(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd);

utils.getWebContentWithHeaders(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,String charSet,Map headers);

utils.getWebContentWithSettings(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,String charSet,Map headers,Number timeout,Map additionalSettings);

utils.getBinaryContent(String toFile,String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd);

utils.findTagsByPath(Map\[] xmlDoc,String path);

utils.findTagsByNames(Map\[] nodes,String\[] tagNames);

utils.generateXML(Map jsonObj,String header,String rootNode,Long dirId,String fileName,String> attrMapping,Map listMapping,Map settings);

utils.getJSONString(Map obj);

utils.getJSONObject(Map obj);

utils.getJSONList(Map\[] aux);

utils.removeAttribute(String host,Integer port,String filterDN,String ldapUsername,String ldapPassword,String attributeNameToRemove,String attributeValueToRemove);

utils.getEntriesList(String host,Integer port,String baseDN,String ldapUsername,String ldapPassword,String searchAttributes,String> attributesListToRead);

utils.getMultipleValuesList(String host,Integer port,String baseDN,String ldapUsername,String ldapPassword,String searchAttributes,String attributeName);

utils.createEntry(String host,Integer port,String ldapUsername,String ldapPassword,String baseDN,String entryName,String entryType,String entryDescription,String\[] attributeNamesValues);

utils.getListResponse(Map\[] list,Number resultSetLength,Boolean moreRows);

utils.formatNumber(Number value,Boolean grouping,String groupingSymbol,Number decimals,String decimalSymbol);

utils.createAllowedUrl(String baseUrl,Long actionId,String aName,String aValue,String rName,String rValue,String params,Long expirationDays,Long maxTimes,String message);

utils.createAllowedLink(Long expirationDays,Long maxTimes);

utils.createAllowedLinkWithRtk(Long expirationDays,Long maxTimes,String rtk);

utils.saveDocument(String reportName,String dirReports,Long datastoreId,Long compId,String reportFormat,Object> reportParams,String savePath);

utils.printDocument(String printerName,int copies,Integer mediaSize,Object> printParams,String reportName,String dirReports,Long datastoreId,String reportFormat,Object> reportParams);

utils.getPrintServices);

utils.encodePassword(String password);

utils.decodePassword(String encriptedPassword);

utils.getConversation(Long conversationId);

utils.getConversationFromTag(String messageTag);

utils.getCertMessageFromPdf(Long srcDirectoryId,Long destDirectoryId,String fileName);

utils.getCertMessage(Long srcDirectoryId,Long destDirectoryId,String fileName);

utils.getCertMessage(String srcFileName,String destFolder);

utils.moveMessages(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String\[] messageIds,String folderName,String moveToFolder,Boolean setAsSeen,Boolean debug);

utils.markMessagesAsSeen(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String\[] messageIds,String folderName,Boolean setAsSeen,Boolean debug);

utils.deleteMessages(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String\[] messagesToDelete,Date startSendDateFilter,Date endSendDateFilter,Date startReceiveDateFilter,Date endReceiveDateFilter,String folderName,String trashName);

utils.deleteMessages(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String\[] messageIdsToDelete,Integer\[] messageNumbersToDelete,String folderName,String trashName);

utils.forwardEmail(String server,Integer port,String username,String password,String protocol,Boolean useTLS,String to,String subject,String text,String messageId,String smtpHost,String smtpPort,String smtpProtocol,String smtpUsername,String smtpPassword);

utils.setAttributeValue(String attributeName,Object value);

utils.setVariable(String attributeName,Object value);

utils.copyCompanyId(String startingCompanyId,String newCompanyId);

utils.copyCompanyId(String startingCompanyId,String newCompanyId,String newCorporateName);

utils.camelToSnake(String str,boolean toUpperCase);

utils.openPDFFile(String fileName,Long directoryId,Map settings);

utils.addPageToPDFFile(String uuid);

utils.addLineToPDFFile(String uuid,String line,Map settings);

utils.movePDFPage(String uuid,int page);

utils.getPDFPageCount(String uuid);

utils.getPDFOrientation(String uuid);

utils.setLineToPDFFile(String uuid,int x,int y,String line,Map settings);

utils.closePDFFile(String uuid);

utils.addBackgroundToPdf(Long dirId,String pdfFile,String background,Map settings);

utils.stringifyForDatabaseField(Object obj);

utils.getTxtFileCharset(String fileName);

utils.getCellsValue(Long directoryId,String fileName,List coordinates,List functions);

utils.executeValueImportFunction(String function,String sheetName,Map values);

utils.decodeBase64(String plainText);

utils.closeCSVFile(String uuid);

utils.openTextFile(String fileName,Boolean overwrite,Long directoryId,Boolean fileAppend);

utils.openTextFile(String fileName,Boolean overwrite,Long directoryId,Boolean fileAppend,String charset);

utils.writeToTextFile(String uuid,String text);

utils.closeTextFile(String uuid);

utils.readCSVFile(String fileName,Long directoryId,String sep,Boolean skipFirstRow,String callbackFunName,String\[] attributeNames);

utils.readCSVFile(String fileName,Long directoryId,String sep,Boolean skipFirstRow,String callbackFunName,String\[] attributeNames,String charSet);

utils.readCSVFileAndWriteToTable(String fileName,Long directoryId,String sep,Boolean skipFirstRow,Long datastoreId,String tableName,Map defaultFieldNames,Map\[] csvFields);

utils.removeLinkedDevices);

utils.createChatGroup(String groupName,String myPhoneNumber,String> contactNames,String> contactPhoneNumbers);

utils.addMembersToChatGroup(String groupId,String myPhoneNumber,String> contactNames,String> contactPhoneNumbers);

utils.removeMembersFromChatGroup(String groupId,String myPhoneNumber,String> contactPhoneNumbers);

utils.createChatContact(Con89ChatContact person);

utils.getXlsContent(String dirId,String fileName,int sheetIndex,int fromRow,String\[] attributeNames);

utils.getXlsContentWithEncoding(String dirId,String fileName,String encoding,int sheetIndex,int fromRow,String\[] attributeNames);

utils.getCsvContent(String sep,String dirId,String fileName,Integer startRow,Integer blockSize,Boolean removeEmptyValues,String\[] attributeNames);

utils.getVariable(String varName);

utils.getFilesInPath(String path);

utils.createRoleForApplication(String appId,String companyId,Long siteId,String roleId,String description);

utils.getCompanyApplParameter(String companyId,Long siteId,String paramId);

utils.addUserRole(String companyId,Long siteId,String userCodeId,Map\[] roles);

utils.updatePeopleData(String companyId,Long siteId,String userCodeId,Map data);

utils.getUserRoles(String companyId,Long siteId,String userCodeId);

utils.addUserRoleForApplication(String appId,String companyId,Long siteId,String userCodeId,Map\[] roles);

utils.updateUserRole(String companyId,Long siteId,String userCodeId,Map\[] roles);

utils.userRoleActive(String companyId,Long siteId,String userCodeId,String roleId,Date activeDate);

utils.getDataModelAttrTypes(Long dataModelId);

utils.backupDirFiles(Long baseDirId,Long toDirId,String ftpHost,Long ftpPort,String ftpUseSSL,String ftpUsername,String ftpPassword,String ftpDestination,String suffixZipFile,Long availbaleBackup);

utils.applicationExportBackup(Long toDirId,String ftpHost,Long ftpPort,String ftpUseSSL,String ftpUsername,String ftpPassword,String ftpDestination,Long availbaleBackup);

utils.renameFTPFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String fromFileName,String toFileName);

utils.renameFTPFile(String host,Integer port,Boolean useSSL,String username,String password,String fromFileName,String toFileName);

utils.deleteFTPFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileName,Integer sessionTimeout);

utils.deleteFTPFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileName);

utils.deleteFTPFile(String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileName);

utils.createFTPDirectories(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String directories);

utils.addResponseHeader(String headerName,String headerValue);

utils.checkFunctionId(String functionId);

utils.checkRoleId(String roleId);

utils.decodeEncToken(String encToken);

utils.getEncToken(String\[] pars);

utils.convertXMLToHTML(Long xmlDirId,String xmlFileName,Long xslDirId,String xslFileName,Long htmlDirId,String htmlFileName,Boolean namespaceAware,Boolean validating);

utils.getSchedNextActivationTime(Long schedId);

utils.setHttpResponseCode(int httpResponseCode);

utils.getHttpResponseCode);

utils.logServiceElaboration(String logType,String logMessage,String messageCode,String fileName);

utils.logServiceElaborationTag(Long tagNumber,String tagValue);

utils.setElaborationState(String elaborationState,String result);

utils.terminateElaborationState(String elaborationState,String result,String logType,String logMessage,String messageCode);

utils.logServiceFileElaboration(String operation,Boolean elaborated,String fileName,Long directoryId,String backupFilename,Long backupDirectoryId,String note);

utils.logServiceFileElaboration(String operation,Boolean elaborated,String fileName,Long directoryId,String backupFilename,Long backupDirectoryId);

utils.logServiceFileElaboration(String operation,String state,String fileName,Long directoryId,String backupFilename,Long backupDirectoryId,String note);

utils.getBlobAsBase64(Long datastoreId,String sql,Object\[] params);

utils.duplicateBlobInPRM17(String appId,String fromCompanyId,String toCompanyId);

utils.getMimeType(String filename);

utils.getCurrentTime);

utils.getObjectTime(int hours,int minutes,int seconds);

utils.getWindowPanelsNavigateTree(Long windowId,String treeTranslation,String\[] excludedProperties);

utils.checkCellsWithMetadataForImport(Long directoryId,String fileName,Long valueImportId);

utils.importSubFolderInWebContext(String appId,String subfolderName);

utils.executeQueryReplaceVariables(String sql,String variablePrefix,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.executeMappedQueryWithCallback(String callbackFunName,String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,Object\[] pars);

utils.getMappedPartialResultWithFieldsToOmit(String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String> attributesMap,Long totalCount,String\[] fieldsToOmit,Object\[] pars);

utils.getMappedPartialResultWithFieldsToInclude(String select,String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String> attributesMap,Long totalCount,Object\[] pars);

utils.sendEmailWithMessageTemplate(String subject,String messageTemplate,Map jsObj,String from,String to,String cc,String bcc,String priority,Boolean isHtmlContent,Boolean returnReceipt,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Boolean zipFiles,Long dirId,String\[] filesToAttach);

utils.sendEmailWithMessageTemplateWithSettings(String subject,String messageTemplate,Map jsObj,String from,String to,String cc,String bcc,String priority,Boolean isHtmlContent,Boolean returnReceipt,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Boolean zipFiles,Map additionalSettings,Long dirId,String\[] filesToAttach);

utils.getProgressiveForApplicationId(String appId,String tableName,String columnName,Boolean separatedTransaction,Boolean interruptExecution);

utils.convertUTCStringToTimeZoneDate(String utcDateAsString,int hrs);

utils.sendAlertEmailWithConversation(String from,String subject,String message,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,String\[] filesToAttach);

utils.sendAlertEmailWithConversation(String from,String subject,String message,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,Long dirId,String fileName,String\[] filesToAttach);

utils.sendAlertEmailWithConversation(String from,String subject,String message,String destinations,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,String\[] filesToAttach);

utils.sendAlertEmailWithEmailAddresses(String fromEmail,String subject,String message,String destinationsEmail,String priority,boolean isHtmlContent,boolean returnReceipt,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithConversation(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,Long dirId,String fileName,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithConversation(String from,Number templateId,String destinations,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithConversation(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String\[] filesToAttach);

utils.getWebContentWithHeadersAndCookies(String uri,boolean replaceVariables,String httpMethod,String contentType,Object requestBody,String user,String pwd,String charSet,Map headers,Number timeout,boolean cookie,Long dirId,String sendFileName);

utils.getWebContentWithHeadersAndCookies(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,String charSet,Map headers,Number timeout);

utils.getBinaryContentWithSettings(String toFile,String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,Map settings);

utils.enqueueActionWithNoteAsString(String queueName,Long actionId,Map params,String priority,Long processWaitTime,Boolean logExecution,String note,Integer maxRetries);

utils.saveGridExportInExtendedCSV(String appId,String companyId,Long siteId,String username,String password,String platformBaseUrl,String functionId,Long panelId,List filters,List orders,List attributes,List titles,String title,String toFile);

utils.getDriverNameDefaultConnection);

utils.convertSecondToHoursMinutesSeconds(Long seconds);

utils.sendAlertEmailWithEmailAddressesWithConversation(String fromEmail,String subject,String message,String destinationsEmail,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,String\[] filesToAttach);

utils.sendAlertEmailWithEmailAddressesWithConversation(String fromEmail,String subject,String message,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,boolean returnReceipt,Long conversationId,String messageTag,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddresses(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddresses(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,Long dirId,String fileName,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithConversationAndSMTPSettings(String from,Number templateId,String destinations,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithConversationAndSMTPSettings(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithConversationAndSMTPSettings(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversation(String fromEmail,Number templateId,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,Long dirId,String fileName,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversation(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversation(String fromEmail,Number templateId,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddressesWithSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddressesWithSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversationAndSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversationAndSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String\[] filesToAttach);

utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversationAndSMTPSettings(String fromEmail,Number templateId,String destinationsEmail,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,String\[] filesToAttach);

utils.log(String msg,String logType);

utils.replaceAll(String text,String pattern,String changedValue);

utils.trim(String text);

utils.info(String msg);

utils.getResource(String entry);

utils.debug(String msg);

utils.suspend(String suspendingId);

utils.suspend);

utils.resume);

utils.getFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String ftpDir,String ftpFileName,String localFile,Integer sessionTimeout);

utils.getFile(String protocol,String host,Integer port,Boolean useSSL,String username,String password,String ftpDir,String ftpFileName,String localFile);

utils.getFile(String host,Integer port,Boolean useSSL,String username,String password,String ftpDir,String ftpFileName,String localFile);

utils.round(Number num,int decimals);

utils.error(String msg);

utils.mkdir(String path);

utils.warn(String msg);

utils.addAttribute(String host,Integer port,String filterDN,String ldapUsername,String ldapPassword,String attributeNameToAdd,String attributeValueToAdd);

utils.createGroup(String host,Integer port,String ldapUsername,String ldapPassword,String baseDN,String folderDN,String groupName,String\[] additionalAttributeNamesValues);

utils.getCount(String tableName,String valueColumnName,String incrementValue,String where,Boolean separatedTransaction,Boolean interruptExecution,Long dataSourceId);

utils.getCount(String tableName,String valueColumnName,String incrementValue,String where,Boolean separatedTransaction,Boolean interruptExecution);

utils.addDate(String date,String format,String field,Number amount);

utils.addDate(Long currentTimeMillis,String field,Number amount);

utils.addDate(String field,Number amount);

utils.setContentType(String contentType);

utils.getParameter(String paramName);

utils.getEntity(String entityName,Object key,int maxCachedEntities);

utils.getEntity(String entityName,Object key,int maxCachedEntities,Long expirationTime);

utils.deleteDir(Long dirId,String subFolder);

utils.addISO8601(Date dt,String period);

utils.encodeJWT(Map dataToSend,String sharedKey);

utils.mergeDocx(Long srcDirId,String\[] docxNames,Long destDirId,String mergedDocxName,Boolean deleteFilesAfterMerge);

utils.bulkImport(Long sourceDirId,Long destDirId,Long backupDirId,Long dataSourceId,String tableName,String csvFileName,String csvFileNameField,String csvUniqueIdField,String csvSep,Object> defaultValues,String> mapping,String nullString,Boolean skipWithErrors,Boolean skipFileNotInCSV,Long beforeInsertActionId,Long afterInsertActionId);

utils.unzipFile(Long zipDirId,String zipFileName,String serverFileSystemDir);

utils.getUUID);

utils.insertCard(Long dataModelId,Long panelId,Map vo,Integer archiveId,Map additionalSettings);

utils.insertCard(Long dataModelId,Long panelId,Map vo,Integer archiveId,Map additionalSettings,Long actionId);

utils.updateCard(Long dataModelId,Long panelId,Map vo);

utils.deleteCard(Long dataModelId,Long panelId,Map vo);

utils.setDatasetId(String datasetId);

utils.setBlockSize(int blockSize);

utils.setStartIndex(int startIndex);

utils.convertListWithMapper(String json,Map settings);

utils.setGoogleTokenResponse(String token);

utils.getValueInCache(String varName,String alternativeFunctionName);

utils.getValueInCache(String varName,String alternativeFunctionName,Long expirationTime);

utils.getValueInCache(String varName);

utils.addValueInCache(String varName,Object value);

utils.addValueInCache(String varName,Object value,Long expirationTime);

utils.convertISO8601(String period);

utils.addGoogleCalendarEvent(String title,Date beginDate,Date endDate);

utils.modifyGoogleCalendarEvent(String calendarEventId,String title,Date beginDate,Date endDate);

utils.deleteGoogleCalendarEvent(String calendarEventId);

utils.getGoogleContactsFiltered(Integer pages,Integer maxPageResults,String searchString,Boolean splitEmails);

utils.addGoogleContact(String name,String surname,String email,String phone,Boolean shared);

utils.updateGoogleContact(String contactId,String name,String surname,String email,String phone,Boolean shared);

utils.deleteGoogleContact(String contactId,Boolean shared);

utils.sharedContatctsSync);

utils.addGoogleDriveFileProperty(String userId,String fileId,String key,String value,String visibility);

utils.addGoogleDriveFileProperty(String fileId,String key,String value,String visibility);

utils.createGoogleDriveFolder(String userId,String folderName,String> parents,String description);

utils.createGoogleDriveFolder(String folderName,String> parents,String description);

utils.deleteGoogleDriveFile(String userId,String fileId,boolean skipTrash);

utils.deleteGoogleDriveFile(String fileId,boolean skipTrash);

utils.getGoogleDriveFileInfo(String fileId);

utils.getGoogleDriveFileInfo(String userId,String fileId);

utils.getGoogleDriveFileOpenURL(String fileId);

utils.getGoogleDriveFileProperty(String userId,String fileId,String key,String visibility);

utils.getGoogleDriveFileProperty(String fileId,String key,String visibility);

utils.moveGoogleDriveFile(String fileId,String newParent,boolean addToRevision);

utils.moveGoogleDriveFile(String userId,String fileId,String newParent,boolean addToRevision);

utils.moveGoogleDriveFile(String userId,String fileId,String newParents);

utils.moveGoogleDriveFile(String fileId,String newParents);

utils.recoverGoogleDriveFile(String userId,String fileId);

utils.recoverGoogleDriveFile(String fileId);

utils.updateGoogleDriveFile(String userId,String fileId,String title,String description,String mimeType);

utils.updateGoogleDriveFile(String fileId,String title,String description,String mimeType);

utils.duplicateGoogleDriveFile(String userId,String sourceFolderId,String destinationFolderId,String newFileName,Boolean copyPermissions);

utils.searchInGoogleDrive(String userId,Integer maxPageResults,Integer pages,String nextPageToken,String folderId,Boolean recursive,String query,Boolean trashed);

utils.searchInGoogleDrive(Integer maxPageResults,Integer pages,String nextPageToken,String folderId,Boolean recursive,String query,Boolean trashed);

utils.setPublicLink(String bucketName,String objectName,Boolean publicLink);

utils.getGoogleOAuth2AccessToken(String\[] scopes);

utils.getGoogleOAuth2AccessToken(String projectId,String serviceAccountEmail,String privateKeyString,String\[] scopes);

utils.getGoogleOAuth2AccessToken(String projectId,String\[] scopes);

utils.getEntities(String entityName,Object\[] entityKeys);

utils.getEntitiesAsJSON(String entityName,Object\[] entityKeys);

utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities);

utils.getEntityAsJSON(String entityName,Object key,int maxCachedEntities,Long expirationTime);

utils.clearDatastoreEntities(String entityName);

utils.removeValueInCache(String varName);

utils.clearAllDatastoreEntities);

utils.executeQueryOnMongoDb(String where,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.getPartialResultOnMongoDb(String where,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.insertObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);

utils.updateObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);

utils.deleteObjectOnMongoDb(Map obj,Long dataModelId,Boolean interruptExecution);

utils.startActivitiProcess(String appId,String processDefinitionId,Map params,Map processVariables);

utils.completeActivitiTask(String processInstanceId,Map params,Map processVariables);

utils.getProcessDefinition(String processDefinitionId,Map params);

utils.getAlfrescoDocument(String id,String fileName,String destPath);

utils.getAlfrescoWebScript(String uri,boolean replaceVariables,String httpMethod,String bodyRequest);

utils.getAlfrescoWebScript(String uri,boolean replaceVariables,String httpMethod,String bodyRequest,String charSet);

utils.generateDocx(Long reportId,Object> args,String langId,String path,String fileName);

utils.convertDocxToOtherFormat(String docxFile,String newFile,Boolean deleteDocxFile,String format);

utils.convertDocxToPdf(String docxFile,String pdfFile,Boolean deleteDocxFile);

utils.sendSmsMessage(String fromPhoneNr,String toPhoneNr,String text,Boolean logMessage);

utils.getShortUrl(String realUrl);

utils.convertUrlToImage(String url,String imagePath);

utils.convertHtmlToImage(String html,String imagePath);

utils.executeAction(Long actionId,Map vo,Map params,Map headers);

utils.addFileToMobileDevices(String fullPathName,String fileName,String username);

utils.convertPdfToImage(Long pdfDirId,String pdfFileName,Long imgDirId,String imgExtension,Float scale);

utils.convertTifToJpg(Long tifDirId,String tifFileName,Long jpgDirId,String jpgFileName,Float compressionFactor);

utils.scaleJpgFile(Long srcJpgDirId,String srcJpgFileName,Long destDirId,String destFileName,Long scale);

utils.scaleJpgFile(Long srcJpgDirId,String srcJpgFileName,Long destDirId,String destFileName,Long maxWidth,Long maxHeight);

utils.importFileInCMS(String path,Long destDirId,Long dataSourceId,String tableName);

utils.importFileInCMS(Long sourceDirId,String fileName,Long destDirId,Long dataSourceId,String tableName);

utils.updateFileInCMS(String uuid,Long sourceDirId,String fileName);

utils.updateFileInCMS(String uuid,String path);

utils.deleteFileFromCMS(String uuid);

utils.bulkImportFromFTP(String host,Integer port,Boolean useSSL,String username,String password,String remoteDir,String fileFilter,Long destDirId,Long backupDirId,Long dataSourceId,String tableName,String csvFileName,String csvFileNameField,String csvUniqueIdField,String csvSep,Object> defaultValues,String> mappingCsvToFields,String nullString,Boolean skipWithErrors,Boolean skipFileNotInCSV,Long beforeInsertActionId,Long afterInsertActionId);

utils.invalidateAll);

utils.invalidateAllCache(String varName);

utils.getKeysFromCache(String keyPrefix);

utils.removeValuesFromCache(String keyPrefix);

utils.getInfoFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive);

utils.deleteFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive);

utils.deleteFiles(Long dirId,Boolean subFolder,String operator,String fileName,Boolean caseSensitive,Boolean removeEmptyDir);

utils.createConDbForCurrentUser(String companyId,Long siteId,String username);

utils.setGooglePrivateKeyString(String key);

utils.setGoogleClientId(String id);

utils.setGoogleClientSecret(String pwd);

utils.sendPushNotification(String appId,String\[] userCodeIds,String title,String shortMessage,Long actionId,String json,Long badgeNr);

utils.sendSinglePushNotification(String appId,String firebaseId,String title,String shortMessage,Long actionId,String json,Long badgeNr,Map rootOptions,Map dataOptions,Map notificationOptions);

utils.createXlsContent(Long dirId,String fileName,String sheetName,Integer sheetIndex,Integer fromRow,Object>\[] vos,String\[] attributeNames);

utils.getModifiedPks(String tableName,String field,Date changedStardDate,Date changedEndDate);

utils.getGoogleSheetData(String userId,Long dataModelId,String spreadsheetId,String range,String valueRenderOption,String dateTimeRenderOption);

utils.getGoogleSheetData(String userId,Long dataModelId,String spreadsheetId,String> range,String valueRenderOption,String dateTimeRenderOption);

utils.getGoogleSheetData(String userId,String spreadsheetId,String> range,String valueRenderOption,String dateTimeRenderOption);

utils.getGoogleSheetData(String userId,String spreadsheetId,String range,String valueRenderOption,String dateTimeRenderOption);

utils.createGoogleSpreadsheets(String userId,String spreadsheetTitle,String\[] sheets);

utils.createGoogleSheets(String userId,String spreadsheetId,String\[] sheets);

utils.deleteGoogleSheets(String userId,String spreadsheetId,Integer\[] sheetIds);

utils.duplicateGoogleSheet(String userId,String spreadsheetId,Integer sourceSheetId,Integer insertSheetIndex,Integer newSheetId,String newSheetName);

utils.copyGoogleSheet(String userId,String spreadsheetId,Integer sheetId,String destinationSpreadsheetId);

utils.appendRangeGoogleSheet(String userId,String spreadsheetId,String range,String valueInputOption,String insertDataOption,Object\[]\[] vos);

utils.updateRangeGoogleSheet(String userId,String spreadsheetId,String range,String valueInputOption,Object\[]\[] vos);

utils.clearRangeGoogleSheet(String userId,String spreadsheetId,String range);

utils.createCsvFromSqlQuery(String sql,Long dataSourceId,Boolean includeRowNum,String replaceNullWith,Long fromRow,Long maxRowsToRead,String firstRow,String sep,Long dirId,String fileName);

utils.sendTensorFlowCsvFromCsv(String csvFilePath,Boolean includeFirstRow,Boolean includeRowNum,int resultValuesNr,Long dirId,String topic,String cmd,Long pkIndex,Map jsObj);

utils.matchTensorFlowCsvResults(Long dirId,Long dataSourceId,String tableName,Map jsObj);

utils.analyzeSentiment(String text,String encodingType,Boolean htmlText);

utils.analyzeEntitySentiment(String text,String encodingType,Boolean htmlText);

utils.analyzeEntities(String text,String encodingType,Boolean htmlText);

utils.analyzeSyntax(String text,String encodingType,Boolean htmlText);

utils.classifyText(String text,Boolean htmlText);

utils.executeExport(Long exportId,String queryType,Map paramValues);

utils.executeExportsInGroup(String groupName,String queryType,Map paramValues);

utils.executeAllExports(String queryType,Map paramValues);

utils.callGaeAction(Long actionId,Boolean async);

utils.enqueueGaeAction(String queueName,Long actionId,Map params);

utils.getElementFromQueueByNote(String note,String namespace);

utils.createBigQueryDataset(String datasetName);

utils.deleteBigQueryDataset(String datasetName);

utils.createBigQueryTable(String datasetName,String tableName,Map> columns);

utils.deleteBigQueryTable(String datasetName,String tableName);

utils.executeBigQuerySaveOnTable(String destinationDataset,String destinationTable,String defaultDataset,String sqlQuery,Object\[] params);

utils.extractBigQueryData(String datasetName,String tableName,String format,String gcsUrl,Boolean deleteTableAfterExport,Boolean exportHeaders);

utils.getBigQueryDataset);

utils.setBigQueryDataset(String bigQueryDataset);

utils.importBigQueryDataFromGCS(String datasetName,String tableName,String format,String sourceUri,String encoding,String separator);

utils.insertBigQueryObject(String datasetName,String tableName,Map obj);

utils.updateBigQueryObject(String datasetName,String tableName,Map obj,String\[] pks);

utils.deleteBigQueryObject(String datasetName,String tableName,Map obj,String\[] pks);

utils.importDataInCloudSQL(String instance,String bucketPath,String dbSchema,Long dataSourceId,String tablename,String where,String\[] columns);

utils.importDataInCloudSQL(String instance,String bucketPath,String dbSchema,Long dataSourceId,String tablename,String where,Integer timeout,String\[] columns);

utils.createXLSXFileFromSQLQuery(Long templateDirectoryId,String templateFileName,String sheetName,Long outDirectoryId,String outFileName,Map\[] formatHeaderColumns,Map\[] formatColumns,Map grouping,Map additionalSettings,Long datastoreId,String sqlQuery,Object\[] pars);

utils.backupEntitiesInGCS(String\[] entityNames,Long directoryId);

utils.setDatastoreNamespace(String namespace);

utils.getDetailOnArchiflow(Long dataModelId,String cardId,Map additionalSettings);

utils.insertCards(Long dataModelId,Long panelId,Map\[] vos,Integer archiveId,Map additionalSettings,Long actionId);

utils.insertCards(Long dataModelId,Long panelId,Map\[] vos,Integer archiveId,Map additionalSettings);

utils.updateCards(Long dataModelId,Long panelId,Map\[] vos);

utils.deleteCards(Long dataModelId,Long panelId,Map\[] vos);

utils.uploadArchiflowDocument(Long dirId,String fileNameSrc,String cardId,String fileName,String documentTitle,Map additionalSettings);

utils.downloadArchiflowDocument(Long dirId,String fileName,String cardId,Map additionalSettings);

utils.validateAlexaRequest(String signingCertificateChainUrl,String baseEncoded64Signature,String requestBody);

utils.exportUsersToDatastore(String companyId);

utils.exportUsersToDatastore);

utils.convertObjectWithMapper(String json,Map settings);

utils.deleteProcessInstance(String processInstanceId);

utils.getActivitiProcessAsJson(String id,Boolean includeSubProcesses,Map tasksDueDates);

utils.enquiryTasks(HashMap pars);

utils.setTaskAssignee(String taskId,String assignee);

utils.closeActivitiTask(String processInstanceId,String taskDefinitionKey,String assignee,Map map);

utils.closeActivitiTask(String taskInstanceId,Map map);

utils.sendWhatsappMessage(String accountId,String secretKey,String fromNr,String toNumber,String message,String publicUrl);

utils.sendWhatsappMessage(String toNumber,String message,String publicUrl);

utils.sendWhatsappMessage(String toNumber,String message,String bucketName,String fileName);

utils.sendWhatsappMessage(String accountId,String secretKey,String fromNr,String toNumber,String message,String bucketName,String fileName);

utils.createStripeCustomer(String apiKey,Map customerData);

utils.prepareStripePayment(String apiKey,String publicKey,Long priceWithCents,String currency,String customerId);

utils.executeStripePayment(String apiKey,Long priceWithCents,String currency,String customerId);

utils.getGCPAuthToken(String user,String serviceAccountEmail,String privateKeyString,String\[] \_scopes);

utils.generateGCPAuthToken(String user,String serviceAccountEmail,String privateKeyString,String redirectUri,String\[] \_scopes);

utils.getGoogleSheets(String userId,String spreadsheetId);

utils.getGoogleSheets(String spreadsheetId);

utils.mergeObjectOnGoogleSpanner(Map attributesToSet,String\[] attributesToSetToNull,Long dataModelId,Boolean interruptExecution);

utils.executeSpannerDdl(String\[] scripts);

utils.bulkImportFromDSToSpanner(String gql,Long datastoreDataModelId,boolean interruptExecution,Object\[] pars);

utils.executeSpannerSql(String sql);

utils.executeQueryOnBigQuery(String sql,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.getPartialResultOnBigQuery(String sql,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.insertObjectsOnBigQuery(Map\[] objs,Long dataModelId,Boolean interruptExecution);

utils.updateObjectOnBigQuery(Map obj,Long dataModelId,Boolean interruptExecution);

utils.updateObjectsOnBigQuery(Map\[] objs,Long dataModelId,Boolean interruptExecution);

utils.deleteObjectOnBigQuery(Map obj,Long dataModelId,Boolean interruptExecution);

utils.bulkImportFromDSToBigQuery(String gql,Long datastoreDataModelId,String location,String bigQueryTable,boolean interruptExecution,Object\[] pars);

utils.maybeStartProcess(Long schedId,Boolean forceRunning,Boolean startNextProcesses);

utils.reinsertElements(String companyId,Long actionId,String queueName,String status,String id);

utils.getWebContentWithNTLM(String url,String contentType,String httpMethod,String bodyRequest,String username,String password,String workstation,String domain,Map settings);

utils.getGroupMembers(String userId,String groupId);

utils.checkGoogleSSOToken(String ssoAuthToken);

utils.addGoogleCalendarEventWithSettings(String serviceAccountEmail,String privateKeyString,String userId,String title,Date beginDate,Date endDate,String description,String location,String calendarId,String creatorEmail,String\[] attendeeEmails);

utils.addGoogleCalendarEventWithConference(String serviceAccountEmail,String privateKeyString,String userId,String title,Date beginDate,Date endDate,String description,String location,String calendarId,String type,String creatorEmail,String\[] attendeeEmails);

utils.modifyGoogleCalendarEventWithSettings(String calendarEventId,String title,Date beginDate,Date endDate,String description,String location,String creatorEmail,String\[] attendeeEmails);

utils.deleteGoogleCalendarEventWithSettings(String serviceAccountEmail,String privateKeyString,String userId,String calendarEventId);

utils.getGoogleSharedContactsFiltered(Integer pages,Integer maxPageResults,String searchString,Boolean splitEmails);

utils.addPermissionsToGoogleDriveFolder(String folderId,String type,String value,String fileRole,String folderRole,String> additionalRoles,Boolean updateBaseFolder,Boolean recursive,Boolean sendNotifications,String message);

utils.addPermissionsToGoogleDriveFolder(String userId,String folderId,String type,String value,String fileRole,String folderRole,String> additionalRoles,Boolean updateBaseFolder,Boolean recursive,Boolean sendNotifications,String message);

utils.deleteGoogleCloudStorageBucket(String bucketName);

utils.deleteGoogleCloudStorageObject(String bucketName,String objectName);

utils.deleteGoogleDriveFileProperty(String userId,String fileId,String key);

utils.deleteGoogleDriveFileProperty(String fileId,String key);

utils.getGoogleDriveFileDownloadURL(String fileId);

utils.getGoogleDriveFileRevisions(String fileId);

utils.getGoogleDriveFileRevisions(String userId,String fileId);

utils.getGoogleDriveFolderContents(String folderId,String query,Boolean trashed);

utils.getGoogleDriveFolderContents(String userId,String folderId,String query,Boolean trashed);

utils.getGoogleDriveFolderContentsIds(String folderId,String query,boolean trashed);

utils.getGoogleDriveFolderContentsIds(String userId,String folderId,String query,boolean trashed);

utils.modifyGoogleDriveFileParents(String userId,String fileId,String parentsToAdd,String parentsToRemove);

utils.modifyGoogleDriveFileParents(String fileId,String parentsToAdd,String parentsToRemove);

utils.patchGoogleDriveFileProperty(String userId,String fileId,String key,String value,String visibility);

utils.patchGoogleDriveFileProperty(String fileId,String key,String value,String visibility);

utils.setGoogleDriveFileAttributes(String fileId,FileAttributes fileAttributes);

utils.setGoogleDriveFileAttributes(String userId,String fileId,FileAttributes fileAttributes);

utils.setGoogleDriveFilePermissions(String fileId,String type,String value,String role,String> additionalRoles,boolean sendNotifications,String message);

utils.setGoogleDriveFilePermissions(String userId,String fileId,String type,String value,String role,String> additionalRoles,boolean sendNotifications,String message);

utils.updateGoogleDriveFileFromFS(String fileId,String fsPath,boolean deleteFsFile,boolean newRevision);

utils.updateGoogleDriveFileFromFS(String userId,String fileId,String fsPath,boolean deleteFsFile,boolean newRevision);

utils.uploadAndRenameGoogleDriveFileFromFS(String fsPath,String parentId,String fileName,boolean deleteFsFile);

utils.uploadAndRenameGoogleDriveFileFromFS(String userId,String fsPath,String parentId,String fileName,boolean deleteFsFile);

utils.uploadGoogleDriveFileFromFS(String userId,String fsPath,String parentId,boolean deleteFsFile);

utils.uploadGoogleDriveFileFromFS(String fsPath,String parentId,boolean deleteFsFile);

utils.uploadGoogleDriveFileInNamedFolderFromFS(String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,boolean deleteFsFile);

utils.uploadGoogleDriveFileInNamedFolderFromFS(String userId,String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,boolean deleteFsFile);

utils.duplicateGoogleDriveFolderAndContents(String sourceFolderId,String newFolderName,String newFolderDescription,String destinationFolderId,String titlePrefix,Boolean copyPermissions);

utils.duplicateGoogleDriveFolderAndContents(String userId,String sourceFolderId,String newFolderName,String newFolderDescription,String destinationFolderId,String titlePrefix,Boolean copyPermissions);

utils.downloadFileFromGoogleDrive(String userId,String fileId,String localPath,String fileName);

utils.createGoogleCloudStorageBucket(String project,String bucketName,String bucketLocation,String storageClass);

utils.getGoogleCloudStorageBucket(String bucketName);

utils.getGoogleCloudStorageBucketVersioning(String bucketName);

utils.setGoogleCloudStorageBucketVersioning(String bucketName,Boolean versioning);

utils.getGoogleCloudStorageObject(String bucketName,String objectName);

utils.getGoogleCloudStorageObjectVersions(String bucketName,String objectName);

utils.getGoogleCloudStorageSignedURL(String verb,Long expiration,String bucketName,String objectName,String mime);

utils.downloadGoogleCloudStorageObject(String bucketName,String objectName,String destPath);

utils.listGoogleCloudStorageObjects(String bucketName,Long maxPageResults,Integer pages,String nextPageToken,String prefix,String delimiter);

utils.listGoogleCloudStorageObjects(String bucketName,String prefix,String delimiter);

utils.copyGoogleCloudStorageObject(String sourceBucketName,String sourceObjectName,Long sourceObjectVersion,String destinationBucketName,String destinationObjectName);

utils.uploadGoogleCloudStorageObjectFromFS(String fsPath,String bucketName,String objectName,Boolean deleteFsFile);

utils.uploadGoogleCloudStoragePublicObjectFromFS(String fsPath,String bucketName,String objectName,Boolean deleteFsFile);

utils.uploadGoogleCloudStorageObjectFromString(String textContent,String bucketName,String objectName,String contentType);

utils.rewriteGoogleCloudStorageObject(String sourceBucketName,String sourceObjectName,Long sourceObjectVersion,String destinationBucketName,String destinationObjectName);

utils.getGoogleDomainContactsFiltered(Integer pages,Integer maxPageResults,String query,String orderBy,String sortOrder);

utils.executeCachedQueryOnGoogleDatastore(int maxCachedEntities,String sql,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.executeQueryOnGoogleDatastoreWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object\[] pars);

utils.executeQueryOnGoogleDatastore(String sql,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.getPartialResultOnGoogleDatastore(String sql,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.insertObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);

utils.insertObjectsOnGoogleDatastore(Map\[] objs,Long dataModelId,Boolean interruptExecution);

utils.insertObjectsOnGoogleDatastoreWithSettings(Map\[] objs,Long dataModelId,Boolean interruptExecution,Map settings);

utils.updateObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);

utils.mergeObjectOnGoogleDatastore(Map attributesToSet,String\[] attributesToSetToNull,Long dataModelId,Boolean interruptExecution);

utils.updateObjectsOnGoogleDatastore(Map\[] objs,Long dataModelId,Boolean interruptExecution);

utils.updateObjectsOnGoogleDatastoreWitSettings(Map\[] objs,Long dataModelId,Boolean interruptExecution,Map settings);

utils.updateObjectsOnGoogleDatastoreWithSettings(Map\[] objs,Long dataModelId,Boolean interruptExecution,Map settings);

utils.bulkUpdateOnGoogleDatastore(String gql,Map attributesToSet,Map attributesToRemove,Long actionId);

utils.bulkDeleteOnGoogleDatastore(String gql);

utils.deleteObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);

utils.executeActionSameTransaction(Long actionId,Map vo,Map params,Map headers);

utils.getButtonsAuthorizationOfUser);

utils.getFunctionAuthorizationOfUser(String functionId);

utils.getLastSynchronizationDevice);

utils.setGoogleServiceAccountEmail(String email);

utils.sendPushNotificationWithOptions(String appId,String\[] userCodeIds,String title,String shortMessage,Long actionId,String json,Long badgeNr,Map rootOptions,Map dataOptions,Map notificationOptions);

utils.sendTensorFlowCsvFromSqlQuery(String sql,Long dataSourceId,Long fromRow,Long maxRowsToRead,String fieldName,Integer resultValuesNr,Long dirId,String fileName,Map jsObj);

utils.executeBigQueryWithCallback(String processRowFunName,String defaultDataset,String sqlQuery,Object\[] params);

utils.importBigQueryDataFromLocalDatasource(String datasetName,String tableName,String location,String format,String csvPath,String encoding,String separator,Integer maxBadRecords,Boolean truncate,Boolean deleteSrcFileAfterImport);

utils.importMultipleDataFromLocalDatasource(String datasetName,String\[] tableNames,String location,String format,String dirPath,String\[] csvFiles,String encoding,String separator,Integer maxBadRecords,Boolean truncate,Boolean deleteSrcFileAfterImport);

utils.importBigQueryThroughStreaming(String datasetName,String tableName,Object\[] objectsForBQ);

utils.executeBigQueryDmlStatement(String datasetName,String sql,Object\[] pars);

utils.executeBigQuerySaveOnLocalTable(Long datastoreId,String localTableName,Map defaultFieldNames,Map\[] csvFields,String defaultDataset,String sqlQuery,Object\[] params);

utils.createTablesFromDatastoreBackup(String\[] entityNames,String gcsURI,String datasetName);

utils.createBigQueryTableFromDatastoreEntities(String\[] entityNames,Long directoryId,String datasetName);

utils.getPartialResultOnArchiflow(Long dataModelId,Map\[] filters,Integer\[] archiveIds,Boolean cardsWithAttachedDoc,Integer searchTypes,Map additionalSettings);

utils.getActivitiLastVersionProcessId(String id);

utils.getInvolvedNotAssignedTasks(HashMap pars,String username);

utils.getActivitiUserAssignedTasks(String assignee,String processInstanceId,String taskDefinitionKey);

utils.getActivitiUserCandidateTasks(String candidate,String processInstanceId,String taskDefinitionKey);

utils.getActivitiProcessInstancesVariables(String processInstanceId,String processDefinitionId);

utils.exportFromExcelFileToGSheet(Long sourceDirId,String sourceFileName,String spreadsheetId,List areas);

utils.exportFromExcelFileToGSheet(String userId,Long sourceDirId,String sourceFileName,String spreadsheetId,List areas);

utils.removeGoogleDriveFilePermissions(String fileId,String emailUser);

utils.removeGoogleDriveFilePermissions(String userId,String fileId,String emailUser);

utils.executeQueryOnGoogleSpanner(String sql,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.executeQueryOnGoogleSpannerWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object\[] pars);

utils.getPartialResultOnGoogleSpanner(String sql,Long dataModelId,Boolean interruptExecution,Object\[] pars);

utils.insertObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);

utils.insertObjectsOnGoogleSpanner(Map\[] objs,Long dataModelId,Boolean interruptExecution);

utils.updateObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);

utils.updateObjectsOnGoogleSpanner(Map\[] objs,Long dataModelId,Boolean interruptExecution);

utils.deleteObjectOnGoogleSpanner(Map obj,Long dataModelId,Boolean interruptExecution);

utils.executeQueryOnBigQueryWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map map,Object\[] pars);

utils.getPartialResultOnBigQueryWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object\[] pars);

utils.upsertObjectOnGoogleDatastore(Map obj,Long dataModelId,Boolean interruptExecution);

utils.upsertObjectsOnGoogleDatastore(Map\[] objs,Long dataModelId,Boolean interruptExecution);

utils.upsertObjectsOnGoogleDatastoreWithSettings(Map\[] objs,Long dataModelId,Boolean interruptExecution,Map settings);

utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(String userId,String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,String fileName,boolean deleteFsFile);

utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(String fsPath,String baseFolderId,String folderName,Boolean createFolderIfNotExists,String fileName,boolean deleteFsFile);

utils.uploadGoogleCloudStoragePublicObjectFromString(String textContent,String bucketName,String objectName,String contentType);

utils.executeCachedQueryOnGoogleDatastoreWithSetting(int maxCachedEntities,String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object\[] pars);

utils.getPartialResultOnGoogleDatastoreWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object\[] pars);

utils.getPartialResultOnGoogleSpannerWithSettings(String sql,Long dataModelId,Boolean interruptExecution,Map settings,Object\[] pars);

utils.clearCache(String varNames);

utils.clearCache(String varNames,String keys);
