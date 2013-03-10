
# Volunteering List

```nginx
GET http://betterplace.dev/en/api_v4/volunteering.json?nelat=51.123&nelng=12.123&order=created_at%3AASC&q=Homework+help&scope=location&swlat=51.001&swlng=12.001
```

A list of betterplace.org volunteering offers (donate time).
Results are contains in a *data* attribute.


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
    <td>Specify how the search-query <code>q</code> should behave:
<ul>
<li>"no scope" (default) performs a full text search
<li><code>human_name</code> searches only on the contact-person-fullname and carrier-fullname.
Use this to get all volunteering offers by "Unicef" or by "Till Behnke".
<li><code>location</code> does a reverse geocoding lookup and shows results based on the
lookup-bounding-box or a default-radius of 30 km.
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
    <td>Order the result by <code>rank</code> (default), <code>id</code>, <code>progress_percentage</code>,
<code>completed</code>, <code>tax_deductible</code>, <code>created_at</code>, <code>updated_at</code>,
<code>last_donation_at</code>.
Use the optional <code>ASC</code> (default) or <code>DESC</code>.
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

## Response Parameter

*TODO*

## Response Example

```json
{
  "total_entries": 6678,
  "offset": 3,
  "total_pages": 2226,
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
      "vacancies": 1,
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
      "vacancies": 1,
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
      "vacancies": 1,
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

