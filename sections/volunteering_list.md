Volunteering_list
===================================

Volunteering List
-------------------

```nginx
GET http://betterplace.dev/en/api_v4/volunteering.json?nelat=51.123&nelng=12.123&order=order%3Drank%3AASC%7Ccreated_at%3ADESC&q=Homework+help&scope=location&swlat=51.001&swlng=12.001
```

A list of betterplace.org volunteering offers (donate time).
Results are contains in a *data* attribute.


### Input Parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Example</th>
    <th>Required/Optional</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>scope</th>
    <td><code>location</code></td>
    <td>optional</td>
    <td>Specify how the search-query <code>q</code> should behave:
<ul>
<li>"no scope" (default) performs a full text search
<li><code>human_name</code> searches only on the contact-person-fullname and carrier-fullname. Use this to get all volunteering offers by "Unicef" or by "Till Behnke".
<li><code>location</code> does a reverse geocoding lookup and shows results based on the lookup-bounding-box or a default-radius of 30 km.
</ul>
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>q</th>
    <td><code>Homework help</code></td>
    <td>optional</td>
    <td>Search query. The searches behaviour is based on the scope.</td>
  </tr>
  <tr>
    <th>order</th>
    <td><code>order=rank:ASC|created_at:DESC</code></td>
    <td>optional</td>
    <td>Order the result by <code>rank</code> (default), <code>id</code>, <code>progress_percentage</code>, <code>completed</code>, <code>tax_deductible</code>, <code>created_at</code>, <code>updated_at</code>, <code>last_donation_at</code>.
Use the optional <code>ASC</code> (defualt) or <code>DESC</code>.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>nelat</th>
    <td><code>51.123</code></td>
    <td>optional</td>
    <td>For geographic bound filterning: The northeast corner's latitude.</td>
  </tr>
  <tr>
    <th>nelng</th>
    <td><code>12.123</code></td>
    <td>optional</td>
    <td>For geographic bound filterning: The northeast corner's longitude.</td>
  </tr>
  <tr>
    <th>swlat</th>
    <td><code>51.001</code></td>
    <td>optional</td>
    <td>For geographic bound filterning: The southwest corner's latitude.</td>
  </tr>
  <tr>
    <th>swlng</th>
    <td><code>12.001</code></td>
    <td>optional</td>
    <td>For geographic bound filterning: The southwest corner's longitude.</td>
  </tr>
</table>

### Example response

```json
{
  "total_entries": 0,
  "offset": 3,
  "total_pages": 0,
  "current_page": 2,
  "per_page": 3,
  "data": [

  ],
  "format": "json"
}
```

