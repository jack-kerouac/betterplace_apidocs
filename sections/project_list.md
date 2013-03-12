
# Project List ⇄ [Details](project_details.md)

```nginx
GET https://betterplace.org/en/api_v4/projects.json?facets=tax_deductible%3Atrue%7Ccompleted%3Afalse&nelat=51.123&nelng=12.123&order=rank%3AASC&q=Skateistan&scope=location&swlat=51.001&swlng=12.001
```

A list of betterplace.org projects (donate money).
Results are contains in a *data* attribute.

*For [betterplace.org clients](README.md#client-api):*
Use this ressource like `/clients/PERMALINK/projects.json`


## Input Parameter

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
<li><code>human_name</code> searches only on the manager-fullname and carrier-fullname. Use this to get all projects by "Unicef" or by "Till Behnke".
<li><code>location</code> does a reverse geocoding lookup and shows results based on the lookup-bounding-box or a default-radius of 30 km.
</ul>
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>q</th>
    <td><code>Skateistan</code></td>
    <td>optional</td>
    <td>Search query. The searches behaviour is based on the scope.</td>
  </tr>
  <tr>
    <th>order</th>
    <td><code>rank:ASC</code></td>
    <td>optional</td>
    <td>Order the result by <code>rank</code> (default), <code>id</code>, <code>progress_percentage</code>,
<code>completed</code>, <code>tax_deductible</code>, <code>created_at</code>, <code>updated_at</code>,
<code>last_donation_at</code>.
Use the optional <code>ASC</code> (default) or <code>DESC</code>.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>facets</th>
    <td><code>tax_deductible:true|completed:false</code></td>
    <td>optional</td>
    <td>Filter the result set by <code>tax_deductible</code> or <code>completed</code>. Possible values are
<code>true</code> or <code>false</code>.
It is possible to set multiple facet filters.
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

## Response Attributes

<table>
  <tr>
    <th>Attribute</th>
    <th>Types</th>
    <th>Example/Optional</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>id</th>
    <td>number</td>
    <td>4</td>
    <td>An integer number ≥ 1</td>
  </tr>
  <tr>
    <th>latitude</th>
    <td>number</td>
    <td>52.499007</td>
    <td>Decimal degrees based on user input</td>
  </tr>
  <tr>
    <th>longitude</th>
    <td>number</td>
    <td>13.44947</td>
    <td>Decimal degrees based on user input</td>
  </tr>
  <tr>
    <th>title</th>
    <td>string</td>
    <td>TODO</td>
    <td>Max 50 character</td>
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
    <th>self</th>
    <td>Link to this resource itself
(<a href="../project_details.md">project details</a>)
</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 2,
  "offset": 0,
  "total_pages": 1,
  "current_page": 1,
  "per_page": 3,
  "data": [
    {
      "format": "json",
      "id": 1114,
      "latitude": 34.531617284782,
      "longitude": 69.13581752939456,
      "title": "Skateistan Afghanistan",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114.json"
        }
      ]
    },
    {
      "format": "json",
      "id": 6233,
      "latitude": 11.55883121490479,
      "longitude": 104.9174423217773,
      "title": "Skateistan Cambodia",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/projects/6233.json"
        }
      ]
    }
  ]
}
```

