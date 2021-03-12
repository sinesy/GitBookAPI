# User management

This section reports a series of utility methods available within a server-side Javascript action.

These methods allows to create users and bind to them a set of roles.

## Check for user existence

This method allows to check for a record in PRM01\_USERS, i.e. whether the specified user has been already created.

**Syntax**:

```javascript
var prm01Object = utils.existUser(companyId, siteId, userCodeId);
```

| Argument | Description |
| :--- | :--- |
| companyId | company id that identifies the user \(text value\) |
| siteId | site id that identifies the user \(numeric value\) |
| userCodeId | username for the user to check out \(text value\) |
| **prm01Object** | the resulting value is a javascript object containing the record in PRM01\_USERS for the specified user. This method returns null if the user does not exist. |

## Create a user

This method creates a record in PRM01_USERS_, one in SUB02\_SUBJECTS and another in SUB01\_PEOPLE, i.e. create a new user account.

**Syntax**:

```javascript
var prm01Object = utils.createUser(companyId, siteId, userCodeId, description, password, languageId, additionalData
, roles);
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">companyId</td>
      <td style="text-align:left">company id that identifies the user (text value)</td>
    </tr>
    <tr>
      <td style="text-align:left">siteId</td>
      <td style="text-align:left">site id that identifies the user (numeric value)</td>
    </tr>
    <tr>
      <td style="text-align:left">userCodeId</td>
      <td style="text-align:left">username for the user to check out (text value)</td>
    </tr>
    <tr>
      <td style="text-align:left">description</td>
      <td style="text-align:left">user description (mandatory argument)<b> </b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">password</td>
      <td style="text-align:left">password (mandatory argument)</td>
    </tr>
    <tr>
      <td style="text-align:left">languageId</td>
      <td style="text-align:left">language id to link to the user</td>
    </tr>
    <tr>
      <td style="text-align:left">additionalData</td>
      <td style="text-align:left">
        <p>can be null: if specified, it is a javascript object containing additional
          data to fill in PRM01_USERS;</p>
        <p>e.g.</p>
        <p><b>{ dateExpirationPassword: new Date() }</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p>Note: if you need to set personal data about the user (stored in SUB02_SUBJECTS
          table<b>)</b>, you can use later the <b>updatePeopleData</b> method.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">roles</td>
      <td style="text-align:left">a list of javascript objects; each object is related to a role to bind
        to the user; the javascript object for a role must have the following attributes:
        companyId, siteId, roleId, startDate, endDate (this one is optional)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>prm01Object</b>
      </td>
      <td style="text-align:left">the resulting value is a javascript object containing the record in PRM01_USERS
        for the specified user.</td>
    </tr>
  </tbody>
</table>

## Update an already existing user

This method updates an already existing record in PRM01\_USERS, i.e. update a user account.

**Syntax**:

```javascript
var prm01Object = utils.updateUser(companyId, siteId, userCodeId, languageId, additionalData);
```

| Argument | Description |
| :--- | :--- |
| companyId | company id that identifies the user \(text value\) |
| siteId | site id that identifies the user \(numeric value\) |
| userCodeId | username for the user to check out \(text value\) |
| password | password \(mandatory argument\) |
| languageId | language id to link to the user |
| additionalData | can be null: if specified, it is a javascript object containing additional data to fill in PRM01\_USERS; e.g. { dateExpirationPassword: new Date\(\) } |
| **prm01Object** | the resulting value is a javascript object containing the record in PRM01\_USERS for the specified user. |

## Update personal data for the specified user

This method update a record in SUB01\_PEOPLE, i.e. update personal data for the specified user, like first name, last name, gender, etc.

**Syntax**:

```javascript
var sub01Object = utils.updatePeopleData(companyId, siteId, userCodeId, personalData);
```

| Argument | Description |
| :--- | :--- |
| companyId | company id that identifies the user \(text value\) |
| siteId | site id that identifies the user \(numeric value\) |
| userCodeId | username for the user to check out \(text value\) |
| personaData | it is a javascript object containing personal data to fill in SUB01\_PEOPLE; e.g. { firstName: "Giulio", lastName: "Cesare", sex: "M" } |
| **sub01Object** | the resulting value is a javascript object containing the record in SUB01\_PEOPLE for the specified user. |

## Get user roles

This method get the roles list linked to the specified user.

**Syntax**:

```javascript
var list = utils.getUserRoles(companyId, siteId, userCodeId);
```

| Argument | Description |
| :--- | :--- |
| companyId | company id that identifies the user \(text value\) |
| siteId | site id that identifies the user \(numeric value\) |
| userCodeId | username for the user to check out \(text value\) |
| **list** | the resulting value is an ArrayList whose elements can be accessed through list.get\(i\) and whose size is list.size\(\). Each element is a javascript object containing the following attributes: checked , editable, startDate, endDate and role |

Note: the a single javascript object returned in the list has the following structure:

```text
{
  checked: "Y", // Y or N
  editable: "Y", // Y or N
  startDate: ... // a Date object
  endDate: ... // a Date object
  role: { ... } // representation of a record of PRM02_ROLES
}
```

## Add a role to the specified user

This method allows to add a role to the specified user.

**Syntax**:

```javascript
var objectPrm01 = utils.addUserRole(companyId, siteId, userCodeId, roles);
```

| Argument | Description |
| :--- | :--- |
| companyId | company id that identifies the user \(text value\) |
| siteId | site id that identifies the user \(numeric value\) |
| userCodeId | username for the user to check out \(text value\) |
| roles | list of javascript objects, where each object has the following attributes: companyId, siteId, roleId, startDate, endDate \(the last one is optional\) |
| **objectPrm01** | the resulting value is the current record in PRM01\_USERS for the specified user |

## Update a role to the specified user

This method allows to update a role to the specified user.

**Syntax**:

```javascript
var objectPrm01 = utils.addUserRole(companyId, siteId, userCodeId, roles);
```

| Argument | Description |
| :--- | :--- |
| companyId | company id that identifies the user \(text value\) |
| siteId | site id that identifies the user \(numeric value\) |
| userCodeId | username for the user to check out \(text value\) |
| roles | list of javascript objects, where each object has the following attributes: companyId, siteId, roleId, startDate, endDate \(the last one is optional\) |
| **objectPrm01** | the resulting value is the current record in PRM01\_USERS for the specified user |

