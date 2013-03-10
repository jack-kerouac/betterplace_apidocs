
# Client donation list

```nginx
GET http://betterplace.dev/en/api_v4/clients/volksfreund/client_donations.json
```

**For [betterplace.org clients](README.md#client-api) only:**

The API returns donations to a project that where made using
the client donation form, but none of the other donation-sources.

Retrieve the list of all projects as a JSON result set, that
contains the results in its *data* attribute.


## Input Parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Example</th>
    <th>Required/Optional</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>client_id</th>
    <td><code>volksfreund</code></td>
    <td>required</td>
    <td>The betterplace.org-internal client permalink</td>
  </tr>
</table>

## Response Parameter

*TODO*

## Response Example

```json
null
```

