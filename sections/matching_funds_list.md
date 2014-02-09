
# Matching Funds List ⇄ [Details](matching_fund_details.md)

```nginx
GET https://api.betterplace.org/en/api_v4/matching_funds.json?facets=state%3Aactivated&project_id=1114
```

A list of betterplace.org matching funds.


## Input Parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Example</th>
    <th>Required/Optional</th>
    <th>Description</th>
  </tr>
  <tr>
    <th align="left">project_id</th>
    <td><code>1114</code></td>
    <td>required</td>
    <td>Project-id as an integer number ≥ 14.</td>
  </tr>
  <tr>
    <th align="left">facets</th>
    <td><code>state:activated</code></td>
    <td>optional</td>
    <td>Filter the result set by <code>state</code> (activated|closed)
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
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
      <td>string</td>
      <td>53</td>
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
      <th align="left">activated_at</th>
      <td>null &#124; string</td>
      <td>"1994-11-05T13:15:30Z"</td>
      <td>DateTime (ISO8601 with Timezone)</td>
    </tr>
    <tr>
      <th align="left">title</th>
      <td>string</td>
      <td>ACME Matching Everything</td>
      <td>Our matching fund's name</td>
    </tr>
    <tr>
      <th align="left">description</th>
      <td>string</td>
      <td>It's all about matching donations…</td>
      <td>The description of the matching fund</td>
    </tr>
    <tr>
      <th align="left">company_name</th>
      <td>string</td>
      <td>ACME</td>
      <td>The company that supports it</td>
    </tr>
    <tr>
      <th align="left">state</th>
      <td>string</td>
      <td>activated</td>
      <td>Current state of this matching fund: either activated or closed</td>
    </tr>
    <tr>
      <th align="left">logo_url</th>
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
(<a href="matching_fund_details.md">matching fund details</a>)
</td>
    </tr>
    <tr>
      <th align="left">platform</th>
      <td>Permalink to betterplace.org</td>
    </tr>
    <tr>
      <th align="left">projects</th>
      <td>Link to the list of projects belonging to this matching fund</td>
    </tr>
    <tr>
      <th align="left">documentation</th>
      <td>Link to this resource in the documentation
</td>
    </tr>
</table>

## Response Example

```json
{
  "total_entries": 1,
  "offset": 0,
  "total_pages": 1,
  "current_page": 1,
  "per_page": 2,
  "data": [
    {
      "id": 2,
      "created_at": "2013-10-14T13:26:19Z",
      "updated_at": "2013-10-22T10:07:02Z",
      "activated_at": "2013-10-21T07:54:41Z",
      "title": "Jetzt mitmachen – OTTO verdoppelt jede Spende!",
      "description": "OTTO hilft Hamburgs Stadtgrün – helfen Sie mit!\r\n \r\nGemeinsam mit der Loki Schmidt Stiftung und der Stadt Hamburg schließen wir Baumlücken in strukturschwachen Stadtteilen. Diese Lücken entstehen aufgrund von Krankheiten oder mangelnder Standfestigkeit der Straßenbäume.\r\n \r\n!{height:140px}http://download.betterplace.org/221023_ottoverdoppelt_logos.png!\r\nSeit 2011 sind Hamburger Bürger aufgerufen, gemeinsam mit den beiden Partner-Organisationen für neue Bäume zu spenden.\r\n \r\nBereits in diesem Jahr hat OTTO das Projekt unterstützt und mit 25.000 Euro 50 Baumlücken in Gebieten geschlossen, in denen weniger gespendet wird – nämlich in Mümmelmannsberg, Nettelnburg, Steinbek, Steilshoop und Willhelmsburg!\r\n \r\nNun wollen wir noch einmal bis zu 60 weitere Bäume pflanzen – und zwar gemeinsam mit Ihnen!\r\n \r\nDas funktioniert folgendermaßen:\r\n1.         Sie spenden einen beliebig hohen Betrag auf betterplace.org.\r\n2.         OTTO verdoppelt Ihren Betrag!\r\n3.         Sobald durch Sie und OTTO 500 Euro zusammengekommen sind, legt die Stadt Hamburg die restlichen 500 Euro drauf, die für eine Pflanzung notwendig sind.\r\n4.         Ein Baum wird gepflanzt – Hamburg wird grüner!\r\n \r\nIhr Engagement zählt – und OTTO honoriert das mit dieser Verdopplungsaktion bis zu einem Maximalbetrag von 15.000 Euro! Helfen Sie jetzt hier mit!",
      "company_name": "OTTO",
      "state": "activated",
      "logo_url": "http:/uploads/matching_fund/logo/2/OTTO_QUADRAT_4c_M-mid.png",
      "links": [
        {
          "rel": "self",
          "href": "https://api.betterplace.org/en/api_v4/matching_funds/2.json"
        },
        {
          "rel": "platform",
          "href": "http://www.betterplace.org/en/matching-funds/2-otto"
        },
        {
          "rel": "projects",
          "href": "https://api.betterplace.org/en/api_v4/matching_funds/2/projects.json"
        },
        {
          "rel": "documentation",
          "href": "https://github.com/betterplace/betterplace_apidocs/blob/master/sections/matching_fund_details.md"
        }
      ]
    }
  ]
}
```

