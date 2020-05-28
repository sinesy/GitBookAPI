# Whatsapp

Platform supports the integration with Whatsapp for Business, through the partner Twilio.

Thanks to this integration, it is possible to:

* send a **text message** to any phone number where Whatsapp has been installed
* send a **text + muti-media message** to any phone number where Whatsapp has been installed; supported media are: images, audio files, PDFs, up to 16MB; _files to send must be accessible through public URLs_ 
* gather **notifications** from Whatsapp, related to "message sent" event and "message read" event.

A few constraints:

* messages must respect the template content defined here: 

{% page-ref page="whatsapp.md" %}

* messages are sent starting from a phone number, assigned by Twilio, after the correct verification of the organization; the verification process is described later.

Message sending are not free: there is a cost involved for each sending; pricing is described here:

{% page-ref page="whatsapp.md" %}

## Setup

Before using services and functions provided by Platform, a few settings must be set as Application parameters.

First of all, there are two available environments:

A **"sand box" environment**, helpful when developing the integration, to test the correction operation of the system; this environment does not follow the pricing policy reported above, but there is a predefined credit available.

Through the sand box, it is possible to define one or more "projects"; each project has an pre-assigned "sending phone number" \(by Twilio\), used when sending messages and cannot be changed; each project can be related to a different tenant. 

At project level, it is possible to define also a **callback**, i.e. a public URL provided by your own Platform application, which receive callbacks from Whatsapp, when a message has been sent \(received\) and when the message has been read.

In any case, the first step is signing up in Twilio Whatsapp and create at least one project.

{% page-ref page="whatsapp.md" %}

Once signed up and confirmed the registration by defining a real phone number where Whatsapp has been installed, it is possible to start using it. It is possible to add any number of other phone numbers, to connect to the sand, but they must be registered step by step.

At this point, it is possible to access the Twilio console at any time:

{% page-ref page="whatsapp.md" %}

The next steps are:

* creating a "from phone number", assigned by Twilio and to use when sending messages
* add additional phone numbers you want to associate to the assigned "from phone number", through the section 

{% page-ref page="whatsapp.md" %}

It is not possible to use the web console to assign additional phone numbers to work with \(devices who would receive messages\); the phone assignment has to start from such a device: through Whatsapp app, the must send a message to the "from number" and write the "initialization text", specific for each project.

Such a text can be retrieved starting from this console:

{% page-ref page="whatsapp.md" %}

Finally, in case you want your Platform web app can receive notifications about messages sent, you have to specify the public URL in your web app which receive such a callbacks.

You can do it by clicking on the Sand box submenu and fill in the STATUS CALLBACK URL input field, with something like:

```text
https://<yourplarformhost>/<platformwebcontext>/whatsapp/<appid>/<companyid>
```

and then press SAVE at the bottom of the page. It seems you have to repeat the saving procedure twice, since the first time it does not work!

Finally, you have to configure some application parameters, in the WHATSAPP section:

* account id
* auth key
* from phone numbers

All  information is available in the Twilio console.

A few limitations of the sandbox environment:

* You can only message users who have joined your sandbox. Messaging other users will fail.
* Twilio Sandbox supports functional testing, but not load testing of profile traffic.
* Sandbox numbers are restricted to 1 message every 3 seconds.
* Sandbox numbers are branded as Twilio numbers.
* You can only use pre-registered templates with the sandbox for outbound messages sent outside a WhatsApp session. Click [here](https://www.twilio.com/docs/sms/whatsapp/api#templates-pre-registered-for-the-sandbox) for more information.



The second environment, is the **production environment**.

In order to configure it, you have to associate a billing account with a credit card and recognize your organization. You can also assign an ad hoc "from phone number".

It would be better to create a second project, for each production environment. Please bear in mind that each project can have ONE ONLY "from number" \(optionally customized\).

You an create up to 15 projects with the same account.

See here for additional information about the right sign up for a production environment:

{% page-ref page="whatsapp.md" %}



## Sending Whatsapp messages from Platform with the same phone number

There are a few server side javascript functions available to send messages:

```text
var json = utils.sendWhatsappMessage(toPhoneNumber, message, publicMediaURL);
```

```text
var json = utils.sendWhatsappMessage(toPhoneNumber, message, bucketName, fileName);
```

| Argument | Description |
| :--- | :--- |
| toPhoneNumber | It contains a phone number; it can be expressed as prefix+number or better as internationalprefixwith+prefix+number \(es. +39....\); in case the international prefix has been not included, the +39 is added automatically |
| message | The message to send |
| publicMediaURL | It is optional; can be set to null; if specified, it must be a public URL related to the media to send \(a PDF, an image, a video/audio file\); up to 16MB file size can be sent; in case the file to send is stored locally in the Platform server, it must be accessible from a public link, as for the Platform's web app sub-context |
| bucketName | It is optional; can be set to null; if specified, the "fileName" argument must be specified as well; together, the define a file in the Google Cloud Storage where the file is located; this file can be public or not; it is not a problem, sincePlatform will create a signed temporary public URL for that |

Bear in mind the 3 application parameters in the WHATSAPP section must be set correctly \(account id, pwd, from number\).

These methods return a JSON string containing the outcome of the sending operation, something like:

```text
{
	"sid": "SM90f54fe9f03d4cbbb07dbe1cfcfebfea",
	"date_created": "Wed, 27 May 2020 15:08:03 +0000",
	"date_updated": "Wed, 27 May 2020 15:08:03 +0000",
	"date_sent": null,
	"account_sid": "...",
	"to": "whatsapp:+...",
	"from": "whatsapp:+...",
	"messaging_service_sid": null,
	"body": "...",
	"status": "queued",
	"num_segments": "1",
	"num_media": "0",
	"direction": "outbound-api",
	"api_version": "2010-04-01",
	"price": null,
	"price_unit": null,
	"error_code": null,
	"error_message": null,
	"uri": "/2010-04-01/Accounts/.../Messages/SM90f54fe9f03d4cbbb07dbe1cfcfebfea.json",
	"subresource_uris": {
		"media": "/2010-04-01/Accounts/.../Messages/SM90f54fe9f03d4cbbb07dbe1cfcfebfea/Media.json"
	}
}
```

The attribute "**sid**" represents the sending transaction id and can be saved in the application database, in order to track the specific sending message. It can be helpful, in case Platform has to receive notification events, when the end user receives the message and/or read the message \(see section later\).

## Sending Whatsapp messages from Platform with the different phone numbers

In case you have a multi-tenant Platform web application, it is possible you want to assign different "from phone numbers" to different tenants. In such a case, the previous methods are not good, since they inherit the settings from the Application parameters.

In case you want to use different "from numbers", you have to create your own application database table where saving such a settings and then pass them forward to the following methods:

```
var json = utils.sendWhatsappMessage(accountId, secretKey, fromNr, toPhoneNumber, message, publicMediaURL);
```

```text
var json = utils.sendWhatsappMessage(accountId, secretKey, fromNr, toPhoneNumber, message, bucketName, fileName);
```

| Argument | Description |
| :--- | :--- |
| account id | specific account id; mandatory; it can be the one you defined as application parameter |
| secret key | specific password related to the account id; mandatory; it can be the one you defined as application parameter |
| fromPhoneNr | mandatory; the from number defined through the Twilio console, one for each Twilio project \(one for each tenant\) |
| toPhoneNumber | It contains a phone number; it can be expressed as prefix+number or better as internationalprefixwith+prefix+number \(es. +39....\); in case the international prefix has been not included, the +39 is added automatically |
| message | The message to send |
| publicMediaURL | It is optional; can be set to null; if specified, it must be a public URL related to the media to send \(a PDF, an image, a video/audio file\); up to 16MB file size can be sent; in case the file to send is stored locally in the Platform server, it must be accessible from a public link, as for the Platform's web app sub-context |
| bucketName | It is optional; can be set to null; if specified, the "fileName" argument must be specified as well; together, the define a file in the Google Cloud Storage where the file is located; this file can be public or not; it is not a problem, sincePlatform will create a signed temporary public URL for that |

These methods return a JSON string containing the outcome of the sending operation, something like:

```text
{
	"sid": "SM90f54fe9f03d4cbbb07dbe1cfcfebfea",
	"date_created": "Wed, 27 May 2020 15:08:03 +0000",
	"date_updated": "Wed, 27 May 2020 15:08:03 +0000",
	"date_sent": null,
	"account_sid": "...",
	"to": "whatsapp:+...",
	"from": "whatsapp:+...",
	"messaging_service_sid": null,
	"body": "...",
	"status": "queued",
	"num_segments": "1",
	"num_media": "0",
	"direction": "outbound-api",
	"api_version": "2010-04-01",
	"price": null,
	"price_unit": null,
	"error_code": null,
	"error_message": null,
	"uri": "/2010-04-01/Accounts/.../Messages/SM90f54fe9f03d4cbbb07dbe1cfcfebfea.json",
	"subresource_uris": {
		"media": "/2010-04-01/Accounts/.../Messages/SM90f54fe9f03d4cbbb07dbe1cfcfebfea/Media.json"
	}
}
```

The attribute "**sid**" represents the sending transaction id and can be saved in the application database, in order to track the specific sending message. It can be helpful, in case Platform has to receive notification events, when the end user receives the message and/or read the message \(see section later\).

## Receiving notifications after sending Whatsapp messages

Platform provides a public web service to receive all notification events from Whatsapp, which has the following URL:

```text
https://<yourplarformhost>/<platformwebcontext>/whatsapp/callback/<yourappid>/<yourcompanyid>
```

This method automatically invoke a server-side javascript action, each time it receives a notification from Whatsapp.

Before using it, you have to fill in the application parameter "Whatsapp callback" in the WHATSAPP section. This parameter must be filled with the action id which receives all notifications for the app id identified in the URL above.

The URL must have the format described above: it must not only include the app id \(it correctly identified the action id to resume\) but also a company id: in this way, the same action can receive the company id related to a specific tenant. In case you do not need it, you have to specify a value in any case \(e.g. NODEFINED\).

The invoked action will received in input a "vo" javascript input object having the following content:

```text
{
  SmsSid: "SM90f54fe9f03d4cbbb07dbe1cfcfebfea",
  SmsStatus: "sent",
  MessageStatus: "sent", 
  ChannelToAddress: "...",
  To: "whatsapp:.." // to phone number, always expressed as +...
  ChannelPrefix: "whatsapp",
  MessageSid: "...", 
  AccountSid: "...",
  From: "whatsapp:...", // from number, always expressed as +...
  ApiVersion: "2010-04-01",
  ChannelInstallSid: "...",
  appId. "...",
  companyId: "..."
}
```

MessageStatus content changes according to the notification event.

MessageSid is the same returned by the JSON described above, when sending messages \("sid" attribute\).

Thanks to it, it is possible to match sending messages with the corresponding notifications.

## Troubleshooting

When sending messages/receiving notifications, you can use the Dashboard web page in Twilio console to track every event and look at errors.





