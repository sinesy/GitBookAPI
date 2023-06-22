# Function JSS

## Send an email, using SMTP settings defined at application level/globally

**Syntax**

```javascript
utils.sendEmail(from, to, cc, bcc, subject, body, isHtmlContent, returnReceipt, zipFiles, deleteFilesAfterSending, dirId, fileName, filesToAttach)
```

**Details**

| Argument                | Description                                                                                                                  |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| from                    | (optional, can be null) a string representing the email address to use as the "from address" to send the email               |
| to                      | a string composed of one or more email addresses, separated by a comma (,)                                                   |
| cc                      | carbon copy addresses - a string composed of one or more email addresses, separated by a comma (,)                           |
| bcc                     | hidden addresses - a string composed of one or more email addresses, separated by a comma (,)                                |
| subject                 | a string representing the email title                                                                                        |
| body                    | the email body content                                                                                                       |
| isHtmlContent           | a boolean flag used to define if the body content is in HTML format or not                                                   |
| returnReceipt           | a boolean flag used to request a return receipt to the destinators                                                           |
| zipFiles                | a boolean flag used to compress all files to attach in a unique zip file and send it, in order to reduce the email size      |
| deleteFilesAfterSending | a boolean flag used to optionally delete files to attach, after sending the email                                            |
| dirId                   | optional dir id used to save the message also to the server file system                                                      |
| fileName                | optional file name required in case the dir id has been specified; the message will be save in eml format on the file system |
| filesToAttach           | a list of files to attach, separated by a comma; use \[] to notinclude files; each file must include the absolute path       |

This method will fire an exception if the email has NOT been sent correctly (e.g. attachment file not found).



**Example without attachments**:

```javascript
utils.sendEmail(
  "fromemailaddress@mydomain.com", // from address
  "toemailaddress@domain.com", // to address, can be a list of email addresses, separated by a comma (,)
  null, // carbon copy 
  null, // blank carbon copy 
  "email title", // subject
  "email body", // it can be plain text or HTML formatted text 
  true, // isHtmlContent, false to set plain text 
  false, // returnReceipt
  false, // zipFiles, in case of attachments
  false, // deleteFilesAfterSending, in case of attachments
  null, // dirId, in case of attachments
  null, // fileName, in case of attachments
  null, // filesToAttach, in case of attachments
);
```

## Send an alert email from template with conversation and SMTP settings

**Syntax**

```javascript
utils.sendAlertEmailFromTemplateWithConversationAndSMTPSettings(String from,Number templateId,String destinations,String carbonCopy,String blindCarbonCopy,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Long dirId,String fileName,String[] filesToAttach)
```

| Argument        | Description                                                                                                                                                                                                                                          |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| from            | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user, whose email address must be defined in the user detail form; it can be overridden by the template "from" field     |
| templateId      | id of the template previously defined, used to set subject and body; optionally, the template can be optionally used to set from, to, cc, receipt flag too                                                                                           |
| destinations    | list of usernames who will receive the alert; they must be separated by a comma (,); for each username specified, its email address must be defined in the user detail form; it can be overridden by the template "to" field                         |
| priority        | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 (minor), 1, (normal), 2 (high) |
| jsObj           | javascript record which substitute the variables in the template previously defined                                                                                                                                                                  |
| carbonCopy      | optional argument used to specify a separated list (by comma) of email addresses which will receive the email message in carbon copy                                                                                                                 |
| blindCarbonCopy | optional argument used to specify a separated list (by comma) of email addresses which will receive the email message in blind carbon copy                                                                                                           |
| isHtmlContent   | lag used to specify if the message text is formatted in HTML or plain text                                                                                                                                                                           |
| conversationId  | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo                                                                                                    |
| smtpHost        | SMPT host name to use                                                                                                                                                                                                                                |
| smtpPort        | SMTP port                                                                                                                                                                                                                                            |
| smtpUsername    | SMTP username to use to authetication to the SMTP server                                                                                                                                                                                             |
| smtpPassword    | SMTP password to use to authetication to the SMTP server                                                                                                                                                                                             |
| protocol        | Protocol to use (e.g. smtp vs smtps)                                                                                                                                                                                                                 |
| useTLS          | flag to use (Y/N) to enable TLS                                                                                                                                                                                                                      |
| fileName        | optional file name required in case the dir id has been specified; the message will be save in eml format on the file system                                                                                                                         |
| dirId           | optional dir id used to save the message also to the server file system                                                                                                                                                                              |
| filesToAttach   | a list of files to attach, separated by a comma; use \[] to notinclude files; each file must include the absolute path                                                                                                                               |

```
 smtpXXX-SMTP settings, required to connect to an SMTP server
```

| Argument      | Description                                                                                                                  |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| dirId         | optional dir id used to save the message also to the server file system                                                      |
| fileName      | optional file name required in case the dir id has been specified; the message will be save in eml format on the file system |
| filesToAttach | list of files, expressed with an absolute path                                                                               |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Execute Query Replace Variables



**Syntax**

```javascript
utils.executeQueryReplaceVariables(String sql,String variablePrefix,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars)
```

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                        |
| variablePrefix       |                                                                                                                                                                |
| dataStoreId          | optional data source id used by the .jasper template to read data from the database                                                                            |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)        |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| pars                 | list of parameters required by the SQL query, one for each binding variable; if not needed, set to \[]                                                         |



```
utils.executeMappedQueryWithCallback(String callbackFunName,String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars)
```

| Argument             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| callbackFunName      | callback function name, invoked by this one for each row                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| where                | can be null; optional WHERE condition to include in the SQL query automatically executed (every 2 seconds) in order to check out if the data to import has been loaded. In null, it is assumed that the table is empty and the executed query would be "SELECT COUNT(\*) FROM tablename". This method terminates when the returned value is > 0. If this argument is filled in, the query would be "SELECT COUNT(\*) from tablename WHERE yourwhere". Again, the method terminates when there is at least one record |
| groupBy              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| having               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| orderBy              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| dataModelId          | it identifies the data model having "datastore" type, related to the entities to insert                                                                                                                                                                                                                                                                                                                                                                                                                              |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)                                                                                                                                                                                                                                                                                                                                                              |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                                                                                                                                                                                                                                                                                                                       |
| pars                 | list of parameters required by the SQL query, one for each binding variable; if not needed, set to \[]                                                                                                                                                                                                                                                                                                                                                                                                               |

## Get the partial result mapped with ommitted fields

```
utils.getMappedPartialResultWithFieldsToOmit(String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String\u003e attributesMap,Long totalCount,String[] fieldsToOmit,Object[] pars)
```

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dataModelId          | it identifies the data model having "datastore" type, related to the entities to insert                                                                        |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)        |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| attributesMap        |                                                                                                                                                                |
| totalCount           |                                                                                                                                                                |
| fieldsToOmit         |                                                                                                                                                                |
| pars                 | list of parameters required by the SQL query, one for each binding variable; if not needed, set to \[]                                                         |

## Get the partial result mapped with included fields

```
utils.getMappedPartialResultWithFieldsToInclude(String select,String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,String\u003e attributesMap,Long totalCount,Object[] pars)
```

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dataModelId          | it identifies the data model having "datastore" type, related to the entities to insert                                                                        |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)        |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| attributesMap        |                                                                                                                                                                |
| totalCount           |                                                                                                                                                                |
| pars                 | list of parameters required by the SQL query, one for each binding variable; if not needed, set to \[]                                                         |

## Send email with message template

```
utils.sendEmailWithMessageTemplate(String subject,String messageTemplate,Map jsObj,String from,String to,String cc,String bcc,String priority,Boolean isHtmlContent,Boolean returnReceipt,String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS,Boolean zipFiles,Long dirId,String[] filesToAttach)
```

<table data-header-hidden><thead><tr><th width="337">Argument</th><th>Description</th></tr></thead><tbody><tr><td>Argument</td><td>Description</td></tr><tr><td>subject</td><td>email subject; can contain variables to replace, expressed as :XXX</td></tr><tr><td>messageTemplate</td><td>email body; can contain variables to replace, expressed as :XXX</td></tr><tr><td>jsObj</td><td>a collection of variable names/values, expressed as a javascript object { varName1: value1, ... } used to replace the subject/body content for all :XXX occurrences</td></tr><tr><td>from</td><td>email address sender</td></tr><tr><td>to</td><td>email address destination; can contain multiple addresses, separated by a comma (,)</td></tr><tr><td>cc</td><td>optional argument: can be null; carbon copy addresses</td></tr><tr><td>bcc</td><td>optional argument: can be null; blind carbon copy addresses</td></tr><tr><td>priority</td><td>optional argument: can be null; define the email message priority</td></tr><tr><td>isHtmlContent</td><td>a boolean flag used to define if the body content is in HTML format or not</td></tr><tr><td>returnReceipt</td><td>a boolean flag used to request a return receipt to the destinations</td></tr><tr><td>smtpHost</td><td>SMPT host name to use</td></tr><tr><td>smtpPort</td><td>SMTP port</td></tr><tr><td>protocol</td><td>Protocol to use (e.g. smtp vs smtps)</td></tr><tr><td>smtpUsername</td><td>SMTP username to use to authentication to the SMTP server</td></tr><tr><td>smtpPassword</td><td>SMTP password to use to authentication to the SMTP server</td></tr><tr><td>zipFiles</td><td>a boolean flag used to compress all files to attach in a unique zip file and send it, in order to reduce the email size</td></tr><tr><td>dirId</td><td>directory identifier, where attachment files are located; can be null, in case no attachment files are required</td></tr><tr><td>filesToAttach</td><td>a list of files to attach, separated by a comma; use [] to not include files; each file is expressed as "subdir/filename" , with regards to the base path expressed through the dir id; GCS are supported as well</td></tr></tbody></table>

## Send an email, using SMTP settings passed forward and with a template text

This method allows to send an email message with optional attachments, starting from a text representing the template for the email body.

No template id is required here: the body text must be provided instead.&#x20;

This method is helpful when there is not a single template to use, but a variety of alternative templates to use, according to specific conditions, like a different text per language, company id, site id, etc.

Decoupling the template id from the template text, allows to pass forward a different text, not directly connected to a template, which not necessarely must be used here.

**Syntax**

```javascript
var ok = utils.sendEmailWithMessageTemplateWithSettings(
      String subject,
      String messageTemplate,
      Map jsObj,
      String from,
      String to,
      String cc, 
      String bcc,
      String priority,
      Boolean isHtmlContent,
      Boolean returnReceipt,
      String smtpHost,
      String smtpPort,
      String protocol,
      String smtpUsername,
      String smtpPassword,
      String useTLS,
      Boolean zipFiles,
      Map additionalSettings,
      Long dirId,
      String... filesToAttach
  )
```

**Details**

| Argument           | Description                                                                                                                                                                                                        |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| subject            | email subject; can contain variables to replace, expressed as :XXX                                                                                                                                                 |
| messageTemplate    | email body; can contain variables to replace, expressed as :XXX                                                                                                                                                    |
| jsObj              | a collection of variable names/values, expressed as a javascript object { varName1: value1, ... } used to replace the subject/body content for all :XXX occurrences                                                |
| from               | email address sender                                                                                                                                                                                               |
| to                 | email address destination; can contain multiple addresses, separated by a comma (,)                                                                                                                                |
| cc                 | optional argument: can be null; carbon copy addresses                                                                                                                                                              |
| bcc                | optional argument: can be null; blind carbon copy addresses                                                                                                                                                        |
| priority           | optional argument: can be null; define the email message priority                                                                                                                                                  |
| isHtmlContent      | a boolean flag used to define if the body content is in HTML format or not                                                                                                                                         |
| returnReceipt      | a boolean flag used to request a return receipt to the destinations                                                                                                                                                |
| smtpHost           | SMPT host name to use                                                                                                                                                                                              |
| smtpPort           | SMTP port                                                                                                                                                                                                          |
| useTLS             | flag to use (Y/N) to enable TLS                                                                                                                                                                                    |
| protocol           | Protocol to use (e.g. smtp vs smtps)                                                                                                                                                                               |
| smtpUsername       | SMTP username to use to authentication to the SMTP server                                                                                                                                                          |
| smtpPassword       | SMTP password to use to authentication to the SMTP server                                                                                                                                                          |
| zipFiles           | a boolean flag used to compress all files to attach in a unique zip file and send it, in order to reduce the email size                                                                                            |
| additionalSettings | <p>can be null; if specified, it represents a javascript object containing additional settings:</p><p>   {</p><p>      elmDirId = &#x3C;number></p><p>      elmFileName: "filename.elm"</p><p>   }</p>             |
| dirId              | directory identifier, where attachment files are located; can be null, in case no attachment files are required                                                                                                    |
| filesToAttach      | a list of files to attach, separated by a comma; use \[] to not include files; each file is expressed as "subdir/filename" , with regards to the base path expressed through the dir id; GCS are supported as well |

This method returns false if the email has NOT been sent correctly (e.g. attachment file not found).

**Example**

Suppose to send an email, whose content changes according to the language and the company id  and site id, but there can be templates not always defined for all company+site+language combinations, so that if a template is not found at company+site+language it can be found at company+language and if not found yet, at language only level.

In such a scenario, template messages can be stored on the Platform server file system as text files, organized in a series of subfolder, hierarchically:

```javascript
invoice_IT.txt
invoice_EN.txt
00000
  invoice_IT.txt
  invoice_EN.txt
  100
    invoice_IT.txt
    invoice_EN.txt
  101
    ...
00001
  ...
```

Email subject must be translated according to the language as well. This can be done either by including subject as the first line of the file or by creating a second text file for subjects only or by including a custom translation in Platform. In this example, we suppose the email subject is defined as a Platform custom translation.

```javascript
var smtpHost = "smtp.mandrillapp.com";
var smtpPort = "2525";
var protocol = "smtp";
var smtpUsername = "...;
var smtpPassword = "...";
var useTLS = "E";

var dirId = 69; // this entry represent a GCS bucket where attachments are located
var filesToAttach = [ "10I3P.jpg" ];

function getMessageTemplateFile(baseDir) {
    var files = utils.getFilesInPath(baseDir);
    for(var i=0;i<files.length;i++) {
        if (files[i]=="invoice_"+userInfo.languageId+".txt") {
            return baseDir+"/"+files[i];
        }
        if (files[i]=="invoice_EN.txt") { // second choice: use EN as a default
            return baseDir+"/"+files[i];
        }
    }
    return null;
}

// let's get template message...
// 1. first check for file in the longest path: company/site
var templateBaseDirId = 49;
var templateBaseDir = utils.getDirectoryPath(templateBaseDirId); // base dir where all template messages are located
var messageTemplateFile = getMessageTemplateFile(templateBaseDir+"/"+userInfo.companyId+"/"+userInfo.siteId);
// 2. second choice: check for file in the path: company
if (messageTemplateFile==null) 
  messageTemplateFile = getMessageTemplateFile(templateBaseDir+"/"+userInfo.companyId);
// 3. last choice: check for file in thebase path:
if (messageTemplateFile==null) 
  messageTemplateFile = getMessageTemplateFile(templateBaseDir);

if (messageTemplateFile==null)
  throw "No message template found";
else {
    // get tempkate messgae file content...
    var messageTemplate = utils.readTextFile(messageTemplateFile,"UTF-8");
    
    // send email...
    var ok = utils.sendEmailWithMessageTemplate(
        "Ciao", // utils.getResource("invoice.subject"), // subject
        messageTemplate, 
        {
            NAME: "John",
            SURNAME: "Smith"
        }, // jsObj
        "...", // from
        "...", // to
        null, //  cc
        null, // bcc
        null, // priority
        true, // isHtmlContent
        false, // returnReceipt,
        smtpHost,
        smtpPort,
        protocol,
        smtpUsername,
        smtpPassword,
        useTLS, 
        false, // zipFiles, 
        dirId, 
        filesToAttach
    );
    if (!ok)
     throw "Error while sending the email";
}
```

## Get Progressive for application Id

```
getProgressiveForApplicationId(String appId,String tableName,String columnName,Boolean separatedTransaction,Boolean interruptExecution)
```

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| appId                | application id having the process defined internally                                                                                                           |
| tableName            | String: name of table for calculating counter                                                                                                                  |
| columnName           | String: column name of field to calculating progressive                                                                                                        |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)        |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |

## Convert UCT String to time zone date

```
/utils.convertUTCStringToTimeZoneDate(String utcDateAsString,int hrs)
```

##

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailWithConversation(from, subject, message, destinations, priority, isHtmlContent, returnReceipt, conversationId, messageTag, filesToAttach)
```

**Details**

| from           | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user, whose email address must be defined in the user detail form                                                        |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| subject        | email title                                                                                                                                                                                                                                          |
| message        | message to send; it can be expressed in HTML format                                                                                                                                                                                                  |
| destinations   | list of usernames who will receive the alert; they must be separated by a comma (,); for each username specified, its email address must be defined in the user detail form                                                                          |
| priority       | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 (minor), 1, (normal), 2 (high) |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo                                                                                                    |
| messageTag     | optional hidden text to add to the message and used to search for specific messages stored in the message history                                                                                                                                    |
| filesToAttach  | list of files, expressed with an absolute path.                                                                                                                                                                                                      |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

{% code fullWidth="false" %}
```
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```
{% endcode %}

## Get web content with headers and cookies

```
utils.getWebContentWithHeadersAndCookies(String uri,boolean replaceVariables,String httpMethod,String contentType,String requestBody,String user,String pwd,String charSet,Map headers,Number timeout)
```

| Argument         | Description                                                                                                                                                                       |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| uri              | URI, expressed as http:// or https:// with or without variables, expressed as :XXX                                                                                                |
| replaceVariables | flag used to replace variables within the uri (variables are expressed as :XXX)                                                                                                   |
| httpMethod       | can be null); if specified, it defines the HTTP method: GET, POST                                                                                                                 |
| contentType      | can be null); if specified, it defines the content type request (e.g. application/json)                                                                                           |
| requestBody      | can be null); if specified, it defines the request body, expressed as a String (e.g. a JSON or XML content)                                                                       |
| user             | can be null); if specified, it defines the username for a BASIC authentication                                                                                                    |
| pwd              | can be null); if specified, it defines the password for a BASIC authentication                                                                                                    |
| charSet          | can be null); if specified, it defines the char set to use for the request body (req property "Accept-Charset"); if not specified, it is auto defined as "UTF-8"                  |
| headers          | can be null); if specified, it defines a collection of attribute-values to pass as request headers; it is expressed as a javascript object: { attr1: value2, attr2: value2, ... } |
| timeout          | optional argument: can be set to null; timeout for the request, expressed in seconds; helpful when the service to invoke could be very slow                                       |

## Execute an HTTP(s) connection and fetch the result (binary content) optionally with a body request (binary content)

result expressed as a binary content and store it into the specified file

**Syntax**

```javascript
utils.getBinaryContentWithSettings(
  toFile, 
  uri, 
  replaceVariables, 
  httpMethod, 
  contentType, 
  requestBody, 
  user, 
  pwd, 
  settings
);
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

You can pass forward a String based request body as usually (using "requestBody" argument) or pass forward a binary content, using the "**settings**" argument, where specifying a "**fromFile**" attribute, filled with an absolute path (including file name) to the file to pass forward, which must be located in the server file system.

Settings can also accept an optional attribute named "**headers**" containing a javascript object related to the set of request headers to pass forward.



**Example**

```javascript
var url = "http://host/context?par1=abc...";
url = encodeURI(url);
utils.getBinaryContentWithSettings(
  "/mylocalpath/outputfile", // toFile
  url, 
  false, // replaceVariables
  "POST", // httpMethod
  "application/octet-stream", // content type 
  null, // requestBody is null, since the input binary content is passed through "settings"
  null, // user
  null, // pwd
  { // settings
    fromFile: "/mylocalpath/inputfile",
    headers: { ... }
  }
);
```

## Enqueue action with note as string

```
utils.enqueueActionWithNoteAsString(String queueName,Long actionId,Map params,String priority,Long processWaitTime,Boolean logExecution,String note,Integer maxRetries)
```

| Argument     | Description                                                                                                                                                                                                                                   |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| queueName    | name of the queue where all elements will be inserted; optional: queue name; if not specified, the process will be enqueued in the DEFAULT queue                                                                                              |
| actionId     | to enqueued action id                                                                                                                                                                                                                         |
| params       | optional list of parameters to pass to the SQL Query (where they are referred always as ?); set to \[] in case of no parameters.                                                                                                              |
| priority     | optional; if specified, processes within the same queue will be sorted according to the priority rathe than to the enqueing time                                                                                                              |
| logExecution | true to log in the predefined table LOG60\_LOGS the execution of the process                                                                                                                                                                  |
| note         | a string value which will be saved in the NOTE field of the CON77\_QUEUES table. This field can be helpful to carry out custom logic on the enqueued elements, for instance to execute statistics about the amount of data not processed yet. |

## Save grid export in extended CSV

```
utils.saveGridExportInExtendedCSV(String appId,String companyId,Long siteId,String username,String password,String platformBaseUrl,String functionId,Long panelId,List filters,List orders,List attributes,List titles,String title,String toFile)
```

| Argument        | Description                                      |
| --------------- | ------------------------------------------------ |
| appId           |                                                  |
| companyId       | company id that identifies the user (text value) |
| siteId          | site id that identifies the user (numeric value) |
| username        | username of the current logged user              |
| platformBaseUrl | --                                               |
| functionId      | --                                               |
| panelId         | --                                               |

## Get driver name default

```
utils.getDriverNameDefaultConnection)
```

## Convert seconds to hours minutes seconds

```
utils.convertSecondToHoursMinutesSeconds(Long seconds)
```

| Argument | Description |
| -------- | ----------- |
| seconds  | seconds int |

## Get window panels navigate tree

```
utils.getWindowPanelsNavigateTree(Long windowId,String treeTranslation,String[] excludedProperties)
```

| Argument           | Description |
| ------------------ | ----------- |
| windowId           |             |
| treeTranslation    |             |
| excludedProperties |             |

## Check cells from excel file

This function check the mapped cells from excel and verify the mandatory values, the format etc

**Syntax**:

```javascript
var result = utils.checkCellsWithMetadataForImport(
    Long directoryId, 
    String fileName, 
    Long valueImportId
);
```

| Argument      | Description                                  |
| ------------- | -------------------------------------------- |
| valueImportId | id of import to duplicate                    |
| directoryId   | id of the directory where to search the file |
| fileName      | file name                                    |
| valueImportId | id of defined import                         |

## Import sub folder in web content

```
utils.importSubFolderInWebContext(String appId,String subfolderName)
```

| Argument      | Description                                          |
| ------------- | ---------------------------------------------------- |
| appId         | application id having the process defined internally |
| subfolderName |                                                      |

## Generic SQL execution (NO SQL queries) <a href="#executesql" id="executesql"></a>

**Syntax**

```javascript
var rows = utils.executeSql(sql, dataSourceId, separatedTransaction, interruptExecution, params)
```

**Details**

| Argument             | Description                                                                                                                                                                                                          |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| rows                 | int value: number of processed rows                                                                                                                                                                                  |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                              |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                           |
| separatedTransaction | boolean value; ignored: it is always separated                                                                                                                                                                       |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                       |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql statement. |

## Text to int

```
utils.textToInt(String text)
```

| Argument | Description |
| -------- | ----------- |
| text     | text to int |

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

## Save a list of email messages on the server file system

Available since 5.2 version. Uses **eml** format.

Messages to save are identified by a list of message id, so utils.getEmails() method mustbe invoked first, in order to get the identifiers needed here to fetch the messages to save.

**Syntax**

```javascript
utils.saveEml(String server,Integer port, String username, String password, String protocol,Boolean useTLS,String folderName,String[] messageIds,String[] fileNames,Long directoryId);
```

**Details**

| Argument | Description                                      |
| -------- | ------------------------------------------------ |
| server   | server host                                      |
| port     | server port                                      |
| username | username to use when accessing the email server  |
| password | password to use when accessing the email server  |
| protocol | protocol to use when connecting the email server |
| useTLS   | flag used to enabled the TLS mode                |

```
 folderName-folder identifier, where the messages are located; the folder name changes according to the mail server; an example is INBOX
 messageIds-a list of message identifiers to save, previously fetched through a getEmails() method invokation
 fileNames-file names to use when saving the messages; this list must have the same length of the message ids list, one for each id
 directoryId-directory identifier, used to identify the path on the server file system, when all messages will be saved
```

The method returns the list of messages ids not found in the specified folder and, consequently, not saved.

## Send Gmail

```
utils.sendGmail(String from,String to,String cc,String bcc,String subject,String body,Boolean isHtmlContent,Boolean returnReceipt,Boolean zipFiles,Boolean deleteFilesAfterSending,String[] filesToAttach)
```

| Argument                | Description                                                                                                             |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| from                    | (optional, can be null) a string representing the email address to use as the "from address" to send the email          |
| to                      | a string composed of one or more email addresses, separated by a comma (,)                                              |
| cc                      | carbon copy addresses - a string composed of one or more email addresses, separated by a comma (,)                      |
| bcc                     | hidden addresses - a string composed of one or more email addresses, separated by a comma (,)                           |
| subject                 | a string representing the email title                                                                                   |
| body                    | the email body content                                                                                                  |
| isHtmlContent           | a boolean flag used to define if the body content is in HTML format or not                                              |
| returnReceipt           | a boolean flag used to request a return receipt to the destinators                                                      |
| zipFiles                | a boolean flag used to compress all files to attach in a unique zip file and send it, in order to reduce the email size |
| deleteFilesAfterSending | a boolean flag used to optionally delete files to attach, after sending the email                                       |
| filesToAttach           | a list of files to attach, separated by a comma; use \[] to notinclude files; each file must include the absolute path  |

## Counter

**Syntax**

```javascript
var value = utils.getCount(String tableName, String valueColumnName, String incrementValue, String where, Boolean separatedTransaction, Boolean interruptExecution, Long dataSourceId)
```

**Details**

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| value                | Long: new value of counter                                                                                                                                     |
| tableName            | String: name of table for calculating counter                                                                                                                  |
| valueColumnName      | String: column name of field to calculating counter                                                                                                            |
| incrementValue       | String: increment value for counter                                                                                                                            |
| where                | String: where condition for query                                                                                                                              |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)        |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| dataSourceId         | additional data source to use when executing this SQL statement; if set to null, the default database connection will be used                                  |

## Remove time from date

**Syntax**

```javascript
var newDate = utils.removeTime(java.util.Date date)
```

**Details**

| Argument | Description                       |
| -------- | --------------------------------- |
| date     | java.util.Date: date without time |

## Adds or subtracts the specified amount of time to the given calendar field, based on the calendar's rules

You can use:

```javascript
utils.addDate(String field, int amount): //use a current date; 
utils.addDate(String date, String format, String field, int amount): //convert the date with the specify format 
(default: "yyyy-MM-dd'T'HH:mm:ss")
```

**Details**

| Argument | Description                                                                                                                             |
| -------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| field    | String: the calendar field                                                                                                              |
| amount   | number: the amount of date or time to be added to the field                                                                             |
| field    | a String value representing the field to work with. Supported values: "DAY", "MONTH", "YEAR", "HOUR", "MINUTE", "SECOND", "MILLISECOND" |

## Parse a simple XML document and generate a Javascript "compatible" representation

_Javascript "compatible" representation is expressed using lists and js objects, where each js object has special attributes named: "tagName", "tagValue" and "subTags"._

The document (list of tags) is expressed as a list of js objects, where each js object can have a list of subtags and attributes, expressed object's attributes. The js object always contains special entries named "tagName", "subTags" and optionally "tagValue" if there is tag value.

**Syntax**

```javascript
utils.parseXML(String xmlDocument);
```

**Details**

| Argument    | Description                 |
| ----------- | --------------------------- |
| xmlDocument | an XML document as a String |

Returns an XML representation, expressed as a list of Javascript objects, where each of them has three special attributes: "tagName", "tagValue" and "subTags". You can then navigate through this js object and extract any data.

**Example**

```markup
<?xml version="1.0"?>

<resultset statement="SELECT * FROM dual" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">

    <row>
        <field name="COD_COMPANY">0</field>
        <field name="TIPO">1</field>
        <field name="DES_DESCRIZIONE">Description 1</field>
        <field name="LOGO" xsi:nil="true" />
        <field name="ATTIVA">T</field>
        <field name="UTENTE_CREAZIONE" xsi:nil="true" />
        <field name="DATA_CREAZIONE">2021-01-15 09:15:56</field>
        <field name="UTENTE_MODIFICA" xsi:nil="true" />
        <field name="DATA_MODIFICA" xsi:nil="true" />
        <field name="VERSIONE">0</field>
    </row>
    
    <row>
        <field name="COD_COMPANY">0</field>
        <field name="TIPO">2</field>
        <field name="DES_DESCRIZIONE">Description 2</field>
        <field name="LOGO" xsi:nil="true" />
        <field name="ATTIVA">T</field>
        <field name="UTENTE_CREAZIONE" xsi:nil="true" />
        <field name="DATA_CREAZIONE">2021-01-15 13:42:35</field>
        <field name="UTENTE_MODIFICA" xsi:nil="true" />
        <field name="DATA_MODIFICA" xsi:nil="true" />
        <field name="VERSIONE">0</field>
    </row>
    
    <row>
        <field name="COD_COMPANY">0</field>
        <field name="TIPO">3</field>
        <field name="DES_DESCRIZIONE">Description 3</field>
        <field name="LOGO" xsi:nil="true" />
        <field name="ATTIVA">T</field>
        <field name="UTENTE_CREAZIONE" xsi:nil="true" />
        <field name="DATA_CREAZIONE">2021-01-15 13:42:35</field>
        <field name="UTENTE_MODIFICA" xsi:nil="true" />
        <field name="DATA_MODIFICA" xsi:nil="true" />
        <field name="VERSIONE">0</field>
    </row>

</resultset>
```

```javascript
var textFile = utils.readTextFile("/path/test.xml");
var xmlDocNodes = utils.parseXML(textFile);
var rows = xmlDocNodes[0].get('subTags');
for (var i=0; i<rows.length;i++) {
    var row = rows[i];
    var fields = row.get('subTags');
    for(var f=0; f<fields.length; f++) {
        var field = fields[f];
        var name = field.get('name');
        var tagValue = field.get('tagValue');
        utils.log('Row ' + i + ', ' + name + " = " + tagValue, 'DEBUG');
    }
}
```

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

## Read a list of remote file names

all files must be stored in the same remote folder within the FTP server; file names are filtered according to the specified filter condition.

**Syntax**

```javascript
utils.getFiles(protocol, host, port, useSSL, username, password, remoteDir, fileFilter);
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

## Read a list of messages from the email server, with filtering

**Syntax**

```javascript
utils.getEmails(server, port, username, password, protocol, useTLS, maxMessagesToRead, notReadFilter, startSendDateFilter, endSendDateFilter, startReceiveDateFilter, endReceiveDateFilter, fromAddressFilter, subjectFilter, bodyFilter, withAttachments, attachmentsPath, folderName, moveToFolderOnceRead, setAsSeen, deleteEmailWhenRead, debug);
```

**Details**

```
server - server host
port - server port (e.g. 995)
username - username to use when accessing the email server
password - password to use when accessing the email server
protocol - protocol to use when connecting to the email server (e.g. imap, imaps, pop, pops)
```

| Argument                                    | Description                                                                                                                   |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| useTLS                                      | flag used to enabled the TLS mode                                                                                             |
| maxMessagesToRead                           | maximum number of messages to read                                                                                            |
| notReadFilter                               | flag used to filter only messages not read yet                                                                                |
| startSendDateFilter - optional parameter    | if not null, messages to read will be filtered by sendingdate; only the ones next or equal to this date wil be returned       |
| endSendDateFilter - optional parameter      | if not null, messages to read will be filtered by sendingdate; only the ones previousor equal to this date wil be returned    |
| startReceiveDateFilter - optional parameter | if not null, messages to read will be filtered by receiving date; only the ones next or equal to this date wil be returned    |
| endReceiveDateFilter - optional parameter   | if not null, messages to read will be filtered by receiving date; only the ones previousor equal to this date wil be returned |
| fromAddressFilter - optional parameter      | if not null, messages to read will be filtered by the "from address" specified                                                |
| subjectFilter - optional parameter          | if not null, messages to read will be filtered and only the ones containing this value in their object will be returned       |
| bodyFilter - optional parameter             | if not null, messages to read will be filtered and only the ones containing this value in their body content will be returned |
| withAttachments - optional parameter        | if not null, messages to read will be filtered and only the ones having at least one attachment will be returned              |
| attachmentsPath                             | absolute path where saving attachments                                                                                        |
| folderName                                  | folder to read; e.g. INBOX; if not specified, it will be set to INBOX                                                         |
| moveToFolderOnceRead                        | move to the specified folder each message, once read; can be null                                                             |
| setAsSeen                                   | flag used to mark as "SEEN" a message just read                                                                               |
| deleteEmailWhenRead                         | flag used to delete the email message once read                                                                               |

```
debug - flag used to debug the communication with the server
emailMessages : return value - list of messages read from the mail box
```

Attributes contained in each message of the list:

| Attribute     | Description                                                            |
| ------------- | ---------------------------------------------------------------------- |
| id            | email identifier, used to delete an email message later                |
| messageNumber | index within the folder of the specific message                        |
| from          | from email addresses                                                   |
| message       | email body                                                             |
| subject       | email subject                                                          |
| mimeType      | e.g. "text/plain" or "text/html"                                       |
| list          | list of absolute paths (strings) where the attachments have been saved |
| sendDate      | message sending date                                                   |
| receiveDate   | message receiving date                                                 |

## Copy the source file to the destination file <a href="#copyfile" id="copyfile"></a>

Since "destFile" contains a file name too, the source file can be renamed when copied.

**Syntax**

```javascript
utils.copyFile(srcFile, destFile, replaceExistingFile, deleteSourceFile);
```

**Details**

| Argument            | Description                                                                                                                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| srcFile             | absolute path + file name                                                                                                                                                                        |
| destFile            | absolute path + file name                                                                                                                                                                        |
| replaceExistingFile | flag used to replace the already existing destination file; if set to false and the destination file already exists, the copy process would be interrupted and the returned value would be false |
| deleteSourceFile    | flag used to delete the source file, once the file has been copied to the destination path                                                                                                       |

## Camel

```
utils.camel(String fieldName,Boolean firstCharUpper)
```

| Argument       | Description                           |
| -------------- | ------------------------------------- |
| fieldName      | file name related to the specified if |
| firstCharUpper | --                                    |

Convert a database field or an upper-case parameter containing underscores (\_) to the camel case format, i.e. lowercase and the underscore remove and next character to uppercase.

Example:

var x = utils.camel("ABC\_DEF",false); -> x = "abcDef"

var x = utils.camel("ABC\_DEF",true); -> x = "AbcDef"

## Uncamel

```
utils.uncamel(String attributeName)
```

| Argument      | Description |
| ------------- | ----------- |
| attributeName |             |

It converts an attribute name to a field name, according to Java convention.

Example:

var x = utils.uncamel("abcD1",true); -> x = "ABC\__D1_"

## Force the site id in a server-side js action

This method set the site id in a server-side js action, independently of the fact the site id has been already set or not.

```javascript
utils.setSiteId(Long siteId);
```

**Details**

| Argument | Description                                                           |
| -------- | --------------------------------------------------------------------- |
| siteId   | attribute name to set in the "vo" Platform is working on to save data |

## Check for user existence

This method allows to check for a record in PRM01\_USERS, i.e. whether the specified user has been already created.

**Syntax**:

```javascript
utils.existUser(companyId, siteId, userCodeId);
```

| Argument    | Description                                                                                                                                                   |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| companyId   | company id that identifies the user (text value)                                                                                                              |
| siteId      | site id that identifies the user (numeric value)                                                                                                              |
| userCodeId  | username for the user to check out (text value)                                                                                                               |
| prm01Object | the resulting value is a javascript object containing the record in PRM01\_USERS for the specified user. This method returns null if the user does not exist. |

## Create a role

This method allows to create a role to the current application

**Syntax**:

```javascript
utils.createRole(String companyId, Long siteId,String roleId,String description);
```

| Argument    | Description                                                                      |
| ----------- | -------------------------------------------------------------------------------- |
| companyId   | company id that identifies the user (text value)                                 |
| siteId      | site id that identifies the user (numeric value)                                 |
| roleId      | ROLE\_ID to create                                                               |
| description | role description                                                                 |
| objectPrm02 | the resulting value is the current record in PRM02\_ROLES for the specified role |

**Creating a role for another application**

There is another method you can use to create a role for another application. In such a case, the application id for the other application must be specified.

## Create a user

This method creates a record in PRM01_USERS_, one in SUB02\_SUBJECTS and another in SUB01\_PEOPLE, i.e. create a new user account.

**Syntax**:

```javascript
utils.createUser(companyId, siteId, userCodeId, description, password, languageId, additionalData
, roles);
```

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| companyId      | company id that identifies the user (text value)                                                                                                                                                                                                                                                                                                                                                                                                      |
| siteId         | site id that identifies the user (numeric value)                                                                                                                                                                                                                                                                                                                                                                                                      |
| userCodeId     | username for the user to check out (text value)                                                                                                                                                                                                                                                                                                                                                                                                       |
| description    | user description (mandatory argument)                                                                                                                                                                                                                                                                                                                                                                                                                 |
| password       | password (mandatory argument)                                                                                                                                                                                                                                                                                                                                                                                                                         |
| languageId     | language id to link to the user                                                                                                                                                                                                                                                                                                                                                                                                                       |
| additionalData | <p>can be null: if specified, it is a javascript object containing additional data to fill in PRM01_USERS; </p><p>e.g. </p><p><strong>{ dateExpirationPassword:</strong> utils.convertDateToString(utils.getCurrentDate(), 'yyyy-MM-dd') <strong>}</strong></p><p></p><p>Note: if you need to set personal data about the user (stored in SUB02_SUBJECTS table<strong>)</strong>, you can use later the <strong>updatePeopleData</strong> method.</p> |
| roles          | a list of javascript objects; each object is related to a role to bind to the user; the javascript object for a role must have the following attributes: companyId, siteId, roleId, startDate, endDate (this one is optional)                                                                                                                                                                                                                         |
| prm01Object    | the resulting value is a javascript object containing the record in PRM01\_USERS for the specified user.                                                                                                                                                                                                                                                                                                                                              |

```
var prm01 = utils.createUser(
  userInfo.companyId, 
  vo.siteId, 
  vo.username, 
  vo.description, 
  vo.password, 
  vo.language, 
  {
        siteIdSub02: vo.siteId,
        dateExpirationPassword: utils.convertDateToString(utils.getCurrentDate(), 'yyyy-MM-dd')
  }, 
  []
  );
```

## Update an already existing user

This method updates an already existing record in PRM01\_USERS, i.e. update a user account.

**Syntax**:

```javascript
utils.updateUser(companyId, siteId, userCodeId, languageId, additionalData);
```

| Argument          | Description                                                                                                                                          |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| companyId         | company id that identifies the user (text value)                                                                                                     |
| siteId            | site id that identifies the user (numeric value)                                                                                                     |
| userCodeId        | username for the user to check out (text value)                                                                                                      |
| decriptedPassword | plain password (mandatory argument); note: "password" field is automatically reckoned by Platform, starting from the plain password                  |
| languageId        | language id to link to the user                                                                                                                      |
| additionalData    | can be null: if specified, it is a javascript object containing additional data to fill in PRM01\_USERS; e.g. { dateExpirationPassword: new Date() } |
| prm01Object       | the resulting value is a javascript object containing the record in PRM01\_USERS for the specified user.                                             |

## Rename Files

```
utils.renameFile(Long directoryId,String oldFileName,String newFileName)
```

| Argument    | Description          |
| ----------- | -------------------- |
| directoryId | directory identifier |
| oldFileName | old file name        |
| newFileName | new file name        |

## Convert a javascript object to a JSON string to work with in an action

In case you need to convert a javascript object to a JSON string within a server-side javascript action, you can use the following  method:

```javascript
utils.stringify(Object obj);
```

**Details**

| Argument | Description                  |
| -------- | ---------------------------- |
| obj      | javascript object to convert |

Such a method is helpful in case of a complex object containing java-type objects rather than javascript-type data.

As an alternative, you can use the standard javascript utility function:

## Parse JSON

```
utils.parseJSON(String json)
```

| Argument | Description |
| -------- | ----------- |
| json     |             |

## Convert a text to an hash key (md5)

MD5 is an hash function you can use to convert a text to a text-based key; multiple invocations to the function with the same input always provide the same result, but the hash function does not provide a unique value: different texts could return the same hash key. This is helpful to check out on the database table the existence of a specific record, starting from its md5 representation.

```javascript
utils.md5(String text);
```

&#x20;**Details**

| Argument | Description                                      |
| -------- | ------------------------------------------------ |
| text     | text to convert to an hash key                   |
| md5Text  | the MD5 hash key corresponding to the input text |

## Log in con 60

```
utils.logInCon60(String logType,String msg,String messageTag)
```

| Argument   | Description                                                                                                        |
| ---------- | ------------------------------------------------------------------------------------------------------------------ |
| logType    |                                                                                                                    |
| msg        | string value: message to log                                                                                       |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history. |

## Lpad

```
utils.lPad(String value,char fillChar,int length)
```

| Argument | Description |
| -------- | ----------- |
| value    |             |
| fillChar |             |
| lenght   |             |

## SaveBlob

```
utils.saveBlob(Map settings)
```

| Argument | Description                                                                     |
| -------- | ------------------------------------------------------------------------------- |
| settings | can be null; if set, it is a javascript object containing additional settings.  |

## File exist

```
utils.fileExists(String filePath)
```

| Argument | Description                                                                                                      |
| -------- | ---------------------------------------------------------------------------------------------------------------- |
| filePath | list of files stored in the server side file system (expressed with absolute path) to copy within the FTP server |



## Protecting **a** PDF file <a href="#getcsvcontent" id="getcsvcontent"></a>

**From 6.0.2 version**

Starting from an already existing PDF file, this method defines the protection policy to add to a document for password-based protection: it protects a PDF document with password for the document owner and in read-only for the generic user\


**Syntax**

```javascript
utils.protectPdf(
  String passwordRestriction,
  String passwordOwner,
  String fullPathSrc,
  String fullPathDst
);
```

**Details**

| Argument            | Description                                                                |
| ------------------- | -------------------------------------------------------------------------- |
| passwordRestriction | password for the read-only user                                            |
| passwordOwner       | password for the document owner                                            |
| fullPathSrc         | absolute path + PDF file name for the already existing PDF file to protect |
| fullPathDest        | absolute path + PDF file name for the PDF file protected                   |

## Get catalog

```
utils.getCatalog(Long datasourceId)
```

| Argument     | Description                                                                                |
| ------------ | ------------------------------------------------------------------------------------------ |
| dataSourceId | num value; it can be null and used to specify a different db to use with the sql statement |

## Start threaded action

```
utils.startThreadedAction(Long actionId,Long waitTime,Map args)
```

| Argument | Description                                                                                           |
| -------- | ----------------------------------------------------------------------------------------------------- |
| actionId | erver-side javascript action identifier to execute                                                    |
| waitTime |                                                                                                       |
| args     | a collection of pairs \<attributeName,attributeValue> to use to bind queries connected to that report |

## Set the return message <a href="#setreturnvalue" id="setreturnvalue"></a>

this method can be omitted; in that case a default json message with success: true will be sent back

**Syntax**

```javascript
utils.setReturnValue(response)
```

**Details**

response - string value: messagge to send back

## Get data store id

```
utils.getDataStoreId(Long dataStoreId)
```

| Argument    | Description                                                                          |
| ----------- | ------------------------------------------------------------------------------------ |
| dataStoreId | optional data source id used by the .jasper template to read data from the database  |

## Generic SQL execution (NO SQL queries) without logging it

**Syntax**

```javascript
var rows = utils.executeSqlNoLog(
sql,
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
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                              |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                           |
| separatedTransaction | boolean value; ignored: it is always separated                                                                                                                                                                       |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                       |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql statement. |

Note: the SQL operation will not be logged. This method csan be useful with bulk operations, whose execution could slow down if a log message were produced for each execution.

## SQL query execution <a href="#executequery" id="executequery"></a>

**Syntax**

```javascript
var jsonString = utils.executeQuery(
  sql,
  dataSourceId,
  separatedTransaction,
  interruptExecution,
  params
)
```

**Details**

| Argument             | Description                                                                                                                                                                                                      |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| jsonList             | string value: list of json objects, i.e. the result of the query execution                                                                                                                                       |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                          |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                       |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)                                                          |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                   |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql query. |

An :XXX variable can be replaced by vo or params values

**Example**

```javascript
var jsonString = utils.executeQuery(
  "SELECT USER_CODE_ID,DESCRIPTION FROM PRM01_USERS WHERE COMPANY_ID=:COMPANY_ID AND STATUS=? AND LOCKED=?",
  null, // no additional datastore!
  false, // do it on a separated transaction
  true, // fire an Execution in case of error
  "E",
  "N"
);
var rows = JSON.parse(jsonString);
for(var i=0;i<rows.length;i++) {  
  var username = rows[i].userCodeId;
  ...
}
```

## SQL query execution with very long result sets <a href="#executequery" id="executequery"></a>

**From 5.4.0 version**

In case of a SQL query returning a very long result set, it is NOT recommended to use the previous method, since it gives back the whole result set at once, which is dangerous because it can consume a large amount of memory on the server.

A better solution is represented by the following method, where the result set is read row by row: for each row, a callback function is invoked, in order to process it.

Consequently, this method cannot be coupled to the user interface, since it would mean that all data would be read in the end. This approach is good when the row processing does not involve the UI, but some other operation on the server side, like writing a text file, starting from the result set.

**Syntax**

```javascript
utils.executeQueryWithCallback(
  callbackFunName,
  sql,
  dataStoreId,
  separatedTransaction,
  interruptExecution,
  params
)
```

**Details**

| Argument             | Description                                                                                                                                                                                                                             |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| callbackFunName      | string value: the name of a callback function, defined inside the action, which will be automatically invoked for each record read from the SQL query. This method must have an argument, which is a js object, representing the record |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                                                 |
| dataSourceId         | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                                              |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)                                                                                 |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                                          |
| params               | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql query.                        |

An :XXX variable can be replaced by vo or params values

**Example**

```javascript
var processRow = function(record) {
  utils.log(record.userCodeId+" "+record.description,"INFO");
}

utils.executeQueryWithCallback(
"processRow",
"SELECT USER_CODE_ID,DESCRIPTION FROM PRM01_USERS WHERE COMPANY_ID=:COMPANY_ID AND STATUS=? AND LOCKED=?",
null, // no additional datastore!
false, // do it on a separated transaction
true, // fire an Execution in case of error
"E",
"N"
);
```

A more complex example is the one reported as follows, where the SQL query result set is coupled with the export of records to a CSV file on the server file system. The CSV file is built by writing row by row, using an optimized approach based on 3 steps: opening the output stream, writing multiple lines, closing the output stream:

**Example of an optimized approach for reading data from a SQL query + writing data on a CSV file**

```javascript
// open the CSV file, in order to write into it
var fileId = utils.openCSVFile(
    "ab.csv",
    true,
    9, // data source id
    ",",
    true,
    ["userCodeId","password","rowVersion","dateExpirationPassword"], // attributes coming from a row, to manage and export
    [null,null,null,null] // optional data converters (es. from number to text: "0.00")
);

// declare a callback function, invoked by a SQL query, used to write a single line into the CSV file
var processRow = function(jsonRow) {
    utils.writeToCSVFile(fileId,jsonRow);
}

// execute the SQL query, whose result set will be read row by row, by invoking each time the specified callback
utils.executeQueryWithCallback(
    "processRow", // callback function, invoked for each record coming from the query, whose argument will receive a JSON object representing the record
    "SELECT U.USER_CODE_ID,U.DESCRIPTION,U.PASSWORD,U.DATE_EXPIRATION_PASSWORD,U.ROW_VERSION FROM PRM01_USERS U",
    null,
    false,
    true,
    []
);

// close the CSV file, after reading all records from the query
utils.closeCSVFile(fileId);
```

## Execute quesry with alias

```
utils.executeQueryWithAlias(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Long dataModelId,Object[] pars)
```

**Details**

|                      |                                                                                                                                                                                                                  |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sql                  | string value: sql to execute; it can contains ? or :XXX                                                                                                                                                          |
| dataStoreId          | num value; it can be null and used to specify a different db to use with the sql statement                                                                                                                       |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)                                                          |
| interruptExecution   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue                                                   |
| dataModelId          | it identifies the data model having "datastore" type, related to the entities to insert                                                                                                                          |
| pars                 | this is optional: you can omit it at all, or you can specify a series of arguments separated by a comma (do not use \[]); these additional parameters represent values which replace ? symbols in the sql query. |

## How to get the field names and types for every fields in the select clause of a SQL query to execute

This can be helpful when creating programmatically a grid and there is the need to know how to format data.

**Syntax**

```javascript
var jsonList = utils.getQueryColumns(sql, dataStoreId, separatedTransaction, interruptExecution, pars);
```

**Details**

| Argument             | Description                                                                                                                                                                                                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sql                  | SQL query to execute, in order to fetch information about each field in the select clause                                                                                                                                                         |
| dataStoreId          | optional parameter (can be null); it defines the additional datastore to use when executing the query                                                                                                                                             |
| separatedTransaction | boolean flag used to define if the SQL query must be execute on a separated transation or not                                                                                                                                                     |
| interruptExecution   | boolean flag used to define if the executing of the current server-side javascript program must be interrupted in case of an errore during the execution of the SQL query                                                                         |
| pars                 | list of parameters required by the SQL query, one for each binding variable; if not needed, set to \[]                                                                                                                                            |
| jsonList             | the list of select fields is expressed as a JSON string, having the following format: \[ { "fieldName": "FIELDXX", "fieldType": 1\|2\|... }, { … } , …] where the fieldType reports the field type according to the JDBC Java.sql.Types notation. |

## Set decode field

```
utils.setDecodeField(String attributeName,String fieldName)
```

| Argument      | Description                                                                         |
| ------------- | ----------------------------------------------------------------------------------- |
| attributeName | attribute name to read: each matching found will generate a row in the results list |
| fieldName     |                                                                                     |

## Set decode uppercase

```
utils.setDecodeUpperCase(String attributeName,Boolean uppercase)
```

| Argument      | Description                                                                         |
| ------------- | ----------------------------------------------------------------------------------- |
| attributeName | attribute name to read: each matching found will generate a row in the results list |
| upperCase     |                                                                                     |

## Execute the specified SQL query and enrich it by adding filtering/sorting and pagination settings <a href="#getpartialresult" id="getpartialresult"></a>

These settings can be defined through ListCommand object automatically created when this method is invoked through a "Server JS business component" connected to a grid panel.

**Syntax**

```
utils.getPartialResult(sql, dataStoreId, separatedTransaction, interruptExecution, pars);
```

**Details**

| Argument             | Description                                                                                                  |
| -------------------- | ------------------------------------------------------------------------------------------------------------ |
| Details              |                                                                                                              |
| sql                  | base SQL query                                                                                               |
| dataStoreId          | optional data source id (a number)                                                                           |
| separatedTransaction | flag used to define if this query has to be perfomed in a separated transaction                              |
| interruptExecution   | flag used to defined if the whole server side transation must be interruped and roolbacked in case of errors |
| pars                 | optional (can be expressed as \[] in js) list of parameters binded to ? variables in the SQL query           |

```
 Returns a list of records, expressed in JSON format, which also includes "valueObjectList", "moreRows" and "resultSetLength" attributes.
```

In case of a complex SQL query including aliases, it could be needed to decode the field (to filter/sort) from the grid panel into an alias. You can do it through a specific utility method:setDecodeField(fieldToDecode, decodedField).

In this way, you can control exactly which fields to apply in case of filtering or sorting conditions.

**Example**

```javascript
utils.setDecodeField("ROW_VERSION*ROW_VERSION AS RV","RV");
var json = utils.getPartialResult(
    "SELECT USER_CODE_ID,DESCRIPTION,ROW_VERSION*ROW_VERSION AS RV "+
    "FROM PRM01_USERS "+
    "WHERE STATUS='E'",
    null,
    false,
    true,
    []
);

utils.setReturnValue(json);
```

## Get partial result no count

**Syntax**

```
utils.getPartialResultNoCount(String sql,Long dataStoreId,Boolean separatedTransaction,Boolean interruptExecution,Long totalCount,Object[] pars)
```

**Details**

| Argument             | Description                                                                                                  |
| -------------------- | ------------------------------------------------------------------------------------------------------------ |
| sql                  | base SQL query                                                                                               |
| dataStoreId          | optional data source id (a number)                                                                           |
| separatedTransaction | flag used to define if this query has to be perfomed in a separated transaction                              |
| interruptExecution   | flag used to defined if the whole server side transation must be interruped and roolbacked in case of errors |
| totalCount           |                                                                                                              |
| pars                 | optional (can be expressed as \[] in js) list of parameters binded to ? variables in the SQL query           |

## Stored SQL function execution <a href="#executestoredfunction" id="executestoredfunction"></a>

**Syntax**

```javascript
var json = utils.executeStoredFunction( sql, dataSourceId, separatedTransaction, interruptExecution, params)
```

**Details**

| Argument     | Description                                                                                                                          |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| json         | string value: the result of the function execution                                                                                   |
| sql          | string value: stored function to execute, including its parameters between parenthesis (see example below); it can contains ? or XXX |
| dataSourceId | num value; it can be null and used to specify a different db to                                                                      |

```
 use with the sql statement
```

| Argument             | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| separatedTransaction | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)        |
| interruptedExecution | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |
| params               | array value: can be \[]; it represents values which replace ? symbols in sql                                                                                   |

**Example**&#x20;

```javascript
var returnedValue = utils.executeStoredFunction("usercheck1(?, ?)",....
```

## Get translation for a specific language, given an entry

**Syntax**

```javascript
var translation = utils.getResourceByLanguageId(entry, languageId)
```

**Details**

| Argument    | Description                                                     |
| ----------- | --------------------------------------------------------------- |
| translation | string value: the translation for the entry value               |
| entry       | string value: the entry to translate                            |
| languageId  | string value: the language id to use when translating the entry |

## Get custom resource

```
utils.getCustomResource(String entry)
```

| Argument | Description |
| -------- | ----------- |
| entry    |             |

## Convert a number to its text representation <a href="#numbertotext" id="numbertotext"></a>

**Syntax**

```javascript
var text = utils.numberToText(num, decimals, languageId, showDecimals, sep)
```

**Details**

| Argument     | Description                                                                         |
| ------------ | ----------------------------------------------------------------------------------- |
| text         | string value: the text representation of the number (e.g. duecento ventiquattro/00) |
| num          | a number, including a decimal number                                                |
| decimals     | a number, it is used to round the num to this number of decimals                    |
| languageId   | language identifier                                                                 |
| showDecimals | true/false; define if the decimal part must be included                             |
| sep          | integer vs decimal separator, e.g. /                                                |

## etting the company id in a server-side js action if not null

In case the company id has not been set yet, this method allows to set it.

```javascript
utils.setCompanyId(String companyId);
```

**Details**

| Argument  | Description                                                           |
| --------- | --------------------------------------------------------------------- |
| companyId | attribute name to set in the "vo" Platform is working on to save data |

## Get a parameter value <a href="#getparameter" id="getparameter"></a>

**Syntax**

var paramValue = utils.getParameter(paramName)

**Details**

ArgumentDescriptionparamNamea string value representing a parameter named defined at installation level (CON44 table) or at application level (CON07 table)

paramValue the value defined for the specified parameter name or null if not found; if the parameter is found as an application parameter, that value is returned, otherwise it will be returned the value defined at installation level

## Get directory path

Syntax:

**var path = utils.getDirectoryPath(directoryId)**

## Convert the date String to a javascript Date

helpful in case you want to use convert a date expressed as a String into a javascript Date (do not pass forward the javascript Date directly to a SQL instruction: convert it to a Java Date before, using the methods below).

**Syntax**

```javascript
util.convertStringToDate(String dateAsString,String format)
```

**Detail**

| Argument     | Description                               |
| ------------ | ----------------------------------------- |
| dateAsString | string to convert (e.g. "2022-12-31")     |
| format       | format for the string (e.g. "yyyy-MM-dd") |

## onvert the date to String with the specify format <a href="#convertdatetostring" id="convertdatetostring"></a>

(default: "yyyy-MM-dd'T'HH:mm:ss")

**Syntax**

```javascript
stringDate = utils.convertDateToString(java.util.Date date, String format)
```

**Detail**

| Argument | Description                               |
| -------- | ----------------------------------------- |
| date     | java.util.Date: date to convert in string |
| format   | String: date format for string            |

| Argument     | Description                               |
| ------------ | ----------------------------------------- |
| dateAsString | string to convert (e.g. "2022-12-31")     |
| format       | format for the string (e.g. "yyyy-MM-dd") |

## Convert the date js object to a java.sql.Date (for a DATE typefield)

helpful in case you want to use it with a **utils.executeSql** or **utils.executeQuery** methods and pass it as a parameter

**Syntax**

```javascript
var javasqlDateValue = utils.convertDateToSqlDate(java.util.Date date)
```

**Detail**

| Argument | Description                               |
| -------- | ----------------------------------------- |
| date     | java.util.Date: date to convert in string |

## Convert the date js object to a java.sql.Date (for a DATETIME/TIMESTAMP typefield)

helpful in case you want to use it with a **utils.executeSql** or **utils.executeQuery** methods and pass it as a parameter

**Syntax**

```javascript
var javasqlTimestampValue= utils.convertDateToTimestamp(java.util.Date date)
```

**Detail**

| Argument | Description                               |
| -------- | ----------------------------------------- |
| date     | java.util.Date: date to convert in string |

## Send a chat message to a user

**Syntax**

```javascript
utils.sendChatMessage(from, message, destinations, priority, conversationId, messageTag)
```

**Details**

| Argument       | Description                                                                                                                                                                                                                                          |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| from           | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user                                                                                                                     |
| message        | message to send                                                                                                                                                                                                                                      |
| destinations   | list of usernames who will receive the alert; they must be separated by a comma (,)                                                                                                                                                                  |
| priority       | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 (minor), 1, (normal), 2 (high) |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo                                                                                                    |
| messageTag     | optional hidden text to add to the message and used to search for specific messages stored in the message history.                                                                                                                                   |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" or "SHOW\_CHAT\_POPUP\_MESSAGE" to "Y", otherwise these messages cannot be showed on the client side.

### &#x20;Send an alert message to a user <a href="#send-an-alert-message-to-a-user" id="send-an-alert-message-to-a-user"></a>

**Syntax**utils.sendAlertMessage(from, message, destinations, priority, conversationId, messageTag)**Details**

| Argument       | Description                                                                                                                                                                                                                                          |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| from           | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user                                                                                                                     |
| message        | message to send                                                                                                                                                                                                                                      |
| destinations   | list of usernames who will receive the alert; they must be separated by a comma (,)                                                                                                                                                                  |
| priority       | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 (minor), 1, (normal), 2 (high) |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo                                                                                                    |
| messageTag     | optional hidden text to add to the message and used to search for specific messages stored in the message history.                                                                                                                                   |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

## Send a not visible notification to the client

(available form 5.3.2) Send a notification to the client side; this is not a visual notification: it can be used to automate the invocation of a javascript method defined on the client. This automation can be helpful for example to open a window or reload a grid or form, when a server-side long operation has terminated.

You have to specify the function name and the argument to pass foward.

A limit it has is that you can only invoke functions having one only argument.

**Syntax**

```javascript
utils.sendJavascriptMessage(String from, Map obj, String destinations, String functionName)
```

**Details**

| Argument     | Description                                                                                                                     |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| from         | username to use to send the message; can be null, if not specified, it will be automatically filled with the current loggeduser |
| obj          | javascript object to pass forward to the javascript function to invoke on the client side                                       |
| destinations | list of usernames who will receive the alert; they must be separated by a comma (,)                                             |
| functionName | callback js function, which must be defined on the client side, invoked automatically from the notification                     |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" or "SHOW\_CHAT\_POPUP\_MESSAGE" to "Y", otherwise these messages cannot be showed on the client side.

In case you need to invoke something from complex, you have to declare a one argument function in some global .js file (stored in the "scripts" folder of your application web context) and use it to do it.

Example of a global scoped js function with one argument, used to show a popup warning window:

```javascript
function openDialogWindow(args) {
  showMessageDialog(
    args.title,
    args.message,
    function() {},
    true,
    true
  );
}
```

The server-side js action generating the notification would be:

```javascript
utils.sendJavascriptMessage(
  "ADMIN", // from username
  { 
    title: "Warning",
    message: "Task completed"  
  }, // argument to pass forward to the client side js function
  userInfo.username, // not necessarely it would be filled out in this way
  "openDialogWindow"
);
```

## Execute a command on the shell <a href="#executeshellcommand" id="executeshellcommand"></a>

Optionally, a list of arguments can be passed to the command.

It returns the exit code produced by the command execution

**Syntax**

```javascript
var exitCode = utils.executeShellCommand(command, arg1, arg2, ...)
```

**Details**

| Argument  | Description                                                                                                                |
| --------- | -------------------------------------------------------------------------------------------------------------------------- |
| command   | command to execute; it must include the absolute path to the command and must end with a .sh or .bat with no spaces within |
| arguments | zero or more String type arguments; \[] otherwise                                                                          |

## Execute an HTTP(s) connection and fetch the result

Available since 6.0.2 version.

Result expressed as a String (e.g. a JSON or XML result content)

**Syntax**

```javascript
var json = utils.getWebContent(uri, settings);
```

**Argument detail**

uri: URI, expressed as http:// or https:// with or without variables, expressed as :XXX

**Settings detail**

| Argument                                      | Description                                                                                                                                                                       |
| --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| httpMethod                                    | if specified, it defines the HTTP method: GET, POST, PATCH, PUT, DELETE                                                                                                           |
| replaceVariables (optional) (default is true) | flag used to replace variables within the uri (variables are expressed as :XXX)                                                                                                   |
| contentType (optional)                        | can be null); if specified, it defines the content type request (e.g. application/json)                                                                                           |
| requestBody (optional)                        | can be null); if specified, it defines the request body, expressed as a String (e.g. a JSON or XML content)                                                                       |
| user (optional)                               | can be null); if specified, it defines the username for a BASIC authentication                                                                                                    |
| pwd (optional)                                | can be null); if specified, it defines the password for a BASIC authentication                                                                                                    |
| charSet (optional)                            | can be null); if specified, it defines the char set to use for the request body (req property "Accept-Charset"); if not specified, it is autodefined as "UTF-8"                   |
| headers(optional)                             | can be null); if specified, it defines a collection of attribute-values to pass as request headers; it is expressed as a javascript object: { attr1: value2, attr2: value2, ... } |
| timeout (optional) (recommended)              | optional argument: can be set to null; timeout for the request, expressed in seconds; helpful when the service to invoke could be very slow                                       |
| additionalSettings (optional)                 | optional argument: can be set to null; it is a javascript object containing additional settings                                                                                   |
| requestBody (optional)                        | if specified, it defines the request body, expressed as a String (e.g. a JSON or XML content)                                                                                     |
| dirId (optional)                              | directory id of file to send                                                                                                                                                      |
| sendFileName (optional)                       | file name to send                                                                                                                                                                 |
| cookie (optional) (default is false)          | true if you want use the cookie                                                                                                                                                   |
| log (optional) (default is true)              | false if you don't want write the logs                                                                                                                                            |

**Example**

<pre><code><strong>var url = "http://host/context?par1=abc de&#x26;par2=ab\ncd";
</strong>url = encodeURI(url);
var settings = {
	"replaceVariables": true,
	"httpMethod": 'POST',
	"contentType": null,
	"requestBody": null,
	"user": "ADMIN",
	"pwd": "ADMIN",
	"cookie": true,
	"headers": {
	    "number": 1,
	    "text": "ciao"
	},
	"additionalSettings": {	    
	},
	"log": false,
	"timeout": 10
};
utils.getWebContent(url, settings);
</code></pre>

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

## Search for the specified path within the XML document parse result

_(i.e. after invoking parseXML method)_

**Syntax**

```javascript
var jsObjectsList = utils.findTagsByPath(xmlDocNodes, path);
```

**Details**

| Argument    | Description                                 |
| ----------- | ------------------------------------------- |
| xmlDocNodes | XML document parsed through parseXML method |
| path        | a tags path, expressed as tag1/tag2/tag3... |

```
 Return all occurrences matching the specified path.
```

**Example**

JohnDoe...

JaneRoe...

```javascript
var xml = utils.getWebContent("[http://...",false,"GET](http://...",false,"GET)", null,null,null,null);
var xmlDocNodes = utils.parseXML(xml); // list of companies
var staffList = utils.findTagsByPath(xmlDocNodes, "company/staff");
```







