# Grids and gallery

## reloadGridPanel\(panelid, args\)

where XXX is the grid identifier \(CON12\) - reload the content of the grid

```javascript
var args = new Object();
args['INPUT_PARAM'] = 'EXAMPLE';

reloadGridPanel603(args);
```

## reloadGalleryPanel\(panelid, args\)

where XXX is the galleryidentifier \(CON12\) - reload the content of the gallerypanel

```javascript
var args = new Object();
args['INPUT_PARAM'] = 'EXAMPLE';

reloadGalleryPanel603(args);
```

## setVisibleColumn\(attr,visible\)

Set the visibility state for a column in grid; the column isidentified by the attribute name. The second argument can have the values "Y" or "N", used to set the visibility.  
This method can be invoked only before showing the grid, so it should be used within a js action binded to a "before rendering grid" event.

```javascript
setVisibleColumn("columnName","Y");
or
setVisibleColumn("columnName","N");
```

## getPanelParameter\(name\)

Get a parameter value passed to the current panel \(trough the window args variable\).  
Required parameters are:

| Parameter | Description |
| :--- | :--- |
| name-parameter | name |

**Example**

```javascript
//From the window "A" I open the window "B"

//Window A
var args = {
    param1: "MyCustomParam"
};

//...
//Window B
getPanelParameter('param1');   //Output: "MyCustomParam"
```

## **setPanelOptionalParameter\(**panelid, **parName, value\)**

Set the optional parameter for panel grid or detail

Required arguments:

| Argument | Description |
| :--- | :--- |
| XXX | panel identifier |
| parName | name of parameter |
| value | value to set for parName |

## **getPanelOptionalParameter\(**panelid, **parName\)**

Return the value of optional parameter of panel grid or detail \(\)

Required arguments:

| Argument | Description |
| :--- | :--- |
| XXX | panel identifier |
| parName | name of parameter |

## **setCustomColumnHeader\(attributeName, header\)**

Set the header of attribute name column for current grid**\(action must be executed BEFORE RENDER\)**  
Required arguments:

| Argument | Description |
| :--- | :--- |
| attributeName | key of column |
| header | text for column header |

## **scrollPanelTo\(**panelid, **x, y\)**

where XXX is the panel identifier \(CON12\), if the panel is scrollable scroll \(ex. web preview o grid\) the panel to the x and y position specified.

NB: not works for gallery

`scrollPanelTo559(0, 0); //scroll panel to top`

## setGridNoDataMessage\(panelid, message**\)**

Set the text message of the grids without data.

| Argument | Description |
| :--- | :--- |
| panelid | panel identifier \(COM12\) |
| message | the message to show |

Example:

```javascript
setGridNoDataMessage(123, "No data found");
```

## enableGridMultiselectionMode**\(panelid, enable\)**

Enable o disable the multi-selection mode in a grid.

| Argument | Description |
| :--- | :--- |
| panelId | the grid id |
| enable | Y or N for enable or disable |

## selectAllGridRows\(panelid\)

If you have enabled the multi-select mode in a grid, select all visible rows in that grid.

Note: if you have activated the lazy loading only the load rows are selected, in this case you should manage multiple selection differently.

| Argument | Description |
| :--- | :--- |
| panelId | The grid id |

## deselectAllGridRows\(panelid\)

If you have enabled the multi-select mode in a grid, deselect all visible rows in that grid.

| Argument | Description |
| :--- | :--- |
| panelId | The grid id |

## getGridSelectedRows\(panelid\)

If you have enabled the multi-select mode in a grid, return the selected rows vo.

| Argument | Description |
| :--- | :--- |
| panelId | The grid id |

Example:

```javascript
var json = getGridSelectedRows(123);
var selectedRows = JSON.parse(json);
for(var i=0; i<selectedRows.length; i++)
{
    logger("sample: "+selectedRows[i].MY_FIELD);
}
```

## setGridReloadPosition\(panelid, position\)

Set grid option to scroll rows on TOP or BOTTOM after data reload.

| Argument | Description |
| :--- | :--- |
| panelId | The grid id |
| position | TOP or BOTTOM Scroll position |

Example:

```javascript
setGridReloadPosition(123, "BOTTOM");
```

## setGridRow\(panelid, position, rowVo, selected\)

Refresh the row at the given position with the passed vo, then force the render to be reload only for that position.

N.B. use this function for refresh ONLY ONE ROW, if you need to refresh more row use the setGridRows function

| Argument | Description |
| :--- | :--- |
| panelId | The gird id |
| position | The row position, start from 0 |
| rowVo | The row map object |
| selected | \[optional\] Y/N if multi-selection is enable select or deselect the row after set vo |

Example:

```javascript
var voNew = {
    selected : 'Y'
    description : 'Gino' 
}
var position = 0, //0 to length - 1

setGridRow(123, position, voNew);
```

## setGridRows\(panelid, rowsVo\)

Set the passed row to the grid and force the render to be refresh only for the given rows.

| Argument | Description |
| :--- | :--- |
| panelId | The gird id |
| rowsVo | An array of rows to refresh |

Example:

```javascript
var updateRows = [];

updateRows.push({
    position : 2, //0 to length - 1
    vo : voNew //the single row vo
})
setGridRows(89, updateRows);
```

## selectGridRow\(panelid, position, select\)

Select or deselect the passed row in a grid if the grid is in multi-selection mode.

| Argument | Description |
| :--- | :--- |
| panelId | The grid id |
| position | The row position |
| select | Y/N select or deselect |

## selectGridRows\(panelid, positions, select\)

Select or deselect the passed row in a grid if the grid is in multi-selection mode.

| Argument | Description |
| :--- | :--- |
| panelId | The grid id |
| positions | The array of row position to select |
| select | Y/N select or deselect |

## refreshGrid\(panelid\)

> Since 6.0.2 version

Invalidate the grid rows and redraw it without execute query. This function force the cell renders and not change the scrollview position.

| Argument | Description |
| :--- | :--- |
| panelId | The grid Id |

