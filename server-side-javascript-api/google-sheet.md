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

