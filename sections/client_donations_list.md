
# Client donation list

```nginx
GET https://www.betterplace.org/en/api_v4/clients/Volksfreund/client_donations.json
```

**For [betterplace.org clients](../README.md#client-api) only:**

This API returns all donations to all client projects that where made using
the client donation form (but none of the other donation-sources).

Results are contained in a *data* attribute.


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
    <td><code>Volksfreund</code></td>
    <td>required</td>
    <td>The betterplace.org-internal client permalink</td>
  </tr>
</table>

## Response Attributes

<table>
  <tr>
    <th>Attribute</th>
    <th>Types</th>
    <th>Example</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>amount_in_cents</th>
    <td>number</td>
    <td>10100</td>
    <td>Donated amount in cents</td>
  </tr>
  <tr>
    <th>created_at</th>
    <td>string</td>
    <td>"1994-11-05T13:15:30Z"</td>
    <td>DateTime (ISO8601 with Timezone)</td>
  </tr>
  <tr>
    <th>receiver_type</th>
    <td>string</td>
    <td>"Project"</td>
    <td>Client donations may go to <code>Project</code>,
Project <code>Element</code>, <code>FundraisingEvent</code>.
</td>
  </tr>
  <tr>
    <th>receiver_id</th>
    <td>number</td>
    <td>1114</td>
    <td>The id of the project, project element or fundraising event.</td>
  </tr>
  <tr>
    <th>receiver_title</th>
    <td>string</td>
    <td>"Skateistan Afghanistan"</td>
    <td>The title of the project, project element or fundraising event.</td>
  </tr>
</table>

## Response Links
#
<table>
  <tr>
    <th>Linkname</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>receiver</th>
    <td>Link to the <a href="../project_details.md">project details</a>
or <a href="../need_details.md">project need details</a>
that is associated with this donation.
</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 0,
  "offset": 0,
  "total_pages": 1,
  "current_page": 1,
  "per_page": 3,
  "data": [

  ]
}
```

