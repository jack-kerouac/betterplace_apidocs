
# Project Picture Details ⇄ [List](project_pictures_list.md)

```nginx
GET https://www.betterplace.org/en/api_v4/projects/1114/pictures/286505.json
```

The details of a betterplace.org project picture.
The details and list view show the same data.

*Custom picture-sizes:* [Please read more!](project_picture_details.md)

*For [betterplace.org clients](../README.md#client-api):*
If you request data for a project that is not part of the client
projects, the API will return a `404` HTTP code.


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
    <td><code>1114</code></td>
    <td>required</td>
    <td>Project-id as an integer number ≥ 14.</td>
  </tr>
  <tr>
    <th>id</th>
    <td><code>286505</code></td>
    <td>required</td>
    <td>Picture-id as an integer number ≥ 1.</td>
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
    <th>width</th>
    <td>number</td>
    <td>1024</td>
    <td>Width of the image</td>
  </tr>
  <tr>
    <th>height</th>
    <td>number</td>
    <td>768</td>
    <td>Height of the image</td>
  </tr>
  <tr>
    <th>size</th>
    <td>number</td>
    <td>100234</td>
    <td>Size of the image in bytes</td>
  </tr>
  <tr>
    <th>description</th>
    <td>string</td>
    <td>Yada…</td>
    <td>Description of the picture</td>
  </tr>
  <tr>
    <th>created_at</th>
    <td>string</td>
    <td>"1994-11-05T13:15:30Z"</td>
    <td>DateTime (ISO8601 with Timezone) of creation</td>
  </tr>
  <tr>
    <th>updated_at</th>
    <td>string</td>
    <td>"1994-11-05T13:15:30Z"</td>
    <td>DateTime (ISO8601 with Timezone) of last update</td>
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
    <th>image</th>
    <td>Link to the original image as uploaded by the user</td>
  </tr>
  <tr>
    <th>self</th>
    <td>The single resource for this picture</td>
  </tr>
  <tr>
    <th>parent</th>
    <td>The parent object of this picture.</td>
  </tr>
</table>

## Response Example

```json
{
  "width": 132,
  "height": 99,
  "description": "Young Afghan Skate Instructor Fazilla sitting on her board at Mekroyan Fountain",
  "created_at": "2012-07-23T11:45:15Z",
  "updated_at": "2012-07-23T11:46:38Z",
  "links": [
    {
      "rel": "image",
      "href": "http://www.betterplace.org/paperclip/000/286/505/original_fazilla.jpg"
    },
    {
      "rel": "self",
      "href": "https://www.betterplace.org/en/api_v4/projects/1114/pictures/286505.json"
    },
    {
      "rel": "parent",
      "href": "https://www.betterplace.org/en/api_v4/projects/1114.json"
    }
  ]
}
```

