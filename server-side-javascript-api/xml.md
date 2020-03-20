# XML

## Parse a simple XML document and generate a Javascript "compatible" representation

_Javascript "compatible" representation is expressed using lists and js objects, where each js object has special attributes named: "tagName", "tagValue" and "subTags"._

The document \(list of tags\) is expressed as a list of js objects, where each js object can have a list of subtags and attributes, expressed object's attributes. The js object always contains special entries named "tagName", "subTags" and optionally "tagValue" if there is tag value.

**Syntax**

```javascript
var jsObjectsList = utils.parseXML(xmlDocument);
```

**Details**

| Argument | Description |
| :--- | :--- |
| xmlDocument | an XML document as a String |

Returns an XML representation, expressed as a list of Javascript objects, where each of them has three special attributes: "tagName", "tagValue" and "subTags". You can then navigate through this js object and extract any data.

**Example**

JohnDoe...

JaneRoe...

## Search for the specified path within the XML document parse result

_\(i.e. after invoking parseXML method\)_

**Syntax**

```javascript
var jsObjectsList = utils.findTagsByPath(xmlDocNodes, path);
```

**Details**

| Argument | Description |
| :--- | :--- |
| xmlDocNodes | XML document parsed through parseXML method |
| path | a tags path, expressed as tag1/tag2/tag3... |

```text
 Return all occurrences matching the specified path.
```

**Example**

JohnDoe...

JaneRoe...

```javascript
var xml = utils.getWebContent("[http://...",false,"GET](http://...",false,"GET)", null,null,null,null);
var xmlDocNodes = utils.parseXML(xml); // list of companies
var staffList = utils.findTagsByPath(xmlDocNodes, "company/staff");
```

## Scroll all input nodes and for each create a js object whose attributes are the subtags having the specified tagNames

_\(i.e. after invoking parseXML and findTagNames methods\)_

For each selected node, a new js object will be created and it will have as many attributes as the ones specified through tagNames argument, whose values will be retrieved by as sub tags values.

**Syntax**

```javascript
var jsObjects = utils.findTagsByNames(selectedNodes, tagNames);
```

**Details**

| Argument | Description |
| :--- | :--- |
| selectedNodes | nodes to analyze |
| tagNames | list of tag names to compare with each subtag of each selected node. |

**Example**

JohnDoe...

JaneRoe...

```javascript
var xml = utils.getWebContent("[http://...",false,"GET](http://...",false,"GET)", null,null,null,null);
var xmlDocNodes = utils.parseXML(xml); // list of companies
var staffList = utils.findTagsByPath(xmlDocNodes, "company/staff");
var jsObjects = utils.findTagsByNames(staffList,["firstname","lastname"]);
```

will return a list of js objects having this structure:

`[{ "firstname": "John", "lastname": ... }, { "firstname": "Jane", ...}]`

## Convert XML to HTML through a stylesheet \(XSL file\)

Platform embeds the Java standard XSLT transformer, through which you can convert data contained in an XML file to an HTML document, using an XSL file describing the layout of the HTML document and how to show data coming from the XML.

Basically, this feature uses XML + XSL to produce HTML

**Syntax**

```javascript
var ok = utils.convertXMLToHTML(
   xmlDirId, xmlFileName, xslDirId, xslFileName, htmlDirId, htmlFileName,
   namespaceAware,Boolean validating
);
```

**Details**

| Argument | Description |
| :--- | :--- |
| xmlDirId | directory id where the XML data file is located |
| xmlFileName | XML data file name, stored in the xmlDirId |
| xlsDirId | directory id where the stylesheet XSL file is located |
| xlsFileName | XLS file, used to define ther layout for the HTML file to generate |
| htmlDirId | directory id where the HTML will be generated |
| htmlFileName | HTML file name to generate |
| namespaceAware | true or false; defines whether the namespace must be checkd; if in dubt, set it to true |
| validating | true or false; defines whether the XML must be validated with respect to the XSL file; if in dubt, set it to true |

Note: if the resulting HTML file seems empty \(contains only CSS content but not data\), it is likely that the XSL definition requires a strong validation; in such a scenario, set both "namespaceAware" and "validating" to true.

