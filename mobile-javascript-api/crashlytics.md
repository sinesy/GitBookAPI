# Crashlytics

Crashlytics must be enabled in the application build phase \(.ipa or .apk\).

If crashlytics has been enabled you can use the following methods

## getCrashlyticsUnsentReports\(\)

Crashlytics automatically sends the errors, if it failed to send the errors \(eg network firewall blocks\) it is possible to extract the error through this method. 

Return the path to a zip file containing errors, otherwise null.

> Since version 6.0.2

## sendCrashlyticsUnsentReports\(\)

Crashlytics automatically sends the errors, if it failed to send the errors \(eg network firewall blocks\) it is possible to force the upload through this method. 

> Since version 6.0.2

## Management of user reports

Below is an example of how to manage user reports.

The following action fetches log, db, crash and uploads everything to a bucket. At the end send a message to a google chat

### Client action

```text
/**
 * Send chat notification
 */
function sendChatNotification() {
    //Send chat notification

    var notifParam = {
        fileLogPath: destFileNameLog,
        fileDbPath: destFileNameDb,
        fileCrashPath: destFileNameCrash
    };
    
    var notifNote = "";
    
    if (!notifParam.fileLogPath || notifParam.fileLogPath == "") {
        notifNote += "Nessun LOG inviato\n";
    }
    if (!notifParam.fileDbPath || notifParam.fileDbPath == "") {
        notifNote += "Nessun DB inviato\n";
    }
    if (!notifParam.fileCrashPath || notifParam.fileCrashPath == "") {
        notifNote += "Nessun CRASH inviato\n";
    }
    
    if (notifNote && notifNote != "") {
        notifNote += "\n";
    }
    
    if (note && note != "") {
        notifNote += note;
    }
    
    notifParam.note = notifNote;
    
    executeServerAction(8479, notifParam);
}


/**
 * Send logs to server
 */
function showError(){
    
    asyncFunction("sendChatNotification", []);
    
    setFormPanelLabel(5269,"lblTitle",getTranslation("error"));
    setFormPanelLabel(5269,"lblSubtitle",getTranslation("segnalazioneNonInviata"));
    setFormPanelValue(5269,"imgStatus","error.png");
    setVisibleComponent(5269,"btnChiudi","Y");
}

/**
* Callback chiamata dopo l'invio del file
**/
function sendCallback(responseFromWebService) {
    
    if(!responseFromWebService){
        showError();
    }else{
        var respObj = JSON.parse(responseFromWebService);
        if(respObj.success){
            asyncFunction("sendChatNotification", []);
            /*
            var risp = {
                title : getTranslation("segnalazioneInviata"),
                subtitle : getTranslation("segnalazioneInviataMsg"),
                colorButtonSuccess : "#50A3ED",
                titleColorButtonSuccess: "#FFFFFF",
                titleColor : "#50A3ED", 
                subtitleColor: "#000000",
                backgroundColor : "#FFFFFF",
                titleButtonSuccess : "Ok"
            };
            showMessageDialog(risp,"");
            */
            setFormPanelValue(5289,"txtComment","");
            setFormPanelLabel(5269,"lblTitle",getTranslation("segnalazioneInviata"));
            setFormPanelLabel(5269,"lblSubtitle",getTranslation("segnalazioneInviataMsg"));
            setFormPanelValue(5269,"imgStatus","success.png");
            setVisibleComponent(5269,"btnChiudi","Y");
        }else{
            showError();    
        }
    }
    
}

/**
 * Salva nel bucket i crash non inviati a chraslytics
 */
function saveUnsentCrash(){
    
    try{
        //recupero il file di log
        var crashPath = getCrashlyticsUnsentReports();
        if(crashPath){
                
            //invio il file al server che lo carica nel bucket
            var logDir = 49;
            //platform in autmatico mette già COMPANY_ID/SITE_ID
            //il file avrà un percorso tipo 210_1001/210_1001_20191126_123000.zip
            destFileNameCrash = destFilePrefix + "_CRASH.zip";
            var url = getBaseURL() + "/uploadfiles/uploadfilegrid?appId=MOBILE_SHOP&applicationId=MOBILE_SHOP&dirId=" + logDir + "&unzip=false&restfulToken="+getToken();
            sendFile(url, crashPath, destFileNameCrash, "saveDb");
        }else{
             log("[3629] saveUnsentCrash SKIPPED NO PATH");
            saveDb();
        }
        
        try{
            //invio i report mancanti a crashlytics
            sendCrashlyticsUnsentReports();
        }catch(ec){
            log("[3629] sendCrashlyticsUnsentReports error: " + ec);
        }
    
    }catch(e){
        log("[3629] saveUnsentCrash ERROR: " + e);
        saveDb();
    }
}

/**
 * Salva nel bucket il db dell'app
 */
function saveDb(connectionData) {
    
    log("Connection data: " + connectionData);
    
    try {
        //uso il path fisso!!
        var dbPath = getDbPath("DBNOSYNC");
        
        if (dbPath) {
            var zipPathDb = zipFile(dbPath,"dbnosync.zip");
            //invio il file al server che lo carica nel bucket
            var logDirDb = 49;
            var filePathDb = zipPathDb;
            //platform in autmatico mette già COMPANY_ID/SITE_ID
            //il file avrà un percorso tipo 210_1001/210_1001_20191126_123000.zip
            destFileNameDb = destFilePrefix + "_DB.zip";
            var urlDb = getBaseURL() + "/uploadfiles/uploadfilegrid?appId=MOBILE_SHOP&applicationId=MOBILE_SHOP&dirId=" + logDirDb + "&unzip=false&restfulToken="+getToken();
            sendFile(urlDb, filePathDb, destFileNameDb, "saveLog");
        }else {
            log("[3629] saveDb SKIPPED NO PATH");
            saveLog();
        }
    }catch(e) {
        log("[3629] saveDb ERROR: " + e);
        saveLog();
    }
}

/**
 * Salva il file di log
 */
function saveLog(){
    log("[3629] NOTE SEGNALAZIONE: " + note);
    //recupero il file di log
    var logPath = getLogFilePath();
    if(logPath){
        
        //faccio uno zip del log
        var zipPath = zipFile(logPath, "log.zip");
        if(zipPath){
            
            //invio il file al server che lo carica nel bucket
            var logDir = 49;
            var filePath = zipPath;
            //platform in autmatico mette già COMPANY_ID/SITE_ID
            //il file avrà un percorso tipo 210_1001/210_1001_20191126_123000.zip
            destFileNameLog = destFilePrefix + "_LOG.zip";
            var url = getBaseURL() + "/uploadfiles/uploadfilegrid?appId=MOBILE_SHOP&applicationId=MOBILE_SHOP&dirId=" + logDir + "&unzip=false&restfulToken="+getToken();
            sendFile(url, zipPath, destFileNameLog, "sendCallback");
     
            //condivide lo zip con le app presenti nel device
            //shareDocument(zipPath,log.zip);
        }else{
            showError();
        }
    }else{
        showError();
    }
}

function inviaSegnalazione() {
    setFormPanelValue(5269,"imgStatus","invio_in_corso.gif");
    //invia crahs, log e db dell'app
    getConnectionData("saveUnsentCrash");
}

setVisibleComponent(5269,"btnChiudi","N");
var lastSyncDate = getVariable("LAST_SYNC_DATE");
log("lastSyncDate: " + lastSyncDate);

var destFilePrefix = userInfo.username + "/" + userInfo.username + "_" + userInfo.deviceId + "_" + stringifyDate(new Date().getTime(), "yyyyMMdd_HHmmss", true);
var destFileNameLog = "";
var destFileNameDb = "";
var destFileNameCrash = "";
var note = getFormPanelValue(5289,"txtComment");
showCardPanel(5309,5269);

asyncFunction("inviaSegnalazione", [],400);


```

### Server action

```text
function appendWidget(topLabel,content,contentMultiline,iconUrl) {
    var tmpWdgt = {
        "keyValue": {
            "topLabel": topLabel,
            "content": content,
            "contentMultiline":contentMultiline,
            "iconUrl":iconUrl
        }
    };
    widgets.push(tmpWdgt);
}

//Invia la notifica a google Chat se viene caricata una segnalazione nel bucket

//WEBHOOK DI GOOGLE CHAT
//var googleChatURL = "https://chat.googleapis.com/v1/spaces/AAAAn2-CE3w/messages?key=AIzaSyDdI0hCZtE6vySjMm-WEfRq3CPzqKqqsHI&token=OS7jOGQ4Fd37Orh-HaM9k7itXfm5ClcA4D3d8a-4RXw%3D&threaKey="+utils.getUUID();
utils.log("[8479] vo: " + JSON.stringify(vo,jsonReplacer),"INFO");

var response = {succcess:true};
var BUCKET_DIR_ID = 49;//bucket segnalazioni

try{
    var bucketName = utils.getDirectoryPath(BUCKET_DIR_ID);
    var expiration = new Date().getTime() + (60 * 60 * 1000); //il link ha durata di 60 minuti
    var filePathBase = userInfo.companyId + "/" + userInfo.siteId + "/";
    
    var buttonsArr = [];
    //LOG DELL'APP
    if (vo.fileLogPath) {
        var fileLogPath = filePathBase + vo.fileLogPath;
        var bucketLogUrl = utils.getGoogleCloudStorageSignedURL("GET", expiration, bucketName, fileLogPath, null) + "";
        //aggiungo il bottone per scaricare il db dell'app
        var logButton = {
            "textButton": {
                "text": "CONTROLLA SEGNALAZIONE (60min Link)",
                "onClick": {
                    "openLink": {
                        "url": bucketLogUrl
                    }
                }
            }
        };
        buttonsArr.push(logButton);
    }
    //DB DELL'APP
    if (vo.fileDbPath) {
        var fileDbPath = filePathBase + vo.fileDbPath;
        var bucketDbUrl = utils.getGoogleCloudStorageSignedURL("GET", expiration, bucketName, fileDbPath, null) + "";
        //aggiungo il bottone per scaricare il db dell'app
        var dbButton = {
            "textButton": {
                "text": "SCARICA DATI APPLICATIVI (60min Link)",
                "onClick": {
                    "openLink": {
                        "url": bucketDbUrl
                    }
                }
            }
        };
        buttonsArr.push(dbButton);
    }
    //CRASH DELL'APP
    if (vo.fileCrashPath) {
        var fileCrashPath = filePathBase + vo.fileCrashPath;
        var bucketCrashUrl = utils.getGoogleCloudStorageSignedURL("GET", expiration, bucketName, fileCrashPath, null) + "";
        //aggiungo il bottone per scaricare il db dell'app
        var crashButton = {
            "textButton": {
                "text": "SCARICA CRASH NON INVIATI (60min Link)",
                "onClick": {
                    "openLink": {
                        "url": bucketCrashUrl
                    }
                }
            }
        };
        buttonsArr.push(crashButton);
    }
    
    var widgets = [];
    //Widget Company - Site
    appendWidget(
        "Company - Site",
        userInfo.companyId + " - " + userInfo.siteId,
        "true",
        "https://github.com/google/material-design-icons/blob/master/png/social/group/materialicons/24dp/1x/baseline_group_black_24dp.png?raw=true"
    );
    //Widget Username
    appendWidget(
        "Utente",
        userInfo.username,
        "true",
        "https://github.com/google/material-design-icons/blob/master/png/social/person/materialicons/24dp/1x/baseline_person_black_24dp.png?raw=true"
    );
    //Widget Data e Ora segnalazione
    appendWidget(
        "Data e Ora Segnalazione",
        utils.convertDateToString(utils.getCurrentDateAndTime(), "yyyy-MM-dd HH:mm:ss"),
        "true",
        "https://github.com/google/material-design-icons/blob/master/png/social/person/materialicons/24dp/1x/baseline_person_black_24dp.png?raw=true"
    );
    //widget Nome del bucket
    appendWidget(
        "Nome del bucket",
        bucketName,
        "true",
        "https://github.com/google/material-design-icons/blob/master/png/file/folder/materialicons/24dp/1x/baseline_folder_black_24dp.png?raw=true"
    );
    
    //Widget note
    if (vo.note && vo.note !== "") {
        appendWidget(
            "Note",
            vo.note,
            "true",
            "https://github.com/google/material-design-icons/blob/master/png/notification/sms/materialicons/24dp/1x/baseline_sms_black_24dp.png?raw=true"
        );  
    }
    
    //aggiungo i pulsanti
    var buttons = {
        "buttons": buttonsArr
    };
    
    widgets.push(buttons);
    
    var requestBody = {
                "cards": [
                    {
                        "header": {
                            "title": "<b>Nuova segnalazione ricevuta</b>",
                            "imageUrl": "https://w7.pngwing.com/pngs/169/167/png-transparent-package-delivery-mail-box-parcel-box-thumbnail.png",
                            "imageStyle": "AVATAR"
                        },
                        "sections": [
                            {
                                "widgets": widgets
                            }
                        ]
                    }
                ]
            };
            
    utils.getWebContent(googleChatURL, false, "POST", "application/json", JSON.stringify(requestBody,jsonReplacer), null, null);
    
}catch(e) {
    utils.log("[8479] Invio notifica fallito: " + e.toString(),"INFO");
}
utils.setReturnValue(JSON.stringify(response,jsonReplacer));
```

