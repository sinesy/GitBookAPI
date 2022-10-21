# HTTP

## Execute an HTTP(s) connection and fetch the result

result expressed as a String (e.g. a JSON or XML result content)

**Syntax**

```javascript
var json = utils.getWebContent(uri, replaceVariables, httpMethod, contentType, requestBody, user, pwd);
```

**Details**

| Argument              | Description                                                                                                 |
| --------------------- | ----------------------------------------------------------------------------------------------------------- |
| uri                   | URI, expressed as http:// or https:// with or without variables, expressed as :XXX                          |
| replaceVariables      | flag used to replace variables within the uri (variables are expressed as :XXX)                             |
| httpMethod (optional  | can be null); if specified, it defines the HTTP method: GET, POST                                           |
| contentType (optional | can be null); if specified, it defines the content type request (e.g. application/json)                     |
| requestBody (optional | can be null); if specified, it defines the request body, expressed as a String (e.g. a JSON or XML content) |
| user (optional        | can be null); if specified, it defines the username for a BASIC authentication                              |
| pwd (optional         | can be null); if specified, it defines the password for a BASIC authentication                              |

```
 Returns the HTTP response, expressed as a String (e.g. a JSON or XML result).
```

HTTP response codes included between 200 and 399 are managed as correct answers and the response is sent back through the "json" return variable.

In case of HTTP response codes above or equal to 400, an exception is fired \_and the exception content would contain the message sent back by the invoked web service; consequently, it would be better to surround this instruction between try-catch.

**Important note**: Please pay attention to the URL definition: it must respect the HTTP syntax, which means it cannot contains special characters, such as a space or \n. In case of special characters, you will get an HTTP error when trying to use the URL. In such a scenario, use the **encodeURI** method:

```javascript
var url = "http://host/context?par1=abc de&par2=ab\ncd";
url = encodeURI(url);
utils.getWeb...
```

**Examples with errors:**

```javascript
try {
 var res = utils.getWebContent("http://www.google.it","PUT"...); // HTTP errors >= 400
}
catch(e) {
  /*
JavaException: java.lang.Exception: 411
<!DOCTYPE html>
<html lang=en>
  <meta charset=utf-8>
  <meta name=viewport content="initial-scale=1, minimum-scale=1, width=device-width">
  <title>Error 411 (Length Required)!!1</title>
  <style>
    *{margin:0;padding:0}html,code{font:15px/22px arial,sans-serif}html{background:#fff;color:#222;padding:15px}body{margin:7% auto 0;max-width:390px;min-height:180px;padding:30px 0 15px}* > body{background:url(//www.google.com/images/errors/robot.png) 100% 5px no-repeat;padding-right:205px}p{margin:11px 0 22px;overflow:hidden}ins{color:#777;text-decoration:none}a img{border:0}@media screen and (max-width:772px){body{background:none;margin-top:0;max-width:none;padding-right:0}}#logo{background:url(//www.google.com/images/branding/googlelogo/1x/googlelogo_color_150x54dp.png) no-repeat;margin-left:-5px}@media only screen and (min-resolution:192dpi){#logo{background:url(//www.google.com/images/branding/googlelogo/2x/googlelogo_color_150x54dp.png) no-repeat 0% 0%/100% 100%;-moz-border-image:url(//www.google.com/images/branding/googlelogo/2x/googlelogo_color_150x54dp.png) 0}}@media only screen and (-webkit-min-device-pixel-ratio:2){#logo{background:url(//www.google.com/images/branding/googlelogo/2x/googlelogo_color_150x54dp.png) no-repeat;-webkit-background-size:100% 100%}}#logo{display:inline-block;height:54px;width:150px}
  </style>
  <a href=//www.google.com/><span id=logo aria-label=Google></span></a>
  <p><b>411.</b> <ins>That’s an error.</ins>
  <p>POST requests require a <code>Content-length</code> header.  <ins>That’s all we know.</ins>
  */
}
```

```javascript
try {
 var res = utils.getWebContent("http://notexistinghost"...); // this URL refers a not existing host 
}
catch(e) {
  // "e = JavaException: java.net.UnknownHostException: www.gooooooooggle.it"
}
```

```javascript
try {
  var json = utils.getWebContent("ht://host"...); // this is an invalid URL 
  ...
}
catch(e) {
  // e = "JavaException:java.net.MalformedURLException: no protocol: xyz"
}
```

## Execute an HTTP(s) connection and fetch the result (with headers)

result expressed as a String (e.g. a JSON or XML result content)

**Syntax**

```javascript
var json = utils.getWebContentWithHeaders(uri, replaceVariables, httpMethod, contentType, requestBody, user, pwd, charSet,  headers);
```

**Details**

| Argument              | Description                                                                                                                                                                       |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| uri                   | URI, expressed as http:// or https:// with or without variables, expressed as :XXX                                                                                                |
| replaceVariables      | flag used to replace variables within the uri (variables are expressed as :XXX)                                                                                                   |
| httpMethod (optional  | can be null); if specified, it defines the HTTP method: GET, POST                                                                                                                 |
| contentType (optional | can be null); if specified, it defines the content type request (e.g. application/json)                                                                                           |
| requestBody (optional | can be null); if specified, it defines the request body, expressed as a String (e.g. a JSON or XML content)                                                                       |
| user (optional        | can be null); if specified, it defines the username for a BASIC authentication                                                                                                    |
| pwd (optional         | can be null); if specified, it defines the password for a BASIC authentication                                                                                                    |
| charSet (optional     | can be null); if specified, it defines the char set to use for the request body (req property "Accept-Charset"); if not specified, it is autodefined as "UTF-8"                   |
| headers(optional      | can be null); if specified, it defines a collection of attribute-values to pass as request headers; it is expressed as a javascript object: { attr1: value2, attr2: value2, ... } |

```
 Returns the HTTP response, expressed as a String (e.g. a JSON or XML result).
```

HTTP response codes included between 200 and 399 are managed as correct answers and the response is sent back throughthe "json" return variable.

In case of HTTP response codes above or equal to 400, an exception is fired and the exception content would contain the message sent back by the invoked web service; consequently, it would be better to surround this instruction between try-catch.

**Important note**: Please pay attention to the URL definition: it must respect the HTTP syntax, which means it cannot contains special characters, such as a space or \n. In case of special characters, you will get an HTTP error when trying to use the URL. In such a scenario, use the **encodeURI** method:

```javascript
var url = "http://host/context?par1=abc de&par2=ab\ncd";
url = encodeURI(url);
utils.getWeb...
```

**Example**

```javascript
try {

 var json = utils.getWebContentWithHeaders(...);

 ...

}

catch(e) {

 // e.message would containthe error message

}
```

## Execute an HTTP(s) connection and fetch the result (most flexible version)

result expressed as a String (e.g. a JSON or XML result content)

**Syntax**

```javascript
var json = utils.getWebContentWithSettings(
  uri, 
  replaceVariables, 
  httpMethod, 
  contentType, 
  requestBody, 
  user, 
  pwd, 
  charSet,  
  headers,
  timeout,
  additionalSettings
);
```

**Details**

| Argument              | Description                                                                                                                                                                       |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| uri                   | URI, expressed as http:// or https:// with or without variables, expressed as :XXX                                                                                                |
| replaceVariables      | flag used to replace variables within the uri (variables are expressed as :XXX)                                                                                                   |
| httpMethod (optional  | can be null); if specified, it defines the HTTP method: GET, POST                                                                                                                 |
| contentType (optional | can be null); if specified, it defines the content type request (e.g. application/json)                                                                                           |
| requestBody (optional | can be null); if specified, it defines the request body, expressed as a String (e.g. a JSON or XML content)                                                                       |
| user (optional        | can be null); if specified, it defines the username for a BASIC authentication                                                                                                    |
| pwd (optional         | can be null); if specified, it defines the password for a BASIC authentication                                                                                                    |
| charSet (optional     | can be null); if specified, it defines the char set to use for the request body (req property "Accept-Charset"); if not specified, it is autodefined as "UTF-8"                   |
| headers(optional      | can be null); if specified, it defines a collection of attribute-values to pass as request headers; it is expressed as a javascript object: { attr1: value2, attr2: value2, ... } |
| timeout               | optional argument: can be set to null; timeout for the request, expressed in seconds; helpful when the service to invoke could be very slow                                       |
| additionalSettings    | optional argument: can be set to null; it is a javascript object containing additional settings                                                                                   |

```
 Returns the HTTP response, expressed as a String (e.g. a JSON or XML result).
```

Supported attributes by "additionalSettings" argument:

* **log**: true|false - used to turn down the automatic logging of an HTTP request; helpful when you don't want to log credentials passed forward or when you have a large number of requests
* **enableSNIExtension**: true|false - used to customize the SNI settings per single request



HTTP response codes included between 200 and 399 are managed as correct answers and the response is sent back throughthe "json" return variable.

In case of HTTP response codes above or equal to 400, an exception is fired and the exception content would contain the message sent back by the invoked web service; consequently, it would be better to surround this instruction between try-catch.

**Important note**: Please pay attention to the URL definition: it must respect the HTTP syntax, which means it cannot contains special characters, such as a space or \n. In case of special characters, you will get an HTTP error when trying to use the URL. In such a scenario, use the **encodeURI** method:

```javascript
var url = "http://host/context?par1=abc de&par2=ab\ncd";
url = encodeURI(url);
utils.getWeb...
```

## Execute an HTTP(s) connection and fetch the result (binary content)

result expressed as a binary content and store it into the specified file

**Syntax**

```javascript
utils.getBinaryContent(toFile, uri, replaceVariables, httpMethod, contentType, requestBody, user, pwd);
```

| Argument              | Description                                                                                                                        |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Details               |                                                                                                                                    |
| toFile                | absolute path including the file name, related to the local binary file to create and fill in with the result of this HTTP request |
| uri                   | URI, expressed as http:// or https:// with or without variables, expressed as :XXX                                                 |
| replaceVariables      | flag used to replace variables within the uri (variables are expressed as :XXX)                                                    |
| httpMethod (optional  | can be null); if specified, it defines the HTTP method: GET, POST                                                                  |
| contentType (optional | can be null); if specified, it defines the content type request (e.g. application/json)                                            |
| requestBody (optional | can be null); if specified, it defines the request body, expressed as a String (e.g. a JSON or XML content)                        |
| user (optional        | can be null); if specified, it defines the username for a BASIC authentication                                                     |
| pwd (optional         | can be null); if specified, it defines the password for a BASIC authentication                                                     |

Fetches the HTTP response, expressed as a binary content and stores in to the specified file.

**Important note**: Please pay attention to the URL definition: it must respect the HTTP syntax, which means it cannot contains special characters, such as a space or \n. In case of special characters, you will get an HTTP error when trying to use the URL. In such a scenario, use the **encodeURI** method:

```javascript
var url = "http://host/context?par1=abc de&par2=ab\ncd";
url = encodeURI(url);
utils.getBinaryContent(...);
```

## Execute an Alfresco web script

starts with "service/xyz?..." and fetch the result, expresses as a String (e.g. a JSON or XML result content)

**Syntax**

```javascript
var responseBody = utils.getAlfrescoWebScript(uri, replaceVariables, httpMethod, bodyRequest, charSet);
```

**Details**

| Argument         | Description                                                                                                                                 |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| uri              | last part of the URI to pass to the Alfresco base URL, in order to invoke a webscript, i.e. from the webscript name to required parameters  |
| replaceVariables | flag used to define if :XXX value in the uri must be replaced by Platform defined variables                                                 |
| httpMethod       | optional: HTTP method to use: GET, POST, etc.                                                                                               |
| bodyRequest      | optional: body request to pass, expressed as a String                                                                                       |
| charSet          | optional: the request/response charset to use; if not specified, Unicode charset will be used (UTF-8); possible values: UTF-8, Windows-1252 |

## Execute an HTTP(s) connection using NLTM authentication

result expressed as a String (e.g. a JSON or XML result content)

**Syntax**

```javascript
var json = utils.getWebContentWithNTLM(
  uri, 
  contentType, 
  httpMethod, 
  requestBody, 
  user, 
  pwd,
  workstation,
  domain,
  settings
);
```

**Details**

| Argument               | Description                                                                                                 |
| ---------------------- | ----------------------------------------------------------------------------------------------------------- |
| uri                    | URI, expressed as http:// or https:// with or without variables, expressed as :XXX                          |
| contentType (optional) | can be null); if specified, it defines the content type request (e.g. application/json)                     |
| httpMethod (optional   | can be null); if specified, it defines the HTTP method: GET, POST                                           |
| requestBody (optional) | can be null); if specified, it defines the request body, expressed as a String (e.g. a JSON or XML content) |
| user (optional)        | Windows username                                                                                            |
| pwd (optional)         | Windows password                                                                                            |
| workstation            | Windows workstation                                                                                         |
| domain                 | Windows domain                                                                                              |
| settings               | optional js object; it can contain a few other settings, reported below                                     |

```
 Returns the HTTP response, expressed as a String (e.g. a JSON or XML result).
```

HTTP response codes included between 200 and 399 are managed as correct answers and the response is sent back through the "json" return variable.

In case of HTTP response codes above or equal to 400, an exception is fired an the exception content would contain the message sent back by the invoked web service; consequently, it would be better to surround this instruction between try-catch.

The "settings" js object can include the following attributes:

* "connectionTimeout: an optional number defining the timeout for the connection
* "headers": a js object containing request headers, e.g. required credentials

Example:

```
var requestBody = "...";
var json = utils.getWebContentWithNTLM(
    'https://...', 
    "application/json; charset=utf-8",
    "POST",
    requestBody,
    "username",
    "pwd",
    "workstation",
    "domain",
    null
); 
```

##
