
# Project Opinion List ⇄ [Details](opinions_details.md)

```nginx
GET https://api.betterplace.org/en/api_v4/projects/1114/opinions.json?facets=score%3A1&order=created_at%3AASC
```

## Attention: The opinions-list for projects is still WIP. Right now it shows all opinions instead of those of the project.

A list of betterplace.org projects opinions (donate money).
Results are contains in a *data* attribute.

*For [betterplace.org clients](../README.md#client-api):*
There is no client-scoped-url.
Please use the api calls that are provided inside the client project _url_ response
to make sure you only request data that is associated with one of your projects.


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
    <td>Order the result by <code>created_at</code> (default), <code>id</code>,
<code>score</code>, <code>type</code>, <code>message</code>
Use the optional <code>ASC</code> (default) or <code>DESC</code>.
<a href="../README.md#request-parameter-format">Learn how to format the parameter</a>.
</td>
  </tr>
  <tr>
    <th>facets</th>
    <td><code>score:1</code></td>
    <td>optional</td>
    <td>Filter the result set:
<ul>
<li><code>facets=score:1</code> only positive opinion
<li><code>facets=score:%2D1</code> only negative opinion
<li><code>facets=type:DonorOpinion</code> only opinions with_donation:true
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
    <th>Example/Optional</th>
    <th>Description</th>
  </tr>
</table>

## Response Links
#
<table>
  <tr>
    <th>Linkname</th>
    <th>Description</th>
  </tr>
</table>

## Response Example

```json
null
```

