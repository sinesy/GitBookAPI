# Others

## NAVIGATIONS:

## openWindowXXX\(args\)

where XXX is the window identifier \(CON08\) - open the specified window

## openWindowXXX\(args, settings\)

same of previous method with one more param "settings" to give the windows additional settings.  
Possible settings parameters:

* **asMainWindow**: boolean value to open the window as the first window in the window stack. It is like to open a window from main menu; _\(Since 5.2.3 version\)_
* **anchoredToPanel** and **anchoredToAttribute**: Display the modal window in a popup window anchored to the bottom-left corner of the anchor view. If there is not enough room on screen to show the popup in its entirety, this method tries to find a parent scroll view to scroll. If no parent scroll view can be scrolled, the bottom-left corner of the popup is pinned at the top left corner of the anchor view. Works only with modal window. _\(Since 6.0.1 version\)_
* **anchoredGravity**: only works on Android, preferred window anchor position, available values are: TOP,BOTTOM,LEFT,RIGHT or a combination of them separated by a pipe. Ex: BOTTOM\|RIGHT anchor the window to the bottom-right corner. Default value is BOTTOM\|LEFT. _\(Since 6.0.1 version\)_
* **preferredOpenDirection**: only works on iOs, preferred window position relative to anchored attribute. Available values are:UP,DOWN,LEFT,RIGHT. _\(Since 6.0.1 version\)_

```javascript
var settings = new Object();
settings.asMainWindow = 'Y';
settings.anchoredToPanel = 129;
setting.anchoredToAttribute = 'myBtn';

openWindow123(args, settings);
```

## openFirstWindow\(\)

Opens the first window if set, otherwise the about window.

## closeWindow\(\)

Close current visible window and move back to the previous one.

## setWindowTitle\(title\);

Change the title of the window currently shown.  
Required arguments:

| Argument | Description |
| :--- | :--- |
| title | the title to set in the currently shown window |

## getWindowId**\(\)**

Get the current window id.

## getPanelId**\(\)**

Get the current panel id, null if the panel is not available \(for example in a window event\).

## WORKS WITH ACTION:

## executeAction\(actionId, params\)

execute the specified Actionand returns the result.  
actionId: a String with the id of the action to execute;  
params: an object with params to use in the action to execute. These params are accessible in the action to execute by vo.xxx or vo\['xxx'\]

**Example**

```javascript
var myArgs = {};
myArgs.title = "This is the title";
myArgs.message = "This is the message";
executeAction("123", myArgs);

------
on the action with id 123:

var message = {};
message.title = vo.title;
message.subtitle = vo.message;
message.titleButtonSuccess = "bye";

showMessageDialog(message, null);
```

## **executeServerAction\(actionId, params\)**

execute the specified Server Side Action and returns the result.

| Argument | Description |
| :--- | :--- |
| actionId | a String with the id of the action to execute |
| params | an object with params to use in the action to execute. These params are accessible in the action to execute by vo.xxx or vo\[‘xxx’\] |

Example:

```javascript
var params = {};
params.title = "This is the title";
params.message = "This is the message";
String jsonRet = executeServerAction(123, params);
The code above corresponds to do this:
String url = getBaseURL() + "/executeJs?applicationId=APPLICATION_ID&appId=APPLICATION_ID&actionId=123&restfulToken=" + getToken(); 
var params = {};
params.title = "This is the title";
params.message = "This is the message";
String jsonPars = convertToObjectJson(params);
String jsonRet = getWebContent(url, "POST", "application/json", jsonPars);
```

## asyncFunction\(jsCallback, paramArray, timeout\)

Call the function passed in jsCallback with params specified in paramArray.

| Argument | Description |
| :--- | :--- |
| jsCallback | Name of function to call asynchronous |
| paramArray | \(Optional\) Array of param to pass to the asyc function |
| timeout | \(Optional\) Wait this millisec. before call callback |

```javascript
function asyncCallback(param1, param2){
    for (var i = 0; i < param1; i++) {
        log("Test: " + i + " " + param2);
    }
}
asyncFunction("asyncCallback", [5,"Red"]);

//logs:
//Test 1 Red
//Test 2 Red
//Test 3 Red
//Test 4 Red
//Test 5 Red
```

## convertToListJson\(list\)

Convert a javascript list returned by the executeQuery method to a JSON string having format: \[{....},{...},...\]

**Example**

```javascript
var listResponse = getPartialResult(
  "SELECT ...",  
  "DBRW", 
  true, 
  []
);
var json = convertToListJson(listResponse.rows);
var res = '{ "moreRows": false, "valueObjectList": '+json+' }';
return res;
```

## convertToListResponseJson\(list,length,moreRows\)

Convert a javascript list returned by the executeQuery method to a JSON string having format: { moreRows: ..., valueObjectList: \[{....},{...},...\] }

**Example**

```javascript
var listResponse = getPartialResult(
  "SELECT ...", 
  "DBRW", 
  true, 
  []
);
var json = convertToListResponseJson(listResponse.rows,listResponse.rows.length,listResponse.moreRows);
return json;
```

## convertToObjectJson\(list,length,moreRows\)

Convert a javascript object contained in the list returned by the executeQuery method to a JSON string corresponding to that object.

**Example**

```javascript
var listResponse = executeQuery(
  "SELECT ...", 
  "DBRW", 
  true, 
  []
);
var json = convertToObjectJson( list[0] );
return json;
```

## MENU, LOGIN AND SYNC:

## sync\(\)

start the synchronization task

## **syncSqlInstruction\(\)**

Send to server the sql instractions of data modified. This operation not is a total sync.

## changeCredentials\(username, password\)

replace the current account with the one specified through "saveCredentials" method and use it by now

## saveCredentials\(username, password\)

save the specified username and password in a permanent area

## logout\(\)

Logout the current user and show the login form \(if login in enable\).

> Since 5.3.2 version

## filterUserRoles\(roles\)

Enable only the passed roles, if you want filter the menu leaves you have to call also restartApp\('N'\) method.

| Argument | Description |
| :--- | :--- |
| roles | An array of roles to filter |

```javascript
var allRoles = userInfo.userRolesIds;
if(userRolesIds.indexOf("9") > -1){
    filterUserRoles(["9"]); //filter only the role 9
    restartApp('N'); //restart the app without do sync
}
```

## clearInitialWindow\(\)

remove the start window.

## setMenuType\(menuType\)

change the menu type used by the app

## changeUser\(value\)

change the username associated to the app

## setDrawerIcon\(path**\)**

Set the icon on the app drawer.

| Argument | Description |
| :--- | :--- |
| imagePath | path of the icon image |

Example:

```javascript
setDrawerIcon("newIcon1.png");
setDrawerIcon("/newFolder/newIcon2.png");
setDrawerIcon(""); //to remove the icon
```

## setDrawerDescriptionRow1\(text, color**\)**

Set the text on the first row on the drawer.  
setDrawerDescriptionRow**2**\(text\) and setDrawerDescriptionRow**3**\(text\) are the same.

| Argument | Description |
| :--- | :--- |
| text | text to set |
| color | optional, the text color |

Example:

```javascript
setDrawerDescriptionRow1("Lorem ipsum"); //set the first row
setDrawerDescriptionRow2("Lorem ipsum 2", "FF0000"); //set the second row red
setDrawerDescriptionRow3("Lorem ipsum 3"); //set the third row
```

## setTopbarRightDescription\(description\)

If menu provide a description in the topbar, update the description.

| Argument | Description |
| :--- | :--- |
| description | button id |

## setTopbarRightCharacter\(charcter, backcolor, forecolor\)

If menu provide a user-char icon update it.

| Argument | Description |
| :--- | :--- |
| charcater | charcater to show in the icon |
| backcolor | icon back color |
| forecolor | icon fore color |

> Since 6.0.1 version

## GENERIC PANEL:

## getPanelParameter\(name\)

Get a parameter value passed to the current panel \(trough the window args variable\).  
Required parameters are:

| Parameter | Description |
| :--- | :--- |
| name-parameter | name |

**Example**

```javascript
//From the window "A" I open the window "B"

//Window A
var args = {
    param1: "MyCustomParam"
};

//...
//Window B
getPanelParameter('param1');   //Output: "MyCustomParam"
```

## panelScreenshot\(panelid\);

Generate an image of the panel shown in the app, identified by idPanel and save it in the local file system. The method gets back the absolute path + image name for the just generated screenshot.

Required arguments:

| Argument | Description |
| :--- | :--- |
| id | identifier of the panel to capture |

**return** the absolute path + image name for the just generated screenshot.

## QUEUE:

Uses the following methods to add or remove items in a queue, the queue is accessible in all client side JS.

These methods are very useful when working with asynchronous and callback methods.

## atomicEnqueue\(String queueName, Object object\)

Atomically adds an item to the queue, returns the number of items in the queue

> Since 6.0.1 version

## atomicDequeue\(String queueName\)

Remove the first item from the queue and return it

> Since 6.0.1 version

## atomicQueueTop\(String queueName\)

Return the first element of the queue without removing it

> Since 6.0.1 version

## atomicQueueClear\(String queueName\)

Empty the queue.

> Since 6.0.1 version

## DATE AND TIME:

## addDate\(timeInMillis,format,amount\)

Return an internal string representation of the current date \(with "yyyy-MM-dd HH:mm:ss" format\) plus an amount which can be specified with different formats, that can be used when creating javascript objects to insert/update and you need to pass a date.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| timeInMillis | number of milliseconds. |
| format | string having one of these values: "DAY", "MONTH", "YEAR", "HOUR", "MINUTE", "SECOND"; it can be null, if not null then also the "amount" parameter is required |
| amount | number of days/months/... to add to the current date/time |

**Example**

```javascript
var s = getCurrentDate();
log("Current date with format yyyy-MM-dd "+s);

s = getCurrentDateAndTime();
log("Current Date with format yyyy-MM-dd HH:mm:ss "+s);

var dt = new Date();
var l = dt.getTime();
s = addDate(l);
log("Current date with format yyyy-MM-dd HH:mm:ss "+s);

s = addDate(l,"DAY",1);
log("Current date + 1 day with format yyyy-MM-dd HH:mm:ss "+s);
```

## getCurrentDate\(\);

Return the current date in string with format yyyy-MM-dd. Use the device time zone.

## getCurrentDateAndTime\(\);

Return the current date and time in string with format yyyy-MM-dd. Use the device time zone.

## getCurrentDateGMT\(\);

Return the current date in string with format yyyy-MM-dd. Use GMT time zone.

> Since 5.3.1 version

## getCurrentDateAndTimeGMT\(\);

Return the current date and time in string with format yyyy-MM-dd. Use the GMT time zone.

## parseDate\(dateString, format, inputGMT\);

Parse the passed string with the passed format and returns the timestamp.

| Argument | Description |
| :--- | :--- |
| dateString | A date in string format |
| format | The string date format use to parse the string |
| inputGMT | true if the passed string is GMT, else use the device timezone |

```javascript
var timestamp = parseDate("2019-01-01 12:30:00", "yyyy-MM-dd HH:mm:ss", true); //return 1546342200000
var jsDate = new Date(timestamp);
```

> Since 6.0.1 version

## stringifyDate\(dateTS, format, outputGMT\)

Convert the passed timestamp with the passed string format and return it

| Argument | Description |
| :--- | :--- |
| dateTS | A timestamp \(long |
| format | The string date format use to parse the string |
| outputGMT | true if you want convert the TS using the device timezone |

```javascript
var timestamp = 1546342200000;
var stringDate = stringifyDate(timestamp, "yyyy-MM-dd HH:mm:ss", true); //return "2019-01-01 12:30:00"
```

> Since 6.0.1 version

## OTHERS:

## logger\(logMessage\) or log\(logMessage\) <a id="logger"></a>

Log a message in the internal app console, in order to see it in the Log Panel.

Note: There is also the "log" standard javascript method, used to log on the app console, but in this case, the messages will not be visible in the Log Panel.

## reloadPreviewPanelXXX\(args\)

where XXX is the previewidentifier \(CON12\) - reload the content of thepreview panel

```javascript
var args = new Object();
args['INPUT_PARAM'] = 'EXAMPLE';

reloadPreviewPanel603(args);
```

## reloadChartPanel\(panelId, args\)

where panelId is the previewidentifier \(CON12\) - reload the content of thepreview panel

```javascript
var args = new Object();
args['INPUT_PARAM'] = 'EXAMPLE';

reloadPreviewPanel603(args);
```

Note that you won't find the _args_ in the server side VO \(since the server call is made through a GET request, hence no request body is present\). You can find the arguments as parameters in the _reqHeaders.referer_.

For simplicity, here is a snippet to copy the parameters in the VO.

```javascript
//Splits the ? and only considers the parameters (after ?)
var tmp = reqHeaders.referer.split('?')[1];

//Splits the & to separate all the parameters, then cycles the array and separates the name from the value
tmp = tmp.split("&").map(function(tmp){ return tmp.split("=")});

//Cycles the parameters and pushes each value inside the vo, under the same name
for(var i = 0; i < tmp.length; i++){
    vo[tmp[i][0]] = tmp[i][1];
}
```

## **reloadMapPanel\(\)**

where XXX is the form identifier \(CON12\) – reload the form content

```javascript
var args = new Object();
args['INPUT_PARAM'] = 'EXAMPLE';
reloadMapPanel603(args);
```

## loadHTMLOnPreviewPanelXXX\(html\)

where XXX is the previewidentifier \(CON12\) - load the htmlin the preview panel

```javascript
var html = "&lt;html&gt;&lt;body&gt;.....&lt;/body&gt;&lt;/html&gt;"

loadHTMLOnPreviewPanel603(html);
```

## showCardPanel\(cardPanelid, panelid\)

Switches from a card to another inside a cardPanel.  
Required parameters are:

| Parameter | Description |
| :--- | :--- |
| cardPanelid | The ID of the cardPanel \(parent panel\) |
| panelid | The ID of the card to focus \(child panel\) |

## **openUrl\(url\)**

Open the browser whith url

## vibrate\(pattern**\)**

Vibrate with a given pattern.  
Pass in an array of longs that are the durations for which to turn on or off the vibrator in milliseconds. The **first** value indicates the number of milliseconds for which to keep the vibrator **on** before turning it off. Subsequent values alternate between durations in milliseconds to turn the vibrator off or to turn the vibrator on.

NOTE: the pattern only works in Android device

| Argument | Description |
| :--- | :--- |
| pattern | optional, an array of longs of times for which to turn the vibrator on or off. |

Example:

```javascript
var sosPattern = [100,30,100,30,100,200,200,30,200,30,200,200,100,30,100,30,100];
vibrate(sosPattern);
```

## getTranslation\(key**\)**

Returns the translated string corresponding to the key.

| Argument | Description |
| :--- | :--- |
| key | key for the message |

Example:

```javascript
getTranslation("hello_world");

returns:
Hello World
```

## formatNumber\(number, format\)

Returns the text formatted in the given format and use the language of the logged in user.

| Argument | Description |
| :--- | :--- |
| number | The number to format |
| format | The format like \#,\#\#0.\#\# |

```javascript
var format = "#,##0.##";
var value1 = 1234.3;
var ret = formatNumber(value1, format)  //return 1'234,4
```

## setWindowButtonSelected\(buttonId, selected\)

Select the window button with the specified Id.

| Argument | Description |
| :--- | :--- |
| buttonId | button id |
| selected | Y/N for select or unselect |

## POSRequestPayments\(host, port, keepSocketOpen, requestImport, printOnPOS, successCallback, errorCallback\)

Select the window button with the specified Id.

| Argument | Description |
| :--- | :--- |
| host | POS ip |
| port | POS port |
| keepSocketOpen | if true keep socket open |
| requestImport | import to pay |
| printOnPOS | if true print the receipt on POS |
| successCallback | Name of function to call on success, if printOnPOS is false the first parameter is the ticket string |
| errorCallback | Name of function to call on error |

> Since 6.0.1 version

## btoa\(String stringToEncode\)

Creates a base-64 encoded ASCII string from a binary string.

> Since 6.0.1 version

## atob\(String stringToDecode\)

> Since 6.0.1 version

Decodes a string of data which has been encoded using base-64 encoding.

## encodePassword\(password\)

> Since 6.0.1 version

Encrypt the passed password using PBE algorithm

## decodePassword\(password\)

> Since 6.0.1 version

Decrypt the passed password using PBE algorithm

##  sendAnalyticsEvent\(category, action, label\)

> Since 6.0.1 version

Log an event to Google Analytics

## playSound\(fileName\)

> Since 5.3.2 verion

Play the sound with the fileName passed. The file must me stored in the  mobile app context in the subfolder "sounds".

