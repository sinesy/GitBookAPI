# Global methods and UI API

## GLOBAL METHODS

4WS.Platform provides a series a global javascript methods, which can be referred on any other part of the client-side application.

These methods can be grouped according to the usage in the following categories.

### UI methods

**reloadApplication(reloadAuthorizations)** - reloadAuthorizations: boolean value, used to force the web page reloading; if the passed argument is set to true, then the user authorizations are reloaded as well.

**closeAll(promptWarn)** - close the web application; if the passed argument is set to true, then a window dialog is shown, in order to prompt the user whether closing the web app or canceling that operation.

**openPage(url,windowName,opts,openPopup,encodeUrl)** - show a web resource (like a web page, a remote PDF, a remote image, etc), starting from its URL; set a name to assign to the browser window to open. the "opts" argument is a set of optional arguments to pass to the window.open() method behind the scenes; finally, the boolean "openPopup" argument defines if the web resource must be shown on an external web page or within the current web app.

**changeUser(companyId,siteId,username,password,successCallback**) - change current logged user, after authenticating him. This method will authenticate the user first, then check out if the previous user had the same user par values and roles and, in such a case, just change the username in session.

On the client side, the following global variables will be changed:

* username
* password
* userDescription
* userImageUrl

Moreover, if a successCallback js function has been defined, it will be automatically invoked, after a successful authentication.

**changeUserDialog(successCallback)** - Show an input dialog in order to change user, after authenticating him. This method will authenticate the user first, then check out if the previous user had the same user par values and roles and, in such a case, just change the username in session.

On the client side, the following global variables will be changed:

* username
* password
* userDescription
* userImageUrl

Moreover, if a successCallback js function has been defined, it will be automatically invoked, after a successful authentication.

**showInputDialog3(title,message,okFun,modal,cancelFun,inputValue,winWidth,winHeight,closable)**

Show an input dialog having "ok"and "cancel" button.

* title window title
* message message to show within the window
* okFun callback function to invoke when user has pressed "ok" button
* modal flag used to set this window as a modal window (optional)
* inputValue optional value to set in

**showMoreInputDialog(title, labels, attributes, okFun, modal, cancelFun, defaultAttributesValue)**

Show an input dialog highly customizable, in terms of number of labels/input fields to show.

It contains also an "ok" and "cancel" button.

* title - window title
* labels - javascript arrays containing a list of Strings, i.e. messages to show within the window, one below the other; each line contains a label + input field
* attributes -  javascript arrays containing a list of Strings, i.e. attribute names, each representing an input field to show; the 2 arrays must have the same length: each line contains a label + input field, where an input field is identified by its attribute name
* okFun - callback function to invoke when user has pressed "ok" button
* modal - flag used to set this window as a modal window (optional)
* defaultAttributesVaulues - optional javascript array, having the same length of labels/attributes and containing the default value for each attribute, reported positionally;

**setFieldValueByItemId(win,formItemId,name,value)**

Set a value into the specified field.

* win window reference
* formItemId FormPanel or FilterPanel identifier (e.g. formPanel123 or filterPanel123)
* name attribute name that identifies the required field
* value value to set

**getFieldValueByItemId(win,formItemId,name)**

Get a value into the specified field.

* win window reference
* formItemId FormPanel or FilterPanel identifier (e.g. formPanel123 or filterPanel123)
* name attribute name that identifies the required field

**showListDialog(title,width,height,codes,descriptions,callback,multipleSelection,closable,closeCallback)**

Show a list of items and allow user to choose one of them. When choosing a value from list, the callback function will be invoked.

* callback function must have the following arguments: codes (list of selected codes)

**drawChartXXX();**

Reload the content of the chart panel identified by the panel id xxx.

**gridxxx.store.reload();**

Reload grid content, where xxx represents the panel id for the grid.

**gridxxx.store.baseParams.myAttribute = "value";**

Pass forward a filter condition to a grid which is required by the bound business component. That means the business component has been configured so that the WHERE condition must contain the corresponding database field for "myAttribute", i.e. something like:

... WHERE MY\_FIELD = :MY\_ATTRIBUTE

For such example, the parameter to pass forward through "baseParams" is its camel form value: myAttribute.

xxx represents the panel id for the grid.

Bear in mind that you also need to force grid loading to apply such filtering parameter and get new grid content.

**formPanelxxx.reload();**

Reload form panel content, where xxx represents the panel id for the form panel.

**var obj = formPanelxxx.pull();**

Get form panel content: copy values showed in input controls to the record in FormPanel.getForm().record (Form's model) and get back the result (the javascript object).

xxx represents the panel id for the form panel.

**setFormValues(formPanelxxx,vo,'');**

Set the content of a form panel, starting from a javascript object.

xxx represents the panel id for the form panel, whereas vo is the javascript object to use to set the form content.

**formPanelxxx.forceClose = true;**

Force a form panel closing, without prompting any message dialog, when the user press on the close button (X) and the form is in insert/edit mode.

xxx represents the panel id for the form panel.

**lookupComponent.setValue(code);**

**lookupComponent.validateCode();**

Force a lookup validation, starting from the specified code ("code" argument), where "lookupComponent" represents the js component for the lookup.

This validation force automatically any event bound to the lookup (before validation, after validation, etc.)

**showToast({title: "common.warning", message: "data changed", sleep: 3, css: "..." ]);**

Show a toast message on the top part of the application. Mandatory attribute is "message".

Optionally, you can include a custom CSS class name through the "css" attribute.

### Network methods

Through the following methods, it is possible to contact the server-side layer and send/receive data, through REST web service invocation.

**function callAction(config)** - Invoke a server-side js action with a synchronous HTTP request. The argument is a js object having this format:

> ```javascript
> { 
>   actionId: xyz, // identifier of the server-side action to invoke
>   httpMethod: "GET|POST", // optional argument; allowed values: GET|POST. Default value: POST
>   params: { ... }, // js optional argument; object containing additional parameters to add to the http request; can be null
>   obj: { ... } // optional argument; js object to send to the action; can be null
> }
> ```

This method returns an HTTP response, expressed as a javascript object

It is strongly recommended to use the method below and not the current one, since in a web application, requests should be asynchronous, so that there are not frozen windows.



**callAsyncAction(config)** - Invoke a server-side js action with an asynchronous HTTP request. The argument is a js object having this format:

```javascript
{ 
  actionId: xyz, // identifier of the server-side action to invoke
  httpMethod: "GET|POST", // optional argument; allowed values: GET|POST. Default value: POST
  params: { ... }, // js optional argument; object containing additional parameters to add to the http request; can be null
  obj: { ... }, // optional argument; js object to send to the action; can be null
  callback: function(json){}, // json is a text formatted content
  callbackError: function(json,status) {} // json is a text formatted content related to the error, status the HTTP error code (a number), e.g. 401
}
```

Example when sending a complex content (e.g. multiple data) to a server-side javascript action:

```javascript
var myComplexObject = {
  attr1: "...",
  attr2: ...
};

callAsyncAction({
  actionId: 1,
  httpMethod: "POST",
  params: { applicationId: "MY_APP }, // usually, complex data should be sent through "obj" attribute and NOT the current one
  obj: myComplexObject,
  callback: function(json) {
    var res = JSON.parse(json); // server-side response, in case the request has been sent successfully
    //...
  },
  callback: function(json,status) {
    var res = JSON.parse(json); // server-side response, in case the request was wrong
    //...
  }
});
```

****

**getCustomApplUserVar(varName)** - get from the server-side layer a user variable, identified by the specified argument.

**getVariable(varName**) - get from the server-side layer a generic variable, identified by the specified argument.

**uploadFile(title,enabled,fileName,dirId,beforeUploadCallback,afterUploadCallback,errorOnUploadCallback,additionalSettings)**

This method can be invoked by any web client-side js action: it shows a popup window containing a readonly input field + button to select a local file and upload it on the server-side.

* title; can be null, in that case, a default title is shown
* enabled true: upload button is enabled, false: upload button is disabled
* fileName file name to set in the input field; if it is not empty, then a "Download" and "Preview" buttons are shown too
* dirId directory id on the server side where saving the file to upload
* beforeUploadCallback callback function invoked just before the uploading; format: function({ filename: "..." }) { return true|false }; false can block the uploading. You can change the file name by working on the argument
* afterUploadCallback callback function invoked after the uploading; format: function({ fileName: "....", success: true|false, message: "..." }). The popup window is automatically closed just before this callback is invoked
* errorOnUploadCallback callback function invoked in case of errors on uploading; format: function({ error: "..." }). The popup window is automatically closed just before this callback is invoke\*/
* additionalSettings: optional argument: can be omitted; it contains a javascript object having the following attributes: { encriptAttachments: true|false, panelId: ... }

**function beep(audioFileName,volume)**

This method execute a sound, a beep if an audioFileName has not been specified.

Arguments:

* audioFileName; can be null; if not specified, a default beep sound will be played; if specified, the file must be a file having format mp3/wav (this not supported on IE) which must be stored into the web app subcontext
* volume; can be null; if not specified it is assumed to be 1.0 (max volume); if specified, must be a float value in the range 0.0-1.0

**function beepOK(volume)**

This method execute a beep related to something went well.

Arguments:

* volume; can be null; if not specified it is assumed to be 1.0 (max volume); if specified, must be a float value in the range 0.0-1.0

**function beepKO(volume)**

This method execute a beep related to something went wrong.

Arguments:

* volume; can be null; if not specified it is assumed to be 1.0 (max volume); if specified, must be a float value in the range 0.0-1.0

**function redAlert(volume)**

This method execute a sound, related to an error event.

Arguments:

* volume; can be null; if not specified it is assumed to be 1.0 (max volume); if specified, must be a float value in the range 0.0-1.0

**function interconn(volume)**

This method execute a sound, related to a message incoming event.

Arguments:

* volume; can be null; if not specified it is assumed to be 1.0 (max volume); if specified, must be a float value in the range 0.0-1.0

****

**Checking threads**

[https://host/platformwebcontext\*\*/processQueues/checkMainNode?appId=...\&queueName=....\*\*](https://host/platformwebcontext\*\*/processQueues/checkMainNode?appId=...\&queueName=....\*\*)

This is not a javascript method available on the web tier: it is a web service which can be invoked from the web tier.

This request can be invoked by a client to force the Queue Manager on the server side to check immediately for new elements in queue. This method is helpful in case of a Platform installation including a cluster of nodes, where one of these nodes is enrolled to be the "main node", .i.e. the node that executes all elements in queues. The main node would control for new elements in queue every 2 minutes. When calling the web service above, the check will be performed immediately.

****

**Camel-case**

camel(name, firstCharUpper)

Convert a database field or an upper-case parameter containing underscores (\_) to the camel case format, i.e. lowercase and the underscore remove and next character to uppercase.

Example:

var x = camel("ABC\_DEF",false); -> x = "abcDef"

var x = camel("ABC\_DEF",true); -> x = "AbcDef"

****

**Snake-case**

camelToSnake(name, toUpperCase)

Convert a camel case string to snake case, i.e a string expressed in lowercase with an underscore (\_) separating each uppercase character in the original string.

Example:

var x = camelToSnake("abcDEF",false); -> x = "abc\__d\_e\__f"

var x = camelToSnake("abcDEF",true); -> x = "ABC\__D\_E\__F"

****

## ExtJS API 3.4

4WS.Platform User Interface is based on ExtJS 3.4 graphics components.

The whole API about this suite can be found in Sencha web site:

[http://docs.sencha.com/extjs/3.4.0/](http://docs.sencha.com/extjs/3.4.0/)

Apart from that, Platform components can be referrred always using the following notation:

| Variable name        | Description                                            |
| -------------------- | ------------------------------------------------------ |
| gridPanelXXX         | grid panels                                            |
| formPanelXXX         | form panels                                            |
| filterPanelXXX       | filter panel for a grid                                |
| treePanelXXX         | tree panels                                            |
| mapPanelXXX          | google map panel                                       |
| imagePanelXXX        | document preview panel (e.g. image, PDF, etc.)         |
| imageGalleryPanelXXX | image gallery panel                                    |
| chartPanelXXX        | google chart panel                                     |
| wizardPanelXXX       | wizard panel (sequence of alternative panels)          |
| pivotXXX             | pivot panel (dynamic number of columns)                |
| chatPanelXXX         | chat panel (for web+mobile apps only, based on Signal) |
