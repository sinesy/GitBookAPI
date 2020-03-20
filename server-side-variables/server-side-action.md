# Inside a server-side Javascript action

Platform makes it possible to create a complex program, through a Javascript action. This program can be executed on the server side.

This program can exploit a series a predefined functions and variables, including database access functions; the whole call to this action is transactional, so that all the SQL instructions executed within this action are related to the same SQL transaction: in case of an error, the whole transaction will be rollbacked.

Server-side Javascript can be embedded within either a server-side Javascript action or in a server-side Javascript business component.

In this way, the action can be binded to a client-side or server-side event, in order to perform complex business logic when a specific event occurs.

Moreover, a list or a tree or a detail form could be fed through a server-side Javascript business component, in case of a very complex data retrieval logic.

When executing the javascript action, it has access to some predefined variables and methods, described below.

Independently of the type of component embedding the server-side Javascript \(an action or a business component\), a few **predefined objects** are always available:

* **vo**
  * the javascript representation of the json string passed through the Ajax request
* **reqParams**
  * a map of related to all request parameters
* **userInfo**
  * a map of , related to the UserInfo java object; e.g.

    **username**

    , languageId, companyId, etc

Moreover, some of the buit-in sever-side javascript methods are related to SQL instructions. For those functions, Platform allows to specify SQL instructions including **binding variables**. These binding variables are always defined using the notation:

:XXX

where XXX is the variable name, always in upper case.

These variables will be automatically replaced by the corresponding values available at user session level.

The user session is composed of a set of variables:

* **predefined variables**, automatically set by Platform, when the user logs on \(see above\)
* **custom variables**, defined using the addCustomApplUserVars server-side javascript method
* **input parameters**, passed to the business component/javascript, defined in the business component definition window \(input pars subfolder\) or passed through reqParams in case of actions.

The predefined variables are:

| Variable name | Description |
| :--- | :--- |
| :APPLICATION\_ID | application identifier |
| :BASE\_URL | server base url |
| :COMPANY\_ID | company identifier \(used in case the app supports partitioned data\) |
| :SITE\_ID | site identifier |
| :USERNAME | current user |
| :UUID or :DEVICE\_ID | device id, i.e. a unique identifier for a specific device, more specific than the username \( only for mobile apps\) |
| :LANGUAGE\_ID | current user |
| :DOCUMENTS\_DIR | absolute path within the mobile device, where files are stored;it is a folder inside the “customFiles” default app folder \(only for mobile app\) |
| :TODAY | current date |
| :NOW | current date+time |
| :YEAR | current year |
| :GPS\_LATITUDE | current latitude \(only for mobile apps\) |
| :GPS\_LONGITUDE | current longitude \(only for mobile apps\) |
| :GPS\_ALTITUDE | current altitude \(only for mobile apps\) |
| :GPS\_SPEED | current speed \(only for mobile apps\) |
| :APP\_VERSION | current app versione |
| :LAST\_SYNC\_DATE | last sync date \(only for mobile apps\) |

By and large, a server-side javascript action \(or GAE action\) allows to access to all resources provided by the server, including:

* database
* NoSQL database
* web services
* local or on the cloud file system

The editor is the same for all javascript actions and it provides:

* syntax checker
* line number
* syntax highlithers
* **auto completion function**, accessible by typing a few character and then pressing CTRL+space \(or COMMAND+space\); this feature shows all compatible predefined functions provided by Platform
* **code generator which provides javascript code for an object** \(data model\) definition, in terms of attributes, accessible by pressing CTRL+I \(or COMMAND+I\); this command prompts the user with a dialog reporting all defined data models: once selected one the corresponding attribute definition is pasted within the js editor.

