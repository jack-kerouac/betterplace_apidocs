
# Client tags list

```nginx
GET https://www.betterplace.org/en/api_v4/clients/Volksfreund/project_tags.json
```

**For [betterplace.org clients](../README.md#client-api) only:**

This API returns all tags defined for a client.

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
    <th>tag</th>
    <td>string</td>
    <td>"Education"</td>
    <td>The name of the tag, that is unique per client.
</td>
  </tr>
  <tr>
    <th>projects_count</th>
    <td>number</td>
    <td>23</td>
    <td>The number of <a href="../project_list.md">projects</a>
that where tagged with this tag.
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
    <td>Link to the <a href="project_list.md">project list</a> of all tagged projects for the current client.
</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 23,
  "offset": 0,
  "total_pages": 12,
  "current_page": 1,
  "per_page": 2,
  "data": [
    {
      "tag": "Gesundheit",
      "projects_count": 57,
      "links": [
        {
          "rel": "projects",
          "href": "https://www.betterplace.org/en/api_v4/clients/volksfreund/project_tags/Gesundheit/projects.json"
        }
      ]
    },
    {
      "tag": "Bildung",
      "projects_count": 48,
      "links": [
        {
          "rel": "projects",
          "href": "https://www.betterplace.org/en/api_v4/clients/volksfreund/project_tags/Bildung/projects.json"
        }
      ]
    }
  ]
}
```

