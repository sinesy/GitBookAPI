# Other Files

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

## Send a list of files stored to an FTP server inside the specified remote folder

Files to send must be in the server side file system

**Syntax**

```javascript
var ok = utils.sendFiles(protocol, host, port, useSSL, username, password, toDir, filePaths);
```

**Details**

| Argument | Description     |
| -------- | --------------- |
| protocol | FTP, FTPS, SFTP |
| host     | FTP server host |
| port     | FTP server port |

```
 useSSL - boolean flag, used to specify if FTPS must be used
```

| Argument  | Description                                                                                                      |
| --------- | ---------------------------------------------------------------------------------------------------------------- |
| username  | username to use to authenticate to the FTP server                                                                |
| password  | password to use to authenticate to the FTP server                                                                |
| toDir     | remote folder, within the FTP server, where files must be copied                                                 |
| filePaths | list of files stored in the server side file system (expressed with absolute path) to copy within the FTP server |

## Send a single file to the FTP server and store it in the specified folder

**Syntax**

```javascript
var ok = utils.sendFile(protocol, host, port, useSSL, username, password, destFile, sourceFile);
```

**Details**

| Argument | Description               |
| -------- | ------------------------- |
| protocol | FTP, FTPS, SFTP           |
| host     | FTP server host           |
| port     | FTP server port (e.g. 21) |

```
 useSSL - boolean flag, used to specify if FTPS must be used
```

| Argument   | Description                                                                                 |
| ---------- | ------------------------------------------------------------------------------------------- |
| username   | username to use to authenticate to the FTP server                                           |
| password   | password to use to authenticate to the FTP server                                           |
| destFile   | folder in the FTP server + destination file name where storing the file                     |
| sourceFile | sourceFile absolute path in the server file system + file name, related to the file to read |

## Read a remote file from FTP server and copy it

Read a remote file, stored within the FTP server and copy it into the specified absolute file, related to the server.

**Syntax**

```javascript
var ok = utils.getFile(protocol, host, port, useSSL, username, password, ftpDir, ftpFileName, localFile);
```

**Details**

| Argument | Description                                         |
| -------- | --------------------------------------------------- |
| protocol | FTP, FTPS, SFTP                                     |
| host     | FTP server host                                     |
| port     | <p>FTP server port (e.g. 21)</p><p></p>             |
| useSSL   |  boolean flag, used to specify if FTPS must be used |

| Argument    | Description                                                                          |
| ----------- | ------------------------------------------------------------------------------------ |
| username    | username to use to authenticate to the FTP server                                    |
| password    | password to use to authenticate to the FTP server                                    |
| ftpDir      | remote folder, within the FTP server, where the file to retrieve is currently stored |
| ftpFileName | file name to retrieve, stored within the specified remote folder                     |
| localFile   | path+file name, where the remote file must be copied, in the server file system      |

## Read a list of remote file names

all files must be stored in the same remote folder within the FTP server; file names are filtered according to the specified filter condition.

**Syntax**

```javascript
var listOfFileNames = utils.getFiles(protocol, host, port, useSSL, username, password, remoteDir, fileFilter);
```

**Details**

| Argument | Description                           |
| -------- | ------------------------------------- |
| protocol | FTP, FTPS, SFTP                       |
| host     | FTP server host                       |
| port     | FTP server port (e.g. 21)Argument     |
| useSSL   | flag used to define whether using SSL |

| Description     |                                                                        |
| --------------- | ---------------------------------------------------------------------- |
| username        | username to use to authenticate to the FTP server                      |
| password        | password to use to authenticate to the FTP server                      |
| remoteDir       | remote folder, within the FTP server, where files are stored           |
| fileFilter      | (optional) parameter to use to filter files to read (e.g. \*.jpg)      |
| listOfFileNames | list of file names (String objects) which satisfy the filter condition |

## Delete a single file to the FTP server

**Syntax**

```javascript
var ok = utils.deleteFTPFile(protocol, host, port, useSSL, username, password, remoteDir, fileName);
```

**Details**

| Argument  | Description                                        |
| --------- | -------------------------------------------------- |
| protocol  | FTP, FTPS, SFTP                                    |
| host      | FTP server host                                    |
| port      | FTP server port (e.g. 21)                          |
| useSSL    | boolean flag, used to specify if FTPS must be used |
| username  | username to use to authenticate to the FTP server  |
| password  | password to use to authenticate to the FTP server  |
| remoteDir | folder in the FTP server                           |
| fileName  | file name                                          |

## Rename or move a single file to the FTP server

**Syntax**

```javascript
var ok = utils.renameFTPFile(protocol, host, port, useSSL, username, password, fromFileName, toFileName);
```

**Details**

| Argument     | Description                                        |
| ------------ | -------------------------------------------------- |
| protocol     | FTP, FTPS, SFTP                                    |
| host         | FTP server host                                    |
| port         | FTP server port (e.g. 21)                          |
| useSSL       | boolean flag, used to specify if FTPS must be used |
| username     | username to use to authenticate to the FTP server  |
| password     | password to use to authenticate to the FTP server  |
| fromFileName | absolute path with file name in the FTP server     |
| toFileName   | new absolute path with file name in the FTP server |

## Extract a file from Alfresco and save it to the specified local file path.

**Syntax**

```javascript
var success = utils.getAlfrescoDocument(id, fileName, destPath);
```

**Details**

| Argument | Description                                                                                                   |
| -------- | ------------------------------------------------------------------------------------------------------------- |
| id       | UUID value which identifies the file to retrieve from Alfresco CMS                                            |
| fileName | file name related to the specified if                                                                         |
| destPath | absolute path related to the A.S. file system, where the file will be saved, once extracted from Alfresco CMS |

## Read the specified file from the source directory and extract signed data and the embedded document

The source file is identified starting from the source directory id + fileName.

The embedded document is then saved in the destination directory. The embedded file, if recognized with a MIME type, is renamed to a name having the original name + its real extension. Otherwise, it is saved with the original source file name.

**Syntax**

```javascript
var obj = utils.getCertMessage(srcDirectoryId, destDirectoryId, fileName);
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

## Read the specified file and extract signed data and the embedded document

The source file is identified through the "srcFileName", containing both the absolute path and the the file name.

The embedded document is then saved in the destination directory. The embedded file, if recognized with a MIME type, is renamed to a name having the original name + its real extension. Otherwise, it is saved with the original source file name.

**Syntax**

```javascript
var obj = utils.getCertMessage(srcFileName, destFolder);
```

**Details**

| Argument    | Description                                                      |
| ----------- | ---------------------------------------------------------------- |
| srcFileName | path + file name to analyze                                      |
| destFolder  | destination folder; if not specified, the srcFolder will be used |
| obj         | embedded document, expressed as a javascript object              |

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

## Read a signed PDF file and extract data coming from the embedded certificate

The source PDF file is identified starting from the source directory id + fileName.

The specified PDF file is signed file, i.e. it contains a certificate; this certificate is then extracted and saved in the destination directory. The certificate file, if recognized with a MIME type, is renamed to a name having the original name + its real extension. Otherwise, it is saved with the original source file name.

**Syntax**

```javascript
var obj = utils.getCertMessageFromPdf(Long srcDirectoryId,Long destDirectoryId,String fileName);
```

**Details**

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
* signDate - the sign date, expressed as a javascript Date &#x20;

## Create a zip file containing the list of passed files <a href="#zipfiles" id="zipfiles"></a>

**Syntax**

```javascript
var ok = utils.zipFiles(baseDir,files,zipFile,deleteFilesAfterZip);
```

**Details**

| Argument            | Description                                                                         |
| ------------------- | ----------------------------------------------------------------------------------- |
| baseDir             | base dir used to calculate the entry in the zip (i.e. "C:/xxx/yyy/")                |
| files               | files to zip (each including an absolute path, "C:/xxx/yyy/fileName.csv")           |
| zipFile             | zip file to create, including the absolute path (i.e. "C:/aaa/bbb/zipFileName.zip") |
| deleteFilesAfterZip | flag used to decide if input files must be deleted after the zip creation           |

## Copy the source file to the destination file <a href="#copyfile" id="copyfile"></a>

Since "destFile" contains a file name too, the source file can be renamed when copied.

**Syntax**

```javascript
var ok = utils.copyFile(srcFile, destFile, replaceExistingFile, deleteSourceFile);
```

**Details**

| Argument            | Description                                                                                                                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| srcFile             | absolute path + file name                                                                                                                                                                        |
| destFile            | absolute path + file name                                                                                                                                                                        |
| replaceExistingFile | flag used to replace the already existing destination file; if set to false and the destination file already exists, the copy process would be interrupted and the returned value would be false |
| deleteSourceFile    | flag used to delete the source file, once the file has been copied to the destination path                                                                                                       |

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

## Retrieving the file length

In case you need to retrieve the dimension of a file stored in the server file system, you can use this method (since 6.0.2).

**Syntax**

```javascript
var length = utils.getFileLength(String absolutePath);
```



##





