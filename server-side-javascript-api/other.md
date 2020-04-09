# Other

## Get translation, given an entry

**Syntax**

```javascript
var translation = utils.getResource(entry)
```

**Details**

| Argument | Description |
| :--- | :--- |
| translation | string value: the translation for the entry value |
| entry | string value: the entry to translate |

## Get translation for a specific language, given an entry

**Syntax**

```javascript
var translation = utils.getResourceByLanguageId(entry, languageId)
```

**Details**

| Argument | Description |
| :--- | :--- |
| translation | string value: the translation for the entry value |
| entry | string value: the entry to translate |
| languageId | string value: the language id to use when translating the entry |

## Get language id for a specific username

**Syntax**

```javascript
var languageId = utils.getLanguageIdFromUsername(userId)
```

**Details**

| Argument | Description |
| :--- | :--- |
| languageId | string value: the language id expressed like \(IT,EN,...\) |
| userId | string value: the username to use to get language id |

## Log a message <a id="log"></a>

**Syntax**

```javascript
utils.log(msg, type);
```

**Details**

| Argument | Description |
| :--- | :--- |
| msg | string value: message to log |
| type | string value: message type; allowed values:INFO,WARN,DEBUG,ERROR |

Since 5.2.1 version

```javascript
utils.info(msg);

utils.warn(msg);

utils.debug(msg);

utils.error(msg);
```

## Set the return message <a id="setreturnvalue"></a>

this method can be omitted; in that case a default json message with success: true will be sent back

**Syntax**

```javascript
utils.setReturnValue(response)
```

**Details**

response - string value: messagge to send back

## Convert a number to its text representation <a id="numbertotext"></a>

**Syntax**

```javascript
var text = utils.numberToText(num, decimals, languageId, showDecimals, sep)
```

**Details**

| Argument | Description |
| :--- | :--- |
| text | string value: the text representation of the number \(e.g. duecento ventiquattro/00\) |
| num | a number, including a decimal number |
| decimals | a number, it is used to round the num to this number of decimals |
| languageId | language identifier |
| showDecimals | true/false; define if the decimal part must be included |
| sep | integer vs decimal separator, e.g. / |

## Round a number to the specified number of decimals <a id="round"></a>

**Syntax**

```javascript
var result = utils.round(num,decimals)
```

**Details**

| Argument | Description |
| :--- | :--- |
| result | rounded decimal number |
| num | a decimal number |
| decimals | number of decimals that the final number must be rounded to |

## Get absolute path of WEB-INF/classes folder of Platform application

**Syntax**

```javascript
var path = utils.getBasePath()
```

**Details**

| Argument | Description |
| :--- | :--- |
| path | the absolute path of WEB-INF/classes folder of Platform application |

It can be helpful for instance to get the basedir for a more complex organization of files.

## Get a parameter value <a id="getparameter"></a>

**Syntax**

```javascript
var paramValue = utils.getParameter(paramName)
```

**Details**

| Argument | Description |
| :--- | :--- |
| paramName | a string value representing a parameter named defined at installation level \(CON44 table\) or at application level \(CON07 table\) |
| paramValue | the value defined for the specified parameter name or null if not found; if the parameter is found as an application parameter, that value is returned, otherwise it will be returned the value defined at installation level |

## Remove time from date

**Syntax**

```javascript
var newDate = utils.removeTime(java.util.Date date)
```

**Details**

| Argument | Description |
| :--- | :--- |
| date | java.util.Date: date without time |

## Convert the date to String with the specify format <a id="convertdatetostring"></a>

\(default: "yyyy-MM-dd'T'HH:mm:ss"\)

**Syntax**

```javascript
stringDate = utils.convertDateToString(java.util.Date date, String format)
```

**Detail**

| Argument | Description |
| :--- | :--- |
| date | java.util.Date: date to convert in string |
| format | String: date format for string |

## Convert the date js object to a java.sql.Date \(for a DATE typefield\)

helpful in case you want to use it with a **utils.executeSql** or **utils.executeQuery** methods and pass it as a parameter

**Syntax**

```javascript
var javasqlDateValue = utils.convertDateToSqlDate(java.util.Date date)
```

**Detail**

| Argument | Description |
| :--- | :--- |
| date | java.util.Date: date to convert in string |

## Convert the date js object to a java.sql.Date \(for a DATETIME/TIMESTAMP typefield\)

helpful in case you want to use it with a **utils.executeSql** or **utils.executeQuery** methods and pass it as a parameter

**Syntax**

```javascript
var javasqlTimestampValue= utils.convertDateToTimestamp(java.util.Date date)
```

**Detail**

| Argument | Description |
| :--- | :--- |
| date | java.util.Date: date to convert in string |

## Send an alert message to a user

**Syntax**

```javascript
utils.sendAlertMessage(from, message, destinations, priority, conversationId, messageTag)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user |
| message | message to send |
| destinations | list of usernames who will receive the alert; they must be separated by a comma \(,\) |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\) |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" to "Y", otherwise these messages cannot be showed on the client side.

## Send a chat message to a user

**Syntax**

```javascript
utils.sendChatMessage(from, message, destinations, priority, conversationId, messageTag)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | username to use to send the message; can be null, if not specified, it will be automatically filled with the current logged user |
| message | message to send |
| destinations | list of usernames who will receive the alert; they must be separated by a comma \(,\) |
| priority | priority to use for the messages to show to a specific user: messages having a higher priority will be showed at the top of the list; it can be null; if not specified, it will be set to "normal"; allowed values: 0 \(minor\), 1, \(normal\), 2 \(high\) |
| conversationId | conversation id used to identify a chain of messages; optional: if not specified, each message represents the first and last message in the convo |
| messageTag | optional hidden text to add to the message and used to search for specific messages stored in the message history. |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" or "SHOW\_CHAT\_POPUP\_MESSAGE" to "Y", otherwise these messages cannot be showed on the client side.

## Send a not visible notification to the client

\(available form 5.3.2\) Send a notification to the client side; this is not a visual notification: it can be used to automate the invocation of a javascript method defined on the client. This automation can be helpful for example to open a window or reload a grid or form, when a server-side long operation has terminated.

You have to specify the function name and the argument to pass foward.

A limit it has is that you can only invoke functions having one only argument.

**Syntax**

```javascript
utils.sendJavascriptMessage(String from, Map obj, String destinations, String functionName)
```

**Details**

| Argument | Description |
| :--- | :--- |
| from | username to use to send the message; can be null, if not specified, it will be automatically filled with the current loggeduser |
| obj | javascript object to pass forward to the javascript function to invoke on the client side |
| destinations | list of usernames who will receive the alert; they must be separated by a comma \(,\) |
| functionName | callback js function, which must be defined on the client side, invoked automatically from the notification |

Note: in order to use this feature, you have first to define an application parameters named "SHOW\_ALERT\_MENU\_ITEM" or "SHOW\_CHAT\_POPUP\_MESSAGE" to "Y", otherwise these messages cannot be showed on the client side.

In case you need to invoke something from complex, you have to declare a one argument function in some global .js file \(stored in the "scripts" folder of your application web context\) and use it to do it.

Example of a global scoped js function with one argument, used to show a popup warning window:

```javascript
function openADialogWindow(args) {
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
  "openADialogWindow"
);
```

## Send an alert message to a user with a clickable callback

The **sendAlertMessage** function can be used also to include a clickable link which can be used to execute a js client side function.

This is possible since the message content is HTML based and therefore you can include a &lt;A&gt; tag to do it.

Example:

```javascript
utils.sendAlertMessage(
  "ADMIN",
  "Click <a href='#' onclick='openWindowXXX()' >here</a> to open the window","ADMIN",
  null
);
```

## Execute a command on the shell <a id="executeshellcommand"></a>

Optionally, a list of arguments can be passed to the command.

It returns the exit code produced by the command execution

**Syntax**

```javascript
var exitCode = utils.executeShellCommand(command, arg1, arg2, ...)
```

**Details**

| Argument | Description |
| :--- | :--- |
| command | command to execute; it must include the absolute path to the command and must end with a .sh or .bat with no spaces within |
| arguments | zero or more String type arguments; \[\] otherwise |

## Convert a javascript object to its JSON representation

**Syntax**

```javascript
var json = utils.getJSONString(obj);
```

**Details**

| Argument | Description |
| :--- | :--- |
| obj | javascript object to convert to its JSON representation |

## Convert a list of javascript objects into its JSON representation

**Syntax**

```javascript
var json = utils.getJSONList(jsObjectsList);
```

**Details**

| Argument | Description |
| :--- | :--- |
| jsObjectList | list of javascript objects to convert to JSON format |
| _return value_ | JSON representation of a list of objects |

Note: this result is NOT compatible with an Ext.grid.GridPanel data protocol: see **getListResponse** instead.

## Convert a list of javascript objects into its JSON representation and embed it to a “Ext.grid.GridPanel like” data representation

based on “valueObjectList”, “resultSetLength” and “moreRows” attributes

**Syntax**

```javascript
var json = utils.getListResponse(jsObjectsList, resultSetLength, moreRows);
```

**Details**

| Argument | Description |
| :--- | :--- |
| jsObjectsList | list of javascript objects to convert to JSON format |
| resultSetLenght | a number : list of objects \(can be list.length\) |
| moreRows | flag used to specify |
| _return value_ | returns a JSON content compatible with Ext grids |

## Replace all occurrences of the “specified” pattern within “text” with the new value

**Syntax**

```javascript
var newtext = utils.replaceAll(text, pattern, newValue)
```

**Details**

| Argument | Description |
| :--- | :--- |
| text | text to analyze |
| pattern | pattern to search for |
| newValue | value that replaces all occurrences of the pattern |

Returns a new text where all occurrences of “pattern” have been replaced with “newValue”.

## **Enqueuing server-side js actions**

```text
enqueueAction(queueName, actionId, params, priority, processWaitTime, logExecution);
```

The arguments are:

* **queueName**– optional: queue name; if not specified, the process will be enqueued in the DEFAULT queue
* **actionId**– server-side javascript action identifier to execute
* **param**– javascript object containing parameters to pass to the action
* **priority**– optional; if specified, processes within the same queue will be sorted according to the priority rathe than to the enqueuing time
* **processWaitTime**– optional; if specified, the process will not be started before that time, expressed in seconds
* **logExecution**– true to log in the predefined table LOG60\_LOGS the execution of the process

Note: the javascript object specified through the "param" can accept an optional attribute named "**queueTimeout**": when the action execution time overpasses that value, \(expressed in minutes\), the element is marked as "timeout" in the queue and the queue is then unlocked, in order to allow extracting new elements from it. Note that the current action is still under execution and this could create drawbacks in case of actions which should be executed sequentially, since the work on the same set of data,by writing them.

There is a variant of the method described above, having one more argument:

```text
enqueueActionWithNote(queueName, actionId, params, priority, processWaitTime, logExecution, note);
```

where **note** is a string value which will be saved in the NOTE field of the CON77\_QUEUES table. This field can be helpful to carry out custom logic on the enqueued elements, for instance to execute statistics about the amount of data not processed yet.

## **Adding a web service invocation as a process to a specific queue**

```text
var queueId = utils.enqueueWebService(queueName, url, params, priority, processWaitTime, logExecution);
```

The required arguments are:

* **queueName**– optional: queue name; if not specified, the process will be enqueued in the DEFAULT queue
* **url**– shell command to execute
* **param**– js object containing parameters to pass to the web service
* **priority**– optional; if specified, processes within the same queue will be sorted according to the priority rathe than to the enqueing time
* **processWaitTime**– optional; if specified, the process will not be started before that time, expressed in seconds
* **logExecution**– true to log in LOG60\_LOGS the execution of the process

## **Adding a shell command as a process to a specific queue**

```text
var queueId = utils.enqueueShellCommand(queueName, cmd, priority, processWaitTime, logExecution);
```

The required arguments are:

* **queueName** – optional: queue name; if not specified, the process will be enqueued in the DEFAULT queue+
* **cmd** – shell command to execute
* **priority**– optional; if specified, processes within the same queue will be sorted according to the priority rathe than to the enqueing time
* **processWaitTime** – optional; if specified, the process will not be started before that time, expressed in seconds
* **logExecution**– true to log in LOG60\_LOGS the execution of the process

## Create a link to access the web app from an email or other external media

In case you need to create a dynamic link which allows you to access a Platform web application, linked to a specific username, you can use this method:

```javascript
var token = utils.createAllowedLink(
  expirationDays, // expirationDays = 0 for no expiration
  maxTimes
);
```

The required arguments are:

* **expirationDays** – optional: it defines the validity of this link, expressed as number of days; if not specified, the link is always valid
* **maxTimes** – optional: it defines the validity of this link, expressed as the number of times it can be used; after reaching this number, the link cannot be used anymore; if not specified, the link is always valid.

This method returns a token, which is a dynamically generated text you can include when logging on the web app.

Note: the link can become invalid either if it reaches the expiration time or when it has been used the max number of times.

**Important note:** it is strongly recommended to always specify at least one of the 2 arguments, so that the link will expire: this will make your Platform web application more secure.

## Create a link to access the web app from an email or other external media with additional data

In case you need to create a dynamic link which allows you to access a Platform web application, linked to a specific username and you also need to pass forward additional data, you can use this method:

```javascript
var token = utils.createAllowedLinkWithRtk(
  expirationDays, // expirationDays = 0 for no expiration
  maxTimes,
  rtk
);
```

The required arguments are:

* **expirationDays** – optional: it defines the validity of this link, expressed as number of days; if not specified, the link is always valid
* **maxTimes** – optional: it defines the validity of this link, expressed as the number of times it can be used; after reaching this number, the link cannot be used anymore; if not specified, the link is always valid
* **rtk** - additional data to include, expressed as a String. You can get this content through the **getEncodedRtk.**

This method returns a token, which is a dynamically generated text you can include when logging on the web app.

Note: the link can become invalid either if it reaches the expiration time or when it has been used the max number of times.

**Important note:** it is strongly recommended to always specify at least one of the 2 first arguments, so that the link will expire: this will make your Platform web application more secure.

## Enconding data to send externally

In case you need to encode data which you need to send outside, for instance in a link, you can use this method:

```javascript
var token = utils.getEncodedRtk(String... data);
```

The required arguments are:

* **data** – data list to encode

This method returns a String object, that can be used for instance in the method **createAllowedLinkWithRtk**.

Note: this method will NOT encrypt data: it only obfuscates data, by not makes it visible in plain text.

If you need more protection and encrypt data, use the method **getEncToken** instead.

## Encrypting data to send externally

In case you need to encrypt data which you need to send outside, for instance in a link, you can use this method:

```javascript
var token = utils.getEncToken(String... data);
```

The required arguments are:

* **data** – data list to encode 

This method returns a String object, that can be used for instance in the method **createAllowedLinkWithRtk**.

## Decrypting data received from the outside

In case you need to decrypt data which has been previously encripted and you need to decode it, you can use this method:

```javascript
var data = utils.decodeEncToken(String token);
```

The required arguments are:

* **token** – encrypted content, expressed as a String received in input

This method returns a String object.  
**Important note**: use this method only in combination with getEncToken, since it can only decrypt content previously decripted by it.

## Adds or subtracts the specified amount of time to the given calendar field, based on the calendar's rules

You can use:

```javascript
utils.addDate(String field, int amount): //use a current date; 
utils.addDate(String date, String format, String field, int amount): //convert the date with the specify format 
(default: "yyyy-MM-dd'T'HH:mm:ss")
```

**Details**

| Argument | Description |
| :--- | :--- |
| field | String: the calendar field |
| amount | number: the amount of date or time to be added to the field |

## Convert a text to an hash key \(md5\)

MD5 is an hash function you can use to convert a text to a text-based key; multiple invocations to the function with the same input always provide the same result, but the hash function does not provide a unique value: different texts could return the same hash key. This is helpful to check out on the database table the existence of a specific record, starting from its md5 representation.

```javascript
var md5Text= utils.md5(String text);
```

**Details**

| Argument | Description |
| :--- | :--- |
| text | text to convert to an hash key |
| md5Text | the MD5 hash key corresponding to the input text |





