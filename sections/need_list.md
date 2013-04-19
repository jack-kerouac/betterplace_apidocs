
# Project Need List ⇄ [Details](need_details.md)

```nginx
GET https://www.betterplace.org/en/api_v4/projects/1114/needs.json
```

A list of betterplace.org projects needs (donate money).
Results are contained in a *data* attribute.
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
  "total_entries": 74,
  "offset": 0,
  "total_pages": 25,
  "current_page": 1,
  "per_page": 3,
  "data": [
    {
      "id": 59517,
      "created_at": "2013-02-05T15:27:06Z",
      "updated_at": "2013-04-17T16:21:40Z",
      "title": "Vehicle Fuel ",
      "description": "Fuel to transport students and staff to and from Skatepark in Kabul for 2013.",
      "completed": false,
      "progress_percentage": 50,
      "donated_amount_in_cents": 89970,
      "open_amount_in_cents": 87530,
      "requested_amount_in_cents": 177500,
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/projects/1114/needs/59517.json"
        },
        {
          "rel": "project",
          "href": "https://www.betterplace.org/en/api_v4/projects/1114.json"
        }
      ]
    },
    {
      "id": 5228,
      "created_at": "2009-03-10T10:38:39Z",
      "updated_at": "2009-07-29T06:31:00Z",
      "title": "Warme Mahlzeiten",
      "description": "Wer sich viel bewegt, der muss auch richtig essen: Mit nur 50 Euro im Monat lassen sich 8-10 warme Mahlzeiten für rund 30 Waisenkinder bereitstellen, die zweimal in der Woche von dem Skateistan-Team besucht werden und lernen Skateboard zu fahren.",
      "completed": true,
      "progress_percentage": 100,
      "donated_amount_in_cents": 5000,
      "open_amount_in_cents": 0,
      "requested_amount_in_cents": 5000,
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/projects/1114/needs/5228.json"
        },
        {
          "rel": "project",
          "href": "https://www.betterplace.org/en/api_v4/projects/1114.json"
        }
      ]
    },
    {
      "id": 5229,
      "created_at": "2009-03-10T10:54:30Z",
      "updated_at": "2009-07-29T06:31:03Z",
      "title": "Skateboardlehrer",
      "description": "Mirwais, 13, ist Afghanistans erster talentierter Skateboardlehrer. Früher wusch er für 2 Dollar am Tag Autos auf der Straße. Heute ist er Skateistans Angestellter und kann mit seinem Gehalt (167 Euro/Monat) seine Familie ernähren.",
      "completed": true,
      "progress_percentage": 100,
      "donated_amount_in_cents": 16700,
      "open_amount_in_cents": 0,
      "requested_amount_in_cents": 16700,
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/projects/1114/needs/5229.json"
        },
        {
          "rel": "project",
          "href": "https://www.betterplace.org/en/api_v4/projects/1114.json"
        }
      ]
    }
  ]
}
```

