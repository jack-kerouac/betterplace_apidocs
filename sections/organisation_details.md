
# Organisation Details ⇄ [List](organisation_list.md)

```nginx
GET https://api.betterplace.org/en/api_v4/organisations/125.json
```

The details of a betterplace.org organisation.
The details and list view show the same data per organisation.

*For [betterplace.org clients](../README.md#client-api):*
There is no client-scoped-url.
Please use the api calls that are provided inside the client project _url_ response
to make sure you only request data that is associated with one of your projects.


## Input Parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Example</th>
    <th>Required/Optional</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>id</th>
    <td><code>125</code></td>
    <td>required</td>
    <td>Organisation-id as an integer number ≥ 14.</td>
  </tr>
</table>

## Response Attributes

<table>
  <tr>
    <th>Attribute</th>
    <th>Types</th>
    <th>Example/Optional</th>
    <th>Description</th>
  </tr>
</table>

## Response Links
#
<table>
  <tr>
    <th>Linkname</th>
    <th>Description</th>
  </tr>
</table>

## Response Example

```json
null
```

