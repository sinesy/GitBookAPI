# Google Sheet

Google Spreadsheets can be accessed starting from Platform, using a server-side javascript action, where a few utility methods are available to read and write content on the sheet.

In order to do it, the Google Cloud Project referring a Google Spreadsheet must be set up, i.e. a few global parameters in the GOOGLE group must defined:

* Google Service Account Email
* Google Service Account Key \(p12 key Base64 encoded\)

Of course, a Google project administrator must have defined a service account key and its private key, described above.

After doing it, any spreadsheet belonging to the same Google Domain can be accessed, **as long as the document has been shared with the user account** specified in the utility javascript method.

## Reading a cell in a spreadsheet

This method allows to read a cell within the specified sheet.

**Syntax**:

```javascript
var values = utils.getGoogleSheetData(
    userEmail, 
    spreadsheetId,
    cellsRange,
    null, // valueRenderOption
    null // dateTimeRenderOption
);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| userEmail | Defining the global parameters to access the Google Cloud Project is not enough to get access to a specific Google Spreadsheet: in order to do it, a valid email address \(google user account\) must be specified here; this email is related to a user belonging to the Google Domain connected to the GCP and this user must have grants to access \(at least for reading\) the Google sheet |
| spreadsheetId | Google sheet identifier; it can be easily retrieved when opening the sheet in Google Drive; the id is the long string reported in the browser URL; e.g. [https://docs.google.com/spreadsheets/d/\*\*thisIsTheDheetId\*\*/edit\#gid=0](https://docs.google.com/spreadsheets/d/**thisIsTheDheetId**/edit#gid=0) |
| cellsRange | this is a javascript Array containing a list of ranges; each range is a String expressed as s single coordinate \(e.g. "A1"\) or like an interval \(e.g. "A1:B2"\). See the example below for more details. |
| valueRendererOption | optional: can be null |
| dateTimeRendererOption | optional: can be null |
| **values** | the return value is always a javascript Array, containing as many cells as the ones required by "cellsRange" argument; in the easiest case, when requesting a cell only \(cellsRange = \["A1"\]\), the return value is: \["value"\], always expressed as a string; in case of date cells, the string format is "dd/MM/yyyy". In case a range of cells have been requested \(cellsRange = \["A1","B2"\]\), the return value is: \[\["value1"\],\["value2"\]\], where each element is always expressed as a string; elements are grouped per row. In case of date cells, the string format is "dd/MM/yyyy"; numeric values are always expressed as strings too. |

Examples of cellsRange:

```text
["A1"] - get one cell only: A1; the returned value is: ["value"]
["A1,"B2"] - get 2 cells: A1 and B2; the returned value is: [["valueA1"],"[valueB2]], since there are 2 distinct rows
["A1:B2"] - get 4 cells: A1,B1, A2, B2; the returned value is: [["valueA1","valueB1"],["valueA2","valueB2"]]
```

## Setting cells in a spreadsheet

This method allows to write a cell or more than one, within the specified sheet.

**Syntax**:

```javascript
var nrOfCellsUdated = utils.updateRangeGoogleSheet(
    userEmail, 
    spreadsheetId,
    cellsRange,
    null, // valueInputOption
    vos
);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| userEmail | Defining the global parameters to access the Google Cloud Project is not enough to get access to a specific Google Spreadsheet: in order to do it, a valid email address \(google user account\) must be specified here; this email is related to a user belonging to the Google Domain connected to the GCP and this user must have grants to access \(at least for reading\) the Google sheet |
| spreadsheetId | Google sheet identifier; it can be easily retrieved when opening the sheet in Google Drive; the id is the long string reported in the browser URL; e.g. [https://docs.google.com/spreadsheets/d/\*\*thisIsTheDheetId\*\*/edit\#gid=0](https://docs.google.com/spreadsheets/d/**thisIsTheDheetId**/edit#gid=0) |
| cellsRange | this is a String, representing either the single cell to set or a range of cells, specified as "COORD1:COORD2" \(e.g. "A1:B2"\). The "vos" argument must be defined according to the number of cells to set \(i.e. same number of values\), otherwise the method will fire an exception |
| valueInputOption | optional: can be null |
| vos | this is a javascript Array containing all values to set, having as many values as the number of cells to update, specified in "cellsRange" argument. These values must be organized in rows \(sub-arrays\). In the easiest case \(cellsRange = "A1"\), this argument must be set with \[\["value"\]\]. In a more complex scenario \(e.g. cellsRange = "A1:B2", i.e. 4 values to set\), this argument must be defined as \[\["valueA1","valueB1"\],\["valueA2","valueB2"\]\]. Here a number can be passed as it is \(not converted to String\). |

Examples:

```javascript
utils.updateRangeGoogleSheet(
    "...", // userEmail
    "...", // spreadsheetId
    "A1", // cellsRange
    null, // valueInputOption
    [["value"]]
); // update ONE only cell

utils.updateRangeGoogleSheet(
    "...", // userEmail
    "...", // spreadsheetId
    "A1:B2", // cellsRange
    null, // valueInputOption
    [["valueA1","valueB1"],["valueA2","valueB2"]]
); // update 4 cells
```

## Clear up cells in a spreadsheet

This method allows to clear up cells within the specified sheet.

**Syntax**:

```javascript
var nrOfCellsUdated = utils.clearRangeGoogleSheet(
    userEmail, 
    spreadsheetId,
    cellsRange
);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| userEmail | Defining the global parameters to access the Google Cloud Project is not enough to get access to a specific Google Spreadsheet: in order to do it, a valid email address \(google user account\) must be specified here; this email is related to a user belonging to the Google Domain connected to the GCP and this user must have grants to access \(at least for reading\) the Google sheet |
| spreadsheetId | Google sheet identifier; it can be easily retrieved when opening the sheet in Google Drive; the id is the long string reported in the browser URL; e.g. [https://docs.google.com/spreadsheets/d/\*\*thisIsTheDheetId\*\*/edit\#gid=0](https://docs.google.com/spreadsheets/d/**thisIsTheDheetId**/edit#gid=0) |
| cellsRange | this is a String, representing either the single cell to set or a range of cells, specified as "COORD1:COORD2" \(e.g. "A1:B2"\). |

## Deploying an AppScript

Google allows to deploy an already existing AppScript, starting from the web service described here:

{% embed url="https://developers.google.com/apps-script/api/reference/rest/v1/projects.deployments/create" %}

In order to do it successfully, a few requirements must be satisfied:

* The AppScript project must have been associated to a "standard" GCP project \(Resources -&gt; GCP -&gt; set the GCP project number, which can be retrieved from the project home page in the GCP console\)
* The AppScript API must be enabled \(go to [https://console.developers.google.com/apis/api/script.googleapis.com/overview?project=.](https://console.developers.google.com/apis/api/script.googleapis.com/overview?project=....)...\)
* The AppScript API must be enabled for the Google user used to edit/deploy/launch the AppScript: \(go to [https://script.google.com/home/usersettings](https://script.google.com/home/usersettings)\)
* Have a OAuth2 credentials defined for that GCP project and in the corresponding credentials in GSuite there must be this permission included: [https://www.googleapis.com/auth/script.deployments](https://www.googleapis.com/auth/script.deployments)
* the AppScript must be already been versioned and the the appscript.json must be set appropriately \(e.g. to deploy a web app\)
* Have the script Id \(see the definition of the AppScript\)

Once all these data are avaiable, you can execute the deployment of an AppScript by getting first a Google Auth Token.

Plaform provides a server-side javascript method you can use to get such a temporary token \(do not save it, since it expirers after a few minutes\).

```javascript
var googleAuthToken = utils.getGCPAuthToken(
    "...", // the email address of the owner/editor of the AppScript
    serviceAccountEmail,
    serviceAccountKey,
    [
        "https://www.googleapis.com/auth/script.deployments" // permissions to be granted
    ]
);
```

where "serviceAccountEmail" and "serviceAccountKey" can be 

* either set to null if you want to reuse the service account credentials defined as global parameters in the GOOGLE section 
* or specified directly

In any case, it is up to you to provide credentials where the permission "[https:// www.googleapis.com/ auth/ script.deployments](https://www.googleapis.com/auth/script.deployments)" has been assigned at GSuite level.

Once you successfully get such an auth token, you can invoke the web service provided by Google to execute a new deployment, starting from the version of the AppScript already set:

```javascript
var scriptId = "...";
var versionNumber = "..."; // info already available, since the AppScript must have been already versioned at least once

var json = utils.getWebContent(
    "https://content-script.googleapis.com/v1/projects/"+scriptId+"/deployments?alt=json&access_token="+googleAuthToken,
    false,
    "POST",
    "application/json",
    JSON.stringify({
        "versionNumber":versionNumber,
        "scriptId": scriptId,
        "description":"..."
    }),
    null,
    null
); 
```

The response JSON string can be something like:

```javascript
{
  "deploymentId": "...",
  "deploymentConfig": {
    "scriptId": "...",
    "versionNumber": 1,
    "manifestFileName": "appsscript",
    "description": "abc"
  },
  "updateTime": "2021-02-12T12:31:54.141Z",
  "entryPoints": [
    {
      "entryPointType": "WEB_APP",
      "webApp": {
        "url": "https://script.google.com/macros/s/.../exec",
        "entryPointConfig": {
          "access": "MYSELF",
          "executeAs": "USER_DEPLOYING"
        }
      }
    }
  ]
}
```

## Executing an AppScript

When an AppScript has been deployed as a web app, it is possible to start it in two alternative ways:

* **within a web browser** where the user is authenticated in the Google SSO \(and he has a GSuite account having the grants to execute an AppScript\)
* **on the server side**

The execution on the browser is possible starting from the URL returned by the deployment task.

Example: 

```javascript
https://script.google.com/macros/s/.../exec
```

Note: you CANNOT use this URL to execute an AppScript on the server side, since it is based on the Google SSO authentication in a browser and what this link returns is HTML, interpreted by the browser.

See also [https://developers.google.com/apps-script/guides/web](https://developers.google.com/apps-script/guides/web) to see additional requirements to respect.

In order to execute the AppScript from the server-side, Google provides an web service you can use to run a specific function declared within the AppScript.

See also [https://developers.google.com/apps-script/guides/web](https://developers.google.com/apps-script/api/reference/rest/v1/scripts/run) to see additional requirements to respect, including permissions to define at GSuite level in order to execute the AppScript and any additional libraries referred by it.

You can use the previous method to get a Google auth token to execute such a web service:

```javascript
var json = utils.getWebContentWithHeaders(
    "https://script.googleapis.com/v1/scripts/"+scriptId+":run",
    false,
    "POST",
    "application/json",
    JSON.stringify({
      "function": "yourFunction",
      "parameters": [
         ...
      ],
      //"sessionState": string,
      "devMode": true // it is up to you to decide how to set it
    }),
    null, // user
    null, // pwd
    null, // charset
    {
        Authorization: "Bearer "+googleAuthToken
    } // headers
);
```

## Getting a permanent auth token

An alternative way to run an AppScript is starting from a permanent auth token, used instead of the one generated on the fly using the method described above. You have to follow this approach in case you are not able to assign the right grants to the OAuth2 credentials in use.

In order to generate a permanent token, you need:

* an email address belonging to your Google domain, having "edit" grants on the AppScript
* the whole list of grants \(scopes\) this token must include, in order to run the AppScript \(look at the AppScript editor to get such a list\)
* OAuth2 credentials to use to get the token
* enable your Platform installation to receive this token from Google service; in order to do it, go to the Google Cloud Platform Console -&gt; API and Services -&gt; Credentials, select your OAuth2 credentials and in the "Authorized redirect URIs" insert a new line with your Platform installation \(e.g. https://&lt;yourhost&gt;/&lt;platformwebcontext&gt;/oauth2callback \) and be sure to save this additional setting

At this point, you can create a server-side javascript action to use to generate the permanent auth token, starting from the OAuth2 credentials, the auth scopes and the email address associated to the auth scopes. The action content can be something like:

```javascript
var tempURL = utils.generateGCPAuthToken(
    "youemailaddress@youdomain", // email address to use 
     "....apps.googleusercontent.com", // your oauth2 client id
     "...", // your oauth2 client private key
    "https://<yourhost>/<platformwebcontext>/oauth2callback", // the same defined in the Google Console above
    [... ] // your auth scopes, used later when running the AppScript
);
utils.setReturnValue(tempURLanentAuthToken);

```

When you run this action, you will get back a temporary URL \(you can use it once\).

The last step is opening a web browser, log on in Google SSO with the email address specified above and then navigate through this link.

Google will prompt the user to accept the specified scopes and finally invokes the callback in Platform to generate the permanent token.

Such a token will be logged in Platform:

```javascript
[DEBUG] ... Generated token: XYZ
```

It is strongly recommended to store it as an Application parameter or in some other application table.

## Create a spreadsheet

This method allows to create a spreadsheet and his sheets.

**Syntax**:

```javascript
var risp = utils.createGoogleSpreadsheets(
    String userId, 
    String spreadsheetTitle, 
    String[] sheets
);
var spreadsheetId = risp.spreadsheetId;
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| spreadsheetTile | Name of spreadsheet |
| sheets | List of name for sheets |

## Create sheets in a spreadsheet

This method allows to create a list of sheet in a spreadsheet.

**Syntax**:

```javascript
var risp = utils.createGoogleSheets(
    String userId, 
    String spreadsheetId, 
    String[] sheets
);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| spreadsheetId | Id of spreadsheet |
| sheets | List of name for sheets |

## Delete sheets in a spreadsheet

This method allows to delete a list of sheet in a spreadsheet.

**Syntax**:

```javascript
var risp = utils.deleteGoogleSheets(
    String userId, 
    String spreadsheetId, 
    Integer[] sheetIds
);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| spreadsheetId | Id of spreadsheet |
| sheetIds | List of sheet id to delete |

## Duplicate sheet in a spreadsheet

This method allows to duplicate a sheet in a spreadsheet.

**Syntax**:

```javascript
var risp = utils.duplicateGoogleSheet(
    String userId, 
    String spreadsheetId, 
    Integer sourceSheetId, 
    Integer insertSheetIndex, 
    Integer newSheetId, 
    String newSheetName
);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| spreadsheetId | Id of spreadsheet |
| sourceSheetId | Id of sheet to copy |
| insertSheetIndex | Index of new sheet |
| newSheetId | id of new sheet |
| newSheetName | name of new sheet |

## Copy sheet in a different spreadsheet

This method allows to copy a sheet in a different spreadsheet.

**Syntax**:

```javascript
var risp = utils.copyGoogleSheet(
    String userId, 
    String spreadsheetId, 
    Integer sheetId, 
    String destinationSpreadsheetId
);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| spreadsheetId | Id of source spreadsheet |
| sheetId | Id of sheet to copy |
| destinationSpreadsheetId | Id of new spreadsheet  |

