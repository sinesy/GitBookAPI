# Inside a mobile Javascript action

Every time an event fired within the app must be captured to perform something, an action must be defined an linked to the event. Basically, this is what the Web Designer allows to define. An action is expressed as a set of Javascript instructions.

This language has been setchosen because it can be interpreted by both the platforms: iOS and Android, so you can define once the application and use it on any platform, thanks to the portability of Javascript.  
reload  
Platform provides a series of utility methods you can incllude in your Javascript scriptlets, described below.

Independently of the javascript code you'll include in your actions, bear in mind that the javascript code must be interpreted on the embedded js interpreter for iOS and Android. These interpreters are not as good as the ones available for desktop computers.  
showm  
There are a view limitations you have to take into account when writing javascript code:

| **Do not use** | **Correct solution** |
| :--- | :--- |
| if \(variable\) | if \(variable!=null\) |
| var1===var2 | var1==var2 |
| var1!==var2 | var1!=var2 |
| eval\(jsonString\) | JSON.parse\(jsonString\) //jsonString must be !=null and !="" |
| var a = b \|\| c | var a = b!=null?b:c; |
| _replace a char_  var newStr = str.replace\(/-/g,""\) | var oRegExp = new RegExp\("-","g"\);  var newStr = str.replace\(oRegExp, ""\); |

Independently of the type of component embedding the Javascript \(a mobile action or a business component\), a few **predefined objects** are always available:

* **vo**
  * the javascript representation of the json string passed through the Ajax request
* **optionalParams**
  * passed as input parameters from the component invoking the action

Moreover, some of the buit-in mobile javascript methods are related to SQL instructions. For those functions, Platform allows to specify SQL instructions including **binding variables**. These binding variables are always defined using the notation:

:XXX

where XXX is the variable name, always in upper case.

These variables will be automatically replaced by the corresponding values available at user session level.

The user session is composed of a set of variables:

* **predefined variables**, automatically set by Platform, when the user starts the app
* **custom variables**, defined using the **setUserSessionVariable** mobile javascript method
* **input parameters**, passed to the business component/javascript

The predefined variables are:

| Variable name |
| :--- |


|  | Description |
| :--- | :--- |
| :APPLICATION\_ID | application identifier |
|  | :BASE\_URL -server base url |
| :COMPANY\_ID | company identifier \(used in case the app supports partitioned data\) |
| :SITE\_ID | site identifier |
| :USERNAME | current user |
| :USERDESC | current user description |
| :UUID or :DEVICE\_ID | device id, i.e. a unique identifier for a specific device \(more specific than the username\) |
| :LANGUAGE\_ID | current user |
| :DOCUMENTS\_DIR | absolute path within the mobile device, where files are stored;it is a folder inside the “customFiles” default app folder. |
| :TODAY | current date |
| :NOW | current date+time |
| :YEAR | current year |
| :GPS\_LATITUDE | current latitude |
| :GPS\_LONGITUDE | current longitude |
| :GPS\_ALTITUDE | currentaltitude |
| :GPS\_SPEED | currentspeed |
| :APP\_VERSION | current app versione |
| :LAST\_SYNC\_DATE | last sync date |

