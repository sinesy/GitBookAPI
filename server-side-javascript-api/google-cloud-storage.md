# Google Cloud Storage

## Create a bucket on Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to create a bucket in GCS in a specific **location** and storage **class**. The location identifies the geographical position of the bucket around the world. For more information see:

{% content-ref url="google-cloud-storage.md" %}
[google-cloud-storage.md](google-cloud-storage.md)
{% endcontent-ref %}

The storage class defines how fast will be the file retrieval. For more information see:

{% content-ref url="google-cloud-storage.md" %}
[google-cloud-storage.md](google-cloud-storage.md)
{% endcontent-ref %}

Be aware that the **bucket name must be unique** at Google level and must contain only letters and - (no underscore symbols), so it would be a good practice to use composed names starting with the googleprojectname-applicationame-somethingelse.

**Syntax**

```
var descriptor = utils.createGoogleCloudStorageBucket(
   project, 
   bucketName, 
   bucketLocation,
   storageClass
);
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                              |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| project        | String: Google project name                                                                                                                                                                                                                              |
| bucketName     | String: Google level unique name; use only letters and - as separator                                                                                                                                                                                    |
| bucketLocation | <p>String: identifies the geographical position  where creating the bucket; allowed values are: <br>US, EU, ASIA. Other locations are supported. See https://cloud.google.com/storage/docs/bucket-locations </p>                                         |
| storageClass   | String (optional - storage class: STANDARD, NEARLINE and DURABLE\_REDUCED\_AVAILABILITY. See https://cloud.google.com/storage/docs/storage-classes                                                                                                       |
| returned value | <p>in case of errors, an exception fill be fired; the returned value is a javascript object having the following structure: </p><p>{ </p><p>  name: "...", // bucket name</p><p>  type: "...", // bucket type</p><p>  versioned: true|false </p><p>}</p> |

## Get the bucket descriptor from Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to get the description of an already existing bucket in GCS.&#x20;

**Syntax**

```
var descriptor = utils.getGoogleCloudStorageBucket(bucketName);
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                              |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| bucketName     | String: Google level unique name; use only letters and - as separator                                                                                                                                                                                    |
| returned value | <p>in case of errors, an exception fill be fired; the returned value is a javascript object having the following structure: </p><p>{ </p><p>  name: "...", // bucket name</p><p>  type: "...", // bucket type</p><p>  versioned: true|false </p><p>}</p> |

## Get the file descriptor from Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to get the description of an already existing file stored inside a Google Cloud Storage bucket.

**Syntax**

```
var descriptor = utils.getGoogleCloudStorageObject(bucketName,objectName);
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                                                            |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| bucketName     | String: bucket name where the file to analyze is located                                                                                                                                                                                                                                                                                                                                               |
| objectName     | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt"                                                                                                                                                                                                                                            |
| returned value | <p>in case of errors, an exception fill be fired; the returned value is a javascript object having the following structure: </p><p>{ </p><p>  id: "...", // file identifier</p><p>  title: "...", // file name</p><p>  mimeType: "...", // mime type for the file</p><p>  pathType: "GCS",</p><p> size: ..., // file size</p><p> md5hash: "...", // hash key representing the file content</p><p>}</p> |

## Get a public (temporary) URL for accessing a Cloud Storage file

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to generate a public URL to access from anywhere an already existing file stored inside a Google Cloud Storage bucket.

**Syntax**

```
var urlString = utils.getGoogleCloudStorageSignedURL(
   verb, 
   expiration, 
   bucketName, 
   objectName, 
   mime
);
```

**Description**

| Argument       | Description                                                                                                                                                        |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| verb           | String: HTTP method to use to get the file; set it to "GET"                                                                                                        |
| expiration     | long: URL expiration time, expressed in milliseconds; for example, to set an URL valid for the next 10 minutes, set it to: new Date().getTime() + (10\*60_\*_1000) |
| bucketName     | String: bucket name where the already existing file is located                                                                                                     |
| objectName     | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt"        |
| mime           | String (optional): mime type for the file to get; you can set it null                                                                                              |
| returned value | a String value representing the public URL to download or show the file                                                                                            |

## Download on the Platform server file system a file stored in Google Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to download an already existing file stored inside a Google Cloud Storage bucket and save it locally, on Platform server file system.

**Syntax**

```
utils.downloadGoogleCloudStorageObject(
   bucketName, 
   objectName, 
   destPath
);
```

**Description**

| Argument   | Description                                                                                                                                                             |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| bucketName | String: bucket name where the file to download is located                                                                                                               |
| objectName | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt"             |
| destPath   | <p>String: the absolute path + file name representing the file to save on the Platform server file system; e.g. </p><p>utils.getDirectoryParth(dirId)+"/myfile.txt"</p> |

It fires and exception in case of errors.

## Get a paginated list of files stored in the specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to get a paginated list of files stored inside a Google Cloud Storage bucket. The list does NOT contain the files, but only file descriptors (helpful to fetch a specific file later).

**Syntax**

```
var response = utils.listGoogleCloudStorageObjects(
     bucketName, 
     maxPageResults, 
     pages, 
     nextPageToken, 
     prefix, 
     delimiter
  )
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| bucketName     | String: bucket name where reading files                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| maxPageResults | long: total number of file descriptors to fetch; e.g. reqParams.limit                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| pages          | int: represents the number of pages already read                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| nextPageToken  | the token returned by the previous invocation of this method, used byCloud Storage API to fetch the next block of data (see the "response" object)                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| prefix         | <p>String (optional) - it allows to filter the list according to the file names prefix; </p><p>for more details see: <a href="https://cloud.google.com/storage/docs/json_api/v1/objects/list">https://cloud.google.com/storage/docs/json_api/v1/objects/list</a></p>                                                                                                                                                                                                                                                                                                                  |
| delimiter      | String: returns results in a directory-like mode. items will contain only objects whose names, aside from the prefix, do not contain delimiter. Objects whose names, aside from the prefix, contain delimiter will have their name, truncated after the delimiter, returned in prefixes. Duplicate prefixes are omitted.                                                                                                                                                                                                                                                              |
| returned value | <p>this function returns a javascript object having the following structure:</p><p>{</p><p>  nextPageToken: "...", // token to use for the next invocation of this function </p><p>                                       // (to get the next block of data)</p><p>  list: [{</p><p>    id: "...", // file identifier</p><p>    title: "...", // file name</p><p>    mimeType: "...", // mime type for the file</p><p>    pathType: "GCS",</p><p>   size: ..., // file size</p><p>   md5hash: "...", // hash key representing the file content</p><p>  },{....</p><p>  ]</p><p>} </p> |

## Get the whole list of files stored in the specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to get a the whole list of files stored inside a Google Cloud Storage bucket. The list does NOT contain the files, but only file descriptors (helpful to fetch a specific file later).

**Syntax**

```
var list = utils.listGoogleCloudStorageObjects(
     bucketName, 
     prefix, 
     delimiter
  )
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                                                        |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| bucketName     | String: bucket name where reading files                                                                                                                                                                                                                                                                                                                                                            |
| prefix         | <p>String (optional) - it allows to filter the list according to the file names prefix; </p><p>for more details see: <a href="https://cloud.google.com/storage/docs/json_api/v1/objects/list">https://cloud.google.com/storage/docs/json_api/v1/objects/list</a></p>                                                                                                                               |
| delimiter      | String: returns results in a directory-like mode. items will contain only objects whose names, aside from the prefix, do not contain delimiter. Objects whose names, aside from the prefix, contain delimiter will have their name, truncated after the delimiter, returned in prefixes. Duplicate prefixes are omitted.                                                                           |
| returned value | <p>this function returns a list of javascript objects, having the following structure:</p><p>[{</p><p>    id: "...", // file identifier</p><p>    title: "...", // file name</p><p>    mimeType: "...", // mime type for the file</p><p>    pathType: "GCS",</p><p>   size: ..., // file size</p><p>   md5hash: "...", // hash key representing the file content</p><p> },{....</p><p>]</p><p></p> |

## Upload a file saved on Platform server file system to the specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to upload an already existing file stored on Platform server file system and save it on a Google Cloud Storage bucket.&#x20;

**Syntax**

```
var descriptor = utils.uploadGoogleCloudStorageObjectFromFS(
   fsPath, 
   bucketName, 
   objectName,
   deleteFsFile
);
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                             |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| fsPath         | absolute path + file name in the Platform server file system, where the file to upload is located                                                                                                                                                                                                                                                                       |
| bucketName     | String: bucket name where saving the file to upload                                                                                                                                                                                                                                                                                                                     |
| objectName     | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt"; in the seconda case, the relative path is automatically "created" by Cloud Storage if not existing yet                                                                                                     |
| deleteFsFile   | boolean: true to auto delete the original file from Platform server file system, after the upload was completed successfully                                                                                                                                                                                                                                            |
| returned value | <p>this function returns a javascript object representing the file just uploaded:</p><p>{</p><p>    id: "...", // file identifier</p><p>    title: "...", // file name</p><p>    mimeType: "...", // mime type for the file</p><p>    pathType: "GCS",</p><p>   size: ..., // file size</p><p>   md5hash: "...", // hash key representing the file content</p><p> }</p> |

**Important note**: the file visibility is inherited by the bucket: if the bucket has been defined as "£public" the uploaded file will be as well.

## Upload a file saved on Platform server file system to the specified bucket of  Cloud Storage and make it public

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to upload an already existing file stored on Platform server file system and save it on a Google Cloud Storage bucket and make it public, i.e. accessible by any device, without any authentication.

**Syntax**

```
var descriptor = utils.uploadGoogleCloudStoragePublicObjectFromFS(
   fsPath, 
   bucketName, 
   objectName,
   deleteFsFile
);
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                             |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| fsPath         | absolute path + file name in the Platform server file system, where the file to upload is located                                                                                                                                                                                                                                                                       |
| bucketName     | String: bucket name where saving the file to upload                                                                                                                                                                                                                                                                                                                     |
| objectName     | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt"; in the seconda case, the relative path is automatically "created" by Cloud Storage if not existing yet                                                                                                     |
| deleteFsFile   | boolean: true to auto delete the original file from Platform server file system, after the upload was completed successfully                                                                                                                                                                                                                                            |
| returned value | <p>this function returns a javascript object representing the file just uploaded:</p><p>{</p><p>    id: "...", // file identifier</p><p>    title: "...", // file name</p><p>    mimeType: "...", // mime type for the file</p><p>    pathType: "GCS",</p><p>   size: ..., // file size</p><p>   md5hash: "...", // hash key representing the file content</p><p> }</p> |

**Important note**: the file visibility is always public, independently on the bucket settings.

## Create a text file on a specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to create on the fly a text file and upload it on a Google Cloud Storage bucket, without the need for a physical file stored on Platform server file system.

**Important note**: do NOT use this method to create on the fly very large text files, since this would consume a large amount of memory on Platform server; use it only for kbytes size files.

**Syntax**

```
var descriptor = utils.uploadGoogleCloudStorageObjectFromString(
  textContent, 
  bucketName, 
  objectName,
  contentType
);
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                             |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| textContent    | the text to include in the file to create on Cloud Storage                                                                                                                                                                                                                                                                                                              |
| bucketName     | String: bucket name where saving the file to upload                                                                                                                                                                                                                                                                                                                     |
| objectName     | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt"; in the seconda case, the relative path is automatically "created" by Cloud Storage if not existing yet                                                                                                     |
| contextType    | String: mime type to use for the text file; e.g. "text/plain" or "text/csv" or "text/html"                                                                                                                                                                                                                                                                              |
| returned value | <p>this function returns a javascript object representing the file just uploaded:</p><p>{</p><p>    id: "...", // file identifier</p><p>    title: "...", // file name</p><p>    mimeType: "...", // mime type for the file</p><p>    pathType: "GCS",</p><p>   size: ..., // file size</p><p>   md5hash: "...", // hash key representing the file content</p><p> }</p> |

**Important note**: the file visibility is inherited by the bucket: if the bucket has been defined as "£public" the uploaded file will be as well.

## Create a text file on a specified bucket of  Cloud Storage and make it public

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to create on the fly a text file and upload it on a Google Cloud Storage bucket, without the need for a physical file stored on Platform server file system and make it public, i.e. accessible by any device, without any authentication.

**Important note**: do NOT use this method to create on the fly very large text files, since this would consume a large amount of memory on Platform server; use it only for kbytes size files.

**Syntax**

```
var descriptor = utils.uploadGoogleCloudStoragePublicObjectFromString(
  textContent, 
  bucketName, 
  objectName,
  contentType
);
```

**Description**

| Argument       | Description                                                                                                                                                                                                                                                                                                                                                             |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| textContent    | the text to include in the file to create on Cloud Storage                                                                                                                                                                                                                                                                                                              |
| bucketName     | String: bucket name where saving the file to upload                                                                                                                                                                                                                                                                                                                     |
| objectName     | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt"; in the seconda case, the relative path is automatically "created" by Cloud Storage if not existing yet                                                                                                     |
| contextType    | String: mime type to use for the text file; e.g. "text/plain" or "text/csv" or "text/html"                                                                                                                                                                                                                                                                              |
| returned value | <p>this function returns a javascript object representing the file just uploaded:</p><p>{</p><p>    id: "...", // file identifier</p><p>    title: "...", // file name</p><p>    mimeType: "...", // mime type for the file</p><p>    pathType: "GCS",</p><p>   size: ..., // file size</p><p>   md5hash: "...", // hash key representing the file content</p><p> }</p> |

**Important note**: the file visibility is always public, independently on the bucket settings.



## Duplicate a file stored in the specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to duplicate an already existing file stored on a a Google Cloud Storage bucket and save it on the specified bucket with the specified file name; a possibile use of this method is when creating a file from a template file.

**Syntax**

```
var descriptor = utils.copyGoogleCloudStorageObject(
  sourceBucketName, 
  sourceObjectName,
  sourceObjectVersion, 
  destinationBucketName, 
  destinationObjectName
);
```

**Description**

| Argument              | Description                                                                                                                                                                                                                                                                                                                                                             |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sourceBucketName      | String: bucket name where the already existing file to copy is located                                                                                                                                                                                                                                                                                                  |
| sourceObjectName      | String: file name (with relative path if needed) of the file to copy                                                                                                                                                                                                                                                                                                    |
| sourceObjectVersion   | String (optional); in case of a versioned file, the version to copy; set it to null if file versioning is not enabled                                                                                                                                                                                                                                                   |
| destinationBucketName | String: bucket name where saving the duplicated file                                                                                                                                                                                                                                                                                                                    |
| destinationObjectName | String: file name for the file to create as a duplication of the first one                                                                                                                                                                                                                                                                                              |
| returned value        | <p>this function returns a javascript object representing the file just uploaded:</p><p>{</p><p>    id: "...", // file identifier</p><p>    title: "...", // file name</p><p>    mimeType: "...", // mime type for the file</p><p>    pathType: "GCS",</p><p>   size: ..., // file size</p><p>   md5hash: "...", // hash key representing the file content</p><p> }</p> |

## Change accessibility for a Cloud Storage file to public or private

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to change the access policy for an already existing file stored on a a Google Cloud Storage bucket and make it public or private.

**Syntax**

```
utils.setPublicLink(bucketName, objectName, publicLink)
```

**Description**

| Argument   | Description                                                    |
| ---------- | -------------------------------------------------------------- |
| bucketName | String: bucket name where the already existing file is located |
| objectName | String: file name (with relative path if needed) of the file   |
| publicLink | boolean: true to set it as public, false to set it as private  |

This method will fire and exception in case of errors.



## Delete a Google Cloud Storage file

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE&#x20;
  * Google: Service Account Email
  * Google:  Service Account Key
* FILE UPLOAD&#x20;
  * Google Cloud Storage Location (US, EU, ASIA)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage (GCS) service.

The current javascript function allows to delete a file from a bucket.

**Syntax**

```
utils.deleteGoogleCloudStorageObject(String bucketName, String objectName)
```

**Description**

| Argument   | Description                                                            |
| ---------- | ---------------------------------------------------------------------- |
| bucketName | String: bucket name where the already existing file is located         |
| objectName | String: file name (with relative path if needed) of the file to delete |

This method will fire and exception in case of errors.

