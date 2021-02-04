# Import Cells from xlsx

## Get a metadata from db table

Read the table structure from database and prepare the metadata for import

**Syntax**:

```javascript
var dbTableId = utils.createDbTableMetadata(Long datasourceId, String tableName);
```

| Argument | Description |
| :--- | :--- |
| datasourceId | optional parameter \(can be null\); it defines the additional datastore to use  |
| tableName | table name |

## Update the table metadata

Update the table metadata if the table structure are changed

**Syntax**:

```javascript
utils.updateDbTableMetadata(Logn dbTableId);
```

| Argument | Description |
| :--- | :--- |
| dbTableId | id of table metadata |

## Create value for imports

This function create the metadata for import. Prepare the data from table and read the xlsx file for values.

**Syntax**:

```javascript
var valueImportId = utils.createValueImports(
    Long dbTableId, 
    Long directoryId, 
    String fileName, 
    String description, 
    String note, 
    String inputData, 
    Long breakOnColumnsEmpty, 
    Long breakOnRowsEmpty
);
```

| Argument | Description |
| :--- | :--- |
| dbTableId | id of table metadata for import |
| directoryId | id of the directory where to search the file |
| fileName | file name |
| description | description for import \(can be null\) |
| note | note for import \(can be null\) |
| inputData | string in json format for data in import \(can be null\) |
| breakOnColumnsEmpty | number of empty cells in row to stop reading values in the sheet \(default 5\) \(can be null\) |
| breakOnRowsEmpty | number of empty rows to stop reading values in the sheet \(default 5\) \(can be null\) |

## Duplicate value import

This function duplicate the import metadata and read the values from the old file or from the new file.

**Syntax**:

```javascript
var valueImportId = utils.duplicateValueImports(
    Long valueImportId, 
    Long directoryId, 
    String fileName, 
    String description, 
    String note, 
    String inputData, 
    Long breakOnColumnsEmpty, 
    Long breakOnRowsEmpty
);
```

| Argument | Description |
| :--- | :--- |
| valueImportId | id of import to duplicate |
| directoryId | id of the directory where to search the file; can bel null if you want read the old file |
| fileName | file name; can bel null if you want read the old file |
| description | description for import \(can be null\) |
| note | note for import \(can be null\) |
| inputData | string in json format for data in import \(can be null\) |
| breakOnColumnsEmpty | number of empty cells in row to stop reading values in the sheet \(default 5\) \(can be null\) |
| breakOnRowsEmpty | number of empty rows to stop reading values in the sheet \(default 5\) \(can be null\) |

## Import Cells from Excel File

This function import the mapped cells value from excel into the database table.

**Syntax**:

```javascript
var result = utils.importCellsFromExcelFile(
    Long directoryId, 
    String fileName, 
    Long valueImportId, 
    Map fieldsData, 
    Map inputData,
    Boolean separatedTransaction
);
```

| Argument | Description |
| :--- | :--- |
| valueImportId | id of import to duplicate |
| directoryId | id of the directory where to search the file |
| fileName | file name |
| valueImportId | id of defined import  |
| fieldsData | other value of fields table to valorize in import |
| inputData | string in json format for data in import \(can be null\) |
| separatedTransaction | flag true\|false indicating whether the SQL query must be executed in a separated database transaction or within the current one |

## Check cells from excel file

This function check the mapped cells from excel and verify the mandatory values, the format etc

**Syntax**:

```javascript
var result = utils.checkCellsWithMetadataForImport(
    Long directoryId, 
    String fileName, 
    Long valueImportId
);
```

| Argument | Description |
| :--- | :--- |
| valueImportId | id of import to duplicate |
| directoryId | id of the directory where to search the file |
| fileName | file name |
| valueImportId | id of defined import  |

## Export areas from excel to new file excel

This function copies the cells value of an area to the specified area in a new file

**Syntax**:

```javascript
var result = utils.exportFromExcelFile(
    Long sourceDirId, 
    String sourceFileName, 
    Long destDirId, 
    String destFileName, 
    List areas
);
```

| Argument | Description |
| :--- | :--- |
| sourceDirId | id of the source file directory |
| sourceFileName | source file name \(xlsx\) |
| destDirId | id of the destination file directory |
| destFileName | destination file name \(xlsx\) |
| areas | list of cells area to export |

Example

```javascript
var result = utils.exportFromExcelFile(
    9, //Long sourceDirID
    'sourceFileName.xlsx', //String sourceFileName
    19, //Long destDirId
    'destFileName.xlsx', //String destFileName
   [
       {
        sourceSheetName: 'Sheet1',
        sourceCoordinates: 'A1:C3',
        destSheetName: 'SheetDest1',
        destCoordinate: 'A1:C3'
       }, 
       {
        sourceSheetName: 'Sheet2',
        sourceCoordinates: 'A11:C15',
        destSheetName: 'SheetDest2',
        destCoordinate: 'A1:C5'
       }
   ]
);
```

## Export areas from excel to Google Spreadsheet

This function copies the cells value of an area to the specified area in a Google Spreadsheet

**Syntax**:

```javascript
var result = utils.exportFromExcelFile(
    Long sourceDirId, 
    String sourceFileName, 
    String spreadsheetId, 
    List areas
);
```

| Argument | Description |
| :--- | :--- |
| sourceDirId | id of the source file directory |
| sourceFileName | source file name \(xlsx\) |
| spreadsheetId | id of the Google Spreadsheet |
| areas | list of cells area to export |

Example

```javascript
var result = utils.exportFromExcelFile(
    9, //Long sourceDirID
    'sourceFileName.xlsx', //String sourceFileName
    'XxXxXxXxXxXxXxXxXxXxXxXxXxXxXxXxXxX', //String spreadsheetId
   [
       {
        sourceSheetName: 'Sheet1',
        sourceCoordinates: 'A1:C3',
        destSheetName: 'SheetDest1',
        destCoordinate: 'A1:C3'
       }, 
       {
        sourceSheetName: 'Sheet2',
        sourceCoordinates: 'A11:C15',
        destSheetName: 'SheetDest2',
        destCoordinate: 'A1:C5'
       }
   ]
);
```

## Disable Import

This function logically disables an import definition

**Syntax**:

```javascript
var result = utils.disableValueImport(
    Long valueImportId
);
```

| Argument | Description |
| :--- | :--- |
| valueImportId | id of the import definition |

## Delete Import

This function definitively cancels an import

**Syntax**:

```javascript
var result = utils.deleteValueImport(
    Long valueImportId
);
```

| Argument | Description |
| :--- | :--- |
| valueImportId | id of the import definition |

