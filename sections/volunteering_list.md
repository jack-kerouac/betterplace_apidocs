Volunteering_list
===================================

Volunteering List
-------------------

```nginx
GET http://betterplace.dev/en/api_v4/volunteering.json?nelat=51.123&nelng=12.123&order=order%3Drank%3AASC%7Ccreated_at%3ADESC&q=Homework+help&sope=location%2C+human_name%2C+location&swlat=51.001&swlng=12.001
```

Retrieve a list of all volunteering as a JSON result set,
that contains the results in its *data* attribute.


### Input Parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Example</th>
    <th>Required/Optional</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>sope</th>
    <td><code>location, human_name, location</code></td>
    <td>optional</td>
    <td>Specify how the search-query `q` should behave:
* "no scope" (default) performs a full text search
* `human_name` searches only on the contact-person-fullname and carrier-fullname. Use this to get all volunteering offers by "Unicef" or by "Till Behnke".
* `location` does a reverse geocoding lookup and shows results based on the lookup-bounding-box or a default-radius of 30 km.
[Learn how to format the parameter](README.md#request-parameter-format).
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
    <td>Order the result by `rank` (default), `id`, `progress_percentage`, `completed`, `tax_deductible`, `created_at`, `updated_at`, `last_donation_at`.
Use the optional `ASC` (defualt) or `DESC`.
[Learn how to format the parameter](README.md#request-parameter-format).
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
  "total_entries": 4,
  "offset": 3,
  "total_pages": 2,
  "current_page": 2,
  "per_page": 3,
  "data": [
    {
      "id": 2,
      "title": "Zusatzangebote in Gruppen",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/volunteering/2.json"
        }
      ]
    }
  ],
  "format": "json"
}
```

