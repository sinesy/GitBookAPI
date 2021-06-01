# Chips panel

Since version 6.0.1 of Platform, there is a new type of panel: the ChipsPanel, which can be used to render a list of chips. This panel is based on ExtJS and completely embeddable in already existing windows.

There are 2 ways to create it:

* in version 6.0.1 it is possible to create an instance of this panel only programmatically, using the object **Tinet.ChipsPanel**
* starting from version 6.0.2, it is also possible to use the wizard for window/panels creation and configure this panel graphically

A Chips panel can render a series of chips on a "column layout", i.e. from left to right and from top to bottom, according to the available space.

Each chip is composed of a description and an X button, used to remove the chip from the panel.

When clicking on the chip, a tooltip window is shown and used to report additional data about the chip, like the code and description associated to the chip and a "remove" button, used to remove the chip from the panel.

Each chip contains behind the scene a javascript object, which be accessed as "**vo**" attribute in the chip object. The unique identifier of the chip \(**valueField** property\) and the description to show in the chip \(**displayField** property\) must be part of this javascript object.

A Tinet.ChipsPanel has the following syntax:

```text
var myChipsPanel = ne Tinet.ChipsPanel({
    listeners: {
      afterDetail: function(vo) {},
      afterRemove: function(vo) {},
      beforeRemove: function(vo) { return true|false },
      beforeDetail: function(vo) { return true|false },
    },
    compId: xyz, // optional, if specified, it represents the remote business component to invoke in order to get the list of data
    panelId: xyz, // optional, if specified, it represents the panel connected to the remote business component to invoke in order to get the list of data
    valueField: "...",  // optional, if not specified, it is autofilled with "id"
    displayField: "...", // mandatory
    translation: true|false, // optional: if true, a translation would be used; example: if displayField="descriptioIt", translation=true, languageAppId="EN" then the real attribute would be "descriptionEn" 
    chipTooltip: "", // optional; contains HTML and attribute values, each expressed as {attribute}; example: "<b>Code: {code}</b><br><span>{description}</span>
    chipStyle: {} // optional;
  });
```

**Syntax**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Attribute</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">listeners.afterDetail</td>
      <td style="text-align:left">optional callback, invoked each time the end user clicks on a chip</td>
    </tr>
    <tr>
      <td style="text-align:left">listeners.afterRemove</td>
      <td style="text-align:left">optional callback, invoked each time the end user clicks on the X button,
        within the chip, in order to remove it</td>
    </tr>
    <tr>
      <td style="text-align:left">listeners.beforeRemove</td>
      <td style="text-align:left">optional callback, invoked each time the end user clicks on the X button:
        this callback can interrupt the removal of the chips, if a &quot;return
        false&quot; is returned</td>
    </tr>
    <tr>
      <td style="text-align:left">listeners.beforeDetail</td>
      <td style="text-align:left">optional callback, invoked each time the end user clicks on a chip: this
        callback can interrupt the opening of the chip tooltip, if a &quot;return
        false&quot; is returned</td>
    </tr>
    <tr>
      <td style="text-align:left">compId</td>
      <td style="text-align:left">this is an optional attribute: if specified, the ChipsPanel will fetch
        data from a remote business component for lists and use this data to fill
        in the panel with a chip for each element in the returned list. If not
        specified, it is up to the programmer to fill in the panel, either using
        the &quot;load&quot; method (add multiple chips at the same time and remove
        the previous ones) or through the &quot;addChip&quot; method (add a single
        chip to the already existing chips)</td>
    </tr>
    <tr>
      <td style="text-align:left">panelId</td>
      <td style="text-align:left">this is an optional attribute: it must be filled with the current panel
        id ONLY IF the &quot;compId&quot; attribute has been specified. Moreover,
        if the application has activated the checking of roles on the server side,
        you have also to include the current compId in the list of compIds allowed
        to be invoked by the client.</td>
    </tr>
    <tr>
      <td style="text-align:left">valueField</td>
      <td style="text-align:left">mandatory attribute used to define the unique identifier for the chip,
        among the attributes stored within the chip</td>
    </tr>
    <tr>
      <td style="text-align:left">displayField</td>
      <td style="text-align:left">mandatory attribute used to show it as the chip description</td>
    </tr>
    <tr>
      <td style="text-align:left">translation</td>
      <td style="text-align:left">optional flag; if set to true, Platform will attempt to show within the
        chip a description coming from an attribute which can be &quot;displayField&quot;
        if this is related to the right language id used by the current user (e.g.
        displayField = &quot;descriptionIt&quot; for language id = &quot;IT&quot;)
        or an alternative attribute reckoned starting from the prefix of &quot;displayField&quot;
        and suffix coming from the current language id (e.g. displayField = &quot;descriptionIt&quot;
        with language id = &quot;EN&quot; would lead to use as description the
        value of &quot;descriptionEn&quot; attribute</td>
    </tr>
    <tr>
      <td style="text-align:left">chipTooltip</td>
      <td style="text-align:left">
        <p>optional attribute: it contains HTML and attribute values, each expressed
          as {attribute}; example:</p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p>&lt;b&gt;Code: {code}&lt;/b&gt;&lt;br/&gt;
          <br />{description}</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">chipStyle</td>
      <td style="text-align:left">optional attribute: it can contains additional CSS settings to pass forward
        when rendering a chip</td>
    </tr>
  </tbody>
</table>



The Tinet.ChipsPanel inherits from Ext.Panel and you can also use any other settings coming from Ext.Panel, including its methods.

Apart from that, ChipsPanel provides also a few utility method, described below:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">removeAll()</td>
      <td style="text-align:left">Remove all chips added to the panel; this method is also invoked automatically
        each time the &quot;load&quot; method is called</td>
    </tr>
    <tr>
      <td style="text-align:left">addChip(vo,opts)</td>
      <td style="text-align:left">vo is a javascript object, to embed in the chip and including the attributes
        referred by &quot;valueField&quot;, &quot;displayField&quot; and any other
        attribute referred in &quot;chipTooltip&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">removeChip(vo)</td>
      <td style="text-align:left">remove a chip from the panel, starting from the vo embedded on it</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <br />getChipByItemId(itemId)</td>
      <td style="text-align:left">get the chip (UI component) starting from its itemId property</td>
    </tr>
    <tr>
      <td style="text-align:left">getChipByValue</td>
      <td style="text-align:left">get the chip (UI component) starting from the unique identifier (valueField)</td>
    </tr>
    <tr>
      <td style="text-align:left">getDataByItemId</td>
      <td style="text-align:left">get the vo embedded in a chip, starting from the chimp itemId</td>
    </tr>
    <tr>
      <td style="text-align:left">getDataByValue</td>
      <td style="text-align:left">get the vo embedded in a chip, starting from its unique identifier (valueField)</td>
    </tr>
    <tr>
      <td style="text-align:left">getChips()</td>
      <td style="text-align:left">get the list of chips currently shown (list of UI components)</td>
    </tr>
    <tr>
      <td style="text-align:left">load()</td>
      <td style="text-align:left">load all data from the remote business component; in order to use this
        method, both panelId and compId panel properties must be defined</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>load({</p>
        <p>vos: [...],</p>
        <p>opts: {...}</p>
        <p>})</p>
      </td>
      <td style="text-align:left">load all data from a local list of objects; &quot;opts&quot; is optional
        and applied to all items</td>
    </tr>
  </tbody>
</table>



### Creating a ChipsPanel programmatically

You can use a javascript event and use it to create an Ext.Window containing a ChipsPanel object or you can include this panel in an already existing or new window. In the latter case, you can use the Window creation wizard and choose the Custom panel or open an already existing window and again add a Custom panel.

When defining the Custom panel, you have to refer a javascript global function which must get back the ChipsPanel. Consequently, you have also to define such a function in some .js file included in the web context or in the starting javascript action bound to the application.

An example of this function is reported below:

```text
function getMyChipsPanel() {
    var chipsPanel = new Tinet.ChipsPanel({
    border: false,
    listeners: {
     afterDetail: function(vo) {},
     afterRemove: function(vo) {},
     beforeRemove: function(vo) { return true },
     beforeDetail: function(vo) { return true },
    },
    panelId: ...,
    compId: ...,
    valueField: "progId",  // optional, if not specified, it is autofilled with "id"
    displayField: "descriptionIt", // mandatory
    translation: true, // optional: if true, a translation would be used; example: if displayField="descriptionIt", translation=true, languageAppId="EN" then the real attribute would be "descriptionEn" 
    chipTooltip: "<b>Code: {progId}</b><br><span>{descriptionIt}</span>", // optional; contains HTML and attribute values, each expressed as {attribute}; example: "<b>Code: {code}</b><br><span>{description}</span>
    chipStyle: {}
  });
  chipsPanel.load();
  return chipsPanel;
}
```

In this example the Chips panel is filled in through the "**load**" method which will invoke asynchronously a server-side business component for lists and use the objects contained in the response to create chips. Each object must contain the attributes defined int he ChipsPanel definition, i.e. valueField and displayField \(and also the ones referred int he chipsTooltip attribute, if specified\).

An alternative way to fill in the panel is through the load method, which can accept a list of objects and optionally also optional CSS settings:

```text
var opts = null;

chipsPanel.load({
  vos: [{ 
    progId: 123,
    descriptionIt: "UnDueTre",
    descriptionen: "OneTwoThree"
  },
  ...
  ],
  opts
});
```

Finally, you can add chips through the "addChip" method:

```text
var opts = null;

chipsPanel.addChip({
    progId: 123,
    descriptionIt: "UnDueTre",
    descriptionen: "OneTwoThree"
}, opts);
```



### Customizing the chips theme

You can customize the chimps theme through CSS. All default settings are stored in app.css default file, in the section named "chips".

When overriding it, you can change for example the tooltip window width, colors, borders, etc.



