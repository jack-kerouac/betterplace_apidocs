
# Client project-tag projects list

```nginx
GET https://www.betterplace.org/en/api_v4/clients/Volksfreund/project_tags/Ernaehrung/projects.json
```

**For [betterplace.org clients](../README.md#client-api) only:**

This API returns all incomplete projects to a client project-tag.
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
    <td>Link to <a href="../opinions_list.md">opinion list</a>
</td>
  </tr>
  <tr>
    <th>pictures</th>
    <td>Link to <a href="../picture_list.md">project picture list</a>
</td>
  </tr>
  <tr>
    <th>needs</th>
    <td>Link to <a href="../needs_list.md">project need list</a>
</td>
  </tr>
  <tr>
    <th>blog_posts</th>
    <td>Link to <a href="../blog_posts_list.md">blog post list</a>
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
      "id": 10745,
      "created_at": "2012-09-04T07:48:34Z",
      "updated_at": "2013-03-18T11:03:11Z",
      "latitude": 34.733879,
      "longitude": 36.71817,
      "city": "Homs",
      "country": "Syrian Arab Republic",
      "title": "Christen in Homs / Syrien! - Sie warten auf Hilfe",
      "description": "Unsere Projektnummer: 10745- Die IGFM–Wittlich, mit ihrer Vorsitzenden Katrin Bornmüller, unterstützt die Christen in Homs in Syrien. Sie sind unverschuldet zwischen die Fronten des alten und noch immer starken Regimes der Alawiten unter Führung des Präsidenten Assad und den Aufständischen – meist sunnitischen Muslimen - geraten.<br /><br />Bald nachdem am 15. März 2011 eine kleine Demonstration die Unruhen in Syrien auslösten, brach auch in Homs der Widerstand gegen das Regime aus.  Diese Groß- und Industriestadt, mit etwa 1 Mill. Einwohner, liegt auf halbem Weg zwischen den Zentren Damaskus und Aleppo. Sie hatte etwa 10% Christen verschiedener Konfessionen. In der Innenstadt waren 10 Kirchen. Alle sind inzwischen stark beschädigt – manche bis zur Unbrauchbarkeit. Die Aufständischen hatten sich besonders in den christlichen Stadtteilen verschanzt, die dann extrem stark beschossen wurden. Viele Einwohner aller Religionen sind geflüchtet. Auch Priester und Bischöfe haben die Stadt verlassen. Schulen und die Universität sind schon viele Monate geschlossen. Die Bewohner haben ihre Arbeitsplätze und damit ihr Einkommen verloren. Viele Wohnungen sind unbrauchbar, andere besetzt.<br /><br />Die IGFM hält Kontakt zu zwei Jesuitenpatres. Sie hatten eigene Gemeinden in der Innenstadt und führten vor den Toren von Homs das landwirtschaftliches Projekt Al Ard – die Erde - in dem Behinderte betreut wurden. Die Jesuiten wollen Homs nicht den Rücken kehren und versuchen denen zu helfen, die nicht fortgehen konnten oder wollten – gleich welcher Religion. Obwohl ihr Pfarrhaus beschädigt ist, haben sie dort 50 Obdachlose aufgenommen und 200 in den Gebäuden von Al Ard. Für Kinder versuchen sie Schulunterricht zu organisieren.<br /><br />Es ist unvorstellbar schwer Lebensmittel und Medikamente in die Stadt hinein zu bekommen. Die Preise sind gewaltig gestiegen. Ersparnisse sind verbraucht. Die IGFM hat einen Weg erprobt Geld direkt in die Hände der Jesuiten zu bringen und die Kommunikation aufrecht zu halten.<br /><br />Ihre Hilfe kommt an!",
      "tax_deductible": true,
      "open_amount_in_cents": 0,
      "positive_opinions_count": 28,
      "negative_opinions_count": 0,
      "donor_count": 21,
      "progress_percentage": 100,
      "incomplete_need_count": 0,
      "completed_need_count": 1,
      "blog_post_count": 2,
      "contact": {
        "name": "K. Bornmüller",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/166/874/original_JHV_2009_004.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/874/big_JHV_2009_004.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/874/profile_JHV_2009_004.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/874/thumb_JHV_2009_004.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "https://www.betterplace.org/en/users/katrin_b13"
          }
        ]
      },
      "carrier": {
        "name": "Internationale Gesellschaft für Menschenrechte",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/166/879/original_IGFM_Logo_blau_R32_G90_B165.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/879/big_IGFM_Logo_blau_R32_G90_B165.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/879/profile_IGFM_Logo_blau_R32_G90_B165.png"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/879/thumb_IGFM_Logo_blau_R32_G90_B165.png"
            }
          ]
        },
        "links": [
          {
            "rel": "self",
            "href": "https://www.betterplace.org/en/api_v4/organisations/4621.json"
          }
        ]
      },
      "profile_picture": {
        "links": [
          {
            "rel": "original",
            "href": "http://www.betterplace.org/paperclip/000/290/036/original_Syrien32sp8-12.jpg"
          },
          {
            "rel": "large_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/290/036/big_Syrien32sp8-12.png"
          },
          {
            "rel": "profile_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/290/036/profile_Syrien32sp8-12.jpg"
          },
          {
            "rel": "thumb_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/290/036/thumb_Syrien32sp8-12.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/projects/10745.json"
        },
        {
          "rel": "platform",
          "href": "https://www.betterplace.org/en/projects/10745-christen-in-homs-syrien-sie-warten-auf-hilfe"
        },
        {
          "rel": "opinions",
          "href": "https://www.betterplace.org/en/api_v4/projects/10745/opinions.json"
        },
        {
          "rel": "pictures",
          "href": "https://www.betterplace.org/en/api_v4/projects/10745/pictures.json"
        },
        {
          "rel": "needs",
          "href": "https://www.betterplace.org/en/api_v4/projects/10745/needs.json"
        },
        {
          "rel": "blog_posts",
          "href": "https://www.betterplace.org/en/api_v4/projects/10745/blog_posts.json"
        }
      ]
    },
    {
      "id": 12431,
      "created_at": "2013-02-20T07:40:37Z",
      "updated_at": "2013-03-18T11:02:43Z",
      "latitude": 56.969664,
      "longitude": 23.15319,
      "street": "",
      "zip": "",
      "city": "Tukums",
      "country": "Latvia",
      "title": "IGFM-Hilfstransporte für Lettland",
      "description": "Unsere Projektnummer: 12431 - Sorgenfreies Leben von 70 € Rente, 200 € Durchschnittseinkommen von einem Viertel der Bevölkerung – aber Lebenshaltungskosten wie bei uns?<br /><br />Der Ombudsmann Lettlands bestätigte in einem Schreiben im November vergangenen Jahres, was viele arme lettische Bürger der Arbeitsgruppe Wittlich der Internationalen Gesellschaft für Menschenrechte schon seit Jahren schreiben. Lettland ist seit 2004 Mitglied der EU, aber den Anschluss an Europa hat Litauen verloren. 70% der Bevölkerung leben in bitterster Armut. Nach offiziellen Angaben liegt die Arbeitslosenquote in Lettland bei 15,9%. Diese Zahl trügt, denn Arbeitslose, die länger als ein Jahr ohne Beschäftigung sind, werden als solche nicht mehr geführt. Eine Grundsicherung wie etwa in Deutschland gibt es nicht. Offiziell garantiert  der lettische Staat eine kostenfreie medizinische Versorgung, doch wird der Patient nahezu immer eine „freiwillige Spende“ abverlangt. Die Versorgung in den Krankenhäusern ist katastrophal, es fehlt an allem, um die Kranken anständig versorgen zu können.<br /><br />Die Internationale Gesellschaft für Menschenrechte IGFM – Wittlich mit ihrer Vorsitzenden Katrin Bornmüller organisiert seit 1990 Hilfsgütertransporte mittels Sattelschleppern. Vor kurzem wurde sogar ein Traktor befördert, um arbeitslosen Menschen eine Chance zu geben, im Wald zu arbeiten. Auch 50 Krankenhausbetten und viele medizinische Geräte kamen so in lettische Krankenhäuser. Zuverlässiger Partner ist die IGFM-Sektion, gegründet und geführt von Peteris Lazda, ehemaliger Dissident, politischer Gefangener in der Sowjetunion, Opfer eines Vergiftungsversuchs durch den KGB. Sie hat ein Lager, in dem die Hilfsgüter sortiert werden. Die Leute kommen zu festen Ausgabezeiten und erhalten Kleidung, Schuhe und die notwendigsten Dinge für den Haushalt. Die Empfänger müssen einen Bedürftigkeitsnachweis haben. Jeder wird auf einer Liste eingetragen und muss den Empfang der Güter mit seiner Unterschrift bestätigen.<br /><br />Auch Sie können helfen. In diesem Jahr sollen noch fünf Transporte nach Lettland geschickt werden, die Spritpreise jedoch diktieren mehr und mehr die Möglichkeiten. Allein die Transportkosten betragen ca. 2.200 €. Schließlich sollen auch Lebensmittelpakete gepackt und Medikamente gekauft werden. Jede Spende hilft!",
      "tax_deductible": true,
      "open_amount_in_cents": 0,
      "positive_opinions_count": 17,
      "negative_opinions_count": 0,
      "donor_count": 15,
      "progress_percentage": 100,
      "incomplete_need_count": 0,
      "completed_need_count": 1,
      "blog_post_count": 1,
      "contact": {
        "name": "K. Bornmüller",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/166/874/original_JHV_2009_004.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/874/big_JHV_2009_004.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/874/profile_JHV_2009_004.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/874/thumb_JHV_2009_004.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "https://www.betterplace.org/en/users/katrin_b13"
          }
        ]
      },
      "carrier": {
        "name": "Internationale Gesellschaft für Menschenrechte",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "http://www.betterplace.org/paperclip/000/166/879/original_IGFM_Logo_blau_R32_G90_B165.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/879/big_IGFM_Logo_blau_R32_G90_B165.png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/879/profile_IGFM_Logo_blau_R32_G90_B165.png"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "http://www.betterplace.org/paperclip/000/166/879/thumb_IGFM_Logo_blau_R32_G90_B165.png"
            }
          ]
        },
        "links": [
          {
            "rel": "self",
            "href": "https://www.betterplace.org/en/api_v4/organisations/4621.json"
          }
        ]
      },
      "profile_picture": {
        "links": [
          {
            "rel": "original",
            "href": "http://www.betterplace.org/paperclip/000/303/274/original_LV-Ausladen.jpg"
          },
          {
            "rel": "large_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/303/274/big_LV-Ausladen.png"
          },
          {
            "rel": "profile_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/303/274/profile_LV-Ausladen.jpg"
          },
          {
            "rel": "thumb_attention_deprecated",
            "href": "http://www.betterplace.org/paperclip/000/303/274/thumb_LV-Ausladen.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "https://www.betterplace.org/en/api_v4/projects/12431.json"
        },
        {
          "rel": "platform",
          "href": "https://www.betterplace.org/en/projects/12431-igfm-hilfstransporte-fur-lettland"
        },
        {
          "rel": "opinions",
          "href": "https://www.betterplace.org/en/api_v4/projects/12431/opinions.json"
        },
        {
          "rel": "pictures",
          "href": "https://www.betterplace.org/en/api_v4/projects/12431/pictures.json"
        },
        {
          "rel": "needs",
          "href": "https://www.betterplace.org/en/api_v4/projects/12431/needs.json"
        },
        {
          "rel": "blog_posts",
          "href": "https://www.betterplace.org/en/api_v4/projects/12431/blog_posts.json"
        }
      ]
    }
  ]
}
```

