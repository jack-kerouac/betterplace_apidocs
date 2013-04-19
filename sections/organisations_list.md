
# Organisations List ⇄ [Details](organisation_details.md)

```nginx
GET https://www.betterplace.org/en/api_v4/organisations.json
```

A list of betterplace.org organisations.
Results are contained in a *data* attribute.
The details and list view show the same data per organisation.

*For [betterplace.org clients](../README.md#client-api):*
This resource is not avaliable at the moment.


## Input Parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Example</th>
    <th>Required/Optional</th>
    <th>Description</th>
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
    <td>Link to the <a href="projects_list.md">project list</a> of this organisation
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
    <th>picture.large_attention_deprecated</th>
    <td>Large size – ATTENTION, this feature is DEPRICATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>picture.large_attention_deprecated</th>
    <td>Large size – ATTENTION, this feature is DEPRICATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 7147,
  "offset": 0,
  "total_pages": 3574,
  "current_page": 1,
  "per_page": 2,
  "data": [
    {
      "id": 14,
      "slug": "mellemfolkeligtsamvirke",
      "created_at": "2007-07-03T11:54:42Z",
      "updated_at": "2010-12-06T17:15:22Z",
      "latitude": 55.68310165405273,
      "longitude": 12.5846996307373,
      "street": "Borgergade 14",
      "zip": "1300",
      "city": "Copenhagen",
      "country": "Denmark",
      "name": "Mellemfolkeligt Samvirke",
      "description": "Danish humanitarian organization promoting global democracy and fair trade since 1944.",
      "tax_deductible": false,
      "contact": {
        "name": "Jeppe Bo P.",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/001/032/original_tegning-2.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/001/032/big_tegning-2.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/001/032/profile_tegning-2.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/001/032/thumb_tegning-2.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "https://www.betterplace.org/en/users/jeppe_p"
          }
        ]
      },
      "picture": {
        "links": [
          {
            "rel": "original",
            "href": "http://www.betterplace.org/paperclip/000/000/339/original_logo_black.gif"
          },
          {
            "rel": "large_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/000/339/big_logo_black.png"
          },
          {
            "rel": "profile_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/000/339/profile_logo_black.png"
          },
          {
            "rel": "thumb_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/000/339/thumb_logo_black.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/organisations/14.json"
        },
        {
          "rel": "platform",
          "href": "https://www.betterplace.org/en/organisations/mellemfolkeligtsamvirke"
        },
        {
          "rel": "projects",
          "href": "https://www.betterplace.org/en/api_v4/organisations/14/projects.json"
        }
      ]
    },
    {
      "id": 15,
      "slug": "gexsi",
      "created_at": "2007-07-03T15:06:31Z",
      "updated_at": "2010-12-06T17:15:22Z",
      "latitude": 51.53049850463867,
      "longitude": -0.12232699990273,
      "street": "1A Birkenhead ",
      "zip": "WC1H 8BA",
      "city": "London",
      "country": "UK",
      "name": "The Global Exchange for Social Investment - GEXSI",
      "description": "GEXSI is a charitable organisation registered in the UK, with offices in London and Berlin. From Philanthropic Support to Commercial Investment Social entrepreneurs who want to become self-sustaining, GEXSI can assist in finding start-up assistance from donors or investors. GEXSI mobilises a blend of philanthropic funds and commercial financing, tailored to the specific needs of social enterprises.\r\n\r\nGEXSI links charitable donors, social entrepreneurs, and social investors in funding exceptional economic, ecological, and social projects for sustainable development in low-income regions around the world. In order to unleash Entrepreneurship in Low-income Countries, GEXSI mobilises the capital and expertise needed by social entrepreneurs to move from 'aid to market'. \r\n\r\nInitially, social enterprises often depend on grants. To move towards self-reliance, many need start-up support – access to expertise, markets and finance. Many evolving social enterprises experience a financing gap: their financial needs exceed microcredit capacities, but do not reach the levels of commercial financing. The Global Exchange for Social Investment (GEXSI) assists in closing this gap. For Social Entrepreneurs, GEXSI provides expertise and financing tailored to the needs of each social entrepreneur. The Global Exchange for Social Investment (GEXSI) focuses on businesses that have social, environmental and economic impact, and clear potential for scaling up or replication.\r\n\r\nGEXSI collaborates with enterprises requiring initial financial support in their business development. Enterprises assisted by GEXSI typically look for investments ranging from EUR 10,000 to EUR 500,000.\r\n\r\nFor social entrepreneurs, GEXSI: Provides technical expertise in business planning and investment structuring; Locates financing, and; Facilitates networking, mentorship and exchanges of information and expertise.\r\n\r\n",
      "tax_deductible": false,
      "contact": {
        "name": "A. Renner",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/000/392/original_Andreas_Renner_GEXSI.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/000/392/big_Andreas_Renner_GEXSI.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/000/392/profile_Andreas_Renner_GEXSI.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/000/392/thumb_Andreas_Renner_GEXSI.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "https://www.betterplace.org/en/users/andreas_r"
          }
        ]
      },
      "picture": {
        "links": [
          {
            "rel": "original",
            "href": "http://www.betterplace.org/paperclip/000/000/373/original_GEXSI.gif"
          },
          {
            "rel": "large_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/000/373/big_GEXSI.png"
          },
          {
            "rel": "profile_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/000/373/profile_GEXSI.png"
          },
          {
            "rel": "thumb_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/000/373/thumb_GEXSI.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/organisations/15.json"
        },
        {
          "rel": "platform",
          "href": "https://www.betterplace.org/en/organisations/gexsi"
        },
        {
          "rel": "projects",
          "href": "https://www.betterplace.org/en/api_v4/organisations/15/projects.json"
        }
      ]
    }
  ]
}
```
