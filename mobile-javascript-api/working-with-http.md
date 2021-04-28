# Working with HTTP

## checkConnection\(\);

Check if there is an Internet connection available: if there is, then returns "true" \(a String\), otherwise "false".

## getWebContent\(url,httpMethod,contentType,bodyRequest\) <a id="getwebcontent"></a>

execute the HTTP request.  
Required parameters:

| Argument | Description |
| :--- | :--- |
| url | URI to invoke \(e.g. [http://host:port/webcontent](http://host:port/webcontent)\) |
| httpMethod | HTTP method to use; allowed values: GET, POST, PUT, DELETE |
| contentType | optional, can be null; e.g. application/json |
| bodyRequest | optional, can be null; the body request, expressed as a String |

```text
 The return value is a String content.
```

**Example**

```javascript
var url = getBaseURL()+"/executeJs?applicationId=...&amp;appId=...&amp;actionId=...&amp;otherparameters&amp;restfulToken="+getToken();
var json = getWebContent(url,"GET","application/json",null);
```

## getWebContent\(url,httpMethod,contentType,bodyRequest,headers\) <a id="sendfile"></a>

execute the HTTP request with headers.  
Required parameters:

| Argument | Description |
| :--- | :--- |
| url | URI to invoke \(e.g. [http://host:port/webcontent](http://host:port/webcontent)\) |
| httpMethod | HTTP method to use; allowed values: GET, POST, PUT, DELETE |
| contentType | optional, can be null; e.g. application/json |
| bodyRequest | optional, can be null; the body request, expressed as a String |
| headers | optional, can be null: the request headers, expressed as a map \(a js object\) |

```text
 The return value is a String content.
```

**Example**

```javascript
var url = getBaseURL()+"/executeJs?applicationId=...&amp;appId=...&amp;actionId=...&amp;otherparameters&amp;restfulToken="+getToken();
var headers = {
                header1 : "ABCDEFG",
                header2 : "12345",
                };
var json = getWebContent(url,"GET","application/json",null,headers);
```

## getWebContent\(url,httpMethod,contentType,bodyRequest,headers,callback\) <a id="sendfile"></a>

execute the HTTP ASYNC request with headers and callback function.  
Required parameters:

| Argument | Description |
| :--- | :--- |
| url | URI to invoke \(e.g. [http://host:port/webcontent](http://host:port/webcontent)\) |
| httpMethod | HTTP method to use; allowed values: GET, POST, PUT, DELETE |
| contentType | optional, can be null; e.g. application/json |
| bodyRequest | optional, can be null; the body request, expressed as a String |
| headers | optional, can be null: the request headers, expressed as a map \(a js object\) |
| callback | optional, can be null: the name of the callback async function, the input of function is the json response |

```text
 The return value is an empty String.
```

**Example**

```javascript
var url = getBaseURL()+"/executeJs?applicationId=...&amp;appId=...&amp;actionId=...&amp;otherparameters&amp;restfulToken="+getToken();
var headers = {
                header1 : "ABCDEFG",
                header2 : "12345",
                };
function callbackAsync(response){
    showMessageDialog({
        title : "TITLE",
        subtitle : "html response length: "+ response.length,
        titleButtonSuccess : "ok"
    },null);
}
var json = getWebContent(url,"GET","application/json",null,headers,"callbackAsync");
```

## getWebContentLite\(url,httpMethod,contentType,bodyContent,headers, Object timeoutMS\) <a id="sendfile"></a>

A lite version of getWebContent, this version not manages cookies, session and not refresh token. Use this function when you have to call a physical device like a WI-FI printer.

> Since 6.0.1 version

## getWebContentAdvanced\(url,httpMethod,contentType,bodyContent,headers, timeoutMS\)

Works like getWebContent, but the returns consists of:

* responseCode
* headers
* body

the getWebContent instead returns the body directly, or null in case of responseCode different from 200

> Since 6.0.2 version

## sendFile\(url, filePath, fileName, jsCallback\); <a id="sendfile"></a>

Invoke a remote serverto pass a local file using the POST HTTP method and the multi-part content type: a file and a filename will be passed.  
At the end of the sending process, the jsCallback will be invoked.  
Required arguments:

```text
 url - URL to invoke
 filePath - absolute path (without the file name) in the local file system related to the file to send
 fileName - file name to send; it is located in the absolute path specified through the previous argument
 callback - function name which will be invoked when the file has been successfully sent;an argument is passed to the function, containing the response of the web service invoked
```

In the following example, a predefined Platform web service is invoked: it has been designed to work withHTTP requests having POST methodand multi-part content-type. Moreover, such a web service requires an action id which will be automatically invoked after sending the file. You can use it to process the file in some way and get back a response to the client.

```javascript
var myCallback = function(responseFromWebService) {
  // do something with the response
}
var filePath = ...
var fileName = ....

var url = getBaseURL() + "/executeJs/uploadfile?appId=...&amp;applicationId=...&amp;actionId=...&amp;dirId=...&amp;unzip=false&amp;restfulToken="+getToken();
sendFile(url, filePath, fileName, "myCallback");
```

## ping\(ip, successCallback,  errorCallback\)

If the ip is available call the successCallback else the errorCallback.

> Since 6.0.2

## getConnectionData\(callback\)

Get the connection data and pass it to a callback. This function also save the connection data to server con60.

```javascript
getConnectionData("fun");

var fun = functioin(jsonData){
    var data = JSON.parse(jsonData);

    data.downloadRate //in KB/s
    data.uploadRate //in KB/s
    data.latency //in seconds
    data.connectionType // WIFI - UNKNOWN - 2G - 3G - 4G - NO_CONNECTION


}
```

## logConnectionData\(\)

Save the connection data on server con60, this function don't block the user interface.

## md5HexDigest\(stringToEncode\)

Return the string encode with md5

