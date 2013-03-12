
# Volunteering Details ⇄ [List](volunteering_list.md)

```nginx
GET https://betterplace.org/en/api_v4/volunteering/23.json
```

The details of a betterplace.org volunteering offer (donate time).

*For [betterplace.org clients](README.md#client-api):*
This ressource is not avaliable at the moment.


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
    <td><code>23</code></td>
    <td>required</td>
    <td>Volunteering-id as an integer number ≥ 1.</td>
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
    <td>null &#124; string</td>
    <td>"1994-11-05T13:15:30Z"</td>
    <td>DateTime (ISO8601 with Timezone)</td>
  </tr>
  <tr>
    <th>updated_at</th>
    <td>null &#124; string</td>
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
    <td>Where the volunteering takes place</td>
  </tr>
  <tr>
    <th>zip</th>
    <td>null &#124; string</td>
    <td>"10997"</td>
    <td>Where the volunteering takes place</td>
  </tr>
  <tr>
    <th>city</th>
    <td>null &#124; string</td>
    <td>"Berlin"</td>
    <td>Where the volunteering takes place</td>
  </tr>
  <tr>
    <th>country</th>
    <td>null &#124; string</td>
    <td>"Deutschland"</td>
    <td>Where the volunteering takes place, translated to the requested language</td>
  </tr>
  <tr>
    <th>title</th>
    <td>string</td>
    <td>TODO</td>
    <td>Max 100 character unless the volunteering is imported</td>
  </tr>
  <tr>
    <th>description</th>
    <td>string</td>
    <td>TODO</td>
    <td>TODO</td>
  </tr>
  <tr>
    <th>carrier.name</th>
    <td>string</td>
    <td>"Viva con Agua de Sankt Pauli e.V."</td>
    <td>An organisation name, Users will be added later</td>
  </tr>
  <tr>
    <th>carrier.street</th>
    <td>string</td>
    <td>"Rosenstr. 3"</td>
    <td>The street of the organisation contact address</td>
  </tr>
  <tr>
    <th>carrier.city</th>
    <td>string</td>
    <td>"Berlin"</td>
    <td>The city of the organisation contact address</td>
  </tr>
  <tr>
    <th>carrier.zip</th>
    <td>string</td>
    <td>"10123"</td>
    <td>The zip code of the organisation contact address</td>
  </tr>
  <tr>
    <th>carrier.country</th>
    <td>string</td>
    <td>"Germany"</td>
    <td>The country of the organisation contact address</td>
  </tr>
  <tr>
    <th>vacancies</th>
    <td>number</td>
    <td>1</td>
    <td>The number of volunteers that are needed, provided by the manager</td>
  </tr>
  <tr>
    <th>image.description</th>
    <td>string</td>
    <td></td>
    <td>Image description</td>
  </tr>
  <tr>
    <th>contact.name</th>
    <td>string</td>
    <td>Till Behnke</td>
    <td>Fullname of the contact person.
For imported volunteering offers, this is the
contact-name that is provided on import.
</td>
  </tr>
  <tr>
    <th>contact.phone</th>
    <td>string</td>
    <td>030 - 7676 4488 44</td>
    <td>Phone number for direct contact.
No validations on input apply.
</td>
  </tr>
  <tr>
    <th>contact.email</th>
    <td>string</td>
    <td>change@betterplace.org</td>
    <td>Plain text email-address for direct contact
</td>
  </tr>
  <tr>
    <th>topics</th>
    <td>array</td>
    <td>["Development cooperation", "Children & youth"]</td>
    <td>Up to 4 categories that describe, what for which causes you need volunteers.
Results are translated to the requested language.
Possible results: "Animal & environment protection", "Culture & sports",
"Children & youth", "Development cooperation ", "DisabledEducation", "Elderly people",
"Human rights", "Immigrants", "Invalid", "Local help", "Socially deprived"
</td>
  </tr>
  <tr>
    <th>activities</th>
    <td>array &#124; null</td>
    <td>["consulting/coaching", "office work"]</td>
    <td>Up to 4 categories that describe, what for which causes you need volunteers.
Results are translated to the requested language.
Possible results: "consulting/coaching", "crafting/gardening", "doing sports",
"doing the chores", "group care", "nursing/parenting", "office work",
"organising/managing", "painting/designing", "tutoring/reading",
"visiting/accompanying", "writing/translating"
</td>
  </tr>
  <tr>
    <th>imported_from</th>
    <td>string</td>
    <td>aktion_mensch</td>
    <td>Betterplace imports volunteering offers from Aktions Mensch.</td>
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
(<a href="../volunteering_details.md">volunteering details</a>)
</td>
  </tr>
  <tr>
    <th>platform</th>
    <td>Permalink to betterplace.org</td>
  </tr>
  <tr>
    <th>carrier.logo</th>
    <td>Thumbnail size</td>
  </tr>
  <tr>
    <th>image.thumb</th>
    <td>Thumbnail size</td>
  </tr>
  <tr>
    <th>image.medium</th>
    <td>Medium size</td>
  </tr>
</table>

## Response Example

```json
{
  "format": "json",
  "id": 23,
  "created_at": "2013-01-28T09:23:17Z",
  "updated_at": "2013-01-28T13:12:37Z",
  "title": "Essensausgabe/Fahrdienst",
  "description": "<p>Die Kasseler Tafel e.V. sammelt qualitativ einwandfreie Lebensmittel, die kurz vor dem Mindesthaltbarkeitsdatum stehen, bei Firmen in der Region ein und verteilt diese gegen einen symbolischen Betrag an bedürftige Mitbürgerinnen und Mitbürger.</p>\n<p>Freiwillige können sich in folgenden Bereichen bei der Kasseler Tafel betätigen:</p>\n<p>1. Lebensmittel sortieren und ausgeben</p>\n<p>2. als Fahrer: Abholung der Lebensmittel bei den Supermärkten</p>\n\n<p>Mehr Informationen finden Sie unter: http://kasseler-tafel.de/</p>\n<p>Wir freuen uns über Ihr Interesse! </p>\n\n<ul><li>Unfallversicherung</li><li>Haftpflichtversicherung</li><li>Anleitung durch Fachkräfte</li><li>Tätigkeitsnachweise</li><li>Ausstattung mit Medien / Arbeitsmaterialien</li></ul>",
  "carrier": {
    "format": "json",
    "name": "FreiwilligenZentrum Kassel",
    "street": "Spohrstraße 5",
    "city": "Kassel",
    "zip": "34117",
    "country": "Germany",
    "links": [

    ]
  },
  "vacancies": 1,
  "contact": {
    "format": "json",
    "name": "Frank Gerhold",
    "phone": "0561 - 10 24 25",
    "email": "info@freiwilligenzentrumkassel.de"
  },
  "topics": [

  ],
  "activities": [

  ],
  "imported_from": "aktion_mensch",
  "links": [
    {
      "rel": "self",
      "href": "http://www.betterplace.dev/en/api_v4/volunteering/23.json"
    },
    {
      "rel": "platform",
      "href": "http://www.betterplace.dev/en/volunteering/23-essensausgabe-fahrdienst"
    }
  ]
}
```

