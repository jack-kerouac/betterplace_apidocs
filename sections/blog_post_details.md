
# Project Blog Post Details | [List](blog_post_list.md)

```nginx
GET http://betterplace.dev/en/api_v4/projects/38/blog_posts/22.json
```

The details of a betterplace.org project blog post.
The details and list view show the same data.

*For [betterplace.org clients](README.md#client-api):*
Use this ressource like `/clients/PERMALINK/projects/ID/blog_posts/ID.json`


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
  <tr>
    <th>id</th>
    <td><code>22</code></td>
    <td>required</td>
    <td>Blog-post-id as an integer number ≥ 9.</td>
  </tr>
</table>

## Response Parameter

*TODO*

## Response Example

```json
null
```

