
# Project Opinion List ⇄ [Details](opinion_details.md)

```nginx
GET https://api.betterplace.org/en/api_v4/projects/1114/opinions.json?facets=score%3A1&order=created_at%3AASC
```

## Attention: The opinions-list for projects is still WIP. Right now it shows all opinions instead of those of the project.

A list of betterplace.org projects opinions (donate money).
Results are contains in a *data* attribute.

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
    <th>order</th>
    <td><code>created_at:ASC</code></td>
    <td>optional</td>
    <td>Order the result by <code>created_at</code> (default), <code>id</code>,
<code>score</code>, <code>type</code>, <code>message</code>
Use the optional <code>ASC</code> (default) or <code>DESC</code>.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>facets</th>
    <td><code>score:1</code></td>
    <td>optional</td>
    <td>Filter the result set:
<ul>
<li><code>facets=score:1</code> only positive opinion
<li><code>facets=score:%2D1</code> only negative opinion
<li><code>facets=type:DonorOpinion</code> only opinions with_donation:true
</ul>
It is possible to set multiple facet filters.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
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
    <td>Opinions can be positive or negative (what we call critial).
Critial opinions usually get a comment as answer very fast but
there is no API for opinion-comments yet.
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
    <th>author.picture.large</th>
    <td>Large size</td>
  </tr>
  <tr>
    <th>author.picture.profile</th>
    <td>Medium size</td>
  </tr>
  <tr>
    <th>author.picture.thumb</th>
    <td>Thumbnail size</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 378,
  "offset": 0,
  "total_pages": 126,
  "current_page": 1,
  "per_page": 3,
  "data": [
    {
      "id": 964,
      "created_at": "2009-03-18T16:34:37Z",
      "score": "positive",
      "author": {
        "name": "A. Bald",
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.dev/en/users/alexandra_b"
          }
        ]
      },
      "message": "Ich unterstütze Skateistan weil: <br />a) ich die Projektleiter Oliver uns Max kenne und von ihnen überzeugt bin,<br />b) ich durch alles, was ich (auch durch meine Arbeit als Designerin) aus Kabul mitbekommen habe sehr berührt wurde,<br />c) ich persönlich als Designerin für Skateistan involviert bin!",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114/opinions/964.json"
        }
      ]
    },
    {
      "id": 1024,
      "created_at": "2009-03-31T18:21:52Z",
      "score": "positive",
      "author": {
        "name": "d. habibi",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/047/224/original_CIMG4253.JPG"
            },
            {
              "rel": "large",
              "href": "http://www.betterplace.org/paperclip/000/047/224/big_CIMG4253.png"
            },
            {
              "rel": "profile",
              "href": "http://www.betterplace.org/paperclip/000/047/224/profile_CIMG4253.jpg"
            },
            {
              "rel": "thumb",
              "href": "http://www.betterplace.org/paperclip/000/047/224/thumb_CIMG4253.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.dev/en/users/omar_a"
          }
        ]
      },
      "message": "ich bin Fürsprecher dieses Projektes, da ich in Kabul geboren bin und meine Kindheit dort verbracht habe, in Deutschland dann als Jugendlicher selbst geskatet habe, jetzt hier studiere und das Thema meiner Diplomarbeit \"Leben in Kabul\" heisst.<br />Ich bin begeistert von dieser Idee \"Skateistan\". Nicht nur wegen der direkten Hilfe vor Ort in Kabul, sondern auch wegen dem großen Presseecho überall in der Welt, wo man sonst nur Nachrichten aus Afghanistan hört, wenn mal wieder ein Attentat verübt wurde, oder nach Bin Laden gesucht wird.",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114/opinions/1024.json"
        }
      ]
    },
    {
      "id": 1323,
      "created_at": "2009-06-14T08:58:06Z",
      "score": "positive",
      "author": {
        "name": "m. mohsen",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/058/762/original_Mirwais_Mohsen_image.jpg"
            },
            {
              "rel": "large",
              "href": "http://www.betterplace.org/paperclip/000/058/762/big_Mirwais_Mohsen_image.png"
            },
            {
              "rel": "profile",
              "href": "http://www.betterplace.org/paperclip/000/058/762/profile_Mirwais_Mohsen_image.jpg"
            },
            {
              "rel": "thumb",
              "href": "http://www.betterplace.org/paperclip/000/058/762/thumb_Mirwais_Mohsen_image.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.dev/en/users/mirwais_m"
          }
        ]
      },
      "message": "In my point of view, Skateistan is the key to changing the lives of children in Afghanistan. Helping my brothers and sisters  will change  our country because these children are the future of Afghanistan. Providing them with education, health care and teaching them respect for each other and their families will help them be productive and responsible members of our community.  They have learned a lot from skating, and I work for Skateistan in order to make the dreams of these children come true, and break these nationalism ethnic barriers.",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/projects/1114/opinions/1323.json"
        }
      ]
    }
  ]
}
```

