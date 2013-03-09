
# Client donation list

```nginx
GET http://betterplace.dev/en/api_v4/clients/volksfreund/client_donations.json
```

The API calls for donations to a project via the client donation form.
Please note, that a project might receive donation via multiple sources
but this client donations api only returns donations that where done via
the client donation form.

**This feature is avaliable only to betterplace.org-clients.**
[Learn more…](README.md#client-feature)

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
    <td>The betterplace.org-internal client_id</td>
  </tr>
</table>

## Response Parameter

*TODO*

## Response Example

```json
null
```

