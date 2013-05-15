
# Project Details ⇄ [List](projects_list.md)

```nginx
GET https://api.betterplace.org/en/api_v4/projects/1114.json
```

The details of a betterplace.org project (donate money).

*For [betterplace.org clients](../README.md#client-api):*
Use this resource like `/clients/PERMALINK/projects/ID.json`


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
    <td>Link to <a href="../opinions_list.md">opinion list</a>
</td>
  </tr>
  <tr>
    <th>pictures</th>
    <td>Link to <a href="../picture_list.md">project picture list</a>
</td>
  </tr>
  <tr>
    <th>needs</th>
    <td>Link to <a href="../needs_list.md">project need list</a>
</td>
  </tr>
  <tr>
    <th>blog_posts</th>
    <td>Link to <a href="../blog_posts_list.md">blog post list</a>
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
    <th>profile_picture.large_attention_deprecated</th>
    <td>Large size – ATTENTION, this feature is DEPRECATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>profile_picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRECATED. See above.</td>
  </tr>
  <tr>
    <th>profile_picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRECATED. See above.</td>
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
    <th>profile_picture.large_attention_deprecated</th>
    <td>Large size – ATTENTION, this feature is DEPRECATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>profile_picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRECATED. See above.</td>
  </tr>
  <tr>
    <th>profile_picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRECATED. See above.</td>
  </tr>
  <tr>
    <th>profile_picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>profile_picture.large_attention_deprecated</th>
    <td>Large size – ATTENTION, this feature is DEPRECATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>profile_picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRECATED. See above.</td>
  </tr>
  <tr>
    <th>profile_picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRECATED. See above.</td>
  </tr>
</table>

## Response Example

```json
{
  "id": 1114,
  "created_at": "2009-03-10T10:12:16Z",
  "updated_at": "2013-05-14T17:54:30Z",
  "latitude": 34.531617284782,
  "longitude": 69.13581752939456,
  "street": "Taimani, behind Qasemi Winhouse",
  "zip": "",
  "city": "Kabul",
  "country": "Afghanistan",
  "title": "Skateistan Afghanistan",
  "description": "With 68% of Afghanistan’s population under the age of 25, Skateistan strongly believes that youth are the ones most capable of bringing about social change.<br /><br />Skateistan is an Afghan NGO which operates Afghanistan’s (and the world’s) first co-educational skateboarding school. The Skateistan school engages nearly 400 Kabul youth weekly through skateboarding, and provides them with new opportunities in cross-cultural interaction, education, and personal empowerment programs. <br /><br />The students (ages 5-17) come from all of Afghanistan’s diverse ethnic and socioeconomic backgrounds, and include 40% female students, hundreds of streetworking children, and youth with disabilities. They develop skills in skateboarding, leadership, problem-solving, multimedia, and creative arts. The students themselves decide what they want to learn; we connect them with a safe space and opportunities for them to develop the skills that they consider important.<br /><br />For Afghan girls Skateistan's programming is especially important as there are very few recreational opportunities for females. For example, it is not culturally acceptable for girls in Afghanistan to ride bicycles or play sports in public. <br /><br />Skateistan has been active in Kabul since 2007 - with our facility built in 2009 - and in that time we’ve seen that Afghan youth of all ethnicities, genders, and socioeconomic backgrounds love to skateboard. Skateistan brings them together, equipping young men and women to lead their communities toward social change and development.<br /><br />In 2012 Skateistan will be opening its second Afghan facility in Mazar-e-Sharif, Northern Afghanistan. It will have space to teach up to 1000 youth weekly.<br /><br />Our program gives hundreds of oppressed youth a voice. Education and the opportunity for self-expression can break the cycles of poverty, illiteracy and exclusion, with sport paving the way.",
  "tax_deductible": true,
  "open_amount_in_cents": 86530,
  "positive_opinions_count": 406,
  "negative_opinions_count": 0,
  "donor_count": 302,
  "progress_percentage": 97,
  "incomplete_need_count": 1,
  "completed_need_count": 73,
  "blog_post_count": 62,
  "contact": {
    "name": "F. Meyn",
    "picture": {
      "links": [
        {
          "rel": "original",
          "href": "http://www.betterplace.org/paperclip/000/269/654/original_IMG_0381.JPG"
        },
        {
          "rel": "large_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/269/654/big_IMG_0381.png"
        },
        {
          "rel": "profile_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/269/654/profile_IMG_0381.jpg"
        },
        {
          "rel": "thumb_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/269/654/thumb_IMG_0381.png"
        }
      ]
    },
    "links": [
      {
        "rel": "platform",
        "href": "https://api.betterplace.org/en/users/frauke_m3"
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
          "rel": "large_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/279/873/big_betterplace-logo.png"
        },
        {
          "rel": "profile_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/279/873/profile_betterplace-logo.png"
        },
        {
          "rel": "thumb_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/279/873/thumb_betterplace-logo.png"
        }
      ]
    },
    "links": [
      {
        "rel": "self",
        "href": "https://api.betterplace.dev/en/api_v4/organisations/1054.json"
      }
    ]
  },
  "profile_picture": {
    "links": [
      {
        "rel": "original",
        "href": "http://asset1.betterplace.org/paperclip/000/307/764/original_default_girls-merza-sm-LOCAL.jpg"
      },
      {
        "rel": "large_attention_deprecated",
        "href": "http://asset1.betterplace.org/paperclip/000/307/764/big_default_girls-merza-sm-LOCAL.png"
      },
      {
        "rel": "profile_attention_deprecated",
        "href": "http://asset1.betterplace.org/paperclip/000/307/764/profile_default_girls-merza-sm-LOCAL.jpg"
      },
      {
        "rel": "thumb_attention_deprecated",
        "href": "http://asset1.betterplace.org/paperclip/000/307/764/thumb_default_girls-merza-sm-LOCAL.png"
      }
    ]
  },
  "links": [
    {
      "rel": "self",
      "href": "https://api.betterplace.dev/en/api_v4/projects/1114.json"
    },
    {
      "rel": "platform",
      "href": "https://api.betterplace.org/en/projects/1114-skateistan-afghanistan"
    },
    {
      "rel": "opinions",
      "href": "https://api.betterplace.dev/en/api_v4/projects/1114/opinions.json"
    },
    {
      "rel": "pictures",
      "href": "https://api.betterplace.dev/en/api_v4/projects/1114/pictures.json"
    },
    {
      "rel": "needs",
      "href": "https://api.betterplace.dev/en/api_v4/projects/1114/needs.json"
    },
    {
      "rel": "blog_posts",
      "href": "https://api.betterplace.dev/en/api_v4/projects/1114/blog_posts.json"
    }
  ]
}
```

