# Google GSuite

## Google Calendar - adding an event

Adding an event to Google Calendar.

**Syntax**:

```javascript
var calendarEvent = utils.addGoogleCalendarEvent(String title, Date beginDate, Date endDate);
```

**Description**:

| Argument  | Description        |
| --------- | ------------------ |
| title     | Event title        |
| beginDate | starting date+time |
| endDate   | ending date+time   |

This event is created for the calendar associated to the current logged user.

The resulting javascript object has the following structure:

```
String id;
String title;
String description;
Date beginDate;
Date endDate;
EventAttendee creator;
List<EventAttendee>attendees;
String location;
String url;
```

where "attendees" is a list of people invited to the event; each javascript object in this list has the following structure:

```
String id;
String displayName;
String email;
String comment;
Boolean optional;
Boolean organizer;
Boolean creator;
String response;
Boolean resource;
```

## Google Calendar - adding an event with more customizations

Adding an event to Google Calendar.

**Syntax**:

```javascript
var calendarEvent = utils.addGoogleCalendarEventWithSettings(
  String title, 
  Date beginDate, 
  Date endDate,
  String description,
  String location,
  String calendarId,
  String creatorEmail,
  String... attendeeEmails
);
```

**Description**:

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                                                                         |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| title          | Event title                                                                                                                                                                                                                                                                                                                                                                                                         |
| beginDate      | starting date+time                                                                                                                                                                                                                                                                                                                                                                                                  |
| endDate        | ending date+time                                                                                                                                                                                                                                                                                                                                                                                                    |
| description    | additional description to include in the event                                                                                                                                                                                                                                                                                                                                                                      |
| location       | can be null; it can be a complete address or a city, a province, etc.                                                                                                                                                                                                                                                                                                                                               |
| calendarId     | can be null; if not filled, the default calendar for the current logged user will be used; if set, it is the calendar id where creating the event; the current admin user must have grants to save data into that calendar:; in order to retrieve the calendar id, go to Google Calendar, right click on the calendar on the list on the left and choose "Settings and sharing"; finally, search for "Calendar ID". |
| creatorEmail   | can be null; if not filled, the current logged user email will be used; if set, this will be the owner of the event (if the specified email address in owner of the specified calendar)                                                                                                                                                                                                                             |
| attendesEmails | a Javascript array containing a list of email addresses, representing people invited to the event                                                                                                                                                                                                                                                                                                                   |

This event is created for the calendar associated to the specified user/calendar.

The resulting javascript object has the following structure:

```
String id;
String title;
String description;
Date beginDate;
Date endDate;
EventAttendee creator;
List<EventAttendee>attendees;
String location;
String url;
```

where "attendees" is a list of people invited to the event; each javascript object in this list has the following structure:

```
String id;
String displayName;
String email;
String comment;
Boolean optional;
Boolean organizer;
Boolean creator;
String response;
Boolean resource;
```

## Google Calendar - adding an event with conference

Adding an event to Google Calendar with a conference linked to it. A conference can be:

* Hangouts for consumers ([http://hangouts.google.com](http://hangouts.google.com))&#x20;
* Classic Hangouts for G Suite users ([http://hangouts.google.com](http://hangouts.google.com))
* Google Meet ([http://meet.google.com](http://meet.google.com))&#x20;
* "addOn" for 3P conference providers

**Syntax**:

```javascript
var calendarEvent = utils.addGoogleCalendarEventWithConference(
  String title, 
  Date beginDate, 
  Date endDate,
  String description,
  String location,
  String calendarId,
  String type,
  String creatorEmail,
  String... attendeeEmails
);
```

**Description**:

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| title          | Event title                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| beginDate      | starting date+time                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| endDate        | ending date+time                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| description    | additional description to include in the event                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| location       | can be null; it can be a complete address or a city, a province, etc.                                                                                                                                                                                                                                                                                                                                                                                                                    |
| calendarId     | can be null; if not filled, the default calendar for the current logged user will be used; if set, it is the calendar id where creating the event; the current admin user must have grants to save data into that calendar:; in order to retrieve the calendar id, go to Google Calendar, right click on the calendar on the list on the left and choose "Settings and sharing"; finally, search for "Calendar ID".                                                                      |
| type           | <p>link to the event a conference; allowed values are: </p><ul><li>"eventHangout" for Hangouts for consumers (<a href="http://hangouts.google.com">http://hangouts.google.com</a>) </li><li>"eventNamedHangout" for classic Hangouts for G Suite users (<a href="http://hangouts.google.com">http://hangouts.google.com</a>)</li><li>"hangoutsMeet" for Google Meet (<a href="http://meet.google.com">http://meet.google.com</a>) </li><li>"addOn" for 3P conference providers</li></ul> |
| creatorEmail   | can be null; if not filled, the current logged user email will be used; if set, this will be the owner of the event (if the specified email address in owner of the specified calendar)                                                                                                                                                                                                                                                                                                  |
| attendesEmails | a Javascript array containing a list of email addresses, representing people invited to the event                                                                                                                                                                                                                                                                                                                                                                                        |

This event is created for the calendar associated to the specified user/calendar.

The resulting javascript object has the following structure:

```
String id;
String title;
String description;
Date beginDate;
Date endDate;
EventAttendee creator;
List<EventAttendee>attendees;
String location;
String url;
String hangoutLink;
```

where "attendees" is a list of people invited to the event; each javascript object in this list has the following structure:

```
String id;
String displayName;
String email;
String comment;
Boolean optional;
Boolean organizer;
Boolean creator;
String response;
Boolean resource;
```

## Google Calendar - modifying an event

Change the event title or timing for a Google Calendar event.

**Syntax**:

```javascript
var calendarEvent = utils.modifyGoogleCalendarEvent(String calendarEventId, String title, Date beginDate, Date endDate);
```

**Description**:

| Argument        | Description                                                                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| calendarEventId | the event id, which is defined when an event is created the first time and available in the "calendar event" js object returned by the previous method. |
| title           | event title                                                                                                                                             |
| beginDate       | starting date+time                                                                                                                                      |
| endDate         | ending date+time                                                                                                                                        |

This event is changed in the calendar associated to the current logged user.

## Google Calendar - deleting an event

Delete and already existing event in the Google Calendar.

**Syntax**:

```javascript
utils.deleteGoogleCalendarEvent(String calendarEventId);
```

**Description**:

| Argument        | Description                                                                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| calendarEventId | the event id, which is defined when an event is created the first time and available in the "calendar event" js object returned by the previous method. |

This event is removed from the calendar associated to the current logged user.

## Google Drive - create a folder

**Syntax**:

```javascript
var file = utils.createGoogleDriveFolder(userId, folderName, parents, description);
```

**Description:**

| Argument    | Description                                                                                                                                                                                                             |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId      | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| folderName  | folder name                                                                                                                                                                                                             |
| parents     | list of folder parents: the list of folders from the root must be specified                                                                                                                                             |
| description | optional folder description                                                                                                                                                                                             |

The method returns a javascript object having the following structure:

```
   String id;
   String title;
   String description;
   Long size;
   String mimeType;
   String path;
   String pathType;
   String iconPath;
   String iconPathType;
   Boolean folder;
   String owner;
   String md5hash;
   Map<String,String> additionalAttributes = new HashMap<String,String>();
```

The "id" value represents a unique identifier for the folder and can be used later to manage it (rename, delete, etc.)

## Google Drive - delete a file or folder

**Syntax**:

```javascript
var file = utils.deleteGoogleDriveFile(userId, fileId, skipTrash);
```

**Description**:

| Argument  | Description                                                                                                                                                                                                                 |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId    | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user.     |
| fileId    | folder identifier (it is the "id" attribute of the js object returned by the previous method)                                                                                                                               |
| skipTrash | boolean flag used to define how a folder deletion will be managed: true to permanently delete the folder; false to mark the folder as deleted and moved to the special "trash" folder (in such a case, it can be restored). |

## Google Drive - add permissions to folder

**Syntax**:

```javascript
var file = utils.addPermissionsToGoogleDriveFolder( 
  userId,
  folderId,
  type,  value,  fileRole,  folderRole,
  additionalRoles, 
  updateBaseFolder, 
  recursive, 
  sendNotifications,
  message
);
```

**Description**:

| Argument          | Description                                                                                                                                                                                                             |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId            | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| folderId          | folder id; permissions will be set for this folder and maybe to subfolders as well, according to the "recursive" boolean flag                                                                                           |
| type              | the type of sharing, one between “user”, “group”, “domain” or “default”                                                                                                                                                 |
| value             | the email of the user/group or the domain name                                                                                                                                                                          |
| fileRole          | the role for files, one of “reader”, “writer” or “owner”                                                                                                                                                                |
| folderRole        | the role for folders, one of “reader”, “writer” or “owner                                                                                                                                                               |
| additionalRoles   | list of additional roles; optional string, for example \[“commenter”]                                                                                                                                                   |
| updateBaseFolder  | boolean flag; if true applies permissions to the base folder identified by folderId                                                                                                                                     |
| recursive         | boolean flag: if set to true, apply the specified permissions to all subfolders as well                                                                                                                                 |
| sendNotifications | boolean flag; if set to true, an email message will be sent to all destinations; the email message is defined through the next argument                                                                                 |
| message           | email notification message                                                                                                                                                                                              |

## Google Drive - set permissions to file

**Syntax**:

```javascript
var file = utils.setGoogleDriveFilePermissions(
 userId,
 fileId,
 type, 
 value, 
 role, 
 additionalRoles,
 sendNotifications, 
 message
);
```

**Description**:

| Argument          | Description                                                                                                                                                                                                             |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId            | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId            | file id                                                                                                                                                                                                                 |
| type              | the type of sharing, one between “user”, “group”, “domain” or “default”                                                                                                                                                 |
| value             | the email of the user/group or the domain name                                                                                                                                                                          |
| role              | the role for files, one of “reader”, “writer” or “owner”                                                                                                                                                                |
| additionalRoles   | list of additional roles; optional string, for example \[“commenter”]                                                                                                                                                   |
| updateBaseFolder  | boolean flag; if true applies permissions to the base folder identified by folderId                                                                                                                                     |
| sendNotifications | boolean flag; if set to true, an email message will be sent to all destinations; the email message is defined through the next argument                                                                                 |
| message           | email notification message                                                                                                                                                                                              |

## Google Drive - set property to a file

**Syntax**:

```javascript
var file = utils.addGoogleDriveFileProperty(userId, fileId, key, value, visibility);
```

**Description**:

| Argument   | Description                                                                                                                                                                                                             |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId     | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId     | file identifier                                                                                                                                                                                                         |
| key        | property identifier                                                                                                                                                                                                     |
| value      | property value                                                                                                                                                                                                          |
| visibility | allowed values: "PRIVATE" or "PUBLIC"                                                                                                                                                                                   |

## Google Drive - remove a property from a file

**Syntax**:

```javascript
var file = utils.deleteGoogleDriveFileProperty(userId, fileId, key);
```

**Description**:

| Argument | Description                                                                                                                                                                                                             |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId   | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId   | file identifier                                                                                                                                                                                                         |
| key      | property identifier                                                                                                                                                                                                     |

## Google Drive - get folder/file information

**Syntax**:

```javascript
var fileInfo = utils.getGoogleDriveFileInfo(userId, fileId);
```

**Description**:

| Argument | Description                                                                                                                                                                                                             |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId   | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId   | file identifier                                                                                                                                                                                                         |

The method returns a javascript object having the following structure:

```
   String id;
   String title;
   String description;
   Long size;
   String mimeType;
   String path;
   String pathType;
   String iconPath;
   String iconPathType;
   Boolean folder;
   String owner;
   String md5hash;
   Map<String,String> additionalAttributes = new HashMap<String,String>();
```

## Google Drive - set file attributes

Change the default file attributes, like trashed, restricted, viewed, etc.

**Syntax**:

```javascript
var fileInfo = utils.setGoogleDriveFileAttributes(userId, fileId, fileAttributes)
```

**Description**:

| Argument       | Description                                                                                                                                                                                                             |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId         | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId         | file identifier                                                                                                                                                                                                         |
| fileAttributes | a javascript object containing the file attributes to set                                                                                                                                                               |

The "fileAttributes" javascript object must have the following structure:

```
  Boolean starred;
  Boolean trashed;
  Boolean restricted;
  Boolean viewed;
  Boolean writersCanShare;
```

## Google Drive - get file revisions

It is possible to upload the same file multiple times; each time the new version will replace the previous one. However, the older versions are still available; this method allows to access to the previous versions of the file.

**Syntax**:

```javascript
var revisions = utils.getGoogleDriveFileRevisions(userId, fileId);
```

**Description**:

| Argument | Description                                                                                                                                                                                                             |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId   | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId   | file identifier                                                                                                                                                                                                         |

The method returns a list of javascript objects, where each object (related to a revision) has the following structure:

```
  String version;
  String id;
  String date;
  String owner;
  Date modifyDate;
```

## Google Drive - get folder content

Retrieve the folder content, in terms of files or subfolders.

**Syntax**:

```javascript
var files = utils.getGoogleDriveFolderContents(userId, folderId, query, trashed);
```

**Description**:

| Argument | Description                                                                                                                                                                                                             |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId   | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| folderId | folder identifier                                                                                                                                                                                                       |
| query    | optional query used to filter the folder content; see [https://developers.google.com/drive/web/search-parameters](https://developers.google.com/drive/web/search-parameters) for additional details                     |
| trashed  | boolean flag; true to fetch also deleted (trashed) files and folders.                                                                                                                                                   |

The method returns a Java List containing Java objects, where each object (related to a file/folder) has the following structure:

```
String id;
String title;
String description;
Date beginDate;
Date endDate;
EventAttendee creator;
List<EventAttendee>attendees;
String location;
String url;
```

Example:

```
var files = ...
for(var i=0;i<files.size();i++) {
  var file = files.get(i);
  var id = file.id;
  //...
}
```

## Google Drive - get folder content (ids)

Retrieve the folder content, in terms of files or subfolders, each expressed only through its id.

**Syntax**:

```javascript
var fileIds = utils.getGoogleDriveFolderContentsIds(userId, folderId, query, trashed);
```

**Description**:

| Argument | Description                                                                                                                                                                                                             |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId   | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| folderId | folder identifier                                                                                                                                                                                                       |
| query    | optional query used to filter the folder content; see [https://developers.google.com/drive/web/search-parameters](https://developers.google.com/drive/web/search-parameters) for additional details                     |
| trashed  | boolean flag; true to fetch also deleted (trashed) files and folders.                                                                                                                                                   |

The method returns a list of file/folder ids.

## Google Drive - duplicate a file

Starting from an already existing document in Drive, duplicate it with another name in the specified destination folder..

**Syntax**:

```javascript
var paginatedList = utils.duplicateGoogleDriveFile(
  String userId, 
  String sourceFileId, 
  String destinationFolderId, 
  String newFileName, 
  Boolean copyPermissions
)
```

**Description**:

| Argument            | Description                                                              |
| ------------------- | ------------------------------------------------------------------------ |
| userId              | email for the user used to create the file                               |
| sourceFileId        | document id related to the already existing file in Drive to duplicate   |
| destinationFolderId | folder id where copying the file                                         |
| newFileName         | the new file name to assign to the duplicated document                   |
| copyPermissions     | boolean flag used to inherit permissions assigned to the source document |

The method returns a Java object, having the following structure:

```
String id;
String title;
String description;
Date beginDate;
Date endDate;
EventAttendee creator;
List<EventAttendee>attendees;
String location;
String url;
```

## Google Drive - get folder content, one page a time

Retrieve the folder content, in terms of files or subfolders, one page a time. It is possible to scroll along the whole content, by working through "maxPageResults" and "pages". This method can be helpful within a javascript business component for list, in case you want to show in a paginated grid the folder content and navigate through it, one page a time.

**Syntax**:

```javascript
var paginatedList = utils.searchInGoogleDrive(maxPageResults, pages, String nextPageToken, folderId, query, trashed);
```

**Description**:

| Argument       | Description                                                                                           |
| -------------- | ----------------------------------------------------------------------------------------------------- |
| maxPageResults | max number of files/subfolders to get back, that will fill in the page                                |
| pages          | page to read                                                                                          |
| nextPageToken  | token to pass forward to the next invocation of this method, in order to get the next page of results |
| folderId       | folder identifier to use when retrieving the content                                                  |
| query          | optional query to use to filter folder content                                                        |
| trashed        | boolean flag; true to fetch also deleted (trashed) files and folders.                                 |

This method returns a javascript object containing the following structure:

```
  List<T> list;
  String nextPageToken;
```

## Google Drive - move file/folder

Move the specified folder, by specifying new parent folders.

**Syntax**:

```javascript
var file = utils.modifyGoogleDriveFileParents(userId, fileId, parentsToAdd, parentsToRemove);
```

**Description**:

| Argument        | Description                                                                                                                                                                                                             |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId          | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId          | folder identifier                                                                                                                                                                                                       |
| parentsToAdd    | a comma separated list of folder ids that will be added as parents of the file/folder. Can be empty                                                                                                                     |
| parentsToRemove | a comma separated list of folder ids that will be removed as parents of the file/folder. Can be empty                                                                                                                   |

## Google Drive - move file

Move the specified folder, by specifying new parent folders.

**Syntax**:

```javascript
var file = utils.moveGoogleDriveFile(userId, fileId, newParents);
```

**Description**:

| Argument   | Description                                                                                                                                                                                                             |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId     | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId     | file identifier                                                                                                                                                                                                         |
| newParents | a comma separated list of folder ids that will be added as parents of the file/folder. Can be empty                                                                                                                     |

## Google Drive - upload a file from the server file system

Upload into Drive the specified file stored in the server file system.

**Syntax**:

```javascript
var file = utils.uploadAndRenameGoogleDriveFileInNamedFolderFromFS(userId, fsPath, baseFolderId,
 folderName, createFolderIfNotExists, fileName, deleteFsFile);
```

**Description**:

| Argument                | Description                                                                                                                                                                                                             |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId                  | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fsPath                  | the full path of the file to upload. This path is in the server where 4WS.Platform is installed                                                                                                                         |
| baseFolderId            | the id of the Drive folder where the named folder must be created                                                                                                                                                       |
| folderName              | a name of the folder where the file must be uploaded to. This folder must be in the base folder                                                                                                                         |
| createFolderIfNotExists | true or false. Whether or not to create the folderName folder if not exists in the base folder                                                                                                                          |
| fileName                | the new name of the uploaded file. If null the original file name is used                                                                                                                                               |
| deleteJsFile            | true or false. Specifies if the file on file system must be deleted or not after upload to Drive                                                                                                                        |

## Google Drive - replace an already existing Drive file from the server file system

Upload the specified file stored in the server file system.

**Syntax**:

```javascript
var file = utils.updateGoogleDriveFileFromFS(userId, fileId, fsPath, deleteFsFile, newRevision)
```

**Description**:

| Argument     | Description                                                                                                                                                                                                             |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId       | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId       | file identifier, related to the already existing file in Drive                                                                                                                                                          |
| fsPath       | the full path of the file to upload. This path is in the server where 4WS.Platform is installed                                                                                                                         |
| deleteFsFile | true or false. Specifies if the file on file system must be deleted or not after upload to Drive                                                                                                                        |
| newRevision  | true/false. If true the file will be new version of a possible homonymous file in the destination folder. If false two files with the same name will be present in the destination folder                               |

## Google Drive - download a file from Drive

Download a file from Drive and save it on the server file system.

**Syntax**:

```javascript
utils.downloadFileFromGoogleDrive(userId, fileId, localPath, fileName);
```

**Description**:

| Argument  | Description                                                                                                                                                                                                             |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId    | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId    | file identifier, related to the already existing file in Drive                                                                                                                                                          |
| localPath | the full path on the server file syste, where saving the file                                                                                                                                                           |
| fileName  | fileName to use when saving the file on the specified "localPath"                                                                                                                                                       |

## Google Drive - get an URL to download a file from Drive web page

Get an URL related to the Drive file to download.

**Syntax**:

```javascript
var url = utils.getGoogleDriveFileDownloadURL(userId, fileId);
```

**Description**:

| Argument | Description                                                                                                                                                                                                             |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId   | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId   | file identifier, related to the already existing file in Drive                                                                                                                                                          |

## Google Drive - get an URL to open a file from GDrive web page

Returns the URL to open a file from Google Drive. This URL shoud be opened in a browser and must be used for files in Google format (documents, spreadsheets, presentations, forms and so on).

**Syntax**:

```javascript
var url = utils.getGoogleDriveFileOpenURL(userId, fileId);
```

**Description**:

| Argument | Description                                                                                                                                                                                                             |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| userId   | optional username; if not specified, the userEmail value set as application property for Google service account will be used as owner for this folder. If this argument is defined, the folder owner will be this user. |
| fileId   | file identifier, related to the already existing file in Drive                                                                                                                                                          |
