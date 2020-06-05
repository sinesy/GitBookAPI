# Invoking Platform from external apps

## Synchronous invocation of a server-side javascript action

\(deprecated, see: "Invocation of server-side javascript actions"\)

Every built-in server-side functionality configured in Platform can be invoked as a Rest JSON based web service \(e.g. a list of data for a grid, a single record to fill a detail form, etc.\).

Moreover, every server-side Javascript action is itself a Rest JSON based web service and can be invoked.

A simple way to invoke a server-side javascript **action** is through an Ajax request:

```text
var response = new SyncRequest().send(
  contextPath+"/executeJs?applicationId=XXX&actionId=YYY&...",
  "POST", 
  jsonStringObject
);
```

where **jsonStringObject** is a string representation of a javascript object; it can be **null**.

The **response** represents a string response, typically expressed as a json format string.

When executing this request, the javascript action has access to some predefined variables and methods, described below.

Independently of the type of component embedding the server-side Javascript \(an action or a business component\), a few predefined variables are always available:

* **vo**
  * the javascript representation of the json string passed through the Ajax request
* **reqParams**
  * a map of related to all request parameters
* **userInfo**
  * a map of , related to the UserInfo java object; e.g. 

    **username**

    , languageId, companyId, etc.

## Upload a file

Another way to invoke a server-side javascript **action** is through a special Ajax request where you can upload a file as well.

The request must have the a multipart/form-data content type, as the one provided by the standard HTML form. An example of such a form is reported below:

```text
<html>
<body>
        <form action="/contexpathplatform/executeJs/uploadfile?companyId=...&siteId=100&username=...&password=...&languageId=...&appId=...&actionId=...&dirId=9&unzip=N" 
                method=POST  
                enctype="multipart/form-data" 
        >
                <input type="hidden" name="actionId" value="..." />
                <input type="hidden" name="dirId" value="..." />
                <input type="hidden" name="unzip" value="N" />
                <input type="file" name="fileName">
                <br/>
                <input type=submit>
        </form>
</body>
</html>
```

This call allows to send the file, save it and then invoke the specified action, which must be a server side js action.

All parameters passed to the server are accessible form the action \(reqParams\), as well as the request headers \(reqHeaders\).

The file name is also included in vo as the attribute fileName.

The dirId is optional: if not specified, the uploaded file is saved in the tmp dir of the Application Server and then passed \(absolute path + file name\) to vo.fileName

The parameter unzip can have values Y or N: if set to Y, then the uploaded file \(which must be a zip file\) is automatically unzipped and its content \(a single file\) is used to set the vo.fileName \(absolute path included\).



An alternative way to upload a file is using the built-in client-side javascript method:

```text
uploadFile(
  title,
  enabled,
  fileName,
  dirId,
  beforeUploadCallback,
  afterUploadCallback,
  errorOnUploadCallback,
  additionalSettings
);
```

This method open a popup window containing an input field to select a local file and upload it. Moreover, it provides preview and download buttons to show an already uploded file.

**Syntax**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">title</td>
      <td style="text-align:left">Popup window title</td>
    </tr>
    <tr>
      <td style="text-align:left">enabled</td>
      <td style="text-align:left">boolean value used to download only an already uploaded file or to upload/download;
        <br
        />true: upload button is enabled, false: upload button is disabled</td>
    </tr>
    <tr>
      <td style="text-align:left">fileName</td>
      <td style="text-align:left">file name to pre-set in the input field; this is helpful when the file
        has been already uploaded in the past and this popup window is used to
        preview/download it (or re-upload and replace the file)</td>
    </tr>
    <tr>
      <td style="text-align:left">dirId</td>
      <td style="text-align:left">directory identifier, used to define where the file to upload will be
        saved (or when the already uploaded file has been saved, to retrieve it
        and show a preview or download it)</td>
    </tr>
    <tr>
      <td style="text-align:left">beforeUploadCallback</td>
      <td style="text-align:left">
        <p>optional javascript function, automatically invoked by Platform when pressing
          the Upload button; this function must have one argument, whose content
          is:</p>
        <p>{ filename: &quot;....&quot; }</p>
        <p>If the callback function would return false, the upload process is interrupted.</p>
        <p>It is also possible to rename the file to upload, by replacing the value
          of the &quot;filename&quot; attribute passed by reference</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">afterUploadCallback</td>
      <td style="text-align:left">
        <p>optional javascript function, automatically invoked by Platform when pressing
          the Upload button and after a successful upload process; this function
          must have one argument, whose content is:</p>
        <p>{</p>
        <p>success: true|false,</p>
        <p>message: &quot;...&quot;,</p>
        <p>fileName: &quot;....&quot;</p>
        <p>}</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">errorOnUploadCallback</td>
      <td style="text-align:left">
        <p>optional javascript function, automatically invoked by Platform when pressing
          the Upload button in case the upload process failed; this function must
          have one argument, whose content is:</p>
        <p>{</p>
        <p>error: &quot;...&quot;</p>
        <p>}</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">additionalSettings</td>
      <td style="text-align:left">
        <p>optional javascript object; if not null, each attribute is passed forward
          to the server-side; built-in optional attributes are:
          <br />{</p>
        <p>encriptAttachments: true|false,</p>
        <p>panelId: ...</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>

## Invocation of server-side javascript actions

It is possible to invoke Platform web services in three alternative ways:

* by invoking directly a specific web service; in that case **credentials must be provided directly in the request**. This is the simplest case, when you do not need to execute multiple requests; in this case, remember also to include as a parameter removeSession=true, in order to invalidate the session just after its usage
* by using an authentication token, previously provided and generated internally to Platform; this token must be included in any request through the parameter **authToken;** remember also to execute a logoutapp request too, at the end of the whole processing sequence, in order to invalidate the session when it is no longer needed
* by logging on to Platform, through the **login** web service \(using either GET or POST methods\), which gets back an authentication token, valid only for that session and to include in any request, through the parameter **restfulToken;** 

  remember also to execute a **logoutapp** request too, at the end of the whole processing sequence, in order to invalidate the session when it is no longer needed

In the following sections, all these cases are reported.

Before going into depth with each case, it is reported a \(good\) way to invoke a server-side service, starting from the UI layer. The best way to invoke the server is through an asynchronous request, which can be carried out in this way:

```text
try {
    new AsyncRequest().send(uri[,method[,data,mimeType]],callback,callbackError);
 } catch (e) {} // e contains the statusText message send back from server
```

**Syntax** 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">uri</td>
      <td style="text-align:left">
        <p>URL to invoke; in case of Platform it can be something like: contextPath+&quot;/...&quot;;</p>
        <p>e.g. contextPath+&quot;/executeJs?applicationId=...&amp;actionId=...</p>
        <p>e.g. contextPath+&quot;/api?applicationId=...&amp;cmd=...</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">method</td>
      <td style="text-align:left">optional argument; if not specified, it is set to &quot;GET&quot;; it
        represents the HTTP method; allowed values: &quot;GET&quot;; &quot;POST&quot;,
        &quot;PUT&quot;, ...</td>
    </tr>
    <tr>
      <td style="text-align:left">data</td>
      <td style="text-align:left">optional argument; it represents the content to pass forward to the server,
        in the HTTP request body, always expressed as a String (e.g. a JSON string);
        this argument is ignored in case of GET based requests</td>
    </tr>
    <tr>
      <td style="text-align:left">mimeType</td>
      <td style="text-align:left">optional argument; request content type (e.g. application/json)</td>
    </tr>
    <tr>
      <td style="text-align:left">callback</td>
      <td style="text-align:left">
        <p>optional argument; if specified, it is a javascript function automatically
          invoked by Platform at the end of a successful HTTP request; bear in mind
          that a &quot;successful request&quot; is a request whose HTTP response
          code is 200, i.e. a response whose JSON content is</p>
        <p>{ success: false, message: &quot;...&quot; }</p>
        <p>is still considered a &quot;successful request&quot; T</p>
        <p>This function must have one argument, containing the response text, expressed
          as a String</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">callbackError</td>
      <td style="text-align:left">
        <p>optional argument; if specified, it is a javascript function automatically
          invoked by Platform at the end of an HTTP request interrupted with errors,
          i.e. whose HTTP response code is NOT 200.</p>
        <p>This function must have two arguments: statusText and status (a number)</p>
      </td>
    </tr>
  </tbody>
</table>

An alternative way to invoke the server layer of Platform, but ONLY for server-side javascript actions, is through the following client-side javascript method:

```text
callAsyncAction({
  actionId: ...,          // identifier of the server-side action to invoke
  httpMethod: "GET|POST", // optional argument; allowed values: GET|POST. Default value: POST
  params: { ... },        // js optional argument; object containing additional parameters to add to the http request; can be null
  obj: { ... },           // optional argument; js object to send to the action; can be null
  callback: function(json){}, // json is a text formatted response
  callbackError: function(json,status) {} // json is a text formatted content related to the error, status the HTTP error code (a number), e.g. 401
});
```



The simplest way to invoke a single request is by calling it directly, and **passing the credentials along with the other parameters** required by the specific web service to invoke.

Example:

1. [http://localhost:8080/platform/getlist?applicationId=...&functionId=utenti\_abilitati.gridReportPanel889&compId=809&panelId=889&](http://localhost:8080/platform/getlist?applicationId=...&functionId=utenti_abilitati.gridReportPanel889&compId=809&panelId=889&)

   companyId=...&siteId=...&=...&username=...password=...&languageId=....&**removeSession=true**

The last parameter force the removal of any session content involved with this single request.

Pay attention that this solution is not the best in case you have to execute the same request multiple times: it would be better in such a case, to perform the login first, get an authentication token and use it for the next requests. This alternative solution is described below.

Another optional parameter is

**onlyLogin=true**

which by-pass the loading of any additional data after the authentication step: that will speed up the response of the web service, which will be a stateless web service. On the other hand, no additional data will be loaded and consequently it is up to the js code within the action to fetch any data needed for the correct execution of the web service.

A better and **more secure solution is to include the applicationId/companyId/siteId/username/password parameters described above as headers parameters**, rather than request parameters: in this way, data is encrypted when using the HTTPS protocol.

Platform allows to create tokens dynamically; **a token can then be included** in a Restful request to access Platform functionalities.

Tokens generation can be performed from within a server-side javascript action \(see that section\).

This can be helpful for example in case of single requests coming from an email message or from a button pressed in another application: a request should be generated, using a token previously generated within platform.

Once got a token, it is possible to use it starting from an external application, when a plain URL can be invoked.

Example:

```text
http://localhost:8080/platform/getlist?applicationId=...&functionId=utenti_abilitati.gridReportPanel889&compId=809&panelId=889&authToken=...&username=...&languageId=...&companyId=...&siteId=...
```

A better way to send such a request is by using HTTPS instead of HTTP: in this case the request headers and body are encrypted.

Moreover, it is a good idea to send the credentials not as request parameters \(like in the example above\), but by passing them in the request header, so that they will be encrypted when using the HTTPS protocol.

In this case, the URI must be something like:

```text
http://localhost:8280/wag/login/loginPostHeader?appId=…&applicationId=…&needTempToken=1&username=..
```

whereas on the request headers you have to include the following parameters:

* companyId
* siteId
* username
* password
* languageId

Another way to get a token is to **perform the authentication before invoking the service**.

An example of Restful authentication is:

[http://localhost:8080/platform/login?username=...&password=...&companyId=...&siteId=100&applicationId=...&appId=...&needTempToken=1](http://localhost:8080/platform/login?username=...&password=...&companyId=...&siteId=100&applicationId=...&appId=...&needTempToken=1)

Again, **better ways to execute such a request is** 

* **by using HTTPS instead of HTTP and pass forward the credentials in the body request, using the POST HTTP method;** in this case the request headers and body are encrypted.
* **by using HTTPS instead of HTTP and pass forward the credentials as request headers, using the POST HTTP method and** "**loginPostHeader**" instead of "login" web-context; in this case the request headers and body are encrypted.

A successful response provided by one of the requests above is something like:

```text
{
"siteId":XXX,
"companyId":"YYYY",
"success":true,
"token":"ZZZZZZ"
}
```

If the authentication task completes successfully, the response expressed in JSON format would contain the token to include in any Restful request sent from this time, as for the one reported above.

In case of errors when trying to authenticate, a JSON error response is sent back:

```text
{
"message":"",
"success":false
}
```

This is the list of possible JSON responses:

* { “success”: false, “message”: “Reached maximum number of concurrent users for this licence”, “errorCode”: “MAX\_NR\_OF\_USERS” }
* { “success”: false, “message”: “Invalid credentials”, “errorCode”: “INVALID\_CREDENTIALS” }
* { “success”: false, “message”: “Password expired”, “errorCode”: “PASSWORD\_EXPIRED” }
* { “success”: false, “message”: “Account locked”, “errorCode”: “ACCOUNT\_LOCKED” }
* { “success”: false, “message”: “Max number of requests reached”, “errorCode”: “MAX\_NR\_OF\_REQUESTS\_REACHED” }
* { “success”: false, “message”: “Token expired”, “errorCode”: “TOKEN\_EXPIRED” }
* { “success”: false, “message”: “Internal error”, “errorCode”: “INTERNAL\_ERROR” }

An example of an action invocation to perform after a successful authentication is:

[http://localhost:8080/platform/executeJs?applicationId=...&actionId=...&restfulToken=...&companyId=...&siteId=....&username=](http://localhost:8080/platform/executeJs?applicationId=...&actionId=...&restfulToken=...&companyId=...&siteId=....&username=)...

**The session is maintained active typically for 10 minutes**, without receiving other requests \(which can be configured on the web.xml file of the web application\). Additional requests will extend the timeout.

If needed, you can create on your external client a thread to maintain the session active, through the “**keepAlive**” command. The following request is provided for that usage:

[http://localhost:8080/platform/keepAlive?applicationId=...&restfulToken=...&companyId=...&siteId=...&username=](http://localhost:8080/platform/keepAlive?applicationId=...&restfulToken=...&companyId=...&siteId=...&username=)...

In any case, you’d better also execute a second request, used to inform Platform that the session is concluded and the force the log out from the application: in this way, any session content is removed from the server.

Platform automatically removes this sessions after a timeout, but if you forget to perform the log out request and execute the same request a large number of times, there is the risk that the sessions will be removed after many minutes and before that time, the server’s memory could overflow the maximum value, is it is always a good idea to call the log out request too:

[http://localhost:8080/platform/logoutapp?applicationId=...&restfulToken=](http://localhost:8080/platform/logoutapp?applicationId=...&restfulToken=)...

## Creating web services starting from alias

It is possible to create URLs like this one:

```text
https://host:port/webcontext/api?cmd=...&appId=...&otherParametersLikeCredentials
```

The value for "cmd" parameter can be anything which can identify an application command as an "alias". The list of "alias" you can define are reported in the Services -&gt; Alias Requests functionality, available in the App Designer.

Through this feature you can enrich the amount of request parameters you can add to the original request, including credentials.

Here they are a few examples of how to use alias:

**A public web service**

A web service is public if it does not require any authentication process.

**Note**: pay attention to this kind of requests. It is never a good idea to design applications whose web services can be invoked any number of times without any authentication process!

```text
https://host:port/webcontext/api?cmd=myPublicWebService&appId=...
```

The corresponding alias definition in "Alias Request" must necessarely be defined with the credentials:

myPublicWebService -&gt; /executeJs?actionId=...&companyId=...&siteId=...&username=...&password=...&languageId=...

**A web service which requires authentication**

In such a case, either a token must be provided or the credentials, as in the following example:

```text
https://host:port/webcontext/api?cmd=myWebService&appId=...&companyId=...&siteId=...&username=...&password=...&languageId=...
```

The corresponding alias definition in "Alias Request" is easier:

```text
myWebService -> /executeJs?actionId=...&removeSession=true
```

In the latter case, it is important also to include the "removeSession" parameter, in oder to define a stateless web service.

**Note**: evaluate the possibility to speed up the web service execution, by including also **onlyLogin=true** parameter in the alias definition: in such a case, you cannot access to any user session parameters form within your web service.

## Loading parameters when invoking a Platform web service

In the previous sections, two ways to invoke a server-side javascript action have been reported: 

* a "login" web service invocation to authenticate and get a token + the web service invocation 
* a direct web service invocation, where credentials are embedded in the request parameters/headers

A difference between the 2 approaches is that the first force the parameters loading as well, during the authentication process \(user parameters, application parameters, global parameters\), whereas the second approach does not load any parameter.

\(since 6.0.1 version\) It is possible to force parameter loading in the second case as well, by including the request the following parameter:

**...&loadPars=true**

## Speed up a Platform web service execution

\(since 6.0.1 version\) Every time a web service in invoked and credentials are passed forward together with the request, an authentication process is automatically carried out behind the scenes. Moreover, if loadPars=true is included in the request, an additional time is required in order to load all parameters.

A way to speed up such a repetitive request is by including the  request URL the following parameter:

**...&cacheInternalState=true**

In this way, credentials passed in the request are compared with credentials fetched in previous checking and already cached. If the authentication process is passed \(in memory\), the internal state \(and parameters loading as well\) is fetched from cache, so that no queries are required to execute the web service.

Finally, if the application parameter named "**Manually loaded digest**" is checked, the server-side javascript action is also cached and no queries are performed in order to retrieve the source code.

When all these settings are activated, a web service invocation does not perform any database access to run the web service.



