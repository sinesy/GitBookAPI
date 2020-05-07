# Google Cloud Storage

## Create a bucket on Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to create a bucket in GCS in a specific **location** and storage **class**. The location identifies the geographical position of the bucket around the world. For more information see:

{% page-ref page="google-cloud-storage.md" %}

The storage class defines how fast will be the file retrieval. For more information see:

{% page-ref page="google-cloud-storage.md" %}

Be aware that the **bucket name must be unique** at Google level and must contain only letters and - \(no underscore symbols\), so it would be a good practice to use composed names starting with the googleprojectname-applicationame-somethingelse.

**Syntax**

```text
var descriptor = utils.createGoogleCloudStorageBucket(
   project, 
   bucketName, 
   bucketLocation,
   storageClass
);
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">project</td>
      <td style="text-align:left">String: Google project name</td>
    </tr>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: Google level unique name; use only letters and - as separator</td>
    </tr>
    <tr>
      <td style="text-align:left">bucketLocation</td>
      <td style="text-align:left">String: identifies the geographical position where creating the bucket;
        allowed values are:
        <br />US, EU, ASIA. Other locations are supported. See https://cloud.google.com/storage/docs/bucket-locations</td>
    </tr>
    <tr>
      <td style="text-align:left">storageClass</td>
      <td style="text-align:left">String (optional - storage class: STANDARD, NEARLINE and DURABLE_REDUCED_AVAILABILITY.
        See https://cloud.google.com/storage/docs/storage-classes</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>in case of errors, an exception fill be fired; the returned value is a
          javascript object having the following structure:</p>
        <p>{</p>
        <p>name: &quot;...&quot;, // bucket name</p>
        <p>type: &quot;...&quot;, // bucket type</p>
        <p>versioned: true|false</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>##  Get the bucket descriptor from Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to get the description of an already existing bucket in GCS. 

**Syntax**

```text
var descriptor = utils.getGoogleCloudStorageBucket(bucketName);
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: Google level unique name; use only letters and - as separator</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>in case of errors, an exception fill be fired; the returned value is a
          javascript object having the following structure:</p>
        <p>{</p>
        <p>name: &quot;...&quot;, // bucket name</p>
        <p>type: &quot;...&quot;, // bucket type</p>
        <p>versioned: true|false</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>## Get the file descriptor from Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to get the description of an already existing file stored inside a Google Cloud Storage bucket.

**Syntax**

```text
var descriptor = utils.getGoogleCloudStorageObject(bucketName,objectName);
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: bucket name where the file to analyze is located</td>
    </tr>
    <tr>
      <td style="text-align:left">objectName</td>
      <td style="text-align:left">String: file identifier; in the simplest case, it can be a filename like
        &quot;a.txt&quot; or the relative path within the bucket, like &quot;subfolder1/subfolder2/a.txt&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>in case of errors, an exception fill be fired; the returned value is a
          javascript object having the following structure:</p>
        <p>{</p>
        <p>id: &quot;...&quot;, // file identifier</p>
        <p>title: &quot;...&quot;, // file name</p>
        <p>mimeType: &quot;...&quot;, // mime type for the file</p>
        <p>pathType: &quot;GCS&quot;,</p>
        <p>size: ..., // file size</p>
        <p>md5hash: &quot;...&quot;, // hash key representing the file content</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>## Get a public \(temporary\) URL for accessing a Cloud Storage file

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to generate a public URL to access from anywhere an already existing file stored inside a Google Cloud Storage bucket.

**Syntax**

```text
var urlString = utils.getGoogleCloudStorageSignedURL(
   verb, 
   expiration, 
   bucketName, 
   objectName, 
   mime
);
```

**Description**

| Argument | Description |
| :--- | :--- |
| verb | String: HTTP method to use to get the file; set it to "GET" |
| expiration | long: URL expiration time, expressed in milliseconds; for example, to set an URL valid for the next 10 minutes, set it to: new Date\(\).getTime\(\) + \(10\*60_\*_1000\) |
| bucketName | String: bucket name where the already existing file is located |
| objectName | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt" |
| mime | String \(optional\): mime type for the file to get; you can set it null |
| returned value | a String value representing the public URL to download or show the file |

## Download on the Platform server file system a file stored in Google Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to download an already existing file stored inside a Google Cloud Storage bucket and save it locally, on Platform server file system.

**Syntax**

```text
utils.downloadGoogleCloudStorageObject(
   bucketName, 
   objectName, 
   destPath
);
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: bucket name where the file to download is located</td>
    </tr>
    <tr>
      <td style="text-align:left">objectName</td>
      <td style="text-align:left">String: file identifier; in the simplest case, it can be a filename like
        &quot;a.txt&quot; or the relative path within the bucket, like &quot;subfolder1/subfolder2/a.txt&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">destPath</td>
      <td style="text-align:left">
        <p>String: the absolute path + file name representing the file to save on
          the Platform server file system; e.g.</p>
        <p>utils.getDirectoryParth(dirId)+&quot;/myfile.txt&quot;</p>
      </td>
    </tr>
  </tbody>
</table>It fires and exception in case of errors.

## Get a paginated list of files stored in the specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to get a paginated list of files stored inside a Google Cloud Storage bucket. The list does NOT contain the files, but only file descriptors \(helpful to fetch a specific file later\).

**Syntax**

```text
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

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: bucket name where reading files</td>
    </tr>
    <tr>
      <td style="text-align:left">maxPageResults</td>
      <td style="text-align:left">long: total number of file descriptors to fetch; e.g. reqParams.limit</td>
    </tr>
    <tr>
      <td style="text-align:left">pages</td>
      <td style="text-align:left">int: represents the number of pages already read</td>
    </tr>
    <tr>
      <td style="text-align:left">nextPageToken</td>
      <td style="text-align:left">the token returned by the previous invocation of this method, used byCloud
        Storage API to fetch the next block of data (see the &quot;response&quot;
        object)</td>
    </tr>
    <tr>
      <td style="text-align:left">prefix</td>
      <td style="text-align:left">
        <p>String (optional) - it allows to filter the list according to the file
          names prefix;</p>
        <p>for more details see: <a href="https://cloud.google.com/storage/docs/json_api/v1/objects/list">https://cloud.google.com/storage/docs/json_api/v1/objects/list</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">delimiter</td>
      <td style="text-align:left">String: returns results in a directory-like mode. items will contain only
        objects whose names, aside from the prefix, do not contain delimiter. Objects
        whose names, aside from the prefix, contain delimiter will have their name,
        truncated after the delimiter, returned in prefixes. Duplicate prefixes
        are omitted.</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>this function returns a javascript object having the following structure:</p>
        <p>{</p>
        <p>nextPageToken: &quot;...&quot;, // token to use for the next invocation
          of this function</p>
        <p>// (to get the next block of data)</p>
        <p>list: [{</p>
        <p>id: &quot;...&quot;, // file identifier</p>
        <p>title: &quot;...&quot;, // file name</p>
        <p>mimeType: &quot;...&quot;, // mime type for the file</p>
        <p>pathType: &quot;GCS&quot;,</p>
        <p>size: ..., // file size</p>
        <p>md5hash: &quot;...&quot;, // hash key representing the file content</p>
        <p>},{....</p>
        <p>]</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>## Get the whole list of files stored in the specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to get a the whole list of files stored inside a Google Cloud Storage bucket. The list does NOT contain the files, but only file descriptors \(helpful to fetch a specific file later\).

**Syntax**

```text
var list = utils.listGoogleCloudStorageObjects(
     bucketName, 
     prefix, 
     delimiter
  )
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: bucket name where reading files</td>
    </tr>
    <tr>
      <td style="text-align:left">prefix</td>
      <td style="text-align:left">
        <p>String (optional) - it allows to filter the list according to the file
          names prefix;</p>
        <p>for more details see: <a href="https://cloud.google.com/storage/docs/json_api/v1/objects/list">https://cloud.google.com/storage/docs/json_api/v1/objects/list</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">delimiter</td>
      <td style="text-align:left">String: returns results in a directory-like mode. items will contain only
        objects whose names, aside from the prefix, do not contain delimiter. Objects
        whose names, aside from the prefix, contain delimiter will have their name,
        truncated after the delimiter, returned in prefixes. Duplicate prefixes
        are omitted.</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>this function returns a list of javascript objects, having the following
          structure:</p>
        <p>[{</p>
        <p>id: &quot;...&quot;, // file identifier</p>
        <p>title: &quot;...&quot;, // file name</p>
        <p>mimeType: &quot;...&quot;, // mime type for the file</p>
        <p>pathType: &quot;GCS&quot;,</p>
        <p>size: ..., // file size</p>
        <p>md5hash: &quot;...&quot;, // hash key representing the file content</p>
        <p>},{....</p>
        <p>]</p>
        <p></p>
      </td>
    </tr>
  </tbody>
</table>## Upload a file saved on Platform server file system to the specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to upload an already existing file stored on Platform server file system and save it on a Google Cloud Storage bucket. 

**Syntax**

```text
var descriptor = utils.uploadGoogleCloudStorageObjectFromFS(
   fsPath, 
   bucketName, 
   objectName,
   deleteFsFile
);
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">fsPath</td>
      <td style="text-align:left">absolute path + file name in the Platform server file system, where the
        file to upload is located</td>
    </tr>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: bucket name where saving the file to upload</td>
    </tr>
    <tr>
      <td style="text-align:left">objectName</td>
      <td style="text-align:left">String: file identifier; in the simplest case, it can be a filename like
        &quot;a.txt&quot; or the relative path within the bucket, like &quot;subfolder1/subfolder2/a.txt&quot;;
        in the seconda case, the relative path is automatically &quot;created&quot;
        by Cloud Storage if not existing yet</td>
    </tr>
    <tr>
      <td style="text-align:left">deleteFsFile</td>
      <td style="text-align:left">boolean: true to auto delete the original file from Platform server file
        system, after the upload was completed successfully</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>this function returns a javascript object representing the file just uploaded:</p>
        <p>{</p>
        <p>id: &quot;...&quot;, // file identifier</p>
        <p>title: &quot;...&quot;, // file name</p>
        <p>mimeType: &quot;...&quot;, // mime type for the file</p>
        <p>pathType: &quot;GCS&quot;,</p>
        <p>size: ..., // file size</p>
        <p>md5hash: &quot;...&quot;, // hash key representing the file content</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>**Important note**: the file visibility is inherited by the bucket: if the bucket has been defined as "£public" the uploaded file will be as well.

## Upload a file saved on Platform server file system to the specified bucket of  Cloud Storage and make it public

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to upload an already existing file stored on Platform server file system and save it on a Google Cloud Storage bucket and make it public, i.e. accessible by any device, without any authentication.

**Syntax**

```text
var descriptor = utils.uploadGoogleCloudStoragePublicObjectFromFS(
   fsPath, 
   bucketName, 
   objectName,
   deleteFsFile
);
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">fsPath</td>
      <td style="text-align:left">absolute path + file name in the Platform server file system, where the
        file to upload is located</td>
    </tr>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: bucket name where saving the file to upload</td>
    </tr>
    <tr>
      <td style="text-align:left">objectName</td>
      <td style="text-align:left">String: file identifier; in the simplest case, it can be a filename like
        &quot;a.txt&quot; or the relative path within the bucket, like &quot;subfolder1/subfolder2/a.txt&quot;;
        in the seconda case, the relative path is automatically &quot;created&quot;
        by Cloud Storage if not existing yet</td>
    </tr>
    <tr>
      <td style="text-align:left">deleteFsFile</td>
      <td style="text-align:left">boolean: true to auto delete the original file from Platform server file
        system, after the upload was completed successfully</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>this function returns a javascript object representing the file just uploaded:</p>
        <p>{</p>
        <p>id: &quot;...&quot;, // file identifier</p>
        <p>title: &quot;...&quot;, // file name</p>
        <p>mimeType: &quot;...&quot;, // mime type for the file</p>
        <p>pathType: &quot;GCS&quot;,</p>
        <p>size: ..., // file size</p>
        <p>md5hash: &quot;...&quot;, // hash key representing the file content</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>**Important note**: the file visibility is always public, independently on the bucket settings.

## Create a text file on a specified bucket of  Cloud Storage

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to create on the fly a text file and upload it on a Google Cloud Storage bucket, without the need for a physical file stored on Platform server file system.

**Important note**: do NOT use this method to create on the fly very large text files, since this would consume a large amount of memory on Platform server; use it only for kbytes size files.

**Syntax**

```text
var descriptor = utils.uploadGoogleCloudStorageObjectFromString(
  textContent, 
  bucketName, 
  objectName,
  contentType
);
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">textContent</td>
      <td style="text-align:left">the text to include in the file to create on Cloud Storage</td>
    </tr>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: bucket name where saving the file to upload</td>
    </tr>
    <tr>
      <td style="text-align:left">objectName</td>
      <td style="text-align:left">String: file identifier; in the simplest case, it can be a filename like
        &quot;a.txt&quot; or the relative path within the bucket, like &quot;subfolder1/subfolder2/a.txt&quot;;
        in the seconda case, the relative path is automatically &quot;created&quot;
        by Cloud Storage if not existing yet</td>
    </tr>
    <tr>
      <td style="text-align:left">contextType</td>
      <td style="text-align:left">String: mime type to use for the text file; e.g. &quot;text/plain&quot;
        or &quot;text/csv&quot; or &quot;text/html&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>this function returns a javascript object representing the file just uploaded:</p>
        <p>{</p>
        <p>id: &quot;...&quot;, // file identifier</p>
        <p>title: &quot;...&quot;, // file name</p>
        <p>mimeType: &quot;...&quot;, // mime type for the file</p>
        <p>pathType: &quot;GCS&quot;,</p>
        <p>size: ..., // file size</p>
        <p>md5hash: &quot;...&quot;, // hash key representing the file content</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>**Important note**: the file visibility is inherited by the bucket: if the bucket has been defined as "£public" the uploaded file will be as well.

## Create a text file on a specified bucket of  Cloud Storage and make it public

Before using this function, the GCP project must be set up correctly, i.e. you have to specify at global parameters level:

* GOOGLE 
  * Google: Service Account Email
  * Google:  Servie Account Key
* FILE UPLOAD 
  * Google Cloud Storage Location \(US, EU, ASIA\)
  * Google Project Id

Once done that, you can start using the Google Cloud Storage \(GCS\) service.

The current javascript function allows to create on the fly a text file and upload it on a Google Cloud Storage bucket, without the need for a physical file stored on Platform server file system and make it public, i.e. accessible by any device, without any authentication.

**Important note**: do NOT use this method to create on the fly very large text files, since this would consume a large amount of memory on Platform server; use it only for kbytes size files.

**Syntax**

```text
var descriptor = utils.uploadGoogleCloudStoragePublicObjectFromString(
  textContent, 
  bucketName, 
  objectName,
  contentType
);
```

**Description**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">textContent</td>
      <td style="text-align:left">the text to include in the file to create on Cloud Storage</td>
    </tr>
    <tr>
      <td style="text-align:left">bucketName</td>
      <td style="text-align:left">String: bucket name where saving the file to upload</td>
    </tr>
    <tr>
      <td style="text-align:left">objectName</td>
      <td style="text-align:left">String: file identifier; in the simplest case, it can be a filename like
        &quot;a.txt&quot; or the relative path within the bucket, like &quot;subfolder1/subfolder2/a.txt&quot;;
        in the seconda case, the relative path is automatically &quot;created&quot;
        by Cloud Storage if not existing yet</td>
    </tr>
    <tr>
      <td style="text-align:left">contextType</td>
      <td style="text-align:left">String: mime type to use for the text file; e.g. &quot;text/plain&quot;
        or &quot;text/csv&quot; or &quot;text/html&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">returned value</td>
      <td style="text-align:left">
        <p>this function returns a javascript object representing the file just uploaded:</p>
        <p>{</p>
        <p>id: &quot;...&quot;, // file identifier</p>
        <p>title: &quot;...&quot;, // file name</p>
        <p>mimeType: &quot;...&quot;, // mime type for the file</p>
        <p>pathType: &quot;GCS&quot;,</p>
        <p>size: ..., // file size</p>
        <p>md5hash: &quot;...&quot;, // hash key representing the file content</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>**Important note**: the file visibility is always public, independently on the bucket settings.

## 

