# Alert

## Send an alert message to a user

**Syntax**

```javascript
utils.sendAlertMessage(from, message, destinations, priority, conversationId, messageTag)
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

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

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

## Send an alert message to a user with a clickable callback

The **sendAlertMessage** function can be used also to include a clickable link which can be used to execute a js client side function.

This is possible since the message content is HTML based and therefore you can include a \<A> tag to do it.

Example:

```javascript
utils.sendAlertMessage(
  "ADMIN",
  "Click <a href='#' onclick='openWindowXXX()' >here</a> to open the window","ADMIN",
  null
);
```

## Show a toast message <a href="executeshellcommand" id="executeshellcommand"></a>

A toast message is a popup message shown starting from the top margin of the browser window, reporting a title and a text. The popup is automatically hidden after a few seconds.

**Syntax**

```javascript
utils.showToast(settings)
```

**Details**

Settings is a javascript object containing the following attributes:

| Argument  | Description                                                                                                                                         |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| title     | popup title                                                                                                                                         |
| message   | message to show within the popup                                                                                                                    |
| sleep     | optional; if specified, it represents the amount of time (in seconds) the popup will be visible; after that time, the popup is automatically hidden |
| className | optional; if specified, it represents the CSS class to add to the popup                                                                             |



**Example**

```javascript
showToast({
    title: "common.warning",
    message: "data changed",
    sleep: 3
});
```





