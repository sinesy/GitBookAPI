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



