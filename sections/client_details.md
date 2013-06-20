
# Client Details

```nginx
GET https://api.betterplace.org/en/api_v4/clients/Volksfreund.json
```

**For [betterplace.org clients](../README.md#client-api) only:**

Some client-statistics for a betterplace.org client. All results are cached for 15 minutes.


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
    <th>donated_amount_in_cents</th>
    <td>number</td>
    <td>10100</td>
    <td>How many cents are donated already to all client projects. 
Calculated based on open_amount_in_cents and requested_amount_in_cents.
Therefore it includes the money of the client-pool-fundraising-event
that still has to be forwarded to one of the client-projects-needs.
</td>
  </tr>
  <tr>
    <th>pool_balance_in_cents</th>
    <td>number</td>
    <td>100</td>
    <td>Clients may have a client-pool-fundraising-event that receives money
from offline-donations that could not be associated with a project or
similar use cases.

The balance repesents the donated amount in cents on the pool
that has not yet been forwarded to one of the client-project-needs.

This is the number that is include in open_amount_in_cents and donated_amount_in_cents.
</td>
  </tr>
  <tr>
    <th>open_amount_in_cents</th>
    <td>number</td>
    <td>9900</td>
    <td>How many cents are still needed to complete all client projects.
This is calculated based on the sum of all
<a href="need_details.md">needs (open_amount_in_cents)</a>.
We also substract the money of the client-pool-fundraising-event
that still has to be forwarded to one of the client-projects-needs.
</td>
  </tr>
  <tr>
    <th>requested_amount_in_cents</th>
    <td>number</td>
    <td>11000</td>
    <td>How many cents are still needed to complete all client projects.
This is also calculated based on the sum of all
<a href="need_details.md">needs (requested_amount_in_cents)</a>.
</td>
  </tr>
  <tr>
    <th>projects_count</th>
    <td>number</td>
    <td>100</td>
    <td>The number of <a href="../projects_list.md">projects</a> of this client
</td>
  </tr>
  <tr>
    <th>client_donations_count</th>
    <td>number</td>
    <td>200</td>
    <td>The number of <a href="../client_donations_list.md">client donations</a> for this client
</td>
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
    <th>projects</th>
    <td>Link to the <a href="../projects_list.md">project list</a> of this client
</td>
  </tr>
  <tr>
    <th>client_donations</th>
    <td>Link to the <a href="../client_donations_list.md">client donations list</a> of this client
</td>
  </tr>
  <tr>
    <th>client_project_tags</th>
    <td>Link to the <a href="../client_project_tags_list.md">client project-tags list</a> of this client
</td>
  </tr>
</table>

## Response Example

```json
{
  "donated_amount_in_cents": 77680131,
  "pool_balance_in_cents": 2847925,
  "open_amount_in_cents": 37385369,
  "requested_amount_in_cents": 115065500,
  "projects_count": 217,
  "client_donations_count": 6235,
  "links": [
    {
      "rel": "projects",
      "href": "https://api.betterplace.dev/en/api_v4/clients/volksfreund/projects.json"
    },
    {
      "rel": "client_donations",
      "href": "https://api.betterplace.dev/en/api_v4/clients/volksfreund/client_donations.json"
    },
    {
      "rel": "client_project_tags",
      "href": "https://api.betterplace.dev/en/api_v4/clients/volksfreund/project_tags.json"
    }
  ]
}
```

