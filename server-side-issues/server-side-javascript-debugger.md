# Server-side Javascript Debugger

In case of server-side Javascript actions \(not js business components\), it is also available a simple debugger you can use to control the right execution of the source code you wrote.

In order to stop the execution of the js code at specific positions, there is a special method you have to include in the code:

**utils.suspend\("executionpoint"\);**

where the text specified as argument is used to give a friendly name to the suspendingpoint.

You can add any number of these instructions inside your js action: the execution will be interrupted at each of them.

More precisely, the execution **is interrupted in a specific action only if** in the App Designer the user has opened the definition window for that action and has pressed the "Debug" button on the right: in that case, a window is opened, showing the list of all executions for that actions which have been suspended.

That means an action will not be suspended until the "Debug" window is showed. Again, when closing the "Debug" window will makes not working the suspension again. This behavior avoids to stop actions executions when there is no one who is checking them through the Debug window.

In the "Debug" window there is a "Resume" button which is used to resume the execution of a suspended action.

The "Resume all" button is used to resume all the suspended execution _for that action_.

A double click on a suspended execution will open a detail window where you can see all the variables defined within that action. A righe click on a node of the variables tree will allow you to changethe current value.

Again,there is a "Resume" button which is used to resume the execution of a suspended action. When pressing it, you can resume the execution.

