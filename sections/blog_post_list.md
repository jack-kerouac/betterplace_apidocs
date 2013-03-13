
# Project Blog Post List ⇄ [Details](blog_post_details.md)

```nginx
GET https://api.betterplace.org/en/api_v4/projects/38/blog_posts.json
```

A list of betterplace.org projects blog posts.
Results are contains in a *data* attribute.

*For [betterplace.org clients](../README.md#client-api):*

* _Project-Blogposts:_ There is no client-scoped-url.
Please use the api calls that are provided inside the client project _url_ response
to make sure you only request data that is associated with one of your projects.

* _All Blogposts:_ Clients can retrieve a list of all blogpost of all client-projects:
`/clients/PERMALINK/blog_posts.json`


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
  "total_entries": 3,
  "offset": 0,
  "total_pages": 2,
  "current_page": 1,
  "per_page": 2,
  "data": [
    {
      "format": "json",
      "id": 22,
      "created_at": "2007-09-06T06:12:42Z",
      "updated_at": "2008-06-03T05:58:47Z",
      "lang": "en",
      "type": "BlogPost",
      "title": "Progress",
      "body": "We are making great progress as far as having a routine and regular turnout to rehearsal.I have spoken to Mudpie. All the outfits will be ready they say by the 25th. The modelling rehearsals begin after September 17th. Dances are looking quite good, the kids just need to rehearse at home so that the whole thing flows and looks finished.\n\n\n\t<p>I have now contacted a costume shop in South Africa and made some lengthy details. She will supply us with all we need from the time we order it in two weeks. Once she has sent me a quotation for her prices, I will readjust the budget accordingly.</p>\n\n\n\t<p>I encountered some problems with the illustrations of the book last week, but managed to solve them. The project is in control which is a great feeling. I am still planning to launch during the first two weekends in October, but if it does not work, we will just start a week later, so all should be well.</p>\n\n\n\t<p>I&#8217;ll keep everyone up to date about the progress.</p>",
      "author": {
        "format": "json",
        "name": "Bontekanye B.",
        "picture": {
          "format": "json",
          "links": [
            {
              "rel": "profile",
              "href": "http://www.betterplace.org/paperclip/000/000/632/profile_Bonty_Botumile.jpg"
            },
            {
              "rel": "thumb",
              "href": "http://www.betterplace.org/paperclip/000/000/632/thumb_Bonty_Botumile.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.dev/en/users/bontekanye_b"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/blog_posts/22.json"
        },
        {
          "rel": "documentation",
          "href": "https://github.com/betterplace/betterplace_apidocs/blob/master/sections/blog_post_details.md"
        }
      ]
    },
    {
      "format": "json",
      "id": 44,
      "created_at": "2007-09-21T13:14:12Z",
      "updated_at": "2008-06-03T05:58:48Z",
      "lang": "en",
      "type": "BlogPost",
      "title": "Book Launch in choral music and poetry",
      "body": "This year, October 2008 Bontekanye Botumile will launch her third children’s’ book “The Seed Children”.  This story carries a conservation message that encourages children to conserve trees, sensitise them on how their daily actions can damage their environment and teaches them about symbiotic relationships between trees and humans in story form.\n\n\n\t<p>The story has already been tested to international students ranging in age from Four to thirteen in Gaborone -West Wood International School, Broadhurst Primary school, 2008 Maitisong Festival and  Maun based Matshwane Primary School and Okavango International School.</p>\n\n\n\t<p>To further test the book, the exercise of reading a manuscript instead of a book had three objectives:</p>\n\n\n\t<p>teach students the process of  how a book is written and published</p>\n\n\n\t<p>demonstrate how their opinions and comments help the writer edit the story</p>\n\n\n\t<p>create a rite of passage so that they relate to the book in its final product stage.</p>\n\n\n\t<p>a marketing research tool to test the reception of the book on its primary target market. (children and teachers)</p>\n\n\n\t<p> THE LAUNCH FOR THE SEED CHILDREN </p>\n\n\n\t<p> THEME - “Trees are life! Reduce, Reuse, Recycle!”</p>\n\n\n\t<p> SLOGAN : “The next time you give a gift, give a tree or plant!”</p>\n\n\n\t<p>To start the chain of giving trees as gifts, 25 indigenous trees purchased from Government nursery will be given away to 25 children at each launch.</p>\n\n\n\t<p>Like the two previous books, the new book will be launched in a live performance and art fair in Maun, Orapa, Francistown, Sua Pan and Gaborone. The medium of the actual stage performance will be choral music, poetry and drama.</p>\n\n\n\t<p>The performance will be acted out by twenty unemployed youth with talent in choral singing, dancing and acting. In preparation for the launch, they will undergo rigorous training by  professionals in the performing arts for a minimum of six weeks prior to the launch.</p>",
      "author": {
        "format": "json",
        "name": "Bontekanye B.",
        "picture": {
          "format": "json",
          "links": [
            {
              "rel": "profile",
              "href": "http://www.betterplace.org/paperclip/000/000/632/profile_Bonty_Botumile.jpg"
            },
            {
              "rel": "thumb",
              "href": "http://www.betterplace.org/paperclip/000/000/632/thumb_Bonty_Botumile.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.dev/en/users/bontekanye_b"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/blog_posts/44.json"
        },
        {
          "rel": "documentation",
          "href": "https://github.com/betterplace/betterplace_apidocs/blob/master/sections/blog_post_details.md"
        }
      ]
    }
  ]
}
```

