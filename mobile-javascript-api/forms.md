# Forms and filter

## reloadFormPanel\(panelid, args\)

where XXX is the form identifier \(CON12\) - reload the form content

```javascript
var args = new Object();
args['INPUT_PARAM'] = 'EXAMPLE';

reloadFormPanel603(args);
```

## getFormPanelLabel\(panelid, attr\)

where XXX is the form identifier \(CON12\) and attr the name of the attribute which identifies a specific input field - returns the textof the input field label or button of the form panel

## setFormPanelLabel\(panelid, attr,value\)

where XXX is the form identifier \(CON12\) and attr the name of the attribute which identifies a specific input field - set the specified textin the input field label or button of the form panel

## getFormPanelValue\(panelid, attr\)

where XXX is the form identifier \(CON12\) and attr the name of the attribute which identifies a specific input field - returns the value currently set on the input field of the form panel

## setFormPanelValue\(panelid, attr,value\)

where XXX is the form identifier \(CON12\) and attr the name of the attribute which identifies a specific input field - set the specified value in the input field of the form panel

## setVisibleComponent\(panelid, attr, visible\)

Set the visibility state for the input control belonging to the panel recognized by panelid, identified by the attribute name. The second argument can have the values "Y" or "N", used to set the visibility

```javascript
setVisibleComponent(123, "controlName","Y");
or
setVisibleComponent(123, "controlName","N");
```

## insertFormPanel\(panelid\)

where XXX is the form identifier \(CON12\) - switch the form in insert mode

## saveFormPanel\(panelid\)

where XXX is the form identifier \(CON12\) -save the content of a form panel \(which can be in insert or edit mode\)

## **clearSearchFilterPanel\(**panelid**\)**

where XXX is the filter panel identifier \(CON12\) – clean the components of panel

## **applySearchFilterPanel\(**panelid**\)**

where XXX is the filter panel identifier \(CON12\) – apply the filter conditions of panel to linked grid

## **setEnabledPanelButton\(**panelid, **buttonId, enable\)**

Enable or disable the button in panel

Required arguments:

| Argument | Description |
| :--- | :--- |
| XXX | panel identifier |
| buttonId | key of button component |
| enable | Y/N for enable of disable |

## **setFormPanelMaxLength\(**panelid, **attr,value\)**

Set the max length for an input text.

Required arguments:

| Argument | Description |
| :--- | :--- |
| XXX | panel identifier \(CON12\) |
| attr | the name of the attribute which identifies a specific input field |
| value | the max lenght for the text |

## **setFormPanelPlaceholder\(panelid,attr,placeholder\)**

The placeholder attribute specifies a short hint that describes the expected value of an input field \(e.g. a sample value or a short description of the expected format\).  
The short hint is displayed in the input field before the user enters a value.

Required arguments:

| Argument | Description |
| :--- | :--- |
| panelid | panel identifier \(COM12\) |
| attr | the name of the attribute which identifies a specific input field |
| placeholder | is the short hint that describes the expected value of an input field |

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

## **setFocusByAttribute\(**panelid, **attr, selectAll\)**

where XXX is the panel identifier \(CON12\) and attr the name of the attribute which identifies a specific input field – set the focus on the component

| Argument | Description |
| :--- | :--- |
| attr | field attribute name |
| selectAll | Y/N \(optional\) - if Y select All |

```javascript
setFocusByAttribute1559("attributeName", "Y");
```

## **scrollPanelTo\(**panelid, **x, y\)**

where XXX is the panel identifier \(CON12\), if the panel is scrollable scroll \(ex. web preview o grid\) the panel to the x and y position specified.

`scrollPanelTo559(0, 0); //scroll panel to top`

## shrinkPanel\(panelid**\)**

Shrinks the panel vertically, removing any empty space after the last component.

| Argument | Description |
| :--- | :--- |
| panelid | panel identifier \(COM12\) |

Example:

```javascript
shrinkPanel(123);
```

## API AVAILABLE ONLY ON CURRENT PANEL:

## setVisibleComponent\(attr,visible\)

Set the visibility state for the input control belonging to the current form panel, identified by the attribute name. The second argument can have the values "Y" or "N", used to set the visibility

```javascript
setVisibleComponent("controlName","Y");
or
setVisibleComponent("controlName","N");
```

## setVisibleComponent\(panelid, attr,visible\)

Set the visibility state for the input control belonging to the current form panel, identified by the attribute name. The second argument can have the values "Y" or "N", used to set the visibility

```javascript
setVisibleComponent("controlName","Y");
or
setVisibleComponent("controlName","N");
```

## forceValidation\(attributeName\)

After setting a value to a lookup control, force the validation, by specifying the attribute name identifying the right lookup control.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| attributeName | attribute name identifying the lookup control where forcing the validation. |

## setBackgroundColorComponent\(attributeName, hexBackgroundColor\)

Sets the background color of the component.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| attributeName | attribute name identifying the component. |
| hexBackgroundColor | color code in hexadecimal \(also with 8 characters for alpha\) |

## setBackgroundColorComponent\(panelId, attributeName, hexBackgroundColor\)

Sets the background color of the component in panel.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| panelId | id of the panel |
| attributeName | attribute name identifying the component. |
| hexBackgroundColor | color code in hexadecimal \(also with 8 characters for alpha\) |

## setForegroundColorComponent\(attributeName, hexForegroundColor\)

Sets the foreground color of the component in the current panel.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| attributeName | attribute name identifying the component. |
| hexForegroundColor | color code in hexadecimal |

## setForegroundColorComponent\(panelId, attributeName, hexForegroundColor\)

Sets the foreground color of the component in panel.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| panelId | id of the panel |
| attributeName | attribute name identifying the component. |
| hexForegroundColor | color code in hexadecimal |

## pull\(\) <a id="pull"></a>

Get data from each input control and refresh the value object behind the form/editable panel.

## checkMandatoryControls\(\)

Check the current panel \(form or editable panel\) for mandatory input controls not filled: when finding one, shows a message dialog with the control name violating the mandatory property. The method returns "true" \(no mandatory controls found\) or "false" \(a string\), according to the outcome.

## setEnabledComponent\(attr, enable\)

Set the enable state for the input control belonging to the current form panel, identified by the attribute name. The second argument can have the values "Y" or "N", used to set the enable

## setEnabledComponent\(panelId, attr, enable\)

Set the enable state for the input control belonging to the panel, identified by the attribute name. The third argument can have the values "Y" or "N", used to set the enable

## **getMode\(\)**

Returns the mode \(READONLY, INSERT or EDIT\) of current panel

## API AVAILABLE ONLY ON FILTER PANEL:

## removeFilter\(fieldName\)

Remove a filtering condition fromthe filter panel search. Typically, this instruction is added to a js action linked to the "before search" event of the Search button in a filter panel.  
Required parameters:

```text
 fieldName - physical field name; the table name is not required; any filtering condition having this field name will be removed
```

## **getFilterPanelValue\(**panelid, **attr\)**

where panelId is the filter identifier \(CON12\) and attr the name of the attribute which identifies a specific input field – returns the value currently set on the input field of the filter panel

```javascript
getFilterPanelValue1559("attributeName");
```

## **setFilterPanelValue\(**panelid, **attr,value\)**

where panelId is the filter identifier \(CON12\) and attr the name of the attribute which identifies a specific input field – set the specified value in the input field of the filter panel

```javascript
setFilterPanelValue(1159, "attributeName", "value");
```

## setFormPanelCurrency\(panelId, attrName, currency\)

where panelId is the panel identifier \(CON12\) and attr the name of the attribute which identifies a specific input field – set the specified currency in the input field of the filter panel

