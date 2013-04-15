
# Project List ⇄ [Details](project_details.md)

```nginx
GET https://api.betterplace.org/en/api_v4/projects.json?facets=completed%3Afalse&nelat=51.123&nelng=12.123&order=rank%3AASC&q=Skateistan&scope=location&swlat=51.001&swlng=12.001
```

A list of betterplace.org projects (donate money).
Results are contains in a *data* attribute.

*For [betterplace.org clients](../README.md#client-api):*
Use this ressource like `/clients/PERMALINK/projects.json`


## Input Parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Example</th>
    <th>Required/Optional</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>scope</th>
    <td><code>location</code></td>
    <td>optional</td>
    <td>Use the scope to specify how the search-query <code>q</code> should behave:
<ul>
<li>"no scope" (default) performs a full text search
<li><code>human_name</code> searches only on the manager-fullname and carrier-fullname.
Use this to get all projects by "Unicef" or by "Till Behnke".
<li><code>location</code> does a reverse geocoding lookup
and shows results based on the lookup-bounding-box.
</ul>
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>q</th>
    <td><code>Skateistan</code></td>
    <td>optional</td>
    <td>Search query. The searches behaviour is based on the scope.</td>
  </tr>
  <tr>
    <th>order</th>
    <td><code>rank:ASC</code></td>
    <td>optional</td>
    <td>Order the result by solr-<code>score</code> (only when a query (q) is given),
<code>rank</code>, <code>id</code>, <code>progress_percentage</code>,
<code>tax_deductible</code>, <code>created_at</code>, <code>updated_at</code>,
<code>last_donation_at</code>, <code>completed</code>.
Use the optional <code>ASC</code> (default) or <code>DESC</code>.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
<br>
The default order is the same as for the
<a href="http//www.betterplace.org/en/projects/list">betterplace.org project list</a>:
<code>completed:asc| score:desc| rank:asc| last_donation_at:desc</code>
</td>
  </tr>
  <tr>
    <th>facets</th>
    <td><code>completed:false</code></td>
    <td>optional</td>
    <td>Filter the result set by <code>tax_deductible</code> or <code>completed</code>. Possible values are
<code>true</code> or <code>false</code>.
It is possible to set multiple facet filters.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>nelat</th>
    <td><code>51.123</code></td>
    <td>optional</td>
    <td>For geographic bound filterning: The northeast corner's latitude.</td>
  </tr>
  <tr>
    <th>nelng</th>
    <td><code>12.123</code></td>
    <td>optional</td>
    <td>For geographic bound filterning: The northeast corner's longitude.</td>
  </tr>
  <tr>
    <th>swlat</th>
    <td><code>51.001</code></td>
    <td>optional</td>
    <td>For geographic bound filterning: The southwest corner's latitude.</td>
  </tr>
  <tr>
    <th>swlng</th>
    <td><code>12.001</code></td>
    <td>optional</td>
    <td>For geographic bound filterning: The southwest corner's longitude.</td>
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
    <td>Where the project takes place</td>
  </tr>
  <tr>
    <th>zip</th>
    <td>null &#124; string</td>
    <td>"10997"</td>
    <td>Where the project takes place</td>
  </tr>
  <tr>
    <th>city</th>
    <td>null &#124; string</td>
    <td>"Berlin"</td>
    <td>Where the project takes place</td>
  </tr>
  <tr>
    <th>country</th>
    <td>null &#124; string</td>
    <td>"Deutschland"</td>
    <td>Where the project takes place, translated to the requested language</td>
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
    <th>tax_deductible</th>
    <td>boolean</td>
    <td>true</td>
    <td>True if the project marked as tax deductible.
If so, Users can request a tax-receipt that can be used
with the german tax authorities.
[More about this](http://www.betterplace.org/c/hilfe/projekt-steuerlich-absetzbar/).
</td>
  </tr>
  <tr>
    <th>open_amount_in_cents</th>
    <td>number</td>
    <td>12382</td>
    <td>How many cents are needed to complete the project</td>
  </tr>
  <tr>
    <th>positive_opinions_count</th>
    <td>number</td>
    <td>13</td>
    <td>Number of positive opinions that are given to a project without a donation.
Those are plain opinions as well as visitor opinions.
</td>
  </tr>
  <tr>
    <th>negative_opinions_count</th>
    <td>number</td>
    <td>0</td>
    <td>Number of *negative* opinions (usually 0) that are given to a project without a donation.
Those are plain opinions as well as visitor opinions.
Critical opinions are part of the betterplace.org
["Web of trust"](http://www.betterplace.org/c/hilfe/woran-erkenne-ich-dass-ein-projekt-vertrauenswurdig-ist/).
</td>
  </tr>
  <tr>
    <th>donor_count</th>
    <td>number</td>
    <td>46</td>
    <td>Number of unique donors, based on the payment-email-address</td>
  </tr>
  <tr>
    <th>progress_percentage</th>
    <td>number</td>
    <td>82</td>
    <td>% financed. Note: We have legacy projects with substantial
donation needs. This percentage includes those needs.
</td>
  </tr>
  <tr>
    <th>incomplete_need_count</th>
    <td>number</td>
    <td>6</td>
    <td>Number of needs that still need donations</td>
  </tr>
  <tr>
    <th>completed_need_count</th>
    <td>number</td>
    <td>12</td>
    <td>Number of completed needs</td>
  </tr>
  <tr>
    <th>blog_post_count</th>
    <td>number</td>
    <td>8</td>
    <td>Number of blogposts (all types)</td>
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
  <tr>
    <th>carrier.name</th>
    <td>string</td>
    <td>"Till B."</td>
    <td>The carrier can be an organisation or user.</td>
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
(<a href="project_details.md">project details</a>)
</td>
  </tr>
  <tr>
    <th>platform</th>
    <td>Permalink to betterplace.org</td>
  </tr>
  <tr>
    <th>opinions</th>
    <td>Link to <a href="../opinion_list.md">opinion list</a>
</td>
  </tr>
  <tr>
    <th>pictures</th>
    <td>Link to <a href="../picture_list.md">project picture list</a>
</td>
  </tr>
  <tr>
    <th>needs</th>
    <td>Link to <a href="../need_list.md">project need list</a>
</td>
  </tr>
  <tr>
    <th>blog_posts</th>
    <td>Link to <a href="../blog_post_list.md">blog post list</a>
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
    <th>profile_picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>profile_picture.large</th>
    <td>Large size</td>
  </tr>
  <tr>
    <th>profile_picture.profile</th>
    <td>Medium size</td>
  </tr>
  <tr>
    <th>profile_picture.thumb</th>
    <td>Thumbnail size</td>
  </tr>
  <tr>
    <th>carrier.self</th>
    <td>Link to this resource itself
(<a href="organisation_details.md">organisation details</a>)
Note: Since the there is no api for users yet, this is only
set for organisations.
</td>
  </tr>
  <tr>
    <th>profile_picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>profile_picture.large</th>
    <td>Large size</td>
  </tr>
  <tr>
    <th>profile_picture.profile</th>
    <td>Medium size</td>
  </tr>
  <tr>
    <th>profile_picture.thumb</th>
    <td>Thumbnail size</td>
  </tr>
  <tr>
    <th>profile_picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>profile_picture.large</th>
    <td>Large size</td>
  </tr>
  <tr>
    <th>profile_picture.profile</th>
    <td>Medium size</td>
  </tr>
  <tr>
    <th>profile_picture.thumb</th>
    <td>Thumbnail size</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 2,
  "offset": 0,
  "total_pages": 1,
  "current_page": 1,
  "per_page": 3,
  "data": [
    {
      "id": 1114,
      "created_at": "2009-03-10T10:12:16Z",
      "updated_at": "2013-04-04T18:21:55Z",
      "latitude": 34.531617284782,
      "longitude": 69.13581752939456,
      "street": "Taimani, behind Qasemi Winhouse",
      "zip": "",
      "city": "Kabul",
      "country": "Afghanistan",
      "title": "Skateistan Afghanistan",
      "description": "With 68% of Afghanistan’s population under the age of 25, Skateistan strongly believes that youth are the ones most capable of bringing about social change.<br /><br />Skateistan is an Afghan NGO which operates Afghanistan’s (and the world’s) first co-educational skateboarding school. The Skateistan school engages nearly 400 Kabul youth weekly through skateboarding, and provides them with new opportunities in cross-cultural interaction, education, and personal empowerment programs. <br /><br />The students (ages 5-17) come from all of Afghanistan’s diverse ethnic and socioeconomic backgrounds, and include 40% female students, hundreds of streetworking children, and youth with disabilities. They develop skills in skateboarding, leadership, problem-solving, multimedia, and creative arts. The students themselves decide what they want to learn; we connect them with a safe space and opportunities for them to develop the skills that they consider important.<br /><br />For Afghan girls Skateistan's programming is especially important as there are very few recreational opportunities for females. For example, it is not culturally acceptable for girls in Afghanistan to ride bicycles or play sports in public. <br /><br />Skateistan has been active in Kabul since 2007 - with our facility built in 2009 - and in that time we’ve seen that Afghan youth of all ethnicities, genders, and socioeconomic backgrounds love to skateboard. Skateistan brings them together, equipping young men and women to lead their communities toward social change and development.<br /><br />In 2012 Skateistan will be opening its second Afghan facility in Mazar-e-Sharif, Northern Afghanistan. It will have space to teach up to 1000 youth weekly.<br /><br />Our program gives hundreds of oppressed youth a voice. Education and the opportunity for self-expression can break the cycles of poverty, illiteracy and exclusion, with sport paving the way.",
      "tax_deductible": true,
      "open_amount_in_cents": 18486,
      "positive_opinions_count": 378,
      "negative_opinions_count": 1,
      "donor_count": 283,
      "progress_percentage": 99,
      "incomplete_need_count": 3,
      "completed_need_count": 70,
      "blog_post_count": 52,
      "contact": {
        "name": "F. Meyn",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/269/654/original_IMG_0381.JPG"
            },
            {
              "rel": "large",
              "href": "http://www.betterplace.org/paperclip/000/269/654/big_IMG_0381.png"
            },
            {
              "rel": "profile",
              "href": "http://www.betterplace.org/paperclip/000/269/654/profile_IMG_0381.jpg"
            },
            {
              "rel": "thumb",
              "href": "http://www.betterplace.org/paperclip/000/269/654/thumb_IMG_0381.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.dev/en/users/frauke_m3"
          }
        ]
      },
      "carrier": {
        "name": "Skateistan",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/279/873/original_betterplace-logo.png"
            },
            {
              "rel": "large",
              "href": "http://www.betterplace.org/paperclip/000/279/873/big_betterplace-logo.png"
            },
            {
              "rel": "profile",
              "href": "http://www.betterplace.org/paperclip/000/279/873/profile_betterplace-logo.png"
            },
            {
              "rel": "thumb",
              "href": "http://www.betterplace.org/paperclip/000/279/873/thumb_betterplace-logo.png"
            }
          ]
        },
        "links": [
          {
            "rel": "self",
            "href": "http://www.betterplace.dev/en/api_v4/organisations/1054.json"
          }
        ]
      },
      "profile_picture": {
        "links": [
          {
            "rel": "original",
            "href": "http://www.betterplace.org/paperclip/000/289/158/original_girls-merza-sm.jpg"
          },
          {
            "rel": "large",
            "href": "http://www.betterplace.org/paperclip/000/289/158/big_girls-merza-sm.png"
          },
          {
            "rel": "profile",
            "href": "http://www.betterplace.org/paperclip/000/289/158/profile_girls-merza-sm.jpg"
          },
          {
            "rel": "thumb",
            "href": "http://www.betterplace.org/paperclip/000/289/158/thumb_girls-merza-sm.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114.json"
        },
        {
          "rel": "platform",
          "href": "http://www.betterplace.dev/en/projects/1114-skateistan-afghanistan"
        },
        {
          "rel": "opinions",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114/opinions.json"
        },
        {
          "rel": "pictures",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114/pictures.json"
        },
        {
          "rel": "needs",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114/needs.json"
        },
        {
          "rel": "blog_posts",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114/blog_posts.json"
        }
      ]
    },
    {
      "id": 6233,
      "created_at": "2011-02-25T07:48:43Z",
      "updated_at": "2013-01-22T08:55:29Z",
      "latitude": 11.55883121490479,
      "longitude": 104.9174423217773,
      "city": "Phnom Penh",
      "country": "Cambodia",
      "title": "Skateistan Cambodia",
      "description": "Skateistan Cambodia began operations in March 2011, building the country's first skatepark in Phnom Penh. Since then the NGO has been teaching skateboarding and creative arts classes with marginalized and streetworking Khmer youth six days a week. <br /><br />Skateboarding is a low-barrier, accessible activity that attracts girls and boys of all backgrounds and abilities. The interest from Cambodia's youth has grown so much since March 2011 that Skateistan Cambodia is now building its own facility to accommodate more than the 150 youth we currently work with weekly.<br /><br />By building a safe and covered Skateistan facility in Phnom Pehn, Skateistan will provide year-round opportunities for youth to engage in recreational activities that encourages girls and boys of all backgrounds to build relationships with one another, while increasing their self-confidence and leadership skills. The facility will also have classroom spaces providing creative arts and multimedia activities for the students.<br /><br />Partnering with local, best-practice NGOs in Cambodia, such as Pour un Sourire d'Enfant (PSE), Friends Intl., and Tiny Toones, Skateistan Cambodia also aims to use skateboarding as a tool to create a bridge between at-risk youth and the quality support services already existing in Phnom Penh.<br /><br />Help us grow this grassroots project and create a safe space for all Cambodian youth to be a part of!",
      "tax_deductible": true,
      "open_amount_in_cents": 34000,
      "positive_opinions_count": 32,
      "negative_opinions_count": 0,
      "donor_count": 30,
      "progress_percentage": 90,
      "incomplete_need_count": 1,
      "completed_need_count": 12,
      "blog_post_count": 24,
      "contact": {
        "name": "F. Meyn",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/269/654/original_IMG_0381.JPG"
            },
            {
              "rel": "large",
              "href": "http://www.betterplace.org/paperclip/000/269/654/big_IMG_0381.png"
            },
            {
              "rel": "profile",
              "href": "http://www.betterplace.org/paperclip/000/269/654/profile_IMG_0381.jpg"
            },
            {
              "rel": "thumb",
              "href": "http://www.betterplace.org/paperclip/000/269/654/thumb_IMG_0381.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.dev/en/users/frauke_m3"
          }
        ]
      },
      "carrier": {
        "name": "Skateistan",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/279/873/original_betterplace-logo.png"
            },
            {
              "rel": "large",
              "href": "http://www.betterplace.org/paperclip/000/279/873/big_betterplace-logo.png"
            },
            {
              "rel": "profile",
              "href": "http://www.betterplace.org/paperclip/000/279/873/profile_betterplace-logo.png"
            },
            {
              "rel": "thumb",
              "href": "http://www.betterplace.org/paperclip/000/279/873/thumb_betterplace-logo.png"
            }
          ]
        },
        "links": [
          {
            "rel": "self",
            "href": "http://www.betterplace.dev/en/api_v4/organisations/1054.json"
          }
        ]
      },
      "profile_picture": {
        "links": [
          {
            "rel": "original",
            "href": "http://www.betterplace.org/paperclip/000/288/830/original_327569_368768896527128_1081473646_o.jpg"
          },
          {
            "rel": "large",
            "href": "http://www.betterplace.org/paperclip/000/288/830/big_327569_368768896527128_1081473646_o.png"
          },
          {
            "rel": "profile",
            "href": "http://www.betterplace.org/paperclip/000/288/830/profile_327569_368768896527128_1081473646_o.jpg"
          },
          {
            "rel": "thumb",
            "href": "http://www.betterplace.org/paperclip/000/288/830/thumb_327569_368768896527128_1081473646_o.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/projects/6233.json"
        },
        {
          "rel": "platform",
          "href": "http://www.betterplace.dev/en/projects/6233-skateistan-cambodia"
        },
        {
          "rel": "opinions",
          "href": "http://www.betterplace.dev/en/api_v4/projects/6233/opinions.json"
        },
        {
          "rel": "pictures",
          "href": "http://www.betterplace.dev/en/api_v4/projects/6233/pictures.json"
        },
        {
          "rel": "needs",
          "href": "http://www.betterplace.dev/en/api_v4/projects/6233/needs.json"
        },
        {
          "rel": "blog_posts",
          "href": "http://www.betterplace.dev/en/api_v4/projects/6233/blog_posts.json"
        }
      ]
    }
  ]
}
```

