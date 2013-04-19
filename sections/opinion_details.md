
# Project Opinion Details ⇄ [List](opinion_list.md)

```nginx
GET https://www.betterplace.org/en/api_v4/projects/38/opinions/22.json
```

The details of a betterplace.org project opinion (donate money).
The details and list view show the same data.

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
    <td>1</td>
    <td>An integer number ≥ 1</td>
  </tr>
  <tr>
    <th>created_at</th>
    <td>string</td>
    <td>"1994-11-05T13:15:30Z"</td>
    <td>DateTime (ISO8601 with Timezone)</td>
  </tr>
  <tr>
    <th>donated_amount_in_cents</th>
    <td>number</td>
    <td>5000</td>
    <td>If the opinion was created as part of a donation, this shows the opinions text</td>
  </tr>
  <tr>
    <th>score</th>
    <td>string</td>
    <td>positive</td>
    <td>Opinions can be positive or negative. Negative opinions usually get
a comment as answer very fast but there is no API for opinion-comments yet.
</td>
  </tr>
  <tr>
    <th>author.name</th>
    <td>null &#124; string</td>
    <td>"Till B."</td>
    <td>Display name of a betterplace.org user.
Possible formats: "Till B.", "T. Behnke", "Till Behnke".
In the case of donation-opinions the name might also be anonymized
like "Payback User" or empty/null for anonymous donations.
</td>
  </tr>
  <tr>
    <th>message</th>
    <td>null &#124; string</td>
    <td>"This is a great project. In spring 2007 I travelled around the area together with my children and …"</td>
    <td>An optional message users can provide to tell others
why they like or dislike this project
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
(<a href="opinion_details.md">opinion details</a>)
</td>
  </tr>
  <tr>
    <th>author.platform</th>
    <td>The user's profile on betterplace.org.
To view a user profile you have to be logged in.
This array is empty if the user has no useraccount
with betterplace.org but donated via one of our partner.
</td>
  </tr>
  <tr>
    <th>author.picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>author.picture.large_attention_deprecated</th>
    <td>Large size – ATTENTION, this feature is DEPRICATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>author.picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>author.picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
</table>

## Response Example

```json
{
  "id": 22,
  "created_at": "2007-11-24T13:14:02Z",
  "score": "positive",
  "author": {
    "name": "G. Krabbe",
    "picture": {
      "links": [
        {
          "rel": "original",
          "href": "http://www.betterplace.org/paperclip/000/004/520/original_Schule_Leutersdorf_2.JPG"
        },
        {
          "rel": "large_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/004/520/big_Schule_Leutersdorf_2.png"
        },
        {
          "rel": "profile_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/004/520/profile_Schule_Leutersdorf_2.jpg"
        },
        {
          "rel": "thumb_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/004/520/thumb_Schule_Leutersdorf_2.png"
        }
      ]
    },
    "links": [
      {
        "rel": "platform",
        "href": "https://www.betterplace.org/en/users/giesela_k"
      }
    ]
  },
  "message": "Ich bin zweimal in Bolivien gewesen, auch in El Alto und im COMPA, und ich habe gesehen, wie schwer das (Über-)leben für viele Leute ist. Wie wichtig Bildung ist, sollte ich als ehemalige Lehrerin ja wissen.... Das hier vorgestellte Projekt erinnert mich an die Fahrbibliotheken in der ehemaligen DDR; und wenn hier benachteiligten Kindern und Jugendlichen in Gegenden ohne kulturelle Infrastruktur eine adäquate Form von Bildung ermöglicht werden soll, ist das nur zu unterstützen. Nach meinen Möglichkeiten werde ich das Projekt unterstützen.",
  "links": [
    {
      "rel": "self",
      "href": "https://www.betterplace.org/en/api_v4/projects/35/opinions/22.json"
    }
  ]
}
```

