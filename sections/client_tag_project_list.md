
# Client project-tag project list

```nginx
GET https://www.betterplace.org/en/api_v4/clients/Volksfreund/tags/Ernaehrung/projects.json
```

**For [betterplace.org clients](../README.md#client-api) only:**

This API returns all projects to a client project-tag.
Client project tags are a custom client feature and andministered
as a service of [betterplace solutions](http://www.betterplace-solutions.de/#buergerzeitung).

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
    <th>client_id</th>
    <td><code>Volksfreund</code></td>
    <td>required</td>
    <td>The betterplace.org-internal client permalink</td>
  </tr>
  <tr>
    <th>id</th>
    <td><code>Ernaehrung</code></td>
    <td>required</td>
    <td>The name of the client project-tag – a list of tags is provided by
<a href="http://www.betterplace-solutions.de/#buergerzeitung">betterplace solutions</a>.
</td>
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
    <td>Link to <a href="../opinion_list.md">opinion list</a>
</td>
  </tr>
  <tr>
    <th>pictures</th>
    <td>Link to <a href="../picture_list.md">project picture list</a>
</td>
  </tr>
  <tr>
    <th>needs</th>
    <td>Link to <a href="../need_list.md">project need list</a>
</td>
  </tr>
  <tr>
    <th>blog_posts</th>
    <td>Link to <a href="../blog_post_list.md">blog post list</a>
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
    <td>Large size – ATTENTION, this feature is DEPRICATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>profile_picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>profile_picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRICATED. See above.</td>
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
    <td>Large size – ATTENTION, this feature is DEPRICATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>profile_picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>profile_picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>profile_picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>profile_picture.large_attention_deprecated</th>
    <td>Large size – ATTENTION, this feature is DEPRICATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>profile_picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>profile_picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": 9,
  "offset": 0,
  "total_pages": 5,
  "current_page": 1,
  "per_page": 2,
  "data": [
    {
      "id": 6270,
      "created_at": "2011-03-01T22:06:55Z",
      "updated_at": "2012-09-13T00:12:12Z",
      "latitude": 49.7577018737793,
      "longitude": 6.64428997039795,
      "street": "Sichelstr. 36",
      "zip": "54290",
      "city": "Trier",
      "country": "Germany",
      "title": "Frühstück für Obdachlose und sozial Benachteiligte",
      "description": "Unsere Projektnummer: 6270 - Der Arbeitskreis für Obdachlose und sozial Benachteiligte (AKOS) wurde 1995 von Trierer Studierenden gegründet. In der Diskussion mit den an der Hilfe beteiligten Behörden und Institutionen wurde deutlich, dass die materielle Versorgung in Trier mit Geld, Nahrungsmitteln, usw. als gut bezeichnet werden kann. Diese offizielle Versorgung mit materiellen Gütern ist jedoch zumeist nicht darauf gerichtet, die Menschen im psycho-sozialen Bereich zu unterstützen. <br /><br />An dieser Stelle setzt die ehrenamtliche Tätigkeit des AKOS an. Wir bieten jeden Samstag von 7 bis 10 Uhr ein leckeres Büffet an. Das Frühstück ist ein neutraler Ort. Hier treffen sich keine Bettler oder Schnorrer, sondern Menschen, die Hunger haben. Aber die meisten unseren Gäste kommen nicht nur wegen des Essens, sondern vor allem wegen der Gesellschaft. Wir haben ein offenes Ohr für unsere Gäste, die jemanden zum zuhören brauchen, Rat suchen oder einfach ein bisschen plaudern wollen. Gespräche werden nicht von Stehendem zu Sitzendem, von oben herab, von Normalbürger zu Außenseiter geführt, sondern von Kaffeetrinker zu Brötchenesser. Es werden ganz normale \"Frühstücksgespräche\" geführt!<br /><br /><br />Es gibt Leute mit alter Kleidung, die in unserer Kleiderkammer nach etwas Neuem suchen. Andere haben sich extra für den Samstag rausgeputzt. SpätaussiedlerInnen, Studierende, junge Mütter mit ihren Kindern sind genauso Gast wie Trierer Urgesteine oder Durchreisende. Es gibt die ewigen Nörgler, wie die immer Lachenden, denen kein Unglück den Tag verderben kann. Das Spektrum der Gäste ist groß. <br /><br />Wir sind keine Institution, die Obdachlose oder soziale Härtefälle betreuen. Wir haben nicht den Anspruch, jemanden auf den \"richtigen Weg\" zu bringen - aber wenn wir gut zusammen frühstücken und miteinander sprechen, dann wird das vielleicht auch ein Stückchen weniger notwendig.<br /><br />Unser Frühstücksangebot ist für jeden offen, die Zahl unserer Gäste schwankt zwischen 30 und 50. Unsere ehrenamtlichen HelferInnen sind genau so unterschiedlich wie unsere Frühstücksgäste: es gibt junge und ältere, Studierende und Arbeitstätige. Aktiv sind derzeit ca. 20 HelferInnen, wobei pro Frühstück 3 bis 7 HelferInnen anwesend sind.<br /><br />Ein herzliches Dankeschön auch an unsere großzügigen Sachspender, die uns jede Woche mit Nahrungsmitteln unterstützen: Bäckerei Kirwald, Fleischerei Tyszak, Trierer Tafel, F. G. Wallner e.K Eier Butter Käse Großhandel sowie die KHG Trier, die uns die Räume zur Verfügung stellt.<br /><br />Leider zeigt unsere Küchenausstattung nach all den Jahren einige Abnutzungserscheinungen und daher würden wir gern einige Gegenstände ersetzen, die einerseits dringend benötigt werden (z.B. neue Kaffeemaschinen) und andererseits gern einige Neuanschaffungen tätigen, um das Frühstück noch einladender zu gestalten (z.B. Wärmesuppentopf, um im Winter  etwas warmes anbieten zu können).",
      "tax_deductible": true,
      "open_amount_in_cents": -10000,
      "positive_opinions_count": 22,
      "negative_opinions_count": 0,
      "donor_count": 18,
      "progress_percentage": 112,
      "incomplete_need_count": 0,
      "completed_need_count": 5,
      "blog_post_count": 7,
      "contact": {
        "name": "Anja H.",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/303/789/original_akos.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/303/789/big_akos.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/303/789/profile_akos.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/303/789/thumb_akos.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "https://www.betterplace.org/en/users/katharina_b13"
          }
        ]
      },
      "carrier": {
        "name": "AKOS",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/216/500/original_logo.gif"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/216/500/big_logo.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/216/500/profile_logo.png"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/216/500/thumb_logo.png"
            }
          ]
        },
        "links": [
          {
            "rel": "self",
            "href": "https://www.betterplace.org/en/api_v4/organisations/6396.json"
          }
        ]
      },
      "profile_picture": {
        "links": [
          {
            "rel": "original",
            "href": "http://www.betterplace.org/paperclip/000/216/488/original_profilbild.JPG"
          },
          {
            "rel": "large_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/216/488/big_profilbild.png"
          },
          {
            "rel": "profile_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/216/488/profile_profilbild.jpg"
          },
          {
            "rel": "thumb_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/216/488/thumb_profilbild.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/projects/6270.json"
        },
        {
          "rel": "platform",
          "href": "https://www.betterplace.org/en/projects/6270-fruhstuck-fur-obdachlose-und-sozial-benachteiligte"
        },
        {
          "rel": "opinions",
          "href": "https://www.betterplace.org/en/api_v4/projects/6270/opinions.json"
        },
        {
          "rel": "pictures",
          "href": "https://www.betterplace.org/en/api_v4/projects/6270/pictures.json"
        },
        {
          "rel": "needs",
          "href": "https://www.betterplace.org/en/api_v4/projects/6270/needs.json"
        },
        {
          "rel": "blog_posts",
          "href": "https://www.betterplace.org/en/api_v4/projects/6270/blog_posts.json"
        }
      ]
    },
    {
      "id": 7559,
      "created_at": "2011-08-29T19:19:36Z",
      "updated_at": "2012-09-13T00:14:52Z",
      "latitude": -3.36160039901733,
      "longitude": 36.68631362915039,
      "street": "Mianzini Road",
      "city": "Arusha",
      "country": "Tanzania",
      "title": "Unterstützen Sie Kinder & Maasaifrauen in Tansania",
      "description": "Unsere Projektnummer: 7559 - Mama Hindu ist Gründerin, treibende Kraft und gute Seele des \"Centre for Women and Children Development\" (CWCD) im tansanischen Arusha. Seit nunmehr 15 Jahren setzt Mama Hindu all ihre Zeit und Energie für in Not geratene Frauen, Kinder und Jugendliche ein. Durch das CWCD ermöglicht sie den Unterprivilegierten in der Region Arusha durch Zuwendung, Bildung und Aufklärung eine echte Zukunftsperspektive. <br /><br />Das Engagement des CWCD erstreckt sich auf unterschiedliche Bereiche, die sich im Wesentlichen mit den Themen Bildung, Aufklärung, Emanzipation und Hilfe gegen Hunger und Armut auseinandersetzen. Ein Schwerpunkt des CWCD ist eine Schule mit Kindergarten für unterprivilegierte Kinder. <br /><br />Weiterhin unterstützt und betreibt das CWCD zahlreiche Projekte in Maasai-Dörfern in der unmittelbaren Umgebung von Arusha, um den Schwachen in der tansanischen Gesellschaft Werkzeuge für die Hilfe zur Selbsthilfe an die Hand zu geben. Die Schwachen sind in erster Linie Waisen oder Halbwaisen, Witwen und allein gelassene Ehefrauen, deren gesellschaftlicher Status oft ein Leben in Armut bedeutet.<br /><br />Mama Hindu ist auch Namensgeberin unseres 2010 gegründeten Fördervereins, der sich der effektiven Unterstützung des CWCD verschrieben hat. Gesammelte Spenden leiten wir direkt und zweckgebunden an das CWCD weiter, wobei regelmäßige Besuche des Vereinsvorstandes vor Ort (selbstverständlich privat finanziert) die Ermittlung von Fortschritten und aktuellem Bedarf sicherstellen.<br /><br />Der Förderverein in Deutschland ist stark mit der Region Trier verbunden. Viele engagierte Mitglieder des Vereins sind wohnhaft in Trier, darunter auch die zweite Vorsitzende Julia Scherer. Zudem besteht eine Partnerschaft zwischen dem Kindergarten „Spatzennest“ in Trier und dem Kindergarten der Waisenschule. Auch unterstützt die Universität Trier das CWCD schon seit mehreren Jahren durch verschiedene Projekte.",
      "tax_deductible": true,
      "open_amount_in_cents": 0,
      "positive_opinions_count": 24,
      "negative_opinions_count": 0,
      "donor_count": 17,
      "progress_percentage": 100,
      "incomplete_need_count": 0,
      "completed_need_count": 7,
      "blog_post_count": 3,
      "contact": {
        "name": "J. Scherer",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/260/996/original_jule%20und%20mama%20hindu.JPG"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/260/996/big_jule%20und%20mama%20hindu.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/260/996/profile_jule%20und%20mama%20hindu.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/260/996/thumb_jule%20und%20mama%20hindu.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "https://www.betterplace.org/en/users/julia_s42"
          }
        ]
      },
      "carrier": {
        "name": "Mama Hindu e.V. - Förderverein des CWCD",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/261/143/original_logo_MH_1a.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/261/143/big_logo_MH_1a.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/261/143/profile_logo_MH_1a.png"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/261/143/thumb_logo_MH_1a.png"
            }
          ]
        },
        "links": [
          {
            "rel": "self",
            "href": "https://www.betterplace.org/en/api_v4/organisations/8354.json"
          }
        ]
      },
      "profile_picture": {
        "links": [
          {
            "rel": "original",
            "href": "http://www.betterplace.org/paperclip/000/260/995/original_IMG_1562.JPG"
          },
          {
            "rel": "large_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/260/995/big_IMG_1562.png"
          },
          {
            "rel": "profile_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/260/995/profile_IMG_1562.jpg"
          },
          {
            "rel": "thumb_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/260/995/thumb_IMG_1562.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/projects/7559.json"
        },
        {
          "rel": "platform",
          "href": "https://www.betterplace.org/en/projects/7559-unterstutzen-sie-kinder-maasaifrauen-in-tansania"
        },
        {
          "rel": "opinions",
          "href": "https://www.betterplace.org/en/api_v4/projects/7559/opinions.json"
        },
        {
          "rel": "pictures",
          "href": "https://www.betterplace.org/en/api_v4/projects/7559/pictures.json"
        },
        {
          "rel": "needs",
          "href": "https://www.betterplace.org/en/api_v4/projects/7559/needs.json"
        },
        {
          "rel": "blog_posts",
          "href": "https://www.betterplace.org/en/api_v4/projects/7559/blog_posts.json"
        }
      ]
    }
  ]
}
```

