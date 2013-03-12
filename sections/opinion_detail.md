
# Project Opinion Details ⇄ [List](opinion_list.md)

```nginx
GET https://api.betterplace.org/en/portals/22/projects.json?action=show&controller=api_v4%2Fopinions&project_id=38
```

The details of a betterplace.org project opinion (donate money).
The details and list view show the same data.

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
    <th>project_id</th>
    <td><code>38</code></td>
    <td>required</td>
    <td>Project-id as an integer number ≥ 14.</td>
  </tr>
  <tr>
    <th>id</th>
    <td><code>22</code></td>
    <td>required</td>
    <td>Blog-post-id as an integer number ≥ 9.</td>
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

