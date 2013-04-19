
# Project Opinion List ⇄ [Details](opinion_details.md)

```nginx
GET https://www.betterplace.org/en/api_v4/projects/1114/opinions.json?facets=has_message%3Atrue&order=created_at%3AASC
```

## Attention: The opinions-list for projects is still WIP. Right now it shows all opinions instead of those of the project.

A list of betterplace.org projects opinions (donate money).
Results are contained in a *data* attribute.

*For [betterplace.org clients](../README.md#client-api):*

* _Project-Opinions:_ There is no client-scoped-url.
Please use the api calls that are provided inside the client project _url_ response
to make sure you only request data that is associated with one of your projects.

* _All Opinions:_ Clients can retrieve a list of all opinions of all client-projects:
`/clients/PERMALINK/opnions.json`


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
    <td><code>1114</code></td>
    <td>required</td>
    <td>Project-id as an integer number ≥ 14.</td>
  </tr>
  <tr>
    <th>order</th>
    <td><code>created_at:ASC</code></td>
    <td>optional</td>
    <td>Order the result by
<code>created_at</code> (default), <code>id</code>, <code>score</code>
Use the optional <code>ASC</code> (default) or <code>DESC</code>.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>facets</th>
    <td><code>has_message:true</code></td>
    <td>optional</td>
    <td>Filter the result set:
<ul>
<li><code>facets=score:positive</code> / <code>negative</code> only positive / negative opinion
<li><code>facets=has_donation:true</code> / <code>false</code> only opinions with / without a donation
<li><code>facets=has_message:true</code> / <code>false</code> only opinions with / without a message
</ul>
It is possible to set multiple facet filters.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
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
    <td>1</td>
    <td>An integer number ≥ 1</td>
  </tr>
  <tr>
    <th>created_at</th>
    <td>string</td>
    <td>"1994-11-05T13:15:30Z"</td>
    <td>DateTime (ISO8601 with Timezone)</td>
  </tr>
  <tr>
    <th>donated_amount_in_cents</th>
    <td>number</td>
    <td>5000</td>
    <td>If the opinion was created as part of a donation, this shows the opinions text</td>
  </tr>
  <tr>
    <th>score</th>
    <td>string</td>
    <td>positive</td>
    <td>Opinions can be positive or negative. Negative opinions usually get
a comment as answer very fast but there is no API for opinion-comments yet.
</td>
  </tr>
  <tr>
    <th>author.name</th>
    <td>null &#124; string</td>
    <td>"Till B."</td>
    <td>Display name of a betterplace.org user.
Possible formats: "Till B.", "T. Behnke", "Till Behnke".
In the case of donation-opinions the name might also be anonymized
like "Payback User" or empty/null for anonymous donations.
</td>
  </tr>
  <tr>
    <th>message</th>
    <td>null &#124; string</td>
    <td>"This is a great project. In spring 2007 I travelled around the area together with my children and …"</td>
    <td>An optional message users can provide to tell others
why they like or dislike this project
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
(<a href="opinion_details.md">opinion details</a>)
</td>
  </tr>
  <tr>
    <th>author.platform</th>
    <td>The user's profile on betterplace.org.
To view a user profile you have to be logged in.
This array is empty if the user has no useraccount
with betterplace.org but donated via one of our partner.
</td>
  </tr>
  <tr>
    <th>author.picture.original</th>
    <td>Original size as uploaded by the user</td>
  </tr>
  <tr>
    <th>author.picture.large_attention_deprecated</th>
    <td>Large size – ATTENTION, this feature is DEPRICATED and will be removed at the end of may 2013. Please use the orginal format. Read the project pictures-documentation at "custom image sizes" for other solutions"</td>
  </tr>
  <tr>
    <th>author.picture.profile_attention_deprecated</th>
    <td>Medium size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
  <tr>
    <th>author.picture.thumb_attention_deprecated</th>
    <td>Thumbnail size – ATTENTION, this feature is DEPRICATED. See above.</td>
  </tr>
</table>

## Response Example

```json
{
  "total_entries": null,
  "offset": null,
  "total_pages": null,
  "current_page": null,
  "per_page": 3,
  "data": null
}
```

