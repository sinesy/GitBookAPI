# Email

## Send an email, using SMTP settings defined at application level/globally

**Syntax**

```javascript
utils.sendEmail(from, to, cc, bcc, subject, body, isHtmlContent, returnReceipt, zipFiles, deleteFilesAfterSending, dirId, fileName, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | \(optional, can be null\) a string representing the email address to use as the "from address" to send the email |
| to | a string composed of one or more email addresses, separated by a comma \(,\) |
| cc | carbon copy addresses - a string composed of one or more email addresses, separated by a comma \(,\) |
| bcc | hidden addresses - a string composed of one or more email addresses, separated by a comma \(,\) |
| subject | a string representing the email title |
| body | the email body content |
| isHtmlContent | a boolean flag used to define if the body content is in HTML format or not |
| returnReceipt | a boolean flag used to request a return receipt to the destinators |
| zipFiles | a boolean flag used to compress all files to attach in a unique zip file and send it, in order to reduce the email size |
| deleteFilesAfterSending | a boolean flag used to optionally delete files to attach, after sending the email |
| dirId | optional dir id used to save the message also to the server file system |
| fileName | optional file name required in case the dir id has been specified; the message will be save in eml format on the file system |
| filesToAttach | a list of files to attach, separated by a comma; use \[\] to notinclude files; each file must include the absolute path |

This method will fire an exception if the email has NOT been sent correctly \(e.g. attachment file not found\).

IMPORTANT NOTE:

In order to use this feature, you have also to define a few parameters:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Send an email, using SMTP settings defined at application level/globally

**Syntax**

```javascript
utils.sendEmail(smtpHost, smtpPort, useTLS, protocol, smtpUsername, smtpPassword, from, to, subject, body, isHtmlContent, zipFiles, deleteFilesAfterSending, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| smtpHost | SMPT host name to use |
| smtpPort | SMTP port |
| useTLS | flag to use \(Y/N\) to enable TLS |
| protocol | Protocol to use \(e.g. smtp vs smtps\) |
| smtpUsername | SMTP username to use to authetication to the SMTP server |
| smtpPassword | SMTP password to use to authetication to the SMTP server |
| from | \(optional, can be null\) a string representing the email address to use as the "from address" to send the email |
| to | a string composed of one or more email addresses, separated by a comma \(,\) |
| cc | carbon copy addresses - a string composed of one or more email addresses, separated by a comma \(,\) |
| bcc | hidden addresses - a string composed of one or more email addresses, separated by a comma \(,\) |
| subject | a string representing the email title |
| body | the email body content |
| isHtmlContent | a boolean flag used to define if the body content is in HTML format or not |
| returnReceipt | a boolean flag used to request a return receipt to the destinators |
| zipFiles | a boolean flag used to compress all files to attach in a unique zip file and send it, in order to reduce the email size |
| deleteFilesAfterSending | a boolean flag used to optionally delete files to attach, after sending the email |
| filesToAttach | a list of files to attach, separated by a comma; use \[\] to notinclude files; each file must include the absolute path |

This method will fire an exception if the email has NOT been sent correctly \(e.g. attachment file not found\).

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailWithConversation(from, subject, message, destinations, priority, isHtmlContent, returnReceipt, conversationId, messageTag, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user, whose email address must be defined in the user detail form |
| subject | email title |
| message | message to send; it can be expressed in HTML format |
| destinations | list of usernames who will receive the alert; they must be separated by a comma \(,\); for each username specified, its email address must be defined in the user detail form |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\) |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history |
| filesToAttach | list of files, expressed with an absolute path. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailWithEmailAddressesWithConversation(from, subject, message, destinations, priority, isHtmlContent, returnReceipt, conversationId, messageTag, dirId, fileName, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | email address to use to send the message; can be null, if not specified, it will be automatically filled with the email address of the current logged user \(defined in the user detail form\) |
| subject | email title |
| message | message to send; it can be expressed in HTML format |
| destinations | list of email addresses who will receive the alert; they must be separated by a comma \(,\) |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\) |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history |
| filesToAttach | list of files, expressed with an absolute path. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailFromTemplate(String from,Number templateId,String destinations, String carbonCopy, String blindCarbonCopy, String priority,boolean isHtmlContent,Map jsObj,Long dirId,String fileName, String... filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user, whose email address must be defined in the user detail form; it can be overridden by the template "from" field |
| templateId | id of the template previously defined, used to set subject and body; optionally, the template can be optionally used to set from, to, cc, receipt flag too |
| destinations | list of usernames who will receive the alert; they must be separated by a comma \(,\); for each username specified, its email address must be defined in the user detail form; it can be overridden by the template "to" field |
| carbonCopy | optional argument used to specify a separated list \(by comma\) of email addresses which will receive the email message in carbon copy |
| blindCarbonCopy | optional argument used to specify a separated list \(by comma\) of email addresses which will receive the email message in blind carbon copy |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\) |
| isHtmlContent | flag used to specify if the message text is formatted in HTML or plain text |
| jsObj | javascript record which substitute the variables in the template previously defined |
| dirId | optional dir id used to save the message also to the server file system |
| fileName | optional file name required in case the dir id has been specified; the message will be save in eml format on the file system |
| filesToAttach | list of files, expressed with an absolute path. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailFromTemplateWithEmailAddresses(String from, Number templateId, String destinations, String priority, boolean isHtmlContent, NativeObject jsObj,  dirId, fileName, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user, whose email address must be defined in the user detail form; it can be overridden by the template "from" field |
| templateId | id of the template previously defined, used to set subject and body; optionally, the template can be optionally used to set from, to, cc, receipt flag too |
| destinations | list of usernames who will receive the alert; they must be separated by a comma \(,\); for each username specified, its email address must be defined in the user detail form; it can be overridden by the template "to" field |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\) |
| jsObj | javascript record which substitute the variables in the template previously defined |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history |
| filesToAttach | list of files, expressed with an absolute path. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailFromTemplateWithEmailAddressesWithSMTPSettings(String from, Number templateId, String destinations, String priority, boolean isHtmlContent, NativeObject jsObj, String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS, dirId, fileName, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user, whose email address must be defined in the user detail form; it can be overridden by the template "from" field |
| templateId | id of the template previously defined, used to set subject and body; optionally, the template can be optionally used to set from, to, cc, receipt flag too |
| destinations | list of usernames who will receive the alert; they must be separated by a comma \(,\); for each username specified, its email address must be defined in the user detail form; it can be overridden by the template "to" field |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\) |
| jsObj | javascript record which substitute the variables in the template previously defined |

```text
 smtpXXX-SMTP settings, required to connect to an SMTP server
```

| Argument | Description |
| :--- | :--- |
| dirId | optional dir id used to save the message also to the server file system |
| fileName | optional file name required in case the dir id has been specified; the message will be save in eml format on the file system |
| filesToAttach | list of files, expressed with an absolute path |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailFromTemplateWithConversation(String from, Number templateId, String destinations, String priority, boolean isHtmlContent, NativeObject jsObj, conversationId, messageTag, dirId, fileName, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user, whose email address must be defined in the user detail form; it can be overridden by the template "from" field |
| templateId | id of the template previously defined, used to set subject and body; optionally, the template can be optionally used to set from, to, cc, receipt flag too |
| destinations | list of usernames who will receive the alert; they must be separated by a comma \(,\); for each username specified, its email address must be defined in the user detail form; it can be overridden by the template "to" field |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\) |
| jsObj | javascript record which substitute the variables in the template previously defined |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history |
| filesToAttach | list of files, expressed with an absolute path. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversationAndSMTPSettings(String from, Number templateId, String destinations, String priority, boolean isHtmlContent, NativeObject jsObj, conversationId, messageTag, String smtpHost,String smtpPort,String protocol,String smtpUsername,String smtpPassword,String useTLS, dirId, fileName, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | email address to use to send the message; can be null, if not specified, it will be automatically filled with the email address of the current logged user \(defined in the user detail form\); it can be overridden by the template "from" field |
| templateId | id of the template previously defined, used to set subject and body; optionally, the template can be optionally used to set from, to, cc, receipt flag too |
| destinations | list of email addresses who will receive the alert; they must be separated by a comma \(,\); it can be overridden by the template "to" field |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\). |
| isHtmlContent | flag used to specify if the message text is formatted in HTML or plain text |
| jsObj | javascript record which substitute the variables in the template previously defined |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history |
| smtpXXX | parameters needed to connect to an SMTP server |
| dirId | optional dir id used to save the message also to the server file system |
| fileName | optional file name required in case the dir id has been specified; the message will be save in eml format on the file system |
| filesToAttach | list of files, expressed with an absolute path. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## Send an email message to a user

**Syntax**

```javascript
utils.sendAlertEmailFromTemplateWithEmailAddressesWithConversation(String from, Number templateId, String destinations, String priority, boolean isHtmlContent, NativeObject jsObj, conversationId, messageTag, dirId, fileName, filesToAttach)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | email address to use to send the message; can be null, if not specified, it will be automatically filled with the email address of the current logged user \(defined in the user detail form\); it can be overridden by the template "from" field |
| templateId | id of the template previously defined, used to set subject and body; optionally, the template can be optionally used to set from, to, cc, receipt flag too |
| destinations | list of email addresses who will receive the alert; they must be separated by a comma \(,\); it can be overridden by the template "to" field |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\). |
| jsObj | javascript record which substitute the variables in the template previously defined |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history |
| dirId | optional dir id used to save the message also to the server file system |
| fileName | optional file name required in case the dir id has been specified; the message will be save in eml format on the file system |
| filesToAttach | list of files, expressed with an absolute path. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

Note: in order to send email, additional application/common parameters must be defined:

```text
 MAIL_SMTP_HOST
 MAIL_SMTP_PORT
```

These are optional:

```text
 MAIL_SMTP_PROTOCOL
 MAIL_SMTP_USE_TLS
 MAIL_SMTP_USERNAME
 MAIL_SMTP_PASSWORD
```

## create an URL which can be invoked later from another client <a id="createallowedurl"></a>

\(e.g. from an email message as a link\) and which will be accepted by Platform, since it contains an authentication token; this URL can be used to invoke a server-side javascript action identified by the specific action id. The URL will show the approve.jsp web page containing the Accept/Reject buttons used to confirm or deny an action invoked when pressing the related button.

**Syntax**

```javascript
var url = createAllowedUrl(baseUrl, actionId, aName, aValue, rName, rValue, params, expirationDays, maxTimes, message);
```

**Details**

| Argument | Description |
| :--- | :--- |
| baseUrl | base URL to pass, related to the host name and web context; it will represent the first part of the final URL \(e.g. [http://host:port/platform/](http://host:port/platform/)\) |
| actionId | action identifier to execute when pressing the Accept/Reject button on the web page opened when clicking of the returning URL |
| aName | parameter name related to the accept event, i.e. parameter passed to the js action when pressing the Accept button |
| aValue | parameter value related to the accept event, i.e. parameter value passed to the js action when pressing the Accept button |
| rName | parameter name related to the reject event, i.e. parameter passed to the js action when pressing the Reject button |
| rValue | parameter name related to the accept event, i.e. parameter value passed to the js action when pressing the Reject button |
| params | additional parameters to pass to the js action, for instance to identify a specific record to work with |
| expirationDays | optional parameter \(can be set to 0\); if set, it represents the maximum number of days the URL is valid, starting from the URL creation date |
| maxTimes | it represents the maximum number of times the URL can be used before it expires |
| message | text to show on the approve.jsp web page, just above the Accept/Reject buttons. |

## Read a list of messages from the email server <a id="getemails"></a>

**Syntax**

```javascript
var emailMessages = utils.getEmails(server, port, username, password, protocol, useTLS, maxMessagesToRead, notReadFilter, startDateFilter, fromAddressFilter, subjectFilter, bodyFilter, withAttachments, attachmentsPath, folderName, moveToFolderOnceRead, setAsSeen, deleteEmailWhenRead, debug);
```

**Details**

```text
 server -server host
 port - server port (e.g. 995)
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server (e.g. imap, imaps, pop, pops)
 useTLS  flag used to enabled the TLS mode
 maxMessagesToRead - maximum number of messages to read
```

| Argument | Description |
| :--- | :--- |
| notReadFilter | flag used to filter only messages not read yet |
| startSendDateFilter - optional parameter; if not null, messages to read will be filtered by sendingdate | only the ones next or equal to this date wil be returned |

```text
 fromAddressFilter - optional parameter; if not null, messages to read will be filtered by the "from address" specified
 subjectFilter - optional parameter; if not null, messages to read will be filtered and only the ones containing this value in their object will be returned
 bodyFilter - optional parameter; if not null, messages to read will be filtered and only the ones containing this value in their body content will be returned
 withAttachments - optional parameter; if not null, messages to read will be filtered and only the ones having at least one attachment will be returned
 attachmentsPath - absolute path where saving attachments
 folderName - folder to read; e.g. INBOX; if not specified, it will be set to INBOX
 moveToFolderOnceRead - move to the specified folder each message, once read; can be null
 setAsSeen - flag used to mark as "SEEN" a message just read
```

| Argument | Description |
| :--- | :--- |
| deleteEmailWhenRead | flag used to delete the email message once read |
| debug | flag used to debug the communication with the server |
| emailMessages - return value | list of messages read from the mail box |

Attributes contained in each message of the list:

| Attribute | Description |
| :--- | :--- |
| id | email identifier, used to delete an email message later |
| from | from email address |
| to | to email address |
| message | email body |
| subject | email subject |
| mimeType | e.g. "text/plain" or "text/html" |
| list | list of absolute paths \(strings\) where the attachments have been saved |
| sendDate | message sending date \(since 5.0.1 version\) |
| receiveDate | message receiving date \(since 5.0.1 version\) |
| replyTo | reply to addresses, separated  by a comma \(since 5.0.0 version\) |

Full list of attributes \(as of September 2016\)

to, returnReceipt, getPlainMessage, subject, getBcc, getTo, hashCode, from, setReturnReceipt, wait, getCc, getAttachments, setTo, id, notify, getFrom, attachments, mimeType, setId, notifyAll, getId, getClass, clone, setMessage, setHtmlMessage, getMessage, equals, plainMessage, setAttachments, bcc, getSubject, class, setFrom, getReturnReceipt, message, getPk, setMimeType, setBcc, setCc, toString, htmlMessage, cc, setPlainMessage, pk, getHtmlMessage, getMimeType, setSubject

## Read a list of messages from the email server, with filtering

**Syntax**

```javascript
var emailMessages = utils.getEmails(server, port, username, password, protocol, useTLS, maxMessagesToRead, notReadFilter, startSendDateFilter, endSendDateFilter, startReceiveDateFilter, endReceiveDateFilter, fromAddressFilter, subjectFilter, bodyFilter, withAttachments, attachmentsPath, folderName, moveToFolderOnceRead, setAsSeen, deleteEmailWhenRead, debug);
```

**Details**

```text
server - server host
port - server port (e.g. 995)
username - username to use when accessing the email server
password - password to use when accessing the email server
protocol - protocol to use when connecting to the email server (e.g. imap, imaps, pop, pops)
```

| Argument | Description |
| :--- | :--- |
| useTLS | flag used to enabled the TLS mode |
| maxMessagesToRead | maximum number of messages to read |
| notReadFilter | flag used to filter only messages not read yet |
| startSendDateFilter - optional parameter | if not null, messages to read will be filtered by sendingdate; only the ones next or equal to this date wil be returned |
| endSendDateFilter - optional parameter | if not null, messages to read will be filtered by sendingdate; only the ones previousor equal to this date wil be returned |
| startReceiveDateFilter - optional parameter | if not null, messages to read will be filtered by receiving date; only the ones next or equal to this date wil be returned |
| endReceiveDateFilter - optional parameter | if not null, messages to read will be filtered by receiving date; only the ones previousor equal to this date wil be returned |
| fromAddressFilter - optional parameter | if not null, messages to read will be filtered by the "from address" specified |
| subjectFilter - optional parameter | if not null, messages to read will be filtered and only the ones containing this value in their object will be returned |
| bodyFilter - optional parameter | if not null, messages to read will be filtered and only the ones containing this value in their body content will be returned |
| withAttachments - optional parameter | if not null, messages to read will be filtered and only the ones having at least one attachment will be returned |
| attachmentsPath | absolute path where saving attachments |
| folderName | folder to read; e.g. INBOX; if not specified, it will be set to INBOX |
| moveToFolderOnceRead | move to the specified folder each message, once read; can be null |
| setAsSeen | flag used to mark as "SEEN" a message just read |
| deleteEmailWhenRead | flag used to delete the email message once read |

```text
debug - flag used to debug the communication with the server
emailMessages : return value - list of messages read from the mail box
```

Attributes contained in each message of the list:

| Attribute | Description |
| :--- | :--- |
| id | email identifier, used to delete an email message later |
| messageNumber | index within the folder of the specific message |
| from | from email addresses |
| message | email body |
| subject | email subject |
| mimeType | e.g. "text/plain" or "text/html" |
| list | list of absolute paths \(strings\) where the attachments have been saved |
| sendDate | message sending date |
| receiveDate | message receiving date |

## Move a list of email messages to another folder <a id="movemessages"></a>

**Syntax**

```javascript
var ok = utils.moveMessages(server,port, username, password, protocol, useTLS, messageIds,folderName, moveToFolder, setAsSeen, debug);
```

**Details**

```text
server - server host
port - server port
username - username to use when connecting to the email server
password - password to use when connecting to the email server
protocol - protocol to use when connecting to the email server
```

| Argument | Description |
| :--- | :--- |
| useTLS | flag used to enabled the TLS mode |
| messageIds | list of email message identifiers, related to emails to move |
| folderName | source folder \(e.g. INBOX\), where the email messages are stored |
| moveToFolder | destination folder \(e.g. Archivio\) |
| setAsSeen | flag used to mark the email as seen |

```text
debug - flag used to debug the process
```

## Mark a list of email messages as seen or not seen <a id="markmessagesasseen"></a>

**Syntax**

```javascript
var ok = utils.markMessagesAsSeen(server,port, username, password, protocol, useTLS, messageIds,folderName, setAsSeen, debug);
```

**Details**

```text
 server -server host
 port - server port
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server
```

| Argument | Description |
| :--- | :--- |
| useTLS | flag used to enabled the TLS mode |
| messageIds | list of email message identifiers, related to emails to move |
| folderName | source folder \(e.g. INBOX\), where the email messages arestored |
| setAsSeen | flag used to mark the email as seen or not seen |

```text
 debug - flag used to debug the process
```

## Delete a list of email messages <a id="deletemessages"></a>

Delete a list of emails from the specified folder by moving them to the trash folder, starting from a list of messages identified both by a list of email ids and a list of corresponding email indexes.

Both properties can retrieved through the message js object returned by the utils.getEmails method.

**Syntax**

```javascript
var ok = utils.deleteMessages(server,port, username, password, protocol, useTLS,messageIdsToDelete, messagesNumbersToDelete,folderName,trashName);
```

**Details**

```text
 server -server host
 port - server port
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server
```

| Argument | Description |
| :--- | :--- |
| useTLS | flag used to enabled the TLS mode |
| messageIdsToDelete | list of email message identifiers to delete; this value can be fetched from the email message js object |
| messageNumbersToDelete | list of email message numbersto delete; this value can be fetched from the email message js object |

```text
 folderName-folder name where themessages to delete are located (e.g. INBOX)
 trashName-identifier of the Trash folder; since this name changes according to the specific email provider, it is not necessarely the value "Trash". If you don't know it, you can try with "Trash" and in case of errors, Platform would log the whole list of folders supported by the email provider.
```

## Delete a list of email messages starting from filtering conditions

Delete a list of email messages from the specified folder by moving them to the trash folder, starting from a filtering condition. At least one filtering condition is required \(one of the four date filters\)

**Syntax**

```javascript
var ok = utils.deleteMessages(server,port, username, password, protocol, useTLS, startSendDateFilter, endSendDateFilter, startReceiveDateFilter, endReceiveDateFilter,  messagesNumbersToDelete, folderName, trashName);
```

**Details**

```text
 server -server host
 port - server port
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server
```

| Argument | Description |
| :--- | :--- |
| useTLS | flag used to enabled the TLS mode |
| startSendDateFilter-optional filter | if specified, only messages sent after the specified date will be deleted |
| endSendDateFilter | optional filter: if specified, only messages sent beforethe specified date will be deleted |
| startReceiveDateFilter | optional filter: if specified, only messages receviedafter the specified date will be deleted |
| endReceiveDateFilter | optional filter: if specified, only messages received beforethe specified date will be deleted |

```text
 trashName-identifier of the Trash folder; since this name changes according to the specific email provider, it is not necessarely the value "Trash". If you don't know it, you can try with "Trash" and in case of errors, Platform would log the whole list of folders supported by the email provider.
 folderName-folder name where themessages to delete are located (e.g. INBOX)
```

## Forward an email to the specified destination <a id="forwardemail"></a>

**Syntax**

```javascript
var ok = utils.forwardEmail(server,port, username, password, protocol, useTLS,to, subject subject, text, messageId);
```

**Details**

```text
 server -server host
 port - server port
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server
```

| Argument | Description |
| :--- | :--- |
| useTLS | flag used to enabled the TLS mode |
| to | destination address |
| subject | additional title to add to the original one |
| text | additional text to add to the body of the email |
| messageId | list of email message identifiers to delete |

## Save a list of email messages on the server file system

Available since 5.2 version. Uses **eml** format.

Messages to save are identified by a list of message id, so utils.getEmails\(\) method mustbe invoked first, in order to get the identifiers needed here to fetch the messages to save.

**Syntax**

```javascript
var ok = utils.saveEml(String server,Integer port, String username, String password, String protocol,Boolean useTLS,String folderName,String[] messageIds,String[] fileNames,Long directoryId);
```

**Details**

```text
 server -server host
 port - server port
 username - username to use when accessing the email server
 password - password to use when accessing the email server
 protocol - protocol to use when connecting to the email server
```

| Argument | Description |
| :--- | :--- |
| useTLS | flag used to enabled the TLS mode |

```text
 folderName-folder identifier, where the messages are located; the folder name changes according to the mail server; an example is INBOX
 messageIds-a list of message identifiers to save, previously fetched through a getEmails() method invokation
 fileNames-file names to use when saving the messages; this list must have the same length of the message ids list, one for each id
 directoryId-directory identifier, used to identify the path on the server file system, when all messages will be saved
```

The method returns the list of messages ids not found in the specified folder and, consequently, not saved.

## Send an SMS message through some carrier <a id="sendsmsmessage"></a>

Important note: an SMS provider must be configured first.  
Two alternatives are allowed:

* Twilio web service; you have to configure two parameters: TWILIO\_ACCOUNT\_ID and TWILIO\_AUTH\_TOKEN 
* an email gateway can be used; in that case, you have to configure the SMS\_SMTP\_xxx parameters and the phone numbers must be expressed appropriately.

**Syntax**

```javascript
var json = utils.sendSmsMessage(String fromPhoneNr,String toPhoneNr,String text,Boolean logMessage);
```

**Details**

| Argument | Description |
| :--- | :--- |
| fromPhoneNr | phone number used to identify the starting device |
| toPhoneNr | phone number where the message will be sent |
| text | text message to send |
| return an outcome, expressed as a JSON string, containing | { "success": true } if the operation has been completed successfully, { "success": false, "message": "..." } otherwise |

Pay attention to the phone number format, with should always include the international prefix:e.g. +0039....

