# Dialogs

## showConfirmDialog\(args,callbackSuccess\(outcome\),callbackCancel\(outcome\)\) <a id="showconfirmdialog"></a>

Show a not blocking confirm dialog, with an "Ok" and "Cancel" buttons; a callback function is invoked when closing the window: the outcome parameter is filled with "Y" \("Ok" button pressed\) or "N" \("Cancel" button pressed\).  
Args is a JSobject containing optional settings:

| Argument | Description |
| :--- | :--- |
| title | dialog title |
| subtitle | dialog subtitle |
| heightPopup | dialog height |
| titleButtonSuccess | "OK" button text |
| titleColorButtonSuccess | "OK" button foreground color |
| colorButtonSuccess | "OK" button background color |
| titleColor | title foreground color |
| subtitleColor | subtitle foreground color |
| backgroundColor | dialog background color |
| titleButtonCancel | "Cancel" button text |
| titleColorButtonCancel | "Cancel" button foreground color |
| colorButtonCancel | "Cancel" button background color |
| placeholderInputValue | placeholder text to show inside an input field to include in the window; it is an alternative to presetInputValue |
| presetInputValue | default value to show inside an input field to include in the window; it is an alternative to placeholderInputValue |
| keyTypeInputValue | input field type; allowed values in iOS: “DEFAULT”, “PASSWORD”, “ASCIICAPABLE”, “NUMBERSANDPUNCTUATION”, “URL”, “NUMBER”, “PHONE”, “NAMEPHONE”, “EMAIL”, “DECIMAL”, “TWITTER”, “WEBSEARCH" |

**Example**

```javascript
var risp = new Object();
risp.title = "This is the window title";
risp.subtitle = "This is the window sub-title, if needed";
risp.titleButtonSuccess = "Ok"; // this is the text for the ok button
var callbackSuccess = function(outcome) {
};
var callbackCancel = function(outcome) {
};
showConfirmDialog(risp,"callbackSuccess","callbackCancel"); // the second argument is the name of the callback function to invoke when the user would press on the Ok button; you have to pass "" if no callback function is needed. The third argument is related to the name of the callback function to invoke when the user would press on the Cancel button.
```

Pay attention that you have to specify the name of the function, NOT the function itself as the second/third argument of this method. Also, the parameter is MANDATORY, pass "" if nocallback is needed.

## showMessageDialog\(args,callbackSuccess\)

Show a not blocking message dialog, with an "Ok" button; a callback function is invoked when closing the window.  
Args is a JSobject containing optional settings:

| Argument | Description |
| :--- | :--- |
| title | dialog title |
| subtitle | dialog subtitle |
| heightPopup | dialog height |
| titleButtonSuccess | "OK" button text |
| titleColorButtonSuccess | "OK" button foreground color |
| colorButtonSuccess | "OK" button background color |
| titleColor | title foreground color |
| subtitleColor | subtitle foreground color |
| backgroundColor | dialog background color |
| placeholderInputValue | placeholder text to show inside an input field to include in the window; it is an alternative to presetInputValue |
| presetInputValue | default value to show inside an input field to include in the window; it is an alternative to placeholderInputValue |
| keyTypeInputValue | input field type; allowed values in iOS: “DEFAULT”, “PASSWORD”, “ASCIICAPABLE”, “NUMBERSANDPUNCTUATION”, “URL”, “NUMBER”, “PHONE”, “NAMEPHONE”, “EMAIL”, “DECIMAL”, “TWITTER”, “WEBSEARCH" |

**Example**

```javascript
var risp = new Object();
risp.title = "This is the window title";
risp.subtitle = "This is the window sub-title, if needed";
risp.titleButtonSuccess = "Ok"; // this is the text for the ok button
showMessageDialog(risp,""); // the second argument is the name of the callback function to invoke when the user would press on the Ok button; you can pass "" if no callback function is needed.
```

Pay attention that you have to specify the name of the function, NOT the function itself as the second argument of this method.

## showInputDialog\(args,callbackSuccess\(outcome\),callbackCancel\(outcome\)\)

show a not blocking input dialog, with an "Ok" and "Cancel" buttons and an input text field; the input field is pre-filled with the default input value, if available; a callback function is invoked when closing the window: the outcome parameter is filled with the value typed by the user

Args is a JSobject containing optional settings:

| Argument | Description |
| :--- | :--- |
| title | dialog title |
| subtitle | dialog subtitle |
| heightPopup | dialog height |
| titleButtonSuccess | "OK" button text |
| titleColorButtonSuccess | "OK" button foreground color |
| colorButtonSuccess | "OK" button background color |
| titleColor | title foreground color |
| subtitleColor | subtitle foreground color |
| backgroundColor | dialog background color |
| titleButtonCancel | "Cancel" button text |
| titleColorButtonCancel | "Cancel" button foreground color |
| colorButtonCancel | "Cancel" button background color |
| placeholderInputValue | placeholder text to show inside an input field to include in the window; it is an alternative to presetInputValue |
| presetInputValue | default value to show inside an input field to include in the window; it is an alternative to placeholderInputValue |
| keyTypeInputValue | input field type; allowed values in iOS: “DEFAULT”, “PASSWORD”, “ASCIICAPABLE”, “NUMBERSANDPUNCTUATION”, “URL”, “NUMBER”, “PHONE”, “NAMEPHONE”, “EMAIL”, “DECIMAL”, “TWITTER”, “WEBSEARCH" |

**Example**

```javascript
var opts = new Object();
opts['title'] = 'Invia mail';
opts['subtitle'] = 'To:';
opts['keyTypeInputValue'] = 'DEFAULT';
opts['titleButtonSuccess'] = 'Send';
opts['titleButtonCancel'] = 'Cancel';

var callbackSuccess = function(outcome) {};

var callbackCancel = function(outcome) {};

showInputDialog(
 opts,
 "callbackSuccess",
 "callbackCancel"
);
```

## showListDialog\(args,callbackSuccess\(itemIndex\),callbackCancel\) <a id="showlistdialog"></a>

Show a dialog containing a list of descriptions. The user can choose one of more of them and a callback function is invoked with the selected items as argument.  
Args is a JSobject containing optional settings:

| Argument | Description |
| :--- | :--- |
| title | dialog title |
| subtitle | dialog subtitle |
| list | Array containing the objects, one for each row |
| attrName | row identifier; it must be one of the object attributes |
| cancelAllowed | allowed values are "Y" o "N" |
| titleButtonCancel | cancel button text |
| heightPopup | dialog height |
| titleColorButtonCancel | cancel button foreground color |
| colorButtonCancel | cancel button background color |
| titleColor | dialog title color |
| subtitleColor | dialog subtitle color |
| backgroundColor | dialog background color |
| rowTextAlign | LEFT\|RIGHT\|CENTER text align inside a row |

**Example**

```javascript
var descriptions = [
  { description: "Item One", code: "Code1" },
  { description: "Item Two", code: "Code2" }
];

var fun = function(ris) {
  // ris contains the INDEX of the selected item
  log(descriptions[ris].code;
};
var opts = {};
opts.title = "Select an item";
opts.list = descriptions;
opts.attrName = "description";
opts.cancelAllowed = "Y";
showListDialog(opts,"fun");
```

Pay attention that you have to specify the name of the function, NOT the function itself as the second argument of this method.

## showContactsList\(dataToShow,callback\(array\)\)

Show the list of contacts from the local Agenda.  
Required arguments:

| Argument | Description |
| :--- | :--- |
| dataToShow type of data to show | it can be a phone number or an email address ; allowed values: "telephone" or "emails"\) |

## shareText\(Text\)

Open the dialog for share the text. The dialog content depends on the specific mobile platform \(Android or iOS\).  
A typical usage of this method isfor share a text on link by Whatsapp o the Email app.

## shareText\(Text, imageUrl, appType\)

Open the dialog for share the text. The dialog content depends on the specific mobile platform \(Android or iOS\).  
A typical usage of this method isfor share a text on link by Whatsapp o the Email app.

| Argument | Description |
| :--- | :--- |
| text | Text to share, can be a link |
| imageUrl | use only if attType is EMAIL to attach an image to the email |
| appType | EMAIL, FACEBOOK, WHATSAPP, SMS, ALL |

## openRemoteDocument\(fileName,url\) <a id="openremotedocument"></a>

open a remote document in a full-size window.  
Required parameters are:

| Parameter | Description |
| :--- | :--- |
| fileName | file name to show on top of the window |
| url | a remote URL to invoke, in order to get the document |

A possibleusage of this method is combined with getBaseURL\(\) and getToken\(\) methods, used to get a document fromthe Platform central site,as for a PDF report.

If this is your need, this is the typical js code to include:

```javascript
var url = 
  getBaseURL()+
  '/reports/getReport?'+
  'applicationId=...&amp;appId=...&amp;'+
  'reportName=reports/myreporttemplate.jasper&amp;'+
  'datastoreId=...&amp;reportFormat=PDF&amp;'+
  'restfulToken='+getToken();

var json = getWebContent(url,"GET","application/json",null);
var response = eval("("+json+")");
if (response.success) {
    var title = "Report.pdf";
    var url = 
      getBaseURL()+'/showDocument?ì+
      'applicationId=MOBILE11&amp;title='+title+
      '&amp;docId='+response.data.docId+
      '&amp;exportFormat='+response.data.exportFormat+
      '&amp;restfulToken='+getToken();

    openRemoteDocument(title,url);
}
```

## scanQRCode\(callbackSuccess, callbackCancel, callbackError\);

Open a QR code reader and execute the scan.

Required arguments:

* callbackSuccess – function name which will be invoked in case of successful scan; an argument is passed to the function: a json with data just read, expressed as a string
  * QRCode with a VCARD:

    ```javascript
    {
     "displayValue": "NameSurname",
     "format": "QR_CODE",
     "rawValue": "BEGIN:VCARD\nVERSION:2.1\nFN:NameSurname\nN:Surname;Name\nTITLE:Mr\nTEL;CELL:+3912345678\nTEL;WORK;VOICE:+ 3912345678\nTEL;HOME;VOICE:+ 3912345678\nEND:VCARD\n",
     "valueFormat": "CONTACT_INFO"
    }
    ```

  * QRCode with a URL:

    ```javascript
    {
     "displayValue":"http://www.sinesy.it",
     "format": "QR_CODE",
     "rawValue":"http://www.sinesy.it",
     "valueFormat":"URL"
    }
    ```

  * Note 1: iOs does not support valueFormat
  * Note 2: in iOs there is not difference between displayValue and rawValue
* callbackSuccess – function name which will be invoked in case the user interrupts the scan
* callbackError – function name which will be invoked in case of failed scan; an argument is passed to the function: the error code, expressed as a stringSupported barcodes are: EAN-13, EAN-8, UPC-A, UPC-E, Code-39, Code-93, Code-128, ITF, Codabar, QR Code, Data Matrix, PDF-417, AZTEC

## scanBarcode\(callbackSuccess, callbackCancel, callbackError\);

Open a barcode reader and execute the scan.  
The supported format are:EAN-13, EAN-8, UPC-A, UPC-E, Code-39, Code-93, Code-128, ITF, Codabar, QR Code, Data Matrix, PDF-417, AZTEC, note that iOS does not support:Codabar andUPC-A.  
Required arguments:

* callbackSuccess – function name which will be invoked in case of successful scan; an argument is passed to the function: a json with data just read, expressed as a string
  * EAN13 with a PRODUCT:

    ```javascript
    {
     "displayValue":"5901234123457",
     "format": "EAN_13",
     "rawValue":"5901234123457",
     "valueFormat":"PRODUCT"
    }
    ```

  * Note 1: iOs does not support valueFormat
  * Note 2: in iOs there is not difference between displayValue and rawValue
* callbackSuccess – function name which will be invoked in case the user interrupts the scan
* callbackError – function name which will be invoked in case of failed scan; an argument is passed to the function: the error code, expressed as a stringSupported barcodes are: EAN-13, EAN-8, UPC-A, UPC-E, Code-39, Code-93, Code-128, ITF, Codabar, QR Code, Data Matrix, PDF-417, AZTEC

## openCamera\(callback\);

Open the camera to take a photo. In case it has been successfully taken,the callback will be invoked. The callback method will have the absolute path to the local image just stored.  
Required arguments:

| Argument | Description |
| :--- | :--- |
| callback | function name which will be invoked in case the photo has been successfully taken; an argument is passed to the function: the absolute path of the image just saved, expressed as a string |

**Example**

```javascript
var getPhoto = function(imagePath) {
  // do something with the image...
}

openCamera("getPhoto");
```

## openGallery\(callback\);

Open the local galleryto choosea photo. When the image is selected,the callback will be invoked. The callback method will have the absolute path to the local image just selected.  
Required arguments:

| Argument | Description |
| :--- | :--- |
| callback | function name which will be invoked when an image from the gallery is chosen;an argument is passed to the function: the absolute path of the image just selected, expressed as a string |

**Example**

```javascript
var getPhoto = function(imagePath) {
  // do something with the image...
}

openGallery("getPhoto");
```

## shareDocument\(path,filename\);

Open a dialog through which the end user can choose an app where sharing the specified file.

Note: In Android you can share files only if these are stored locally in app filesystem in a folder named "download" folder. If you need to share a file not located there you to contact the Android administrator.

Required arguments:

| Argument | Description |
| :--- | :--- |
| path | absolute path where the file to share is located |
| filename | name of the file to download, located in the specified absolute path |

## downloadDocument\(path,filename\);

Open a dialog through which the end user can download locally the specified file.

Required arguments:

| Argument | Description |
| :--- | :--- |
| path | absolute path where the file to download is located |
| filename | name of the file to download, located in the specified absolute path |

## **showToast\(message\)**

A toast provides simple feedback about an operation in a small popup. It only fills the amount of space required for the message and the current activity remains visible and interactive. Toasts automatically disappear after a timeout.

## showDateRangePicker\(title,minDateMS,maxDateMS, openAtMS,selectionFromMS,selectionToMS,positiveCallback, cancelCallback\)

Show a picker dat let users select a range of dates.

Required arguments:

| Argument | Description |
| :--- | :--- |
| title | Title of the dialog |
| minDateMs | Min allowed date in milliseconds |
| maxDateMS | Max allowed date in milliseconds |
| openAtMs | Open calendar in this date |
| selectionFromMS | Preselection start date |
| selectionToMS | Preselected end date |
| positiveCallback | positive callback |
| cacelCallback | cancel callback |

**Example**

```text
var positiveCallback = function(firstMS, secondMS){
    showToast("OK, first: " + new Date(first) + " second: " + new Date(second));
}

var cancelCallback = function(){
    showToast("cancel");
}

showDateRangePicker("Data scontrino", 0, 0, 0, 0, 0, "positiveCallback", "cancelCallback");
```

