
# Client project-tag projects list

```nginx
GET https://api.betterplace.org/en/api_v4/clients/Volksfreund/project_tags/Trier/projects.json?facets=completed%3Afalse
```

**For [betterplace.org clients](../README.md#client-api) only:**

This API returns all projects to a client project-tag.
Client project tags are a custom client feature and administered
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
    <th align="left">client_id</th>
    <td><code>Volksfreund</code></td>
    <td>required</td>
    <td>The betterplace.org-internal client permalink</td>
  </tr>
  <tr>
    <th align="left">id</th>
    <td><code>Trier</code></td>
    <td>required</td>
    <td>The name of the client project-tag – a list of tags is provided by
<a href="http://www.betterplace-solutions.de/#buergerzeitung">betterplace solutions</a>.
</td>
  </tr>
  <tr>
    <th align="left">facets</th>
    <td><code>completed:false</code></td>
    <td>optional</td>
    <td>Filter the result set:
<code>facets=completed:true</code> / <code>false</code>
Ony completed/uncompleted projects (see progress_percentage-value).
Default is all projects.
</td>
  </tr>
</table>

## Response Attributes

### Root Attributes

  <table>
    <tr>
      <th>Attribute</th>
      <th>Types</th>
      <th>Example</th>
      <th>Description</th>
    </tr>
    <tr>
      <th align="left">id</th>
      <td>number</td>
      <td>4</td>
      <td>An integer number ≥ 1</td>
    </tr>
    <tr>
      <th align="left">created_at</th>
      <td>string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone)</td>
    </tr>
    <tr>
      <th align="left">updated_at</th>
      <td>string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone)</td>
    </tr>
    <tr>
      <th align="left">completed_at</th>
      <td>string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone) when the project was completed</td>
    </tr>
    <tr>
      <th align="left">latitude</th>
      <td>number</td>
      <td>52.499007</td>
      <td>Decimal degrees based on user input</td>
    </tr>
    <tr>
      <th align="left">longitude</th>
      <td>number</td>
      <td>13.44947</td>
      <td>Decimal degrees based on user input</td>
    </tr>
    <tr>
      <th align="left">street</th>
      <td>null &#124; string</td>
      <td>"Schlesische Straße 26"</td>
      <td>Where the project takes place</td>
    </tr>
    <tr>
      <th align="left">zip</th>
      <td>null &#124; string</td>
      <td>"10997"</td>
      <td>Where the project takes place</td>
    </tr>
    <tr>
      <th align="left">city</th>
      <td>null &#124; string</td>
      <td>"Berlin"</td>
      <td>Where the project takes place</td>
    </tr>
    <tr>
      <th align="left">country</th>
      <td>null &#124; string</td>
      <td>"Deutschland"</td>
      <td>Where the project takes place, translated to the requested language</td>
    </tr>
    <tr>
      <th align="left">title</th>
      <td>string</td>
      <td></td>
      <td>Max 50 character</td>
    </tr>
    <tr>
      <th align="left">description</th>
      <td>string</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th align="left">tax_deductible</th>
      <td>boolean</td>
      <td>true</td>
      <td>True if the project marked as tax deductible.
If so, Users can request a tax-receipt that can be used
with the german tax authorities.
[More about this](http://www.betterplace.org/c/hilfe/projekt-steuerlich-absetzbar/).
</td>
    </tr>
    <tr>
      <th align="left">donations_prohibited</th>
      <td>boolean</td>
      <td>false</td>
      <td>True if the project must not receive donations. This might happen if a tax-receipt
of german tax authorities rans out.
</td>
    </tr>
    <tr>
      <th align="left">open_amount_in_cents</th>
      <td>number</td>
      <td>12382</td>
      <td>How many cents are needed to complete the project</td>
    </tr>
    <tr>
      <th align="left">positive_opinions_count</th>
      <td>number</td>
      <td>13</td>
      <td>Number of positive opinions that are given to a project without a donation.
Those are plain opinions as well as visitor opinions.
</td>
    </tr>
    <tr>
      <th align="left">negative_opinions_count</th>
      <td>number</td>
      <td>0</td>
      <td>Number of *negative* opinions (usually 0) that are given to a project without a donation.
Those are plain opinions as well as visitor opinions.
Critical opinions are part of the betterplace.org
["Web of trust"](http://www.betterplace.org/c/hilfe/woran-erkenne-ich-dass-ein-projekt-vertrauenswurdig-ist/).
</td>
    </tr>
    <tr>
      <th align="left">donor_count</th>
      <td>number</td>
      <td>46</td>
      <td>Number of unique donors, based on the payment-email-address</td>
    </tr>
    <tr>
      <th align="left">progress_percentage</th>
      <td>number</td>
      <td>82</td>
      <td>% financed. Note: We have legacy projects with substantial
donation needs. This percentage includes those needs.
</td>
    </tr>
    <tr>
      <th align="left">incomplete_need_count</th>
      <td>number</td>
      <td>6</td>
      <td>Number of needs that still need donations</td>
    </tr>
    <tr>
      <th align="left">completed_need_count</th>
      <td>number</td>
      <td>12</td>
      <td>Number of completed needs</td>
    </tr>
    <tr>
      <th align="left">blog_post_count</th>
      <td>number</td>
      <td>8</td>
      <td>Number of blogposts (all types)</td>
    </tr>
    <tr>
        <th align="left" style="white-space: nowrap">
          <a name="contact-ref" href="#contact">
            ↓contact
          </a>
        </th>
      <td>object</td>
      <td>TODO</td>
      <td>The public face of the project / project manager</td>
    </tr>
    <tr>
        <th align="left" style="white-space: nowrap">
          <a name="carrier-ref" href="#carrier">
            ↓carrier
          </a>
        </th>
      <td>object</td>
      <td>TODO</td>
      <td>An organisation, Users will be added later</td>
    </tr>
    <tr>
      <th align="left">profile_picture</th>
      <td>null &#124; object</td>
      <td></td>
      <td>TODO</td>
    </tr>
    <tr>
        <th align="left" style="white-space: nowrap">
          <a name="active_matching_fund-ref" href="#active_matching_fund">
            ↓active_matching_fund
          </a>
        </th>
      <td>null &#124; object</td>
      <td>TODO</td>
      <td>TODO</td>
    </tr>
  </table>
### <a name="contact" href="#contact-ref">↑Nested Attributes: contact</a>

  <table>
    <tr>
      <th>Attribute</th>
      <th>Types</th>
      <th>Example</th>
      <th>Description</th>
    </tr>
    <tr>
      <th align="left">contact.name</th>
      <td>null &#124; string</td>
      <td>"Till B."</td>
      <td>Display name of a betterplace.org user.
Possible formats: "Till B.", "T. Behnke", "Till Behnke".
In the case of donation-opinions the name might also be anonymized
like "Payback User" or empty/null for anonymous donations.
</td>
    </tr>
    <tr>
      <th align="left">contact.picture</th>
      <td>string</td>
      <td>//assets.betterplace.org/…</td>
      <td>User profile picture or a fallback image</td>
    </tr>
  </table>
### <a name="carrier" href="#carrier-ref">↑Nested Attributes: carrier</a>

  <table>
    <tr>
      <th>Attribute</th>
      <th>Types</th>
      <th>Example</th>
      <th>Description</th>
    </tr>
    <tr>
      <th align="left">carrier.name</th>
      <td>string</td>
      <td>"Till B."</td>
      <td>The carrier can be an organisation or user.</td>
    </tr>
    <tr>
      <th align="left">carrier.picture</th>
      <td>string</td>
      <td>//assets.betterplace.org/…</td>
      <td>The organisation logo, user profile picture or a fallback image</td>
    </tr>
  </table>
### <a name="active_matching_fund" href="#active_matching_fund-ref">↑Nested Attributes: active_matching_fund</a>

  <table>
    <tr>
      <th>Attribute</th>
      <th>Types</th>
      <th>Example</th>
      <th>Description</th>
    </tr>
    <tr>
      <th align="left">active_matching_fund.id</th>
      <td>string</td>
      <td>53</td>
      <td>An integer number ≥ 1</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.created_at</th>
      <td>string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone)</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.updated_at</th>
      <td>string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone)</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.activated_at</th>
      <td>null &#124; string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone)</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.title</th>
      <td>string</td>
      <td>ACME Matching Everything</td>
      <td>Our matching fund's name</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.description</th>
      <td>string</td>
      <td>It's all about matching donations…</td>
      <td>The description of the matching fund</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.company_name</th>
      <td>string</td>
      <td>ACME</td>
      <td>The company that supports it</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.state</th>
      <td>string</td>
      <td>activated</td>
      <td>Current state of this matching fund: either activated or closed</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.logo_url</th>
      <td>string</td>
      <td>http://example.com/images/logo.png</td>
      <td>The URL of the logo image.</td>
    </tr>
  </table>
</table>

## Response Links

<table>
  <tr>
    <th>Linkname</th>
    <th>Description</th>
  </tr>

    <tr>
      <th align="left">self</th>
      <td>Link to this resource itself
(<a href="project_details.md">project details</a>)
</td>
    </tr>
    <tr>
      <th align="left">platform</th>
      <td>Permalink to betterplace.org</td>
    </tr>
    <tr>
      <th align="left">opinions</th>
      <td>Link to <a href="opinions_list.md">opinion list</a>
</td>
    </tr>
    <tr>
      <th align="left">pictures</th>
      <td>Link to <a href="picture_list.md">project picture list</a>
</td>
    </tr>
    <tr>
      <th align="left">needs</th>
      <td>Link to <a href="needs_list.md">project need list</a>
</td>
    </tr>
    <tr>
      <th align="left">blog_posts</th>
      <td>Link to <a href="blog_posts_list.md">blog post list</a>
</td>
    </tr>
    <tr>
      <th align="left">matching_funds</th>
      <td>Link to <a href="manager_details.md">matching funds list</a>
</td>
    </tr>
    <tr>
      <th align="left">contact.platform</th>
      <td>The user's profile on betterplace.org.
To view a user profile you have to be logged in.
This array is empty if the user has no useraccount
with betterplace.org but donated via one of our partner.
</td>
    </tr>
    <tr>
      <th align="left">contact.contact_data</th>
      <td>The user's contact data. Please note that you need to be
<a href="../README.md#client-authentication">authenticated as a client</a> with matching
access rights in order to see this information.
</td>
    </tr>
    <tr>
      <th align="left">contact.picture.original</th>
      <td>Original size as uploaded by the user</td>
    </tr>
    <tr>
      <th align="left">contact.picture.large_attention_deprecated</th>
      <td>Large size – ATTENTION, this feature is DEPRECATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
    </tr>
    <tr>
      <th align="left">contact.picture.profile_attention_deprecated</th>
      <td>Medium size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">contact.picture.thumb_attention_deprecated</th>
      <td>Thumbnail size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">carrier.self</th>
      <td>Link to this resource itself
(<a href="organisation_details.md">organisation details</a>)
Note: Since the there is no api for users yet, this is only
set for organisations.
</td>
    </tr>
    <tr>
      <th align="left">carrier.picture.original</th>
      <td>Original size as uploaded by the user</td>
    </tr>
    <tr>
      <th align="left">carrier.picture.large_attention_deprecated</th>
      <td>Large size – ATTENTION, this feature is DEPRECATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
    </tr>
    <tr>
      <th align="left">carrier.picture.profile_attention_deprecated</th>
      <td>Medium size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">carrier.picture.thumb_attention_deprecated</th>
      <td>Thumbnail size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">profile_picture.original</th>
      <td>Original size as uploaded by the user</td>
    </tr>
    <tr>
      <th align="left">profile_picture.large_attention_deprecated</th>
      <td>Large size – ATTENTION, this feature is DEPRECATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
    </tr>
    <tr>
      <th align="left">profile_picture.profile_attention_deprecated</th>
      <td>Medium size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">profile_picture.thumb_attention_deprecated</th>
      <td>Thumbnail size – ATTENTION, this feature is DEPRECATED. See above.</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.self</th>
      <td>Link to this resource itself
(<a href="matching_fund_details.md">matching fund details</a>)
</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.platform</th>
      <td>Permalink to betterplace.org</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.projects</th>
      <td>Link to the list of projects belonging to this matching fund</td>
    </tr>
    <tr>
      <th align="left">active_matching_fund.documentation</th>
      <td>Link to this resource in the documentation
</td>
    </tr>
</table>

## Response Example

```json
{
  "total_entries": 39,
  "offset": 0,
  "total_pages": 20,
  "current_page": 1,
  "per_page": 2,
  "data": [
    {
      "id": 7551,
      "created_at": "2011-08-28T22:19:43Z",
      "updated_at": "2013-10-24T16:59:32Z",
      "latitude": -4.0347900390625,
      "longitude": 21.75629997253418,
      "city": "Kinshasa",
      "country": "Congo (Democratic Republic)",
      "title": "Ausbildungswerkstatt für Kinder im Kongo",
      "description": "Unsere Projektnummer: 7551 - In der Demokratische Republik Kongo sind sehr viele Kinder durch Armut und Krieg zu den Straßenkindern geworden. Unter ihnen zählen ehemalige Kindersoldaten, Waisenkinder und Kinder aus sehr armen Familien. Um sich das Brot zu verdienen, sind viele Jungenmädchen zur Straßenprostitution geworden und die meisten Jungs sind Straßendieb und kriminellen. Die schwächten Kinder die sich nicht zu helfen wissen erkranken meistens an Marasmus und sterben anschließend. Diesen Kindern fehlt jegliche Hilfe zum Überleben. Der kongolesische Staat hat bisher keinerlei Hilfsmaßnahmen für diese Kindergrupe unternommen. Ohne Hilfe von außen haben diesen Kinder keiner Zukunft. <br /><br />Seit 2007 haben wir uns auf die Arbeit gemacht und unterstützen heute 40 Kinder aus Kinshasa und Bukavu mit Patenschaft und Spenden. In Zusammenarbeit mit unseren Partner Vorort verteilen wir Nahrungsmittel und sorgen für die nötige medizinische Versorgung, damit die Kleinen erst einmal zu Kräften kommen. Im Weiteren kümmern wir uns um ihre Schulbildung; wir verteilen Schulmaterialien und übernehmen die Schulgebühren für sie. Denn nachdem der Hunger gestillt ist, braucht jedes Kind Bildung, um sich aus seinem Schicksal befreien zu können.<br /><br />Viele von den Kinder die wir seit 4 Jahren den Besuch der Schule ermöglicht haben könnten mit unserer Hilfe die sekundären Schulabschluss absolvieren bzw. erlangen. Mit nur diesem Abschluss ist es leider nicht möglich eine Zukunftssichere Arbeitsstelle zu finden. Eine weitführende Schule und/oder ein Studium zu besuchen kostet viele Geld und ist nicht erfolgssprechend. Da diese Kinder nach ihrer Schulabschlusse keine Arbeit haben und wir sie bisher nichts Weiteres anbieten könnten, sind einige von ihnen wieder dahin gelangt wo sie herkamen; sie sind wieder zu Straßenkindern geworden und laufen Gefahr wieder in der Prostitution und in der Kriminalität zu gelangen.<br /><br />Mit einer abgeschlossenen Ausbildung sehen wir eine große Chance diese Kinder sowie weitere hilfsbedürftige Kinder eine Arbeitsplatz zu vermitteln. Ziel ist, sie auf eigene Füße zu stellen um zu verhindern dass sie nicht wieder auf die Straße gelangen. Genau gesagt: Hauptziel ist, sie dauerhaft aus der Armut zu holen. <br /><br />Geplant ist den Bau einer Ausbildungswerkstatt (für Schneiderei, Schreinerei, KFZ-Mechaniker und EDV) und eine medizinische Notfallstation. <br />Für den Anfang wollen wir erstmals eine Schneidereiwerkstatt für ca. 20 Kinder in der Hauptstadt Kinshasa bauen. Dort sollen in erste Linie Mädchen als Schneiderin ausgebildet werden. Nach erfolgreichen abgeschlossen Ausbildung von 1,5 Jahre werden sie die Möglichkeit haben sich selbständig zu machen oder auf freie Markt einen Arbeitsplatz zu bekommen.<br /><br />Um diese Maßnahme realisieren zu können, benötigen wir finanzielle und/oder materielle Hilfe!",
      "tax_deductible": true,
      "donations_prohibited": false,
      "open_amount_in_cents": 2429000,
      "positive_opinions_count": 34,
      "negative_opinions_count": 0,
      "donor_count": 27,
      "progress_percentage": 9,
      "incomplete_need_count": 10,
      "completed_need_count": 6,
      "blog_post_count": 3,
      "contact": {
        "name": "M. Namegabe",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "/paperclip/000/176/415/original_Foto1__Manda__1_.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "/paperclip/000/176/415/default_Foto1__Manda__1_.jpg"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "/paperclip/000/176/415/profile_Foto1__Manda__1_.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "/paperclip/000/176/415/thumb_Foto1__Manda__1_.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.org/en/users/manda_n"
          },
          {
            "rel": "contact_data",
            "href": "https://api.betterplace.org/en/api_v4/users/131304/contact_data.json"
          }
        ]
      },
      "carrier": {
        "name": "Agentur für Kinderpatenschaft e. V.",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "/uploads/organisation/profile_picture/5044/original_original_Akipa_LOGO_1_.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "/uploads/organisation/profile_picture/5044/default_original_Akipa_LOGO_1_.jpg"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "/uploads/organisation/profile_picture/5044/profile_original_Akipa_LOGO_1_.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "/uploads/organisation/profile_picture/5044/thumb_original_Akipa_LOGO_1_.jpg"
            }
          ]
        },
        "links": [
          {
            "rel": "self",
            "href": "https://api.betterplace.org/en/api_v4/organisations/5044.json"
          }
        ]
      },
      "profile_picture": {
        "links": [
          {
            "rel": "original",
            "href": "/paperclip/000/264/083/original_P1000771.JPG"
          },
          {
            "rel": "large_attention_deprecated",
            "href": "/paperclip/000/264/083/default_P1000771.jpg"
          },
          {
            "rel": "profile_attention_deprecated",
            "href": "/paperclip/000/264/083/profile_P1000771.jpg"
          },
          {
            "rel": "thumb_attention_deprecated",
            "href": "/paperclip/000/264/083/thumb_P1000771.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "https://api.betterplace.org/en/api_v4/projects/7551.json"
        },
        {
          "rel": "platform",
          "href": "http://www.betterplace.org/en/projects/7551-ausbildungswerkstatt-fur-kinder-im-kongo"
        },
        {
          "rel": "opinions",
          "href": "https://api.betterplace.org/en/api_v4/projects/7551/opinions.json"
        },
        {
          "rel": "pictures",
          "href": "https://api.betterplace.org/en/api_v4/projects/7551/pictures.json"
        },
        {
          "rel": "needs",
          "href": "https://api.betterplace.org/en/api_v4/projects/7551/needs.json"
        },
        {
          "rel": "blog_posts",
          "href": "https://api.betterplace.org/en/api_v4/projects/7551/blog_posts.json"
        },
        {
          "rel": "matching_funds",
          "href": "https://api.betterplace.org/en/api_v4/matching_funds.json?project_id=7551"
        }
      ]
    },
    {
      "id": 7701,
      "created_at": "2011-09-16T15:06:28Z",
      "updated_at": "2013-10-22T00:34:43Z",
      "latitude": 49.74660110473633,
      "longitude": 6.63549995422363,
      "street": "Saarstraße 55",
      "zip": "54290",
      "city": "Trier",
      "country": "Germany",
      "title": "Förderung des Ehrenamts in der AIDS-Hilfe",
      "description": "Unsere Projektnummer: 7701 - Ehrenamt ist nicht umsonst, aber auch nicht kostenlos! Helfen Sie uns, freiwilligen Helfer/innen günstige Rahmenbedingungen für ihr Engagement zu bieten!<br /><br />Ohne unsere freiwilligen Helferinnen und Helfer könnten wir als AIDS-Hilfe viele unserer Angebote gar nicht aufrecht erhalten. Egal ob im Vorstand, bei der Organisation des Positiven-Frühstücks oder am Infostand – unsere ehrenamtlichen Mitarbeiter/innen stellen uns ihre Zeit, ihre Energie und ihre ganz persönlichen Kompetenzen zur Verfügung, damit wir unserer Arbeit nachgehen können. So sind es Ehrenamtliche, die einmal in der Woche ein „Positiven-Frühstück“ und damit eine niedrigschwellige Begegnungsmöglichkeit für Menschen mit HIV und AIDS organisieren, und ebenso sind es Ehrenamtliche, die in Schulklassen und Jugendgruppen über HIV-Übertragungswege, Schutzmöglichkeiten und die Situation der von HIV betroffenen Menschen informieren. Freiwillige Helfer/innen stehen am Informationsstand für Fragen zu HIV zur Verfügung und unterstützen auch das Beraterteam unseres Anonymen Beratungstelefons. Insgesamt sind es um die 30 Ehrenamtlichen, die uns in unserer Arbeit unterstützen.<br /><br />Während einige Tätigkeiten nur wenig Vor- und Hintergrundwissen erfordern, können andere Aufgaben nur nach einer gründlichen Einarbeitung von Ehrenamtlichen übernommen werden. Eine solche Einarbeitung ist vor allem zeitintensiv. Da der Großteil unserer Helfer/innen Arbeit bzw. Studium, Privatleben und Ehrenamt unter einen Hut bringen muss, dauert es mitunter recht lange, bis sich unsere Ehrenamtlichen wirklich eigenständig in die Beratungs-, Unterstützungs- und Präventionsarbeit einbringen können.<br /><br />Durch eine Reihe aufeinander aufbauender Schulungs- und Fortbildungsveranstaltungen könnte die Einarbeitungszeit für unsere freiwilligen Helfer/innen deutlich verkürzt werden. Ein solches Angebot zu erstellen und umzusetzen kostet jedoch Geld, das die AIDS-Hilfe Trier alleine nicht aufbringen kann. Daher unsere Bitte: Helfen Sie uns, damit unsere Ehrenamtlichen ihrerseits helfen können! Spenden Sie für unser Projekt Geld, damit die Zeitspenden unserer Helfer/innen schnellstmöglich der inhaltlichen AIDS-Hilfe-Arbeit zugute kommen. <br /><br />Wir möchten ansprechende Infoflyer drucken, um mehr Menschen über die Möglichkeit eines Engagements in der AIDS-Hilfe zu informieren. Fortbildungen zu den medizinischen Hintergründen von HIV-Infektion und AIDS-Erkrankung, zur Beratungs-, der psychosozialen Unterstützungs- sowie zur Präventionsarbeit sollen bis zu zehn neuen Ehrenamtlichen einen schnelleren Einstieg in unsere Arbeit ermöglichen. Darüber hinaus benötigen wir für die Durchführung der Fortbildungen eine Multifunktionswand, die auch langfristig der Einarbeitung neuer Ehrenamtlicher zugute kommen kann.<br /><br />Ihre Hilfe zählt! Unsere Ehrenamtlichen zählen auf Sie!",
      "tax_deductible": true,
      "donations_prohibited": false,
      "open_amount_in_cents": 44900,
      "positive_opinions_count": 20,
      "negative_opinions_count": 0,
      "donor_count": 17,
      "progress_percentage": 84,
      "incomplete_need_count": 2,
      "completed_need_count": 6,
      "blog_post_count": 20,
      "contact": {
        "name": "B. Geller",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "/paperclip/000/262/052/original_Bernd%20Geller.jpg"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "/paperclip/000/262/052/default_Bernd%20Geller.jpg"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "/paperclip/000/262/052/profile_Bernd%20Geller.jpg"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "/paperclip/000/262/052/thumb_Bernd%20Geller.png"
            }
          ]
        },
        "links": [
          {
            "rel": "platform",
            "href": "http://www.betterplace.org/en/users/bernd_g6"
          },
          {
            "rel": "contact_data",
            "href": "https://api.betterplace.org/en/api_v4/users/220753/contact_data.json"
          }
        ]
      },
      "carrier": {
        "name": "AIDS-Hilfe Trier e.V.",
        "picture": {
          "links": [
            {
              "rel": "original",
              "href": "/uploads/organisation/profile_picture/8515/original_profile_thumb_Logo_AIDS-Hilfe_Trier_e.V..png"
            },
            {
              "rel": "large_attention_deprecated",
              "href": "/uploads/organisation/profile_picture/8515/default_profile_thumb_Logo_AIDS-Hilfe_Trier_e.V..png"
            },
            {
              "rel": "profile_attention_deprecated",
              "href": "/uploads/organisation/profile_picture/8515/profile_profile_thumb_Logo_AIDS-Hilfe_Trier_e.V..png"
            },
            {
              "rel": "thumb_attention_deprecated",
              "href": "/uploads/organisation/profile_picture/8515/thumb_profile_thumb_Logo_AIDS-Hilfe_Trier_e.V..png"
            }
          ]
        },
        "links": [
          {
            "rel": "self",
            "href": "https://api.betterplace.org/en/api_v4/organisations/8515.json"
          }
        ]
      },
      "profile_picture": {
        "links": [
          {
            "rel": "original",
            "href": "/paperclip/000/262/049/original_Fotolia_30845874_XS.jpg"
          },
          {
            "rel": "large_attention_deprecated",
            "href": "/paperclip/000/262/049/default_Fotolia_30845874_XS.jpg"
          },
          {
            "rel": "profile_attention_deprecated",
            "href": "/paperclip/000/262/049/profile_Fotolia_30845874_XS.jpg"
          },
          {
            "rel": "thumb_attention_deprecated",
            "href": "/paperclip/000/262/049/thumb_Fotolia_30845874_XS.png"
          }
        ]
      },
      "links": [
        {
          "rel": "self",
          "href": "https://api.betterplace.org/en/api_v4/projects/7701.json"
        },
        {
          "rel": "platform",
          "href": "http://www.betterplace.org/en/projects/7701-forderung-des-ehrenamts-in-der-aids-hilfe"
        },
        {
          "rel": "opinions",
          "href": "https://api.betterplace.org/en/api_v4/projects/7701/opinions.json"
        },
        {
          "rel": "pictures",
          "href": "https://api.betterplace.org/en/api_v4/projects/7701/pictures.json"
        },
        {
          "rel": "needs",
          "href": "https://api.betterplace.org/en/api_v4/projects/7701/needs.json"
        },
        {
          "rel": "blog_posts",
          "href": "https://api.betterplace.org/en/api_v4/projects/7701/blog_posts.json"
        },
        {
          "rel": "matching_funds",
          "href": "https://api.betterplace.org/en/api_v4/matching_funds.json?project_id=7701"
        }
      ]
    }
  ]
}
```

