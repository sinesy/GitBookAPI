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

## getFormPanelAddressValue\(panelid, attr\)

where panelid is the form identifier \(CON12\) and attr the name of the attribute which identifies a specific input field, the input type must be  an address autocomplete fields. - returns the selected address components  string in JSON format

```javascript
{
  "administrativeAreaLevel1": "Lazio",
  "administrativeAreaLevel1Short": "Lazio",
  "administrativeAreaLevel2": "Città Metropolitana di Roma",
  "administrativeAreaLevel2Short": "RM",
  "administrativeAreaLevel3": "Roma",
  "administrativeAreaLevel3Short": "Roma",
  "country": "Italia",
  "countryShort": "IT",
  "locality": "Roma",
  "localityShort": "Roma",
  "route": "Via del Corso",
  "routeShort": "Via del Corso",
  "streetnumber": "1",
  "streetnumberShort": "1"
}
```

```javascript
var addressJSONString = getFormPanelAddressValue(4819,"txtAddress");
var addressMap = JSON.parse(addressJSONString);
```

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

## setFormPanelControlBackgroundColor\(attributeName, hexBackgroundColor\)

Sets the background color of the component.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| attributeName | attribute name identifying the component. |
| hexBackgroundColor | color code in hexadecimal \(also with 8 characters for alpha\) |

> before the 6.0.2 version this function name was: **setBackgroundColorComponent**

## setFormPanelControlBackgroundColor\(panelId, attributeName, hexBackgroundColor\)

Sets the background color of the component in panel.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| panelId | id of the panel |
| attributeName | attribute name identifying the component. |
| hexBackgroundColor | color code in hexadecimal \(also with 8 characters for alpha\) |

> before the 6.0.2 version this function name was: **setBackgroundColorComponent**

## setFormPanelControlForegroundColor\(attributeName, hexForegroundColor\)

Sets the foreground color of the component in the current panel.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| attributeName | attribute name identifying the component. |
| hexForegroundColor | color code in hexadecimal |

> before the 6.0.2 version this function name was: setForegroundColorComponent

## setFormPanelControlForegroundColor\(panelId, attributeName, hexForegroundColor\)

Sets the foreground color of the component in panel.  
Required parameters are:

| Argument | Description |
| :--- | :--- |
| panelId | id of the panel |
| attributeName | attribute name identifying the component. |
| hexForegroundColor | color code in hexadecimal |

> before the 6.0.2 version this function name was: setForegroundColorComponent

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

where panelId is the panel identifier \(CON12\) and attrName the name of the attribute which identifies a specific input field – set the specified currency in the input field of the panel

## setFormPanelStyle\(panelId, attrName, style\)

> Since 6.0.2 version

where panelId is the panel identifier \(CON12\) and attrName the name of the attribute which identifies a specific input field -  set the specified style to the field of the panel.

The available attributes for the style object are:

* mobileControlBorderColor
* mobileControlBorder
* mobileBackgroundColor
* mobileForeColor
* mobileFontName
* mobileFontStyle
* mobileFontSize
* showCounterChars
* disableSelfCorrection
* textStrikethrough

```javascript
var style = {
	mobileControlBorder: "ALL_ROUNDED",
	mobileControlBorderColor  : "#FF0000",
	mobileFontSize : 14,
	textStrikethrough : "Y"
}
setFormPanelStyle(19, "descriptionIt", style)
```

## getFormPanelVo\(panelId\)

> Since 6.0.2

Returns the passed panel vo.

## addFormPanelControl\(panelId,controlArgs,constraints,style\)

> Since 6.0.2

Add a control to visible panel, the panel must have a CONSTRAINT layout, absolute layout is not supported.

| Argument | Description |
| :--- | :--- |
| panelId | panel identifier |
| controlArgs | the controls properties |
| constraints | the control constraints |
| style | the control sytle \(see setFormPanelStyle\) |

**controlArgs** is a JSON and support  this properties:

* type
* attributeName
* label
* value \[OPTIONAL\]
* eventClick \[OPTIONAL\]: the actionId of the action to call on click event
* eventChangeValue \[OPTIONAL\]: the actionId of the action to call on change event
* eventLostFocus \[OPTIONAL\]: the actionId of the action to call on lost focus event

Supported controls are:

* "TEXT\_FIELD";
* "BUTTON\_FIELD";
* "LABEL\_FIELD";
* "LINE\_FIELD";
* "TEXTAREA\_FIELD";
* "IMAGE\_URL\_FIELD";
* "IMAGE\_PATH\_FIELD";

**constraints** is a JSON, see [Constraints](constraints.md) for the list   of  available properties

**style** is a JSON, see  **setFormPanelStyle** method for the list  of available properties

```javascript
var controlArgs = { 
    type : "BUTTON_FIELD", 
    attributeName : "customButton1", 
    label : "Bottone 1", 
    eventClick : 7219
}
var constraints = {
                      "layoutConstraintLeftToLeftOf": "center",
                      "layoutConstraintTopToTopOf": "center",
                      "height": 250,
                      "width": 250
                    }

var style = {
    mobileBackgroundColor : "2f4352",
    mobileForeColor : "FFFFFF"
};

addFormPanelControl(279, controlArgs, constraints, style);

```

## setFormPanelDatePickerStyle\(panelId, attributeName, style\)

> Since 6.0.2

Set the style of a date picker controls.

| Argument | Description |
| :--- | :--- |
| panelId | panel identifier |
| attributeName | attribute name |
| style | the control sytle \(see setFormPanelStyle\) |

Style accept the following properties:

* showNowButton: only works on iOs Picker
* title: only works on iOs Picker

## resetFormPanelControls\(panelId\)

> Since 6.0.2

Reset the panel to its initial state, remove any runtime components added

| Argument | Description |
| :--- | :--- |
| panelId | panel identifier |

