# Function JSS 2

## Send an alert email from template with conversation and SMTP settings

**Syntax**



```javascript
utils.sendAlertEmailFromTemplateWithConversation(String from,Number templateId,String destinations,String priority,boolean isHtmlContent,Map jsObj,Long conversationId,String messageTag,String[] filesToAttach)
```



| Argument       | Description                                                                                                                                                                                                                                          |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| from           | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user, whose email address must be defined in the user detail form; it can be overridden by the template "from" field     |
| templateId     | id of the template previously defined, used to set subject and body; optionally, the template can be optionally used to set from, to, cc, receipt flag too                                                                                           |
| destinations   | list of usernames who will receive the alert; they must be separated by a comma (,); for each username specified, its email address must be defined in the user detail form; it can be overridden by the template "to" field                         |
| priority       | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 (minor), 1, (normal), 2 (high) |
| jsObj          | javascript record which substitute the variables in the template previously defined                                                                                                                                                                  |
| massageTag     | optional hidden text to add to the message and used to search for specific messages stored in the message history.                                                                                                                                   |
| isHtmlContent  | lag used to specify if the message text is formatted in HTML or plain text                                                                                                                                                                           |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo                                                                                                    |
| filesToAttach  | a list of files to attach, separated by a comma; use \[] to not include files; each file must include the absolute path                                                                                                                              |
|                |                                                                                                                                                                                                                                                      |
|                |                                                                                                                                                                                                                                                      |
|                |                                                                                                                                                                                                                                                      |
|                |                                                                                                                                                                                                                                                      |
