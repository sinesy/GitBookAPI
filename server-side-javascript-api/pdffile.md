# PDF File

## Read a signed PDF file and extract data coming from the embedded certificate <a href="#getcsvcontent" id="getcsvcontent"></a>

The source PDF file is identified starting from the source directory id + fileName.

The specified PDF file is signed file, i.e. it contains a certificate; this certificate is then extracted and saved in the destination directory. The certificate file, if recognized with a MIME type, is renamed to a name having the original name + its real extension. Otherwise, it is saved with the original source file name.

**Syntax**

```javascript
var obj = utils.getCertMessageFromPdf(Long srcDirectoryId,Long destDirectoryId,String fileName);
```

**Details**

| Argument        | Description                                                                                                        |
| --------------- | ------------------------------------------------------------------------------------------------------------------ |
| srcDirectoryId  | id used to identify a source folder in the server file system where the PDF signed file to read has been stored    |
| destDirectoryId | id used to identify a folder in the server file system when the extracted document (the certificate) will be saved |
| fileName        | file name inside the specified folder                                                                              |
| obj             | embedded document, expressed as a javascript object                                                                |

The returned javascript object contains the following attributes:

* expirationDate
* firstName
* lastName
* personId
* signerCountry
* signerId
* signerOrganization
* personalVatNumber
* corporateVatNumber
* corporateName
* personCountry
* mimeType - MIME type for the embedded file; e.g. application/xml, application/pdf, etc.
* destFilePath - absolute path + file name, related to the embedded file
* signDate - the sign date, expressed as a javascript Date &#x20;

## Writing a very long PDF file on the server file system <a href="#zipfiles" id="zipfiles"></a>

**From 6.0.2 version**

Write a very long PDF file on the server file system, through a 3 steps approach:

* first, open the output stream, through the "openPDFFile" method
* next, add as many rows as you need, by invoking the "addLineToPDFFile" method multiple times, for each row to add
* finally, close the output stream, by invoking the "closePDFFile"

Data could be retrieved from a SQL query, through the **executeQueryWithCallback** method, since this will ensure a limited amount of memory consumption.

**Important note**: the PDF file can be filled starting from a set of text lines; all lines inherit the same style (font + line height); lines are appended automatically, each with the same specified height; it is possibile to define the page size (e.g. A4, Letter, etc.), orientation (portrait vs landscape) and margins; a new page is automatically created when appended lines reach the bottom part of the current page.

This method can be used to create up to 1M lines (more or less some tens thousand pages), approximately in 15 mins, consuming about 200Mb of memory. Memory is upper-bound limited to such amount, since data is automatically flushed every 1000 pages.



**Syntax for openPDFFile method**

```javascript
var fileId = utils.openPDFFile(
  fileName, 
  directoryId,
  additionalSettings
);
```

**Details**

| Argument           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| fileName           | CSV file name to create within the specified directory                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| directoryId        | directory identifier, used to define the absolute path, in the central server, where the file will be stored; if null, there must be one only entry for this application                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| additionalSettings | <p>optional javascript object, containing additional settings to define the PDF rendering, in terms of margins, page format (A4, Letter, etc.), line height, font name/size, etc.</p><p>{</p><p>  fontName: "Courier", </p><p>  fontSize: 10, </p><p>  size: "A4", </p><p>  top: 20, // top margin</p><p>  left: 20, // left margin</p><p>  bottom: 20, // bottom margin</p><p>  height: 10, // line height</p><p>  orientation: "portrate"</p><p>}</p><p></p><p>Allowed values for fontName: "Courier-Bold", "Courier-BoldOblique", "Times-Roman", "Helvetica-Oblique", "Courier-Oblique", "Symbol", "Times-Italic", "Helvetica", "Helvetica-Bold", "Times-BoldItalic", "ZapfDingbats", "Times-Bold", "Helvetica-BoldOblique", "Courier"</p><p></p><p>Allowed values for orientation: "portrait","landscape"</p><p></p><p>Allowed values for size: "A0"..."A6","LETTER"</p> |
| fileId             | a text id, representing the output stream, to refer in the next two methods.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |



**Syntax for addLineToPDFFile method**

```javascript
var fileId = utils.addLineToPDFFile(fileId, line, additionalSettings)
```

**Details**

| Argument           | Description                                                                                                                                                                                                                                                                                                                               |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| fileId             | a text id, representing the output stream, needed to work qwith the correct output stream                                                                                                                                                                                                                                                 |
| line               | String text to append to the current page; a new page is automatically created when the next line position would be over the max page height - bottom margin - line height. Page height depends on the page "size". It is possible to force a new page before reaching the bottom part of the page through the "addPageToPDFFile" method. |
| additionalSettings | additional settings for the current line, expressed as a javascript object; not supported at the moment                                                                                                                                                                                                                                   |

**Syntax for setLineToPDFFile method**

```javascript
var fileId = utils.setLineToPDFFile(fileId, x, y, line, additionalSettings)
```

**Details**

| Argument           | Description                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------- |
| fileId             | a text id, representing the output stream, needed to work qwith the correct output stream                |
| x                  | X coordinate where positioning the text                                                                  |
| y                  | Y coordinate where positioning the text                                                                  |
| line               | String text to include to the current page, at the specified position                                    |
| additionalSettings | additional settings for the current line, expressed as a javascript object; not supported at the moment  |

**Syntax for closePDFFile method**

```javascript
var fileId = utils.closePDFFile(fileId)
```

**Details**

| Argument | Description                                                                              |
| -------- | ---------------------------------------------------------------------------------------- |
| fileId   | a text id, representing the output stream, needed to work with the correct output stream |

**Example**

```javascript
// open the PDF file, in order to write into it
var fileId = utils.openPDFFile(
    "ab.pdf",
    9, // directory id
    {
      top: 20,
      left: 20,
      bottom: 20,
      fontName: "Courier",
      fontSize: 10,
      height: 10, 
      size: "A4",
      orientation: "portrait"
    } 
);
// if the additional settings are not specified, 
// a set of default values are used; the default values are as reported above

// declare a callback function, invoked by a SQL query, used to write a single line into the CSV file
var processRow = function(jsonRow) {
    utils.addLineToPDFFile(fileId,jsonRow.description);
}

// execute the SQL query, whose result set will be read row by row, by invoking each time the specified callback
utils.executeQueryWithCallback(
    "processRow", // callback function, invoked for each record coming from the query, whose argument will receive a JSON object representing the record
    "SELECT U.DESCRIPTION FROM PRM01_USERS U",
    null,
    false,
    true,
    []
);

// close the PDF file, after reading all records from the query
utils.closePDFFile(fileId);
```

****

**Syntax for addPageToPDFFile method**

It can be used to force the creation of a new page.

```javascript
utils.addPageToPDFFile(fileId);
```

**Details**

| Argument | Description                                                                              |
| -------- | ---------------------------------------------------------------------------------------- |
| fileId   | a text id, representing the output stream, needed to work with the correct output stream |

****

## Writing a **background text to a** PDF file <a href="#getcsvcontent" id="getcsvcontent"></a>

**From 6.0.2 version**

Starting from an already existing PDF file, this method adds a text in the middle of the page, for each page, in the background.

**Syntax**

```javascript
utils.addBackgroundToPdf(
  Long dirId,
  String pdfFile,
  String background,
  Map settings
);
```

**Details**

| Argument   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dirId      | a directory id, where the already existing PDF file is stored                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| pdfFile    | PDF file name                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| background | text to include in the background, for each page                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| settings   | <p>additional settings, expressed as a javascript object, having the following optional attributes:</p><p>{ </p><p>  red: 200, </p><p>  green: 200, </p><p>  blue: 200, </p><p>  fontName: "Helvetica-Bold", </p><p>  fontSize: 50, </p><p>  fileName: "newfile.pdf" </p><p>}</p><p></p><p>Allowed values for "fontName": "Courier-Bold", "Courier-BoldOblique", "Times-Roman", "Helvetica-Oblique", "Courier-Oblique", "Symbol", "Times-Italic", "Helvetica", "Helvetica-Bold", "Times-BoldItalic", "ZapfDingbats", "Times-Bold", "Helvetica-BoldOblique", "Courier"</p> |

Note: if no settings has been specified, the default values reported above will be used.





