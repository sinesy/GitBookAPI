# Activiti

## Activiti BPM - Start a process

Method used to start a process and get back a process instance id.

**Syntax**:

```javascript
var responseObj = utils.startActivitiProcess(
  String appId, 
  String processDefinitionId, 
  Map params, 
  Map processVariables
);
```

**Description**:

| Argument | Description |
| :--- | :--- |
| appId | application id having the process defined internally |
| processDefinitionId | process id defined when creating the workflow though the Activiti Web Designer |
| params | optional parameters which can override the default ones; for example there can be attributes like "username" and "password" which can be used instead of the current logged user, when starting the process |
| processVariables | input parameters defined for the Start task within the process definition |

The responseObj javascript object can contain:

* success - boolean flag reporting whether the process was started successfully
* id  - the process instance id related to the instance just started, in case of success = true
* msg - error message, in case of success = false

## Activiti BPM - Complete a manual task

Method used to start and complete a manual task for the current logged user.

**Syntax**:

```javascript
var responseObj = utils.completeActivitiTask(
  String processInstanceId, 
  Map params, 
  Map processVariables
);
```

**Description**:

| Argument | Description |
| :--- | :--- |
| processInstanceId | instance id related to a process started |
| params | optional parameters which can override the default ones; for example there can be attributes like "username" and "password" which can be used instead of the current logged user, when starting the process |
| processVariables | input parameters to pass forward to the manual task to start/complete |

The responseObj javascript object can contain:

* success - boolean flag reporting whether the process was started successfully
* msg - error message, in case of success = false

