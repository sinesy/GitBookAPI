---
description: (version 6.0.2)
---

# Import Rows from csv, xls and xlsx

It is possible to start importing data from a csv, xls and xlsx file also from javascript server actions.

**Syntax**:

```javascript
utils.importRowsFromFile(
      Long dirId, 
      String fileName, 
      Long importId,
      boolean insert, 
      Long maxErrors, 
      Long maxRowErrors, 
      Map inputData, 
      Long destErrorsFileDirId, 
      String destErrorsFileName,
      boolean rollbackIfErrors 
);
```

| Argument | Description |
| :--- | :--- |
| dirId | id of the directory where to search the file |
| fileName | file name |
| importId | id of import \(\*\) |
| insert | true if you want insert the rows; false if you want insert or update the rows |
| maxErrors | \(optional\) number of errors to block the reading of file |
| maxRowErrors | \(optional\) number of errors to block the process of row |
| inputData | \(optional\) map of variables or data to use to insert/update the rows |
| destErrorsFileDirId | \(optional\) id of the directory where saving the errors file |
| destErrorsFileName | \(optional\) name of errors file |
| rollbackIfErrors | true: if there are errors it cancels everything; false: confirms only the successfully imported rows |

\(\*\) You can configure the import [here](https://4wsplatform.gitbook.io/user-guide/core-features/defining-the-ui/3-1-app-designer/3-1-24-bulk-import-binded-to-a-grid)

**Example**:

```javascript
utils.importRowsFromFile(
      9, 
      "example.xlsx", 
      9,
      true, 
      10, 
      2, 
      { "FIELD1": 123, "USERNAME": "TEST_USER" }, 
      9, 
      "errors_of_example.xlsx",
      true 
);
```

