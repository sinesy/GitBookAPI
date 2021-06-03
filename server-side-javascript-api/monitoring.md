# Monitoring

Platform provides an health check mechanism which can be invoked by external IT monitoring systems in order to check out if the current node is working correctly.

This web service is public and can be invoked as a Rest Service. In the easiest case, the invokation URL is

```text
https://<domain>/platform/healthCheck
```

If the node is working, this service will respond with an HTTP 200 status and no content.

There are additional settings you can pass forward as request parameters, described as follows.

### 

### OK output

```text
https://<domain>/platform/healthCheck?gimmeOk=true
```

If the node is working, this service will respond with an HTTP 200 status and content set to "OK".

### 

### Database status

```text
https://<domain>/platform/healthCheck?checkBaseDatasourceToo=true
```

If the node is working, this service will respond with an HTTP 200 status and content set to something like:

```text
Time required to execute a query on the main repository using EntityManager: 28ms
Time required to get a connection on the main repository: 0ms
Time required to execute a query on the main repository using JDBC: 1ms
```



### Consumed memory

```text
http://localhost:8280/wag/healthCheck/traceUserSessions?json=true
```

If the node is working, this service will respond with an HTTP 200 status and content set to something like:

```text
{
"totalMemory": 210,
"freeMemory": 150,
"consumedMemory": 60,
"currentActiveSessions": 0,
"sessions": [

]
}
```



### Out of memory errors

```text
https://<domain>/platform/healthCheck?checkMemory=<minutes>
```

This web service will check if there have been out of memory errors in the last &lt;minutes&gt;.

This call is more helpful than the first one, since an out of memory could still allow a web application to run and respond with an HTTP 200, but this does not mean that the web app is in a stable state: checking for out of memories can avoid unpredictable behaviors by the application and inform the calling system to restart the VM.

In case of out of memory errors found, an HTTP 500 error is returned.













