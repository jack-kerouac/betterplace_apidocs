
# Organisation Details ⇄ [List](organisation_list.md)

```nginx
GET https://api.betterplace.org/en/api_v4/organisations/125.json
```

The details of a betterplace.org organisation.
The details and list view show the same data per organisation.

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
    <th>id</th>
    <td><code>125</code></td>
    <td>required</td>
    <td>Organisation-id as an integer number ≥ 14.</td>
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
    <th>slug</th>
    <td>string</td>
    <td>vivaconagua</td>
    <td><a href="http://en.wikipedia.org/wiki/Clean_URL#Slug">URL slug</a>
for the permalink
</td>
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
    <th>street</th>
    <td>null &#124; string</td>
    <td>"Schlesische Straße 26"</td>
    <td>Address of the organisation</td>
  </tr>
  <tr>
    <th>zip</th>
    <td>null &#124; string</td>
    <td>"10997"</td>
    <td>Address of the organisation</td>
  </tr>
  <tr>
    <th>city</th>
    <td>null &#124; string</td>
    <td>"Berlin"</td>
    <td>Address of the organisation</td>
  </tr>
  <tr>
    <th>country</th>
    <td>null &#124; string</td>
    <td>"Deutschland"</td>
    <td>Address of the organisation, translated to the requested language</td>
  </tr>
  <tr>
    <th>name</th>
    <td>string</td>
    <td>"Viva con Agua de Sankt Pauli e.V."</td>
    <td>Name of the organisation</td>
  </tr>
  <tr>
    <th>description</th>
    <td>string</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <th>tax_deductible</th>
    <td>boolean</td>
    <td>true</td>
    <td>True if the organisation is a tax-exempt charity.
If so, Users can request a tax-receipt for donations to that organisation.
[More about this](http://www.betterplace.org/c/hilfe/projekt-steuerlich-absetzbar/).
</td>
  </tr>
  <tr>
    <th>contact.name</th>
    <td>null &#124; string</td>
    <td>"Till B."</td>
    <td>Display name of a betterplace.org user.
Possible formats: "Till B.", "T. Behnke", "Till Behnke".
In the case of donation-opinions the name might also be anonymized
like "Payback User" or empty/null for anonymous donations.
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
    <th>self</th>
    <td>Link to this resource itself
(<a href="organisation_details.md">organisation details</a>)
</td>
  </tr>
  <tr>
    <th>platform</th>
    <td>Permalink to betterplace.org</td>
  </tr>
  <tr>
    <th>projects</th>
    <td>Link to the <a href="project_list.md">project list</a> of this organisation
</td>
  </tr>
  <tr>
    <th>contact.platform</th>
    <td>The user's profile on betterplace.org.
To view a user profile you have to be logged in.
This array is empty if the user has no useraccount
with betterplace.org but donated via one of our partner.
</td>
  </tr>
  <tr>
    <th>picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>picture.large</th>
    <td>Large size</td>
  </tr>
  <tr>
    <th>picture.profile</th>
    <td>Medium size</td>
  </tr>
  <tr>
    <th>picture.thumb</th>
    <td>Thumbnail size</td>
  </tr>
  <tr>
    <th>picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>picture.large</th>
    <td>Large size</td>
  </tr>
  <tr>
    <th>picture.profile</th>
    <td>Medium size</td>
  </tr>
  <tr>
    <th>picture.thumb</th>
    <td>Thumbnail size</td>
  </tr>
</table>

## Response Example

```json
{
  "format": "json",
  "id": 125,
  "slug": "vivaconagua",
  "created_at": "2008-02-06T16:10:42Z",
  "updated_at": "2013-01-30T22:44:23Z",
  "latitude": 53.55759811401367,
  "longitude": 9.96815967559815,
  "street": "Neuer Kamp 32",
  "zip": "20357",
  "city": "Hamburg",
  "country": "Germany",
  "name": "Viva con Agua de Sankt Pauli e.V.",
  "description": "Viva con Agua de Sankt Pauli e.V. is a leading German charity dedicated to fighting global poverty by helping the world’s poorest people gain access to clean water, basic sanitation and hygiene education, and encourages people from around the world to lend support.",
  "tax_deductible": true,
  "contact": {
    "format": "json",
    "name": "C. Wiebe",
    "picture": {
      "format": "json",
      "links": [
        {
          "rel": "original",
          "href": "http://www.betterplace.org/paperclip/000/007/084/original_Fidel.jpg"
        },
        {
          "rel": "large",
          "href": "http://www.betterplace.org/paperclip/000/007/084/big_Fidel.png"
        },
        {
          "rel": "profile",
          "href": "http://www.betterplace.org/paperclip/000/007/084/profile_Fidel.jpg"
        },
        {
          "rel": "thumb",
          "href": "http://www.betterplace.org/paperclip/000/007/084/thumb_Fidel.png"
        }
      ]
    },
    "links": [
      {
        "rel": "platform",
        "href": "http://www.betterplace.dev/en/users/christian_w"
      }
    ]
  },
  "picture": {
    "format": "json",
    "links": [
      {
        "rel": "original",
        "href": "http://www.betterplace.org/paperclip/000/007/098/original_Viva_con_Agua_Logo.jpg"
      },
      {
        "rel": "large",
        "href": "http://www.betterplace.org/paperclip/000/007/098/big_Viva_con_Agua_Logo.png"
      },
      {
        "rel": "profile",
        "href": "http://www.betterplace.org/paperclip/000/007/098/profile_Viva_con_Agua_Logo.png"
      },
      {
        "rel": "thumb",
        "href": "http://www.betterplace.org/paperclip/000/007/098/thumb_Viva_con_Agua_Logo.png"
      }
    ]
  },
  "links": [
    {
      "rel": "self",
      "href": "http://www.betterplace.dev/en/api_v4/organisations/125.json"
    },
    {
      "rel": "platform",
      "href": "http://www.betterplace.dev/en/organisations/vivaconagua"
    },
    {
      "rel": "projects",
      "href": "http://www.betterplace.dev/en/api_v4/organisations/125/projects.json"
    }
  ]
}
```

