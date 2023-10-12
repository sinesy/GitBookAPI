# Other

## **Camel-case**

camel(name, firstCharUpper)

Convert a database field or an upper-case parameter containing underscores (\_) to the camel case format, i.e. lowercase and the underscore remove and next character to uppercase.

Example:

var x = utils.camel("ABC\_DEF",false); -> x = "abcDef"

var x = utils.camel("ABC\_DEF",true); -> x = "AbcDef"



## **Snake-case**

camelToSnake(name, toUpperCase)

It is the opposite function of the camel-case function: it converts a camel case string to snake case, i.e a string expressed in lowercase with an underscore (\_) separating each uppercase character in the original string.

Example:

var x = utils.camelToSnake("abcDEF",false); -> x = "abc\__d\_e\__f"

var x = utils.camelToSnake("abcDEF",true); -> x = "ABC\__D\_E\__F"

## **Uncamel**

uncamel(attributeName)

It converts an attribute name to a field name, according to Java convention.

Example:

var x = utils.uncamel("abcD1",true); -> x = "ABC\__D1_"

## Get translation, given an entry

**Syntax**

```javascript
var translation = utils.getResource(entry)
```

**Details**

| Argument    | Description                                       |
| ----------- | ------------------------------------------------- |
| translation | string value: the translation for the entry value |
| entry       | string value: the entry to translate              |

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

## Get language id for a specific username

**Syntax**

```javascript
var languageId = utils.getLanguageIdFromUsername(userId)
```

**Details**

| Argument   | Description                                              |
| ---------- | -------------------------------------------------------- |
| languageId | string value: the language id expressed like (IT,EN,...) |
| userId     | string value: the username to use to get language id     |

## Log a message <a href="#log" id="log"></a>

**Syntax**

```javascript
utils.log(msg, type);
```

**Details**

| Argument | Description                                                      |
| -------- | ---------------------------------------------------------------- |
| msg      | string value: message to log                                     |
| type     | string value: message type; allowed values:INFO,WARN,DEBUG,ERROR |

Since 5.2.1 version

```javascript
utils.info(msg);

utils.warn(msg);

utils.debug(msg);

utils.error(msg);
```

## Set the return message <a href="#setreturnvalue" id="setreturnvalue"></a>

this method can be omitted; in that case a default json message with success: true will be sent back

**Syntax**

```javascript
utils.setReturnValue(response)
```

**Details**

response - string value: messagge to send back

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

## Round a number to the specified number of decimals <a href="#round" id="round"></a>

**Syntax**

```javascript
var result = utils.round(num,decimals)
```

**Details**

| Argument | Description                                                 |
| -------- | ----------------------------------------------------------- |
| result   | rounded decimal number                                      |
| num      | a decimal number                                            |
| decimals | number of decimals that the final number must be rounded to |

## Get absolute path of WEB-INF/classes folder of Platform application

**Syntax**

```javascript
var path = utils.getBasePath()
```

**Details**

| Argument | Description                                                         |
| -------- | ------------------------------------------------------------------- |
| path     | the absolute path of WEB-INF/classes folder of Platform application |

It can be helpful for instance to get the basedir for a more complex organization of files.

## Get a parameter value <a href="#getparameter" id="getparameter"></a>

**Syntax**

```javascript
var paramValue = utils.getParameter(paramName)
```

**Details**

| Argument   | Description                                                                                                                                                                                                                   |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| paramName  | a string value representing a parameter named defined at installation level (CON44 table) or at application level (CON07 table)                                                                                               |
| paramValue | the value defined for the specified parameter name or null if not found; if the parameter is found as an application parameter, that value is returned, otherwise it will be returned the value defined at installation level |

## Remove time from date

**Syntax**

```javascript
var newDate = utils.removeTime(java.util.Date date)
```

**Details**

| Argument | Description                       |
| -------- | --------------------------------- |
| date     | java.util.Date: date without time |

## Convert the date to String with the specify format <a href="#convertdatetostring" id="convertdatetostring"></a>

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

## Convert the date String to a javascript Date

helpful in case you want to use convert a date expressed as a String into a javascript Date (do not pass forward the javascript Date directly to a SQL instruction: convert it to a Java Date before, using the methods below).

**Syntax**

```javascript
var javascriptDateValue = convertStringToDate(String dateAsString,String format)
```

**Detail**

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

## Convert a javascript object to its JSON representation

**Syntax**

```javascript
var json = utils.getJSONString(obj);
```

**Details**

| Argument | Description                                             |
| -------- | ------------------------------------------------------- |
| obj      | javascript object to convert to its JSON representation |

## Convert a list of javascript objects into its JSON representation

**Syntax**

```javascript
var json = utils.getJSONList(jsObjectsList);
```

**Details**

| Argument       | Description                                          |
| -------------- | ---------------------------------------------------- |
| jsObjectList   | list of javascript objects to convert to JSON format |
| _return value_ | JSON representation of a list of objects             |

Note: this result is NOT compatible with an Ext.grid.GridPanel data protocol: see **getListResponse** instead.

## Convert a list of javascript objects into its JSON representation and embed it to a “Ext.grid.GridPanel like” data representation

based on “valueObjectList”, “resultSetLength” and “moreRows” attributes

**Syntax**

```javascript
var json = utils.getListResponse(jsObjectsList, resultSetLength, moreRows);
```

**Details**

| Argument        | Description                                          |
| --------------- | ---------------------------------------------------- |
| jsObjectsList   | list of javascript objects to convert to JSON format |
| resultSetLenght | a number : list of objects (can be list.length)      |
| moreRows        | flag used to specify                                 |
| _return value_  | returns a JSON content compatible with Ext grids     |

## Replace all occurrences of the “specified” pattern within “text” with the new value

**Syntax**

```javascript
var newtext = utils.replaceAll(text, pattern, newValue)
```

**Details**

| Argument | Description                                        |
| -------- | -------------------------------------------------- |
| text     | text to analyze                                    |
| pattern  | pattern to search for                              |
| newValue | value that replaces all occurrences of the pattern |

Returns a new text where all occurrences of “pattern” have been replaced with “newValue”.

## **Enqueuing server-side js actions**

```
enqueueAction(queueName, actionId, params, priority, processWaitTime, logExecution);
```

The arguments are:

* **queueName**– optional: queue name; if not specified, the process will be enqueued in the DEFAULT queue
* **actionId**– server-side javascript action identifier to execute
* **param**– javascript object containing parameters to pass to the action
* **priority**– optional; if specified, processes within the same queue will be sorted according to the priority rathe than to the enqueuing time
* **processWaitTime**– optional; if specified, the process will not be started before that time, expressed in seconds
* **logExecution**– true to log in the predefined table LOG60\_LOGS the execution of the process

Note: the javascript object specified through the "param" can accept an optional attribute named "**queueTimeout**": when the action execution time overpasses that value, (expressed in minutes), the element is marked as "timeout" in the queue and the queue is then unlocked, in order to allow extracting new elements from it. Note that the current action is still under execution and this could create drawbacks in case of actions which should be executed sequentially, since the work on the same set of data,by writing them.

There is a variant of the method described above, having one more argument:

```
enqueueActionWithNote(queueName, actionId, params, priority, processWaitTime, logExecution, note);
```

where **note** is a string value which will be saved in the NOTE field of the CON77\_QUEUES table. This field can be helpful to carry out custom logic on the enqueued elements, for instance to execute statistics about the amount of data not processed yet.



## **Enqueuing multiple elements in queue, starting from a SQL query**

It is possible to speed up the enqueuing process of a large amount of elements, starting from a SQL query whose result (a list of records) represents the data to pass forward to each element in the queue. For each record read from the SQL query, an element is enqueued in the specified queue: such an element would receive in input the current record.

This can improve the enqueuing process of about 40%.

**Syntax**

```
utils.enqueueActionsFromSqlQuery(
  String queueName,String payload,Long actionId,
  Long datasourceId,String sqlQuery,Object[] params
);
```

| Argument     | Description                                                                                                                      |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| queueName    | name of the queue where all elements will be inserted                                                                            |
| payload      | optional  payload to pass forward to each element                                                                                |
| actionId     | to enqueued action id                                                                                                            |
| datasourceId | optional datasource id where the SQL query will be executed                                                                      |
| sqlQuery     | SQL query to execute: for each record, an element will be enqueued and the record would represent the input data                 |
| params       | optional list of parameters to pass to the SQL Query (where they are referred always as ?); set to \[] in case of no parameters. |

## **Adding a web service invocation as a process to a specific queue**

```
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

```
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

* **data** – data list to encode&#x20;

This method returns a String object, that can be used for instance in the method **createAllowedLinkWithRtk**.

## Decrypting data received from the outside

In case you need to decrypt data which has been previously encripted and you need to decode it, you can use this method:

```javascript
var data = utils.decodeEncToken(String token);
```

The required arguments are:

* **token** – encrypted content, expressed as a String received in input

This method returns a String object.\
**Important note**: use this method only in combination with getEncToken, since it can only decrypt content previously decripted by it.

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

## Convert a text to an hash key (md5)

MD5 is an hash function you can use to convert a text to a text-based key; multiple invocations to the function with the same input always provide the same result, but the hash function does not provide a unique value: different texts could return the same hash key. This is helpful to check out on the database table the existence of a specific record, starting from its md5 representation.

```javascript
var md5Text= utils.md5(String text);
```

**Details**

| Argument | Description                                      |
| -------- | ------------------------------------------------ |
| text     | text to convert to an hash key                   |
| md5Text  | the MD5 hash key corresponding to the input text |

## Setting a value in a value object to save from a server-side js action

In case you are saving data from a grid or form, using the standard Platform saving system (form Save button on the UI), you can inject new attributes or change attribute values just before saving data on the server. Using the "before saving data on insert/update" event, you can link a server-side js action. Here you can execute any kind of business logic and the use calculated data and inject it in the "vo" which is just to be saved, through the following method:

```javascript
utils.setAttributeValue(String attrName,Object value);
```

**Details**

| Argument | Description                                                           |
| -------- | --------------------------------------------------------------------- |
| attrName | attribute name to set in the "vo" Platform is working on to save data |
| value    | value to set for this attribute                                       |



## Convert a javascript object to a JSON string to work with in an action

In case you need to convert a javascript object to a JSON string within a server-side javascript action, you can use the following  method:

```javascript
var jsonString = utils.stringify(Object obj);
```

**Details**

| Argument | Description                  |
| -------- | ---------------------------- |
| obj      | javascript object to convert |

Such a method is helpful in case of a complex object containing java-type objects rather than javascript-type data.

As an alternative, you can use the standard javascript utility function:

```javascript
var jsonString = JSON.stringify(jsonCarrello,jsonReplacer)
```



## Convert a javascript object to a JSON strings compatible with a database field

In case you need to convert a javascript object to a JSON string  you wanna save in to a database field, you have to save it using escape characters, otherwise it would be impossibile to use JSON.parse() later. This is a utility method you can use for that:

```javascript
var jsonString = utils.stringifyForDatabaseField(Object obj);
```

**Details**

| Argument | Description                  |
| -------- | ---------------------------- |
| obj      | javascript object to convert |

Example:

```
var obj = {
  text: "ABC"
};
var text = utils.stringifyForDatabaseField(obj);
// text is "{ \"text\": \"ABC\" }"
// and it can be saved into a database field and then used to be reconverted to a js object
```



## Invoking a server-side action from another one

When you need to invoke a second server-side js class, starting from a first server-side javascript action and pass forward some input data, you can use one of the following two methods, deferring only for the transaction management:

* **utils.executeActionSameTransaction(Long actionId,Map vo,Map params,Map headers)** - the invoked action inherits the same transaction, that is to say, if the first one has written data in the database and does not commit data yet, this data is visibile from the second action as well
* **utils.executeAction(Long actionId,Map vo,Map params,Map headers)** - the invoked action creates its own SQL transaction, which is independent from the one owned by the first action; pay attention in such a scenario: you cannot see data written by the first action not committed yet and you cannot update data written by the first action or this would leads to a database lock!

Example:

```javascript
var actionId = ...
var vo = {
  ...
};
var jsonResult = utils.executeActionSameTransaction(
  actionId,
  vo,
  {}, // params,
  {}  // headers
);

```

The action invocation is synchronous in both scenarios: the calling action suspends its execution until the called action terminates; moreover, in case of exceptions not managed by the called action, these exceptions will be propagated to the first action , which must be designed to manage them as well.



## Setting the company id in a server-side js action if not null

In case the company id has not been set yet, this method allows to set it.

```javascript
utils.setCompanyId(String companyId);
```

**Details**

| Argument  | Description                                                           |
| --------- | --------------------------------------------------------------------- |
| companyId | attribute name to set in the "vo" Platform is working on to save data |





## Force the company id in a server-side js action

This method set the company id in a server-side js action, independently of the fact the company id has been already set or not.

```javascript
utils.forceCompanyId(String companyId);
```

**Details**

| Argument  | Description                                                           |
| --------- | --------------------------------------------------------------------- |
| companyId | attribute name to set in the "vo" Platform is working on to save data |





## Force the site id in a server-side js action

This method set the site id in a server-side js action, independently of the fact the site id has been already set or not.

```javascript
utils.setSiteId(Long siteId);
```

**Details**

| Argument | Description                                                           |
| -------- | --------------------------------------------------------------------- |
| siteId   | attribute name to set in the "vo" Platform is working on to save data |



## Set a value to Redis cache

This method allows to cache a value to Redis server. In order to do it, you have first to setup correctly the Redis server connection, through the global parameters in the REDIS group.

**Syntax**:

```javascript
utils.setVaueInRedis(String key,Object value)
```

**Details**

| key   | entry in Redis cache |
| ----- | -------------------- |
| value |  value to cache      |

## Get a value from Redis cache

This method allows to retrieve a value previously cached in Redis server. In order to do it, you have first to setup correctly the Redis server connection, thorugh the global parameters in the REDIS group.

**Syntax**:

```javascript
var cachedValue = utils.getValueFromRedis(String key)
```

**Details**

| key            | entry in Redis cache |
| -------------- | -------------------- |
| returned value | the cached value     |



## Delete a value from Redis cache

This method allows to remove a value from the  Redis server. In order to do it, you have first to setup correctly the Redis server connection, thorugh the global parameters in the REDIS group.

**Syntax**:

```javascript
utils.deleteValueFromRedis(String key)
```

**Details**

<table data-header-hidden><thead><tr><th width="210">Argument</th><th>Description</th></tr></thead><tbody><tr><td>key</td><td>entry in Redis cache to remove</td></tr></tbody></table>

## Increment a numeric value from Redis cache

This method allows to increment by 1 a numeric value previously cached in Redis server. In order to do it, you have first to setup correctly the Redis server connection, thorugh the global parameters in the REDIS group.

**Syntax**:

```javascript
var cachedValue = utils.incrValueFromRedis(String key)
```

**Details**

| key            | entry in Redis cache              |
| -------------- | --------------------------------- |
| returned value | the cached value incremented by 1 |

## &#x20;

## Decrement a numeric value from Redis cache

This method allows to decrement a numeric value previously cached in Redis server. In order to do it, you have first to setup correctly the Redis server connection, thorugh the global parameters in the REDIS group.

**Syntax**:

```javascript
var cachedValue = utils.decrValueFromRedis(String key)
```

**Details**

| key            | entry in Redis cache              |
| -------------- | --------------------------------- |
| returned value | the cached value decremented by 1 |

## Push a list of string values  to Redis cache

This method allows to push for an entry a list of values, cached in Redis server. In order to do it, you have first to setup correctly the Redis server connection, thorugh the global parameters in the REDIS group.

**Syntax**:

```javascript
var cachedValue = utils.pushValuesToRedis(String key,String[] values)
```

**Details**

| key    | entry in Redis cache      |
| ------ | ------------------------- |
| values | an array of String values |

&#x20;&#x20;

## Pop a value from an enrty containing a list of values from Redis cache

This method pop the first element of a lis of String values previously cached in Redis server for a specific entry. In order to do it, you have first to setup correctly the Redis server connection, thorugh the global parameters in the REDIS group.

**Syntax**:

```javascript
var cachedValue = utils.popValueFromRedis(String key)
```

**Details**

| key            | entry in Redis cache                                          |
| -------------- | ------------------------------------------------------------- |
| returned value | the first element of a lis of String values previously cached |

## &#x20;

## &#x20;

##

##
