# Variables and parameters

## getVariable\(varName**\)**

Get a value stored in the **predefined variables**, automatically set by Platform, when the user logs on; value is fetched starting from the varName identifier

| Argument | Description |
| :--- | :--- |
| varName | variable identifier |

Example:

```javascript
var languageId = getVariable("LANGUAGE_ID");
var languageId = getVariable("languageId");
```

## getAppParameter\(name\)

Get a parameter value defined at application level, through the Web Designer in the Application Parameter folder of the App detail window.  
Required parameters are:

| Parameter | Description |
| :--- | :--- |
| name-parameter | name |

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

## getBaseURL\(\)

Fetch the base URL used by the app to connect to Platform's server side installation. This method is tipically used by getWebContent method.

## getCurrentDate\(\)

Return an internal string representation of the current date \(with "yyyy-MM-dd" format\), that can be used when creating javascript objects to insert/update and you need to pass a date.

## getCurrentDateAndTime\(\)

Return an internal string representation of the current date \(with "yyyy-MM-dd HH:mm:ss" format\), that can be used when creating javascript objects to insert/update and you need to pass a date.

## getGPSLongitude\(\)

returns the longitude GPS coordinate, expressed as a string

## getGPSLatitude\(\)

returns the latitudine GPS coordinate, expressed as a string

## getUsername\(\)

get the current user id

## getApplicationId\(\)

get the current applicationid

## getToken\(\)

get the authentication token, which can be used in case you need to invoke Platform web services; the parameter to include in the URL is: "&restfulToken="+getToken\(\)

Note: It is strongly recommended to pass a String value, not a complex object, to ensure compatibility between Android and iOS apps

## getUUID**\(\)**

Return random UUID \(UNIQUEIDENTIFIER\) string.

## STORE VARIABLES:

## setUserSessionVariable\(varName,varValue, log\)

store temporarelly a value in the user mobile session; value is referred by the varName

> log is an optional parameter available from versione 6.0.2, if true log the variable, default il false.

## getUserSessionVariable\(varName, log\)

get a value previously stored in the user mobile session; value is fetched starting from the varName identifier

> log is an optional parameter available from versione 6.0.2, if true log the variable, default il false.

## **setUserAppCustomVariable\(varNames,varValues\)**

store temporarily a value in the user mobile and server session; value is referred by the varName  
varNames and varValues can be a list of comma separated strings

```javascript
var valueOfVarName = setUserAppCustomVariable('varName', 'value');
setUserAppCustomVariable('varName1,varName2,varName3', 'value1,value2,value3');
```

## **getUserAppCustomVariable\(varName\)**

get a value previously stored in the user mobile and server session; value is fetched starting from the varName identifier

```javascript
var valueOfVarName = getUserAppCustomVariable(varName);
logger('valueOfVarName: ' + valueOfVarName);
```

## **setLocalPersistentVariable\(varName, varValue\)**

Store a value in the user mobile; value is referred by the varName  
varValue can be an Object

| Argument | Description |
| :--- | :--- |
| varName | variable name to set |
| varValue | Object to set on the variable |

Example:

```javascript
var value1 = {"field1":"value for field 1", "field2": 2};
var value2 = "value 2";
setLocalPersistentVariable("varName1", value1);
setLocalPersistentVariable("varName2", value2);
```

## g**etLocalPersistentVariable\(varName\)**

Get a value in the user mobile; value is referred by the varName  
varName can be an Object

| Argument | Description |
| :--- | :--- |
| varName | variable name to set |

Example:

```javascript
var value1 = getLocalPersistentVariable("varName1");
var value2 = getLocalPersistentVariable("varName2");

var opts = new Object();
opts['title'] = "Local Variables";
opts['subtitle'] = 'varName1: field1='+value1.field1+"\n    field2="+value1.field2+"\n"+
                   'varName2: '+value2;
opts['titleButtonSuccess'] = 'Ok';
var fun1 = function() { };
showMessageDialog(opts,"fun1");
```

## getAllUserSessionKeys\(\)

Return an array with all key in user session.

