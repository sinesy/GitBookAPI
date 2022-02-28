# Window

A window created through the App Designer comes along with a series of javascript methods you can use to manage dependencies among windows.

A complex scenario in an application could involve a couple of windows:

* a window A containing a grid and a detail (e.g. variables "grid1" and "formPanel1"); a click on a row in the grid leads to open a second window
* a window B, opened from the row click in the grid of the window; this second window can contain another panel, a grid or a form (e.g. variable "formPanel2"), something editable

The need is to being aware in the first window about writing operations applied in the second window which make the content currently shown in window A not any more valid (consistent).

A way to make consistent the content in window A is force the reloading of the content of the window. Another alternative is just inform the user about the old content (e.g. through a toast message).

In any case, window A must be informed about changes in window B. A sort of dependency is in action among panels of the first window, which depend on a panel in the second one.

A window (variable "win") provides a series of methods which come in handy to manage the scenario described above:

### Declaring a dependency between a panel in window B with a list of panels in window A

This dependency can be declared for example through a javascript action linked to the event "after render" of a window.

**Syntax**

```
win.addDependingPanels("formPanel2",["grid1","formPanel1"]);
```



### Mark a panel in B as changed

The following method can be invoked for example within actions like "after save in insert" and "after save in edit" of the form in window B. **In this way, the window A is informed about changes and can mark its panels as "to reload"**, using the dependency declared above.

**Syntax**

```
windowA.markPanelsToReload("formPanel2");
```

Here the problem is how to get a reference to the windowA instance.

In order to have it inside window B, a good practice is to pass forward the window ID when creating window B; suppose this is the action invoked when opening window B from window A:

```
// here I am opening window B and I pass forard a reference to the current window (window A)
openWindowXYZ({ parentWindowId: win.id, ... });
```



### Check out if at least one panel has been marked as "to reload"

After invoking the maskPanelsToReload(..), the window A will mark every depending panel ("grid1", "formPanel1") as "to reload".

You can checkout this value through another method, which returns true if there is at least one panel marked as "to reload":

**Syntax**

```
if (win.isPanelToReload()) {
  // do something, like showToast(..)
}
```



### Check out if a specific panel has been marked as "to reload"

After invoking the maskPanelsToReload(..), the window A will mark every depending panel ("grid1", "formPanel1") as "to reload".

You can checkout this value for a specific panel, through another method:

**Syntax**

```
if (win.isPanelToReload("grid1")) {
  // do something, like showToast(..)
}
```



### Unmark panels (not to reload)

It is also possible to undo the "to reload" state for all panels in the dependecy list:

**Syntax**

```
windowA.markPanelsNotToReload("formPanel2");
```

**Note**: bear in mind that this is not needed! Each time a grid or a form is reloaded, they internally change their state to "not to reload".



### Waiting for BigQuery async saving completion on the UI

In case a form or grid is saving data on Google Datastore and the Datastore object is synchronized with BigQuery, the saving operation on BigQuery is asynchronous, since it is slow.

As a consequence, freshed data coming from BigQuery to show on the UI is really updated only after the asynchronous operation has been completed.

In order to wait for this completion, it is possible to pass forward a parameter to a Form or Grid when saving data on insert or in update. This parameter would force the server layer to inform the UI when all writing operations on BigQuery have been completed.

You can use the "before saving data in insert/edit" events in grid/form to include the following scriptlet:

```javascript
var uuid = addSaveCompletedEvent(gridxxx,function() {
    // callback invoked when the async task on BQ has been completed
    // after saving data on grid/form
    /*
    showToast({
        title: "common.warning",
        message: "Saving on BQ completed.",
        sleep: 3
    });
    gridxxx.store.reload();
    */
});

additionalParams = "&saveCompleted="+uuid;
```

Basically, it adds a listener on the UI, waiting for BQ saving completion, then the callback is invoked and can be used to reload data on that panel or in other panels.











