# Inside a mobile business component

Platform allows to specify SQL instructions including **binding variables**.

These binding variables are always defined using the notation:

:XXX

where XXX is the variable name, always in upper case.

These variables will be automatically replaced by the corresponding values available at user session level.

The user session is composed of a set of variables:

* **predefined variables**, automatically set by Platform, when the user logs on
* **custom variables**, defined using the addCustomApplUserVars server-side javascript method
* **input parameters**, passed to the business component, defined in the business component definition window \(input pars subfolder\)

The predefined variables are:

| Variable name | Description |
| :--- | :--- |
| :APPLICATION\_ID | application identifier |
|  | :BASE\_URL -server base url |
| :COMPANY\_ID | company identifier \(used in case the app supports partitioned data\) |
| :SITE\_ID | site identifier |
| :USERNAME | current user |
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

