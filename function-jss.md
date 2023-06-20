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

| Argument                                      | Description                                                                                                                                                    |
| --------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre><code>sql
</code></pre>                  | string value: sql to execute; it can contains ? or :XXX                                                                                                        |
| <pre><code>variablePrefix
</code></pre>       |                                                                                                                                                                |
| <pre><code>dataStoreId
</code></pre>          | optional data source id used by the .jasper template to read data from the database                                                                            |
| <pre><code>separatedTransaction
</code></pre> | boolean value; if true, the SQL instruction is executed on a separated transaction which is immediately committed (as for a REQUIRE\_NEW EJB directive)        |
| <pre><code>interruptExecution
</code></pre>   | boolean value; if true, an erroneous SQL instruction fires an exception that will interrupt the javascript execution; if false, the js execution will continue |



```
utils.executeMappedQueryWithCallback(String callbackFunName,String where,String groupBy,String having,String orderBy,Long dataModelId,Boolean separatedTransaction,Boolean interruptExecution,Object[] pars)
```
