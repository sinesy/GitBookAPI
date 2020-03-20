# Push notifications

Through the following [**server-side**](../server-side-javascript-api/email.md) javascript function you can notify via push notification the mobile app.

**utils.sendPushNotification\(appId, usernamesList, title, body, actionIdToCall, valueObject, iOSBadgeCount\);**

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

## **getUnreadNotificationsCount\(\);**

Returns the unread notifications count

## **setMenuBadges\(menuFunctionId, count\);**

Sets the badge for the menu item by its functionId

## **resetUnreadNotifications\(\);**

Sets to zero the unread notifications count.  
After this, the method**getNotificationsCount\(\)**will return zero.  
This method doesn’t update the menu item badge, you have to call

