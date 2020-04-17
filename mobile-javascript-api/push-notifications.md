# Push notifications

## Send a Push notification to all devices having the same username

Through the following [**server-side**](../server-side-javascript-api/email.md) javascript function you can notify via push notification the mobile app.

**Syntax**

```javascript
var json = utils.sendPushNotification(
  appId, 
  usernamesList, 
  title, 
  body, 
  actionIdToCall, 
  valueObject, 
  iOSBadgeCount
);
// the "json" result value is a String having the following format:
// [{...},...] with an element for each push notification sent (for each involved device id)
```

**Example**

```javascript
var usersEmails = ["email1@gmail.com","email2@gmail.com","emailN@gmail.com"]; //an array of registered user email accounts
var appMobileId = "MINION"; //the mobile application id
var notificationTitle = "Hello!"; //notification title
var notificationBody = "How did the cat get so fat?"; //notification body
var actionIdToCall = 123; //[optional] mobile actionId to call on the notification click if necessary
var valueObject = {"field1":"value1","field2":"value2","fieldN":"valueN"}; //[optional] map of <String, String> to use in the action id if necessary
var iOSBadgeCount = 1; //Total count of notification

utils.sendPushNotification(appMobileId, usersEmails , notificationTitle, notificationBody, 123, JSON.stringify(valueObject), iOSBadgeCount);
```

When the push notification reaches the mobile application, it calls the optional actionId defined in the **sendPushNotification** injecting in the valueObject a parameter with the status of the push:

`vo.notificationFieldStatus ="RECEIVED"`

When the user clicks on the notification, the mobile app calls the optional actionId defined in the **sendPushNotification** injecting in the valueObject a parameter with the status of the push:

`vo.notificationFieldStatus = "CLICKED"`

This is an example of the optional actionIdToCall

```javascript
if(vo.notificationStatus == "RECEIVED"){

    //For example this will update the "ideas" menu badge count with the count of unread notifications
    var unreadNotification = getUnreadNotificationsCount();
    setMenuBadges("ideas",unreadNotification);

} else if(vo.notificationStatus == "CLICKED"){

    //Reset the notification count
    resetUnreadNotifications();

    //update the "ideas" menu count
    setMenuBadges("ideas",0);

    //Open the window 39
    var args = {
       "param1":vo.field1,
       "param2":vo.field2,
       "paramN":vo.fieldN
    };
    openWindow39(args);  

}
```

## **Send a Push notification to a single device**

Through the following [**server-side**](../server-side-javascript-api/email.md) javascript function you can notify via push notification **a specific device** where the  mobile app has been installed.

**Syntax**

```javascript
var json = utils.sendSinglePushNotification(
  String appId,
  String firebaseId,
  String title,
  String shortMessage,
  Long actionId,
  String json,
  Long badgeNr,
  Map rootOptions,
  Map dataOptions,
  Map notificationOptions //this is mandatory for iOs Device
);
// the "json" result value is a String having the following format:
// [{...}] with ONE OLNY element for the single push notification sent
```

Note that **notificationOptions** is mandatory for iOs Deice

**Example**

```javascript
var firebaseId = "erwerhwejkrhwkjrhwjhkr"; // this is the value of CON45_DEVICES.FIREBASE_ID field for the specific device
var appMobileId = "MYAPP"; //the mobile application id
var notificationTitle = "Hello!"; //notification title
var notificationBody = "How did the cat get so fat?"; //notification body
var actionIdToCall = 123; //[optional] mobile actionId to call on the notification click if necessary
var valueObject = {"field1":"value1","field2":"value2","fieldN":"valueN"}; //[optional] map of <String, String> to use in the action id if necessary
var iOSBadgeCount = 1; //Total count of notification

 var iOsNotification = {};
        
if(isiOsDevice){
    //iOs need the notification info
    iOsNotification = {
        badge: iOSBadgeCount + "", //must be a string, 1 or 1.0 throw an error, "1" is ok
        content_available: true,
        sound: "Default",
        title: notificatonTitle,
        body: notificationBody
    }
}

utils.sendSinglePushNotification(
  appMobileId, 
  firebaseId, 
  notificationTitle, 
  notificationBody, 
  123, 
  JSON.stringify(valueObject), 
  iOSBadgeCount,
  null,
  null,
  iOsNotification
);
```

If you need to get the firebaseId, you can just append this scriptlet at the beginning of the the previous one, where the input data is the device id:

```javascript
var deviceId = "...";
var json = utils.executeQuery(
  "SELECT FIREBASE_ID FROM CON45_SYNC_DEVICES WHERE APPLICATION_ID=? AND DEVICE_ID=?",
  null,
  false,
  true,
  [appMobileId,deviceId]
);
var list = JSON.parse(json);
if (list.length>0) {
  var firebaseId = list[0].firebaseId;
  // ...
}
```

When the push notification reaches the mobile application, it calls the optional actionId defined in the **sendSinglePushNotification** injecting in the valueObject a parameter with the status of the push:

`vo.notificationFieldStatus ="RECEIVED"`

When the user clicks on the notification, the mobile app calls the optional actionId defined in the **sendSinglePushNotification** injecting in the valueObject a parameter with the status of the push:

`vo.notificationFieldStatus = "CLICKED"`

This is an example of the optional actionIdToCall

```javascript
if(vo.notificationStatus == "RECEIVED"){

    //For example this will update the "ideas" menu badge count with the count of unread notifications
    var unreadNotification = getUnreadNotificationsCount();
    setMenuBadges("ideas",unreadNotification);

} else if(vo.notificationStatus == "CLICKED"){

    //Reset the notification count
    resetUnreadNotifications();

    //update the "ideas" menu count
    setMenuBadges("ideas",0);

    //Open the window 39
    var args = {
       "param1":vo.field1,
       "param2":vo.field2,
       "paramN":vo.fieldN
    };
    openWindow39(args);  

}
```

\*\*\*\*

## **getUnreadNotificationsCount\(\);**

Returns the unread notifications count

## **setMenuBadges\(menuFunctionId, count\);**

Sets the badge for the menu item by its functionId

## **resetUnreadNotifications\(\);**

Sets to zero the unread notifications count.  
After this, the method**getNotificationsCount\(\)**will return zero.  
This method doesn’t update the menu item badge, you have to call

