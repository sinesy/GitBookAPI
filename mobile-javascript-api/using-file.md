# File and image

## shareDocument\(path, filename\)

Open the dialog for share the document. The dialog content depends on the specific mobile platform \(Android or iOS\).  
Required parameters must be included in a javascript object, containing the following attributes:

| Argument | Description |
| :--- | :--- |
| path | the path file, including the file name |
| filename | the name of the file \(with the extension\) |

A typical usage of this method is combined with getRemoteFileURL\(\) method, used to get the right \(remote\) path for a file stored in the Platform central site, within a specific directory.

## downloadDocument\(path, filename\) <a id="downloaddocument"></a>

In Android launch the download of the file \(Save the file in the default download folder\), in iOs open the dialog for share or download the file \(the dialogis the same as the shareDocument methot\).  
Required parameters must be included in a javascript object, containing the following attributes:

| Argument | Description |
| :--- | :--- |
| path | the path file, including the file name |
| filename | the name of the file \(with the extension\) |

A typical usage of this method is combined with getRemoteFileURL\(\) method, used to get the right \(remote\) path for a file stored in the Platform central site, within a specific directory.

## getRemoteFileURL\(dirId,filename\)

Get the complete URL to get a document path, previously stored in the Platform central site, within a specific directory.  
Required parameters are:

```text
 dirId-remote directory id, defined through the Web Designer
 filename-the remote file name, stored within the specified directory.
```

## openPreview\(directoryId, fileName\)

> If you want to share an online public file see [openremotedocument](https://4wsplatform.gitbook.io/api/mobile-javascript-api/dialogs#openremotedocument) method.

Show on a modal full size window a web content stored online on the Platform server, identified by the specified directory + file name.  
Required parameters are:

```text
 directoryId-The directory id identifying the absolute path where the resource has been stored on the Platform server
```

| Argument | Description |
| :--- | :--- |
| fileName | filename related to the web resource to download and show |

## panelScreenshot\(idPanel\);

Generate an image of the panel shown in the app, identified by idPanel and save it in the local file system. Themethod gets back the absolute path + image name for the just generated screenshot.  
Required arguments:

```text
 id -identifier ofthe panel to capture
 return theabsolute path + image name for the just generated screenshot.
```

## shareOrDownloadDocument\(pathToShare,filename\);

Open a dialog through whichthe end user can choose an app where sharing the specified file. It is also possible to choose to download the file locally.  
Required arguments:

```text
 pathToShare - absolute path where the file to share/download is located
 filename - name of the file to share/download, located in the specified absolute path
```

## shareDocument\(path,filename\);

Open a dialog through whichthe end user can choose an app where sharing the specified file.  
Required arguments:

```text
 path - absolute path where the file to shareis located
 filename - name of the file to download, located in the specified absolute path
```

## downloadDocument\(path,filename\);

Open a dialog through whichthe end user can download locallythe specified file.  
Required arguments:

```text
 path - absolute path where the file to downloadis located
 filename - name of the file to share, located in the specified absolute path
```

## sendFile\(url, filePath, fileName, jsCallback\);

Invoke a remote server to pass a local file using the POST HTTP method and the multi-part content type: a file and a filename will be passed.

At the end of the sending process, the jsCallback will be invoked.

Required arguments:

| Argument | Description |
| :--- | :--- |
| url | URL to invoke |
| filePath | absolute path \(with the file name\) in the local file system related to the file to send |
| fileName | file name passed to the server |
| callback | function name which will be invoked when the file has been successfully sent; an argument is passed to the function, containing the response of the web service invoked |

In the following example, a predefined Platform web service is invoked: it has been designed to work withHTTP requests having POST method and multi-part content-type. Moreover, such a web service requires an action id which will be automatically invoked after sending the file. You can use it to process the file in some way and get back a response to the client.

```javascript
var myCallback = function(responseFromWebService) {
  // do something with the response
}
var filePath = ...
var fileName = ....

var url = getBaseURL() + "/executeJs/uploadfile?appId=...&applicationId=...&actionId=...&dirId=...&unzip=false&restfulToken="+getToken();
sendFile(url, filePath, fileName, "myCallback");
```

## **getPaletteFromImage\(filePath\)**

Returns the color palette from an image, the palette si an array like: \[\[r,g,b\],….,\[r,g,b\]\]

Required arguments:

| Argument | Description |
| :--- | :--- |
| filePath | path of a local image \(no remote file\) |

```javascript
var palette = getPaletteFromImage(filePaht);
var paletteArray = JSON.parse(palette);
```

## getLogFilePath\(\);

Return complete the log file path, you can use it for share o send this file.

> Since 6.0.1 version

## zipFile\(String sourcePath, String fileName\)

Zip the passed file with the passed fileName. Return the complete path to the zip, you can use it for share o send this file.

> Since 6.0.1 version

## deleteFile\(String sourcePath\)

Delete the passed file.

> Since 6.0.1 version

