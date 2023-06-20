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
utils.convertUTCStringToTimeZoneDate(String utcDateAsString,int hrs)
```
