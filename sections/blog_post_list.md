
# Project Blog Post List ⇄ [Details](blog_post_details.md)

```nginx
GET https://api.betterplace.org/en/api_v4/projects/38/blog_posts.json
```

A list of betterplace.org projects blog posts.
Results are contains in a *data* attribute.

*For [betterplace.org clients](README.md#client-api):*
Use this ressource like `/clients/PERMALINK/projects/ID/blog_posts.json`

In addition, clients can use a list of all blogpost of all client-projects:
`/clients/PERMALINK/blog_posts.json`


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

