# Archiflow

## Get a paginated list of data to fill in a grid or selector

Archiflow ECM does not allows to read the whole content, but only a block of data.

Consequently, the only way to get data to show in a grid is through a javascript method which reads a block of records, where a record is an Archiflow Card content, that is to say, a set of metadata \(Archiflow field values\).

This method can be used within a javascript type business component linked to a grid/selector.

**Syntax**:

```javascript
var json = utils.getPartialResultOnArchiflow(
  dataModelId,
  filters,
  archiveIds,
  cardsWithAttachedDoc,
  searchType,
  mapAdditionalSettings
);

utils.setReturnValue(json);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dataModelId | data model id related to the document type; before creating a grid filled by this method, you have to reverse engineer an Archiflow Document Type, by creating a "Data Model from Archiflow". This data model id is related to such a model |
| filters | mandatory javascript Array, containing filters \(each a javascript object\); see below for the extract content of a filter; if not filters are need, set it to \[\] |
| archiveIds | javascript Array containing the id for the archive id where searching for cards, i.e. Archiflow will get back only cards having the specified document type \(inherited by the data model id\); these cards must be stored in any of the archives specified here |
| cardsWithArrachedDoc | boolean flag indicating whether Archiflow has to get back only cards having a document attached to them. If set to false, all cards are returned, not only the ones having a document |
| searchType | integer value used by Archiflow to drive which kind of search to carry out: indexed or generic; it must be set to null |
| mapAdditionalSettings | additional settings to pass forward to Archiflow, expressed as a javascript object; it must be set to null |

A filter has the following structure:

```text
{
  FieldId: "...", // the id for the field defined in Archiflow; look at the corresponding data model (without the prefix Field)
  FieldValue: "...",
  FieldValueTo: "..."
}
```

## Get a card content to fill in a detail form

This method can be used within a javascript type business component to fill in a form panel, starting from a specific Card stored in Archiflow, which can be retrieved using the card id.

**Syntax**:

```javascript
var json = utils.getDetailOnArchiflow(
  dataModelId,
  reqParams.cardId,
  mapAdditionalSettings
);

utils.setReturnValue(json);
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dataModelId | data model id related to the document type; before creating a grid filled by this method, you have to reverse engineer an Archiflow Document Type, by creating a "Data Model from Archiflow". This data model id is related to such a model |
| reqParams.cardId | let's suppose that this business component is linked to a form: in such a case, the form will automatically pass the primary key, which will be always the standard field cardId |
| mapAdditionalSettings | additional settings to pass forward to Archiflow, expressed as a javascript object; it must be set to null |

## Create a card

A card in Archiflow can be automatically created starting from a form panel linked to a business component linked to a "data model from Archiflow": Platform will create a card automatically, starting from the document type id specified with the data model from Archiflow" and the archive id defined at form level.

Moreover, it is possible to programatically create a card, starting from a server-side javascript action, by means of the following utility method:

**Syntax**:

```javascript
var card = utils.insertCard(Long dataModelId, Long panelId, Map vo, Integer archiveId, Map additionalSettings)
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dataModelId | data model id related to the document type; before creating a grid filled by this method, you have to reverse engineer an Archiflow Document Type, by creating a "Data Model from Archiflow". This data model id is related to such a model |
| panelId | actually, it is not essential |
| vo | the card content, expressed as a javascript object having the same attributes defined in the corresponding data model |
| archiveId | it identified where to store the card, within Archiflow repository |
| additionalSettings | additional settings to pass forward to Archiflow, expressed as a javascript object; it must be set to null |

## Create a list of cards

A list of cards in Archiflow can be automatically created starting from a grid panel linked to a business component linked to a "data model from Archiflow": Platform will create a list of cards automatically, starting from the list of new rows created in grid and from the document type id specified with the data model from Archiflow" and the archive id defined at grid level.

Moreover, it is possible to programatically create a list of cards, starting from a server-side javascript action, by means of the following utility method:

**Syntax**:

```javascript
var card = utils.insertCards(Long dataModelId, Long panelId, Map[] vos, Integer archiveId, Map additionalSettings)
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dataModelId | data model id related to the document type; before creating a grid filled by this method, you have to reverse engineer an Archiflow Document Type, by creating a "Data Model from Archiflow". This data model id is related to such a model |
| panelId | actually, it is not essential |
| vos | a javascript Array, where each element is a javascript object representing a card to create, having the same attributes defined in the corresponding data model |
| archiveId | it identified where to store the card, within Archiflow repository |
| additionalSettings | additional settings to pass forward to Archiflow, expressed as a javascript object; it must be set to null |

## Update a card

A card in Archiflow can be automatically updated starting from a form panel linked to a business component linked to a "data model from Archiflow": Platform will create a card automatically, starting from the document type id specified with the data model from Archiflow" .

Moreover, it is possible to programatically update a card, starting from a server-side javascript action, by means of the following utility method:

**Syntax**:

```javascript
var card = utils.updateCard(Long dataModelId, Long panelId, Map vo)
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dataModelId | data model id related to the document type; before creating a grid filled by this method, you have to reverse engineer an Archiflow Document Type, by creating a "Data Model from Archiflow". This data model id is related to such a model |
| panelId | actually, it is not essential |
| vo | the card content, expressed as a javascript object having the same attributes defined in the corresponding data model |

## Update a list of cards

A list of cards in Archiflow can be automatically updated starting from a grid panel linked to a business component linked to a "data model from Archiflow": Platform will update these cards automatically, starting from a list of modified rows in grid and from the document type id specified with the data model from Archiflow"

Moreover, it is possible to programatically update a list of cards, starting from a server-side javascript action, by means of the following utility method:

**Syntax**:

```javascript
var card = utils.updatesCard(Long dataModelId, Long panelId, Map[] vos)
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dataModelId | data model id related to the document type; before creating a grid filled by this method, you have to reverse engineer an Archiflow Document Type, by creating a "Data Model from Archiflow". This data model id is related to such a model |
| panelId | actually, it is not essential |
| vos | a javascript Array containing a list of javascript objects, where each object contains the card content, having the same attributes defined in the corresponding data model |

## Delete a card

A card in Archiflow can be automatically deleted starting from a form panel linked to a business component linked to a "data model from Archiflow": Platform will delete a card automatically, starting from the the form content.

Moreover, it is possible to programatically delete a card, starting from a server-side javascript action, by means of the following utility method:

**Syntax**:

```javascript
var card = utils.deleteCard(Long dataModelId, Long panelId, Map vo)
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dataModelId | data model id related to the document type; before creating a grid filled by this method, you have to reverse engineer an Archiflow Document Type, by creating a "Data Model from Archiflow". This data model id is related to such a model |
| panelId | actually, it is not essential |
| vo | the card content, expressed as a javascript object having the same attributes defined in the corresponding data model |

## Delete a list of cards

A list of cards in Archiflow can be automatically deleted starting from a grid panel linked to a business component linked to a "data model from Archiflow": Platform will delete these cards automatically, starting from the list of selected rows in grid, related to the rows to delete.

Moreover, it is possible to programatically delete cards, starting from a server-side javascript action, by means of the following utility method:

**Syntax**:

```javascript
var card = utils.deleteCards(Long dataModelId, Long panelId, Map[] vos)
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dataModelId | data model id related to the document type; before creating a grid filled by this method, you have to reverse engineer an Archiflow Document Type, by creating a "Data Model from Archiflow". This data model id is related to such a model |
| panelId | actually, it is not essential |
| vos | a javascript Array, containing javascript objects, where each object represents a card, having the same attributes defined in the corresponding data model |

## Upload a document into an already existing card

Archiflow allows to upload a document starting from an already existing card.

The simplest way to upload a document in Archiflow, starting from Platform, is through a form panel \(or grid\) linked to a business component linked to a "data model from Archiflow": once the panel has been correctly setup, there is a special input control the end user can use to open a file dialog, through which it is possible to upload/download/preview the document linked to such form \(card\).

Moreover, it is possible to programatically upload a document in Archiflow, starting from a server-side javascript action, by means of the following utility method. A precondition is the availability of the document to upload in the Platform server file system.

**Syntax**:

```javascript
var ok = utils.uploadArchiflowDocument(Long dirId, String fileNameSrc, String cardId, String fileName, String documentTitle, Map additionalSettings)
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dirId | a directory id defined in Platform, where the document to upload in Archiflow has been previously saved |
| fileNameSrc | file name for the document to upload \(saved in the Platform server file system\) |
| cardId | the id which identifies a Card in Archiflow: it is used to upload the document for that card |
| fileName | the final name assigned to the document to uploading Archiflow |
| documentTitle | a description for the file name to upload \(managed by Archiflow\) |
| additionalSettings | a javascript object; can be set to null |

This method can be helpful when the document to upload does not come from the user interface, that is to say, it is not provided by the end user.

It can be helpful when Platform has just generated a report \(a PDF document for example\) and this must be uploaded to Archiflow: in such a case, the document already exists in the Platform server file system.

## Download a document starting from a card

Archiflow allows to download a document previously uploaded and linked to a card.

The simplest way to download a document in Archiflow, starting from Platform, is through a form panel \(or grid\) linked to a business component linked to a "data model from Archiflow": once the panel has been correctly setup, there is a special input control the end user can use to open a file dialog, through which it is possible to upload/download/preview the document linked to such form \(card\).

Moreover, it is possible to programatically download a card, starting from a server-side javascript action, by means of the following utility method.

**Syntax**:

```javascript
var vo = utils.downloadArchiflowDocument(Long dirId, String fileName, String cardId, Map additionalSettings)
```

Arguments meaning:

| Argument | Description |
| :--- | :--- |
| dirId | a directory id defined in Platform, where the document to download will be saved |
| fileName | file name for the document to download and save in the Platform server file system, coming from Archiflow |
| cardId | the id which identifies a Card in Archiflow: it is used to download the document for that card |
| additionalSettings | a javascript object; can be set to null |

This method can be helpful when the document to download must NOT be provided directly to the end user through the user interface. Conversely, in case the document must be sent via email or other system to someone else, the document can be download on the Platform server file system and from there joined to others, compressed, sent by email.

