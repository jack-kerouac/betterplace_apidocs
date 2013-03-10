
# Volunteering Details

```nginx
GET http://betterplace.dev/en/api_v4/volunteering/23.json
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

## Response Parameter

*TODO*

## Response Example

```json
{
  "format": "json",
  "id": 1,
  "created_at": "2013-01-28T09:23:06Z",
  "updated_at": "2013-01-28T13:12:29Z",
  "latitude": 51.4971,
  "longitude": 9.38605,
  "street": "Poppenhäuser Weg 3",
  "zip": "34369",
  "city": "Hofgeismar",
  "country": "Germany",
  "title": "Sonntagsessen kochen im \"Kanapee\"",
  "description": "<p>Von Oktober bis Ende März bietet der Tagestreff Kanapee jeden Sonntag in der Zeit von 11.00 Uhr bis 14.00 Uhr ein warmes Essen an, das von ehrenamtlichen Helfern zubereitet wird. Von April bis Ende September findet dieses Angebot jeden 3. Sonntag im Monat statt. Dafür werden Freiwillige gesucht!</p>\n\n\n<ul><li>Unfallversicherung</li><li>kostenlose Verpflegung</li><li>kostenlose Ausflüge</li><li>Haftpflichtversicherung</li><li>Anleitung durch Fachkräfte</li></ul>",
  "carrier": {
    "name": "Fachberatungsstelle \"Kanapee\" der Fachberatungsstelle Wohnen",
    "links": [

    ]
  },
  "vacancies": 1,
  "contact": {
    "name": "Sabine Soldan",
    "phone": "05671-797",
    "email": "kanapee.hog@ekkw.de"
  },
  "topics": [

  ],
  "activities": [

  ],
  "imported_from": "aktion_mensch",
  "links": [
    {
      "rel": "self",
      "href": "http://www.betterplace.dev/en/api_v4/volunteering/1.json"
    },
    {
      "rel": "platform",
      "href": "http://www.betterplace.dev/en/volunteering/1-sonntagsessen-kochen-im-kanapee"
    }
  ]
}
```

