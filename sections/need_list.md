
# Project Need List ⇄ [Details](need_details.md)

```nginx
GET https://api.betterplace.org/en/api_v4/projects/1114/needs.json
```

A list of betterplace.org projects needs (donate money).
Results are contains in a *data* attribute.
The details and list view show the same data per project need.

*For [betterplace.org clients](../README.md#client-api):*
There is no client-scoped-url.
Please use the api calls that are provided inside the client project _url_ response
to make sure you only request data that is associated with one of your projects.


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
    <th>id</th>
    <td>number</td>
    <td>29</td>
    <td>A integer number ≥ 1</td>
  </tr>
  <tr>
    <th>created_at</th>
    <td>string</td>
    <td>"1994-11-05T13:15:30Z"</td>
    <td>DateTime (ISO8601 with Timezone)</td>
  </tr>
  <tr>
    <th>updated_at</th>
    <td>string</td>
    <td>"1994-11-05T13:15:30Z"</td>
    <td>DateTime (ISO8601 with Timezone)</td>
  </tr>
  <tr>
    <th>title</th>
    <td>string</td>
    <td></td>
    <td>Max 50 character</td>
  </tr>
  <tr>
    <th>description</th>
    <td>string</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <th>completed</th>
    <td>boolean</td>
    <td>false</td>
    <td>True if the need is 100 % financed</td>
  </tr>
  <tr>
    <th>progress_percentage</th>
    <td>number</td>
    <td>82</td>
    <td>% financed</td>
  </tr>
  <tr>
    <th>donated_amount_in_cents</th>
    <td>number</td>
    <td>12382</td>
    <td>How many cents are donated already</td>
  </tr>
  <tr>
    <th>open_amount_in_cents</th>
    <td>number</td>
    <td>12382</td>
    <td>How many cents are still needed to complete the need</td>
  </tr>
  <tr>
    <th>requested_amount_in_cents</th>
    <td>number</td>
    <td>12382</td>
    <td>How much money is needed in total</td>
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
(<a href="element_details.md">element details</a>)
</td>
  </tr>
  <tr>
    <th>project</th>
    <td>Link to the related <a href="../project_details.md">project's details</a>
</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 73,
  "offset": 0,
  "total_pages": 25,
  "current_page": 1,
  "per_page": 3,
  "data": [
    {
      "id": 58515,
      "created_at": "2013-01-14T08:49:05Z",
      "updated_at": "2013-04-04T18:21:38Z",
      "title": "Ping Pong Table ",
      "description": "A moveable Ping Pong (Table Tennis) table for our multi-sport facility in Skateistan's new Skatepark in Mazar-e-Sharif in Northern Afghanistan.",
      "completed": false,
      "progress_percentage": 67,
      "donated_amount_in_cents": 19300,
      "open_amount_in_cents": 9100,
      "requested_amount_in_cents": 28400,
      "links": [
        {
          "rel": "self",
          "href": "https://api.betterplace.org/en/api_v4/projects/1114/needs/58515.json"
        },
        {
          "rel": "project",
          "href": "https://api.betterplace.org/en/api_v4/projects/1114.json"
        }
      ]
    },
    {
      "id": 58518,
      "created_at": "2013-01-14T08:54:25Z",
      "updated_at": "2013-01-15T10:05:47Z",
      "title": "Full Badminton Set",
      "description": "This kit has everything needed for Badminton including 3 nets, 16 rackets and 20 shuttlecocks. The kit is for Skateistan's multi-sport facility at the new Skatepark in Mazar-e-Sharif, in Northern Afghanistan. ",
      "completed": false,
      "progress_percentage": 91,
      "donated_amount_in_cents": 34014,
      "open_amount_in_cents": 3286,
      "requested_amount_in_cents": 37300,
      "links": [
        {
          "rel": "self",
          "href": "https://api.betterplace.org/en/api_v4/projects/1114/needs/58518.json"
        },
        {
          "rel": "project",
          "href": "https://api.betterplace.org/en/api_v4/projects/1114.json"
        }
      ]
    },
    {
      "id": 58985,
      "created_at": "2013-01-22T18:35:15Z",
      "updated_at": "2013-01-22T18:35:16Z",
      "title": "Heater for the Kitchen",
      "description": "Heater for kitchen facility in Kabul where we cook meals for our \"Back-to-School\" program 5 days/week.",
      "completed": false,
      "progress_percentage": 0,
      "donated_amount_in_cents": 0,
      "open_amount_in_cents": 6100,
      "requested_amount_in_cents": 6100,
      "links": [
        {
          "rel": "self",
          "href": "https://api.betterplace.org/en/api_v4/projects/1114/needs/58985.json"
        },
        {
          "rel": "project",
          "href": "https://api.betterplace.org/en/api_v4/projects/1114.json"
        }
      ]
    }
  ]
}
```

