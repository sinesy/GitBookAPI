# Reporting

## Create a .docx file starting from a template and save it to the specified absolute path

**Syntax**

```javascript
var file = utils.generateDocx(reportId,args,langId,path,fileName)
```

**Details**

| Argument | Description |
| :--- | :--- |
| reportId | long value representing a specific report template in CON66 |
| args | a collection of pairs &lt;attributeName,attributeValue&gt; to use to bind queries connected to that report |
| langId | \(optional\) language that identify the template to use; can be null |
| path | the absolute path where saving the document \(it must not include the file name\) |
| fileName | \(optional\) the name to use when creating the file; may be null: in that case, a dynamic name will be assigned automatically |
| file | the file name of the generated .docx file |

This method will fire an exception in case of problems when generating the docx file.

## Merge a list of docx files to a new docx file

Starting from a list of already existing docx files, stored in the same location, merge them and product a new one.

**Syntax**

```javascript
utils.mergeDocx(Long srcDirId, String[] docxNames, Long destDirId, String mergedDocxName, boolean deleteFilesAfterMerge)
```

**Details**

| Argument | Description |
| :--- | :--- |
| srcDirId | directory id where the already existing docx files are located |
| docxNames | a list of file names, related to docx files to merge; they must be specified as a javascript Array of strings, where each element contains only the file name, NOT the absolute path |
| destDirId | directory id where the new docx file will be saved |
| mergedDocxName | docx file name |
| deleteFilesAfterMerge | flag true\|false indicating whether the source docx files must be automatically deleted, after the marge operation has been successfully completed |

This method will fire an exception in case of problems when generating the docx file.

## Convert a docx file to a pdf file and save it to the file system

**Syntax**

```javascript
utils.convertDocxToPdf(docxFile, pdfFile, deleteDocxFile)
```

**Details**

| Argument | Description |
| :--- | :--- |
| docxFile | string representing the source file, in docx format |
| pdfFile | string representing the new file to create, in pdf format |
| deleteDocxFile | boolean flag used to automatically delete the source file, when the pdf file has been created |

Important note: this method can work with 3 alternative implementations behind the scenes:

* using **CloudConvert Web Service API** - in order to enable this implementation, you have to set the global property CloudConv Key, i.e. you have to buy this online service before invoking it 
* using **LibreOffice Portable** - this product must be installed in the same server hosting Platform; moreover, the global property named "LibreOffice Path" must be defined too. In case you need to convert a docx to a PDF/A \(PDF archive format\), you have first to change the file &lt;pathlibreoffice&gt;/Data/settings/user/registrymodifications.xcu and change/add the following line: 

```javascript
<item oor:path="/org.openoffice.Office.Common/Filter/PDF/Export"><prop oor:name="SelectPdfVersion" oor:op="fuse"><value>1</value></prop></item>
```

In that case, all PDFs generated will have this format.

You can download and install LibreOffice portable, according to the operating system, starting from this link:

[https://download.documentfoundation.org/libreoffice/stable/6.3.6/](https://download.documentfoundation.org/libreoffice/stable/6.3.6/)

If none of the previous settings have been defined, a **default PDF conversion is used**, based on **POI** open source library, which does not ensure a good PDF conversion anyway.

## How to print a report directly to a printer

**Syntax**

```javascript
var response = utils.printDocument( printerName, copies, mediaSize, printParams, reportName,dirReports, datastoreId, reportFormat, reportParams);
```

**Details**

| Argument | Description |
| :--- | :--- |
| printerName | printer name |
| copies | number of copies; e.g. 1 |
| mediaSize | dimernsion of the paper, expressed as 1-10 values \(i.e. A0-A10\); can be null |
| printParams | js object containing parameters specific for the selected printer; if not needed, set it to {} |
| reportName | .jasper file name, which must be stored with the folder |

```text
 /reports
```

| Argument | Description |
| :--- | :--- |
| dirReports | optional subfolder where the .jasper file is located; it is a subfolder of the one described above; if not needed, you have to set it to ‘’ |
| datastoreId | optional, related to the data source used by the .jasper report to get data from the database; if the default repository is used, then set it to null |
| reportFormat | report format, e.g. PDF |
| reportParams | input parameters required vy the .jasper report file; if not needed, set it to {} |
| result | outcome; it could contain an error message if no printers has been configured or if the specified printer name has not been recognized or if the .jasper file is not located in the required path or in case of a generic print error. If the report has been successfully genrated and it has been sent to the printer spooler, then the ""Report printed." message is sent back |

## Generate a report starting from a .jasper report template and save it to the server file system, in the specified path.

**Syntax**

```javascript
var json = utils.saveDocument(reportName,dirReports, datastoreId, compId,reportFormat, reportParams,savePath);
```

**Details**

```text
 reportName .jasper report name
 dirReports optional folder where the .jasper file is located; thisis arelative pathand it is always contained within the subolder &lt;application-context-path&gt;/reports/
 datastoreId optional data source id used by the .jasper template to read data from the database
 compId optional value: business component id to use to fill in the report
 reportFormat report format to use when creating the report; e.g. PDF
 reportParams input parameters required by the report template
 savePath path where the generated report will be saved; it must includes the file name
 error message, in case of errors; "" if the generation has been successfully completed
```

It returns a JSON string containg:  
{ "success": true }  
if the report has been created successfully, or a JSON string having this format otherwise:  
{ "success": false, "message": "..."}

**Example**

and the database schema to pass forward to the report is the Platform repository schema:

```javascript
var reportParams = new Object();

reportParams.paramxyz = "...";
...
var json = utils.saveDocument("mytemplate.jasper",null, null, null,"PDF", reportParams,"pathwheresavingthepdf/myreport.pdf");
utils.setReturnValue('{ "success": true, "fileName": "myreport.pdf", "dirId": ' + dirId + ' }');
```

If you want showing the report you can create a javascript action

```javascript
if(response!==null && response!=='') {
    var risp = Ext.decode(response);
    if(risp.success) {
        mydesktop.createWindow({
          title: 'uploadfilesgrid.preview.text',
          width: 800,
          height: 600,
          manager: mydesktop.getManager(),
          modal: true,
          plain: true,
          layout: 'fit',
          items: 
            new Ext.Panel({
              html: '<iframe src="' + contextPath + 
                '/filemanager/downloadfile?dirId='+ risp.dirId + '&fileName='+ risp.fileName +
                '&appId='+applicationId+'&applicationId='+applicationId+
                '&preview=true" width="100%" height="100%"/>'
            })
        }).show();    
    } else {
       showMessageDialog("Error",risp.msg,function() {}, true);
    }
}
```

## Generate a screenshot of the first page of a PDF document

Useful when you need to create a documents gallery where showing a preview of every document.

**Syntax**

```javascript
var json = utils.convertPdfToImage(pdfDirId, pdfFileName, imgDirId, imageExtension, scale);
```

**Details**

```text
pdfDirId - folder identifier, where the input PDF file is already stored 
pdfFileName - PDF file name, stored in the folder identified by pdfDirId 
imgDirId- folder identifier, where the image will be saved 
imgExtension- image format; allowed formats: png 
scale- positive number <= 1.0, used to define how much to reduce the PDF; e.g. 0.3; the more is reduced, 
the smaller the image is 
The method returns the image name.
```

**Example**

```javascript
var fileName = utils.convertPdfToImage(19,"a1.pdf",9,"png",0.3);
utils.log("FILE: "+fileName,"WARN");
```

