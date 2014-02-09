
# Organisation Details ⇄ [List](organisations_list.md)

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
    <th align="left">id</th>
    <td><code>125</code></td>
    <td>required</td>
    <td>Organisation-id as an integer number ≥ 14.</td>
  </tr>
</table>

## Response Attributes

### Root Attributes

  <table>
    <tr>
      <th>Attribute</th>
      <th>Types</th>
      <th>Example</th>
      <th>Description</th>
    </tr>
    <tr>
      <th align="left">id</th>
      <td>number</td>
      <td>4</td>
      <td>An integer number ≥ 1</td>
    </tr>
    <tr>
      <th align="left">slug</th>
      <td>string</td>
      <td>vivaconagua</td>
      <td><a href="http://en.wikipedia.org/wiki/Clean_URL#Slug">URL slug</a>
for the permalink
</td>
    </tr>
    <tr>
      <th align="left">created_at</th>
      <td>string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone)</td>
    </tr>
    <tr>
      <th align="left">updated_at</th>
      <td>string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone)</td>
    </tr>
    <tr>
      <th align="left">latitude</th>
      <td>number</td>
      <td>52.499007</td>
      <td>Decimal degrees based on user input</td>
    </tr>
    <tr>
      <th align="left">longitude</th>
      <td>number</td>
      <td>13.44947</td>
      <td>Decimal degrees based on user input</td>
    </tr>
    <tr>
      <th align="left">street</th>
      <td>null &#124; string</td>
      <td>"Schlesische Straße 26"</td>
      <td>Address of the organisation</td>
    </tr>
    <tr>
      <th align="left">zip</th>
      <td>null &#124; string</td>
      <td>"10997"</td>
      <td>Address of the organisation</td>
    </tr>
    <tr>
      <th align="left">city</th>
      <td>null &#124; string</td>
      <td>"Berlin"</td>
      <td>Address of the organisation</td>
    </tr>
    <tr>
      <th align="left">country</th>
      <td>null &#124; string</td>
      <td>"Deutschland"</td>
      <td>Address of the organisation, translated to the requested language</td>
    </tr>
    <tr>
      <th align="left">name</th>
      <td>string</td>
      <td>"Viva con Agua de Sankt Pauli e.V."</td>
      <td>Name of the organisation</td>
    </tr>
    <tr>
      <th align="left">description</th>
      <td>string</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th align="left">tax_deductible</th>
      <td>boolean</td>
      <td>true</td>
      <td>True if the organisation is a tax-exempt charity.
If so, Users can request a tax-receipt for donations to that organisation.
[More about this](http://www.betterplace.org/c/hilfe/projekt-steuerlich-absetzbar/).
</td>
    </tr>
    <tr>
        <th align="left" style="white-space: nowrap">
          <a name="contact-ref" href="#contact">
            ↓contact
          </a>
        </th>
      <td>object</td>
      <td></td>
      <td>The public contact person for this organisation.</td>
    </tr>
    <tr>
      <th align="left">picture</th>
      <td>null &#124; object</td>
      <td></td>
      <td>TODO</td>
    </tr>
  </table>
### <a name="contact" href="#contact-ref">↑Nested Attributes: contact</a>

  <table>
    <tr>
      <th>Attribute</th>
      <th>Types</th>
      <th>Example</th>
      <th>Description</th>
    </tr>
    <tr>
      <th align="left">contact.name</th>
      <td>null &#124; string</td>
      <td>"Till B."</td>
      <td>Display name of a betterplace.org user.
Possible formats: "Till B.", "T. Behnke", "Till Behnke".
In the case of donation-opinions the name might also be anonymized
like "Payback User" or empty/null for anonymous donations.
</td>
    </tr>
    <tr>
      <th align="left">contact.picture</th>
      <td>string</td>
      <td>//assets.betterplace.org/…</td>
      <td>User profile picture or a fallback image</td>
    </tr>
  </table>
</table>

## Response Links

<table>
  <tr>
    <th>Linkname</th>
    <th>Description</th>
  </tr>

    <tr>
      <th align="left">self</th>
      <td>Link to this resource itself
(<a href="organisation_details.md">organisation details</a>)
</td>
    </tr>
    <tr>
      <th align="left">platform</th>
      <td>Permalink to betterplace.org</td>
    </tr>
    <tr>
      <th align="left">projects</th>
      <td>Link to the <a href="projects_list.md">project list</a> of this organisation
</td>
    </tr>
    <tr>
      <th align="left">contact.platform</th>
      <td>The user's profile on betterplace.org.
To view a user profile you have to be logged in.
This array is empty if the user has no useraccount
with betterplace.org but donated via one of our partner.
</td>
    </tr>
    <tr>
      <th align="left">contact.contact_data</th>
      <td>The user's contact data. Please note that you need to be
<a href="../README.md#client-authentication">authenticated as a client</a> with matching
access rights in order to see this information.
</td>
    </tr>
    <tr>
      <th align="left">contact.picture.original</th>
      <td>Original size as uploaded by the user</td>
    </tr>
    <tr>
      <th align="left">contact.picture.large_attention_deprecated</th>
      <td>Large size – ATTENTION, this feature is DEPRECATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
    </tr>
    <tr>
      <th align="left">contact.picture.profile_attention_deprecated</th>
      <td>Medium size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">contact.picture.thumb_attention_deprecated</th>
      <td>Thumbnail size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">picture.original</th>
      <td>Original size as uploaded by the user</td>
    </tr>
    <tr>
      <th align="left">picture.large_attention_deprecated</th>
      <td>Large size – ATTENTION, this feature is DEPRECATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
    </tr>
    <tr>
      <th align="left">picture.profile_attention_deprecated</th>
      <td>Medium size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">picture.thumb_attention_deprecated</th>
      <td>Thumbnail size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
</table>

## Response Example

```json
{
  "id": 125,
  "slug": "vivaconagua",
  "created_at": "2008-02-06T16:10:42Z",
  "updated_at": "2013-10-21T21:12:42Z",
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
    "name": "C. Wiebe",
    "picture": {
      "links": [
        {
          "rel": "original",
          "href": "/paperclip/000/007/084/original_Fidel.jpg"
        },
        {
          "rel": "large_attention_deprecated",
          "href": "/paperclip/000/007/084/default_Fidel.jpg"
        },
        {
          "rel": "profile_attention_deprecated",
          "href": "/paperclip/000/007/084/profile_Fidel.jpg"
        },
        {
          "rel": "thumb_attention_deprecated",
          "href": "/paperclip/000/007/084/thumb_Fidel.png"
        }
      ]
    },
    "links": [
      {
        "rel": "platform",
        "href": "http://www.betterplace.org/en/users/christian_w"
      },
      {
        "rel": "contact_data",
        "href": "https://api.betterplace.org/en/api_v4/users/1399/contact_data.json"
      }
    ]
  },
  "picture": {
    "links": [
      {
        "rel": "original",
        "href": "/uploads/organisation/profile_picture/125/original_original_VCA_Logo_Blau.jpg"
      },
      {
        "rel": "large_attention_deprecated",
        "href": "/uploads/organisation/profile_picture/125/default_original_VCA_Logo_Blau.jpg"
      },
      {
        "rel": "profile_attention_deprecated",
        "href": "/uploads/organisation/profile_picture/125/profile_original_VCA_Logo_Blau.jpg"
      },
      {
        "rel": "thumb_attention_deprecated",
        "href": "/uploads/organisation/profile_picture/125/thumb_original_VCA_Logo_Blau.jpg"
      }
    ]
  },
  "links": [
    {
      "rel": "self",
      "href": "https://api.betterplace.org/en/api_v4/organisations/125.json"
    },
    {
      "rel": "platform",
      "href": "http://www.betterplace.org/en/organisations/vivaconagua"
    },
    {
      "rel": "projects",
      "href": "https://api.betterplace.org/en/api_v4/organisations/125/projects.json"
    }
  ]
}
```

