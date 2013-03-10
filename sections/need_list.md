
# Project Need List | [Details](need_details.md)

```nginx
GET http://betterplace.dev/en/api_v4/projects/1114/needs.json
```

A list of betterplace.org projects needs (donate money).
Results are contains in a *data* attribute.

*For [betterplace.org clients](README.md#client-api):*
Use this ressource like `/clients/PERMALINK/projects/ID/needs.json`


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
    <td><code>1114</code></td>
    <td>required</td>
    <td>Project-id as an integer number ≥ 14.</td>
  </tr>
</table>

## Response Parameter

*TODO*

## Response Example

```json
null
```

