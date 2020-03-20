# Constraints

## setConstraints\(panelid, constraints, doAnimation\)

> Since 5.3.2 version

If the panel \(constraint panel, form, filter, editable panel, grid ecc\) is inside to a constraints panel, you can use this function for change panel constraints.

| Argument | Description |
| :--- | :--- |
| paneid | constraint panel idetifier |
| constraints | the array of controls constraint you want to change |
| doAnimation | true/false if you want animate the constraint changes |

For each elements of the constraints array you have to specify: the **panelId** \(or **attributeName**\)of the panel \(or control\) you want to change and the new **constraints** values.

Note: if you don't specify a control constraint this constraint will removed from the panel \(or control\).

This is the available constraint property:

```text
height
width
maxHeight
maxWidth
minHeight
minWidth
layoutConstraintLeftToLeftOf: platform_parent or panelId or a control attributeName.
layoutConstraintLeftToRightOf: platform_parent or panelId or a control attributeName.
layoutConstraintRightToLeftOf: platform_parent or panelId or a control attributeName.
layoutConstraintRightToRightOf: platform_parent or panelId or a control attributeName.
layoutConstraintTopToTopOf: platform_parent or panelId or a control attributeName.
layoutConstraintTopToBottomOf: platform_parent or panelId or a control attributeName.
layoutConstraintBottomToTopOf: platform_parent or panelId or a control attributeName.
layoutConstraintBottomToBottomOf: platform_parent or panelId or a control attributeName.
marginTop
marginBottom
marginLeft
marginRight
```

> Since 6.0.2 version

Example:

```javascript
//FOR CONSTRAINT PANEL:

var args = [
                {
                    panelId: "9",
                    constraints:{
                        layoutConstraintTopToTopOf: "platform_parent",
                        layoutConstraintLeftToLeftOf: "platform_parent",
                        marginLeft : 0,
                        width : 100
                    }
                },
                {
                    panelId: "19",
                    constraints:{
                        layoutConstraintTopToTopOf: "9",
                        layoutConstraintLeftToRightOf: "9",
                        marginRight : 10,
                        width : 300
                    }
                }
            ];
var animation = true;
setConstraints("349", args, animation);
```

## setConstraints\(panelid, constraints, doAnimation\)

> Since 5.3.2 version

If the panel \(form, filter or editable panel\) has the constraints layout enable, you can use this function for change controls constraints.

| Argument | Description |
| :--- | :--- |
| paneid | panel idetifier |
| constraints | the array of controls constraint you want to change |
| doAnimation | true/false if you want animate the constraint changes |

For each elements of the constraints array you have to specify the **attributeName** of the control you want to change and the new **constraints** values.

Note: if you don't specify a control constraint this constraint will removed from the control.

This is the available constraint property:

```text
height
width
maxHeight
maxWidth
minHeight
minWidth
layoutConstraintLeftToLeftOf: platform_parent or a control  attributeName.
layoutConstraintLeftToRightOf: platform_parent or a control  attributeName.
layoutConstraintRightToLeftOf: platform_parent or a control  attributeName.
layoutConstraintRightToRightOf: platform_parent or a control  attributeName.
layoutConstraintTopToTopOf: platform_parent or a control  attributeName.
layoutConstraintTopToBottomOf: platform_parent or a control  attributeName.
layoutConstraintBottomToTopOf: platform_parent or a control  attributeName.
layoutConstraintBottomToBottomOf: platform_parent or a control  attributeName.
marginTop
marginBottom
marginLeft
marginRight
```

Example:

```javascript
var args = [
                {
                    attributeName: "btnUno",
                    constraints:{
                        layoutConstraintTopToTopOf: "platform_parent",
                        layoutConstraintLeftToLeftOf: "platform_parent",
                        marginLeft : 0,
                        width : 100
                    }
                },
                {
                    subpanelId: "txtDue",
                    constraints:{
                        layoutConstraintTopToTopOf: "btnUno",
                        layoutConstraintLeftToRightOf: "btnUno",
                        marginRight : 10,
                        width : 300
                    }
                }
            ];
var animation = true;
setConstraints("349", args, animation);
```

## setConstraint\(panelId, attributeOrPanelID, constraints, doAnimation\)

> Since 5.3.2 version

Set the constraint of a panel or an attribute.

If panelId is a constraint panel the second params represents a panelId \(form, grid, map etc\).

If panelId is a form o filter panel with constraint layout enabled, the second params represents an attribute name.

| Argument | Description |
| :--- | :--- |
| paneid | panel idetifier \(constraint panel or form/filter panel with constraint layout\) |
| panelId or attribute name |  |
| constraints | the control constraint you want to change |
| doAnimation | true/false if you want animate the constraint changes |

