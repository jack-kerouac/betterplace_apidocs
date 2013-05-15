
# Project Need Details ⇄ [List](needs_list.md)

```nginx
GET https://api.betterplace.org/en/api_v4/projects/1114/needs/59220.json
```

The details of a betterplace.org project need (donate money).
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
  <tr>
    <th>id</th>
    <td><code>59220</code></td>
    <td>required</td>
    <td>Need-id as an integer number ≥ 29.</td>
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
    <td>How many cents are donated already.
This includes all donations that can be given to a need
(direct donation, forwarding of project donation,
forwarding of organisation donation,
forwarding of fundraising event donations,
offline donations and also(!) external donations)
</td>
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
(<a href="need_details.md">need details</a>)
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
  "id": 58985,
  "created_at": "2013-01-22T18:35:15Z",
  "updated_at": "2013-02-16T14:31:18Z",
  "title": "Heater for the Kitchen",
  "description": "Heater for kitchen facility in Kabul where we cook meals for our \"Back-to-School\" program 5 days/week.",
  "completed": true,
  "progress_percentage": 100,
  "donated_amount_in_cents": 6100,
  "open_amount_in_cents": 0,
  "requested_amount_in_cents": 6100,
  "links": [
    {
      "rel": "self",
      "href": "https://api.betterplace.dev/en/api_v4/projects/1114/needs/58985.json"
    },
    {
      "rel": "project",
      "href": "https://api.betterplace.dev/en/api_v4/projects/1114.json"
    }
  ]
}
```

