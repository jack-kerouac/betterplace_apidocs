
# Project Blog Post Details ⇄ [List](blog_posts_list.md)

```nginx
GET https://www.betterplace.org/en/api_v4/projects/38/blog_posts/22.json
```

The details of a betterplace.org project blog post.
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
    <td>string</td>
    <td>53</td>
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
    <th>lang</th>
    <td>string</td>
    <td>en</td>
    <td>Blog posts have only one language at the moments</td>
  </tr>
  <tr>
    <th>type</th>
    <td>string</td>
    <td>PayoutBlogPost</td>
    <td>Blogposts can be created by a user <code>BlogPost</code>
to update your donors about new developments
or as part of the payout process <code>PayoutBlogPost</code>
where you tell what needs you payed our and
what you plan to do with the money.
</td>
  </tr>
  <tr>
    <th>title</th>
    <td>string</td>
    <td>Thank you from Beijing</td>
    <td></td>
  </tr>
  <tr>
    <th>body</th>
    <td>string</td>
    <td>I am so happy to hear about the first donation for the Good Gifted Garden. If I told Chun …</td>
    <td>The body has html like links, embeded videos, pictures.</td>
  </tr>
  <tr>
    <th>author</th>
    <td>string</td>
    <td>"Till B."</td>
    <td>Display name of a betterplace.org user.
Possible formats: "Till B.", "T. Behnke", "Till Behnke"
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
(<a href="blog_post_details.md">blog post details</a>)
</td>
  </tr>
  <tr>
    <th>documentation</th>
    <td>Link to this resource in the documentation
</td>
  </tr>
</table>

## Response Example

```json
{
  "id": 22,
  "created_at": "2007-09-06T06:12:42Z",
  "updated_at": "2008-06-03T05:58:47Z",
  "lang": "en",
  "type": "BlogPost",
  "title": "Progress",
  "body": "We are making great progress as far as having a routine and regular turnout to rehearsal.I have spoken to Mudpie. All the outfits will be ready they say by the 25th. The modelling rehearsals begin after September 17th. Dances are looking quite good, the kids just need to rehearse at home so that the whole thing flows and looks finished.\n\n\n\t<p>I have now contacted a costume shop in South Africa and made some lengthy details. She will supply us with all we need from the time we order it in two weeks. Once she has sent me a quotation for her prices, I will readjust the budget accordingly.</p>\n\n\n\t<p>I encountered some problems with the illustrations of the book last week, but managed to solve them. The project is in control which is a great feeling. I am still planning to launch during the first two weekends in October, but if it does not work, we will just start a week later, so all should be well.</p>\n\n\n\t<p>I&#8217;ll keep everyone up to date about the progress.</p>",
  "author": {
    "name": "Bontekanye B.",
    "picture": {
      "links": [
        {
          "rel": "original",
          "href": "http://www.betterplace.org/paperclip/000/000/632/original_Bonty_Botumile.jpg"
        },
        {
          "rel": "large_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/000/632/big_Bonty_Botumile.png"
        },
        {
          "rel": "profile_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/000/632/profile_Bonty_Botumile.jpg"
        },
        {
          "rel": "thumb_attention_deprecated",
          "href": "http://www.betterplace.org/paperclip/000/000/632/thumb_Bonty_Botumile.png"
        }
      ]
    },
    "links": [
      {
        "rel": "platform",
        "href": "https://www.betterplace.org/en/users/bontekanye_b"
      }
    ]
  },
  "links": [
    {
      "rel": "self",
      "href": "https://www.betterplace.org/en/api_v4/blog_posts/22.json"
    },
    {
      "rel": "documentation",
      "href": "https://github.com/betterplace/betterplace_apidocs/blob/master/sections/blog_post_details.md"
    }
  ]
}
```

