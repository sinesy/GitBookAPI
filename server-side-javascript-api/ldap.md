# Ldap

## Add an attribute \(e.g. "member of"\) to the entry identified by "filterDN"

**Syntax**

```javascript
var num = utils.addAttribute(host, port, filterDN, ldapUsername, ldapPassword, attributeNameToAdd, attributeValueToAdd);
```

**Details**

| Argument | Description |
| :--- | :--- |
| host | LDAP host |
| port | LDAP port \(optional: if not specified, 389 will be used\) |

```text
 filterDN - base DN to apply as a filter
```

| Argument | Description |
| :--- | :--- |
| ldapUsername | username to use to authenticate to the LDAP server |
| ldapPassword | password to use to authenticate to the LDAP server |
| attributeNameToAdd | attribute name to add to every entry matching the search criteria |
| attributeValueToAdd | attribute value to add to every entry matching the search criteria |

```text
Returns the number of entries found and updated
```

## Remove an attribute \(e.g. "memberOf"\) from the entry identified by "filterDN"

**Syntax**

```javascript
var num = utils.removeAttribute(host, port, filterDN, ldapUsername, ldapPassword, attributeNameToRemove, attributeValueToRemove);
```

**Details**

| Argument | Description |
| :--- | :--- |
| host | LDAP host |
| port | LDAP port \(optional: if not specified, 389 will be used\) |

```text
 filterDN - base DN to apply as a filter
```

| Argument | Description |
| :--- | :--- |
| ldapUsername | username to use to authenticate to the LDAP server |
| ldapPassword | password to use to authenticate to the LDAP server |
| attributeNameToRemove | attribute name to remove from every entry matching the search criteria |
| attributeValueToRemove | attribute value to remove from every entry matching the search criteria |

```text
Returns number of entries found and updated
```

## Get a list of records read from the LDAP server

where each record is expressed as a Javascript Object

**Syntax**

```javascript
var listOfObjects = utils.getEntriesList(host, port, baseDN, ldapUsername, ldapPassword, searchAttributes,attributesListToRead);
```

**Details**

| Argument | Description |
| :--- | :--- |
| host | LDAP host |
| port | LDAP port \(optional: if not specified, 389 will be used\) |

```text
 baseDN - base DN to apply as a filter
```

| Argument | Decription |
| :--- | :--- |
| ldapUsername | username to use to authenticate to the LDAP server |
| ldapPassword | password to use to authenticate to the LDAP server |
| searchAttributes | attributes to apply as a filter |
| attributesListToRead | list of attribute names to take into account when reading records from the LDAP server: these will be the only ones to use when creating the JSON result |

```text
Returns a list of records read from the LDAP server, where each record is expressed as a Javascript object.
```

## Get a list of Strings, related to multiple attribute values

starting from a specified attribute name of a specific entry read from the LDAP server

**Syntax**

```javascript
var listOfStrings = utils.getMultipleValuesList(host, port, baseDN, ldapUsername, ldapPassword, searchAttributes, attributeName);
```

**Details**

| Argument | Description |
| :--- | :--- |
| host | LDAP host |
| port | LDAP port \(optional: if not specified, 389 will be used\) |

```text
 baseDN - base DN to apply as a filter
```

| Argument | Description |
| :--- | :--- |
| ldapUsername | username to use to authenticate to the LDAP server |
| ldapPassword | password to use to authenticate to the LDAP server |
| searchAttributes | attributes to apply as a filter, in order to identity a single entry into the LDAP server |
| attributeName | attribute name to read: each matching found will generate a row in the results list |

