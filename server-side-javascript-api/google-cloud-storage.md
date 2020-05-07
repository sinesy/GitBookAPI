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
      <td style="text-align:left">String: Google level unique name; use only letters and - as separator</td>
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

The current javascript function allows to get the description of an already existing file stored inside a Google Cloud Storage bucket.

**Syntax**

```text
var urlString = utils.getGoogleCloudStorageSignedURL(
  String verb, 
  Long expiration, 
  String bucketName, 
  String objectName, 
  String mime
);
```

**Description**

| Argument | Description |
| :--- | :--- |
| verb | String: HTTP method to use to get the file; set it to "GET" |
| expiration | long: URL expiration time, expressed in milliseconds; for example, to set an URL valid for the next 10 minutes, set it to: new Date\(\).getTime\(\) + \(10\*60_\*_1000\) |
| bucketName | String: Google level unique name; use only letters and - as separator |
| objectName | String: file identifier; in the simplest case, it can be a filename like "a.txt" or the relative path within the bucket, like "subfolder1/subfolder2/a.txt" |
| mime | String \(optional\): mime type for the file to get; you can set it null |
| returned value | a String value representing the public URL to download or show the file |





