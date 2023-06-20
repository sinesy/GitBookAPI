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

