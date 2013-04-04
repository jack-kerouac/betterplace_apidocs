
# Volunteering List ⇄ [Details](volunteering_details.md)

```nginx
GET https://api.betterplace.org/en/api_v4/volunteering.json?nelat=51.123&nelng=12.123&order=created_at%3AASC&q=Homework+help&scope=location&swlat=51.001&swlng=12.001
```

A list of betterplace.org volunteering offers (donate time).
Results are contains in a *data* attribute.

*For [betterplace.org clients](../README.md#client-api):*
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
    <th>scope</th>
    <td><code>location</code></td>
    <td>optional</td>
    <td>Use the scope to specify how the search-query <code>q</code> should behave:
<ul>
<li>"no scope" (default) performs a full text search
<li><code>human_name</code> searches only on the contact-person-fullname and carrier-fullname.
Use this to get all volunteering offers by "Unicef" or by "Till Behnke".
<li><code>location</code> does a reverse geocoding lookup
and shows results based on the lookup-bounding-box.
</ul>
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>q</th>
    <td><code>Homework help</code></td>
    <td>optional</td>
    <td>Search query. The searches behaviour is based on the scope.</td>
  </tr>
  <tr>
    <th>order</th>
    <td><code>created_at:ASC</code></td>
    <td>optional</td>
    <td>Order the result by <code>has_image</code> (default), <code>created_at</code> (second default).
Use the optional <code>ASC</code> (default) or <code>DESC</code>.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
<br>
The default order is the same as for the
<a href="http//www.betterplace.org/en/volunteering/list">betterplace.org volunteering list</a>:
<code>has_image:desc| carrier_has_image:desc| created_at:desc</code>
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
    <td>Contact data for the organisation</td>
  </tr>
  <tr>
    <th>carrier.city</th>
    <td>string</td>
    <td>"Berlin"</td>
    <td>Contact data for the organisation</td>
  </tr>
  <tr>
    <th>carrier.zip</th>
    <td>string</td>
    <td>"10123"</td>
    <td>Contact data for the organisation</td>
  </tr>
  <tr>
    <th>carrier.country</th>
    <td>string</td>
    <td>"Germany"</td>
    <td>Contact data for the organisation</td>
  </tr>
  <tr>
    <th>carrier.latitude</th>
    <td>number</td>
    <td>13.1234</td>
    <td>Contact data for the organisation</td>
  </tr>
  <tr>
    <th>carrier.longitude</th>
    <td>number</td>
    <td>54.123</td>
    <td>Contact data for the organisation</td>
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
  <tr>
    <th>contact.picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>contact.picture.large</th>
    <td>Large size</td>
  </tr>
  <tr>
    <th>contact.picture.profile</th>
    <td>Medium size</td>
  </tr>
  <tr>
    <th>contact.picture.thumb</th>
    <td>Thumbnail size</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 6679,
  "offset": 3,
  "total_pages": 2227,
  "current_page": 2,
  "per_page": 3,
  "data": [
    {
      "format": "json",
      "id": 4,
      "created_at": "2013-01-28T09:23:08Z",
      "updated_at": "2013-01-28T13:12:30Z",
      "latitude": 51.3171,
      "longitude": 9.49246,
      "street": "Rathaus Obere Königstrasse F 405 a 4. St.",
      "zip": "34117",
      "city": "Kassel",
      "country": "Germany",
      "title": "Betreuung & Begleitung im Rahmen des Betreuungsrechts",
      "description": "<p>eine Art \"ehrenamtlicher Anwalt\" sein; adminstrative Tätigkeiten: Unterstützung beim Ausfüllen von Formularen, Daueraufträge, Bankgeschäfte etc.; Behördengänge, wenn nötig Korrespondenzen mit Ämtern u.ä.; Gespräche führen, zuhören</p>\n\n<ul><li>Haftpflichtversicherung</li><li>Erfahrungsaustausch</li><li>Fortbildung/Qualifizierungsangebote</li><li>kostenlose Veranstaltungen</li></ul>",
      "carrier": {
        "format": "json",
        "name": "Betreuungsbehörde",
        "street": "Rathaus Obere Königstrasse F 405 a 4. St.",
        "city": "Kassel",
        "zip": "34117",
        "country": "Germany",
        "latitude": 51.3171,
        "longitude": 9.49246,
        "links": [

        ]
      },
      "vacancies": 1,
      "contact": {
        "format": "json",
        "name": "Heidi Schulz",
        "phone": "0561 / 787-5110",
        "email": "heidi.schulz@stadt-kassel.de"
      },
      "topics": [
        "Invalid",
        "Disabled"
      ],
      "activities": [

      ],
      "imported_from": "aktion_mensch",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/volunteering/4.json"
        },
        {
          "rel": "platform",
          "href": "http://www.betterplace.dev/en/volunteering/4-betreuung-begleitung-im-rahmen-des-betreuungsrechts"
        }
      ]
    },
    {
      "format": "json",
      "id": 5,
      "created_at": "2013-01-28T09:23:09Z",
      "updated_at": "2013-01-28T13:12:31Z",
      "title": "Patientenbesuchsdienst im Diakonissen- und Burgfeldkrankenhaus",
      "description": "<ul><li>Wir stellen den Menschen in den Mittelpunkt</li>\n    <li>Wir sind für die Patienten da</li>\n    <li>Wir begleiten Spaziergänge im Haus und draußen</li>\n    <li>Wir lesen vor aus \"Was ihr wollt\"</li>\n    <li>Wir erledigen Besorgungen</li>\n    <li>Wir bringen die Bücherei ans Bett</li>\n    <li>Wir gehen Kranken zur Hand</li>\n    <li>Wir hören zu, begleiten und betreuen</li>\n    <li>Wir helfen bei der Aufnahme ins Krankenhaus</li>\n</ul>\n\n<p>Jeder/r von uns arbeitet einen Tag pro Woche von 9:00 bis 12:00 Uhr auf einer Station. Wir treffen uns monatlich zu 2stündigen Themennachmittagen zum Gedanken- und Erfahrungsaustausch. Das Einsatzgebiet (Aufnahme, Pflege, Büchereidienst oder Dienst im Altenheim) kann nach Neigung gewählt werden.</p>\n<p>Bei all diesen Aufgaben sind wir durch das Krankenhaus pauschal unfallversichert.</p>\n<p>Es gibt einen monatlich festgelegten Einsatzplan.</p>\n<p>Wir freuen uns über Ihr Interesse und beantworten gern Ihre Fragen.</p>\n\n<ul><li>Unfallversicherung</li><li>Haftpflichtversicherung</li><li>regelmäßige Informationen</li><li>Erfahrungsaustausch</li><li>Fortbildung/Qualifizierungsangebote</li><li>Anleitung durch Fachkräfte</li><li>Tätigkeitsnachweise</li><li>kostenlose Verpflegung</li><li>kostenlose Veranstaltungen</li></ul>",
      "carrier": {
        "format": "json",
        "name": "FreiwilligenZentrum Kassel",
        "street": "Spohrstraße 5",
        "city": "Kassel",
        "zip": "34117",
        "country": "Germany",
        "latitude": 51.3171,
        "longitude": 9.49561,
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
        "Invalid",
        "Elderly people"
      ],
      "activities": [

      ],
      "imported_from": "aktion_mensch",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/volunteering/5.json"
        },
        {
          "rel": "platform",
          "href": "http://www.betterplace.dev/en/volunteering/5-patientenbesuchsdienst-im-diakonissen-und-burgfeldkrankenhaus"
        }
      ]
    },
    {
      "format": "json",
      "id": 6,
      "created_at": "2013-01-28T09:23:09Z",
      "updated_at": "2013-01-28T13:12:31Z",
      "latitude": 51.327,
      "longitude": 9.50938,
      "street": "Mönchebergstr. 41-43",
      "zip": "34125",
      "city": "Kassel",
      "country": "Germany",
      "title": "Blaue Helferin/ blauer Helfer - Besuchsdienst im Klinikum Kassel",
      "description": "<p>Sie geben Zeit, Aufmerksamkeit und Einfühlungsvermögen und bekommen Zufriedenheit und eine andere Sicht von Krankheit. Der Einsatzbereich der HelferInnen umfasst die Fürsorge um das persönliche Wohl der Kranken. Dazu gehören insbesondere die Zuwendung im Gespräch, kleine Einkäufe und Besorgungen, Begleitungen zu Untersuchungen und Spaziergänge, Vorlesen oder auch die Versorgung der Patienten mit Lesestoff mittels unseres fahrbaren Bücherwagens mit allen anfallenden Büchereiarbeiten. Wir unterhalten auch eine kleine Wäschekammer für bedürftige Patienten.</p>\n\n\n<p>Die Blauen Helferinnen suchen zur Verstärkung ihres ehrenamtlichen Teams im Klinikum Kassel aufgeschlossene Mitarbeiter, die Besuchsdienste am Krankenbett durchführen, für unsere Patientenbibliothek tätig sind oder den Lotsendienst unterstützen. Geboten werden u.a. Fortbildung, Versicherungsschutz während des Einsatzes und Fahrtkostenerstattungen. Wir arbeiten Sie in Ihre Aufgaben durch Gespräche und Begleitung umfassend ein.</p>\n<p>Suchworte: </p>\n<p>Krankenhaus, Krankenhausbesuchsdienst, Besuchsdienst, Besuch, Patient, vorlesen. Besorgung</p>\n\n<ul><li>Unfallversicherung</li><li>Tätigkeitsnachweise</li><li>kostenlose Nutzung weiterer Angebote</li><li>Haftpflichtversicherung</li><li>Fortbildung/Qualifizierungsangebote</li><li>Erstattung entstandener Kosten</li><li>Erfahrungsaustausch</li><li>Ausstattung mit Medien / Arbeitsmaterialien</li></ul>",
      "carrier": {
        "format": "json",
        "name": "Blaue Helferinnen und Blaue Helfer im Klinikum Kassel",
        "street": "Mönchebergstr. 41-43",
        "city": "Kassel",
        "zip": "34125",
        "country": "Germany",
        "latitude": 51.327,
        "longitude": 9.50941,
        "links": [

        ]
      },
      "vacancies": 1,
      "contact": {
        "format": "json",
        "name": "Elisabeth Meineke-Wolf",
        "phone": "0561-980-2675",
        "email": "meineke@klinikum-kassel.de"
      },
      "topics": [
        "Children & youth",
        "Invalid",
        "Elderly people"
      ],
      "activities": [

      ],
      "imported_from": "aktion_mensch",
      "links": [
        {
          "rel": "self",
          "href": "http://www.betterplace.dev/en/api_v4/volunteering/6.json"
        },
        {
          "rel": "platform",
          "href": "http://www.betterplace.dev/en/volunteering/6-blaue-helferin-blauer-helfer-besuchsdienst-im-klinikum-kassel"
        }
      ]
    }
  ]
}
```

