
# Project Details

```nginx
GET http://betterplace.dev/en/api_v4/projects/1114.json
```

The details of a betterplace.org project (donate money).


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

## Response Parameter

*TODO*

## Response Example

```json
{
  "format": "json",
  "id": 1114,
  "created_at": "2009-03-10T10:12:16Z",
  "updated_at": "2013-02-04T13:24:15Z",
  "latitude": "34.531617284782",
  "longitude": "69.13581752939456",
  "street": "Taimani, behind Qasemi Winhouse",
  "zip": "",
  "city": "Kabul",
  "country": "Afghanistan",
  "title": "Skateistan Afghanistan",
  "description": "With 68% of Afghanistan’s population under the age of 25, Skateistan strongly believes that youth are the ones most capable of bringing about social change.\n\nSkateistan is an Afghan NGO which operates Afghanistan’s (and the world’s) first co-educational skateboarding school. The Skateistan school engages nearly 400 Kabul youth weekly through skateboarding, and provides them with new opportunities in cross-cultural interaction, education, and personal empowerment programs. \n\nThe students (ages 5-17) come from all of Afghanistan’s diverse ethnic and socioeconomic backgrounds, and include 40% female students, hundreds of streetworking children, and youth with disabilities. They develop skills in skateboarding, leadership, problem-solving, multimedia, and creative arts. The students themselves decide what they want to learn; we connect them with a safe space and opportunities for them to develop the skills that they consider important.\n\nFor Afghan girls Skateistan's programming is especially important as there are very few recreational opportunities for females. For example, it is not culturally acceptable for girls in Afghanistan to ride bicycles or play sports in public. \n\nSkateistan has been active in Kabul since 2007 - with our facility built in 2009 - and in that time we’ve seen that Afghan youth of all ethnicities, genders, and socioeconomic backgrounds love to skateboard. Skateistan brings them together, equipping young men and women to lead their communities toward social change and development.\n\nIn 2012 Skateistan will be opening its second Afghan facility in Mazar-e-Sharif, Northern Afghanistan. It will have space to teach up to 1000 youth weekly.\n\nOur program gives hundreds of oppressed youth a voice. Education and the opportunity for self-expression can break the cycles of poverty, illiteracy and exclusion, with sport paving the way.",
  "tax_deductible": true,
  "outstanding_amount_in_cents": 19086,
  "positive_opinions_with_donations_count": 357,
  "positive_opinions_without_donations_count": 17,
  "negative_opinions_count": 1,
  "number_of_all_unique_supporters": 282,
  "progress_percentage": 99,
  "incomplete_need_count": 3,
  "completed_need_count": 70,
  "news_count": 52,
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
      "rel": "blog_posts",
      "href": "http://www.betterplace.dev/en/api_v4/projects/1114/blog_posts.json"
    }
  ]
}
```

