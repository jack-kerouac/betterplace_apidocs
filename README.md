# The betterplace.org API Version 4 (beta)

This is the latest API for betterplace.org. It's a REST-style API that returns
JSON for serialization.
It incorporates some ideas from [hypermedia apis](https://www.google.de/search?q=hypermedia+api)
like the link-strukture.

**Still under development:** This API is still unter development for
the new mobile feature of betterplace.org

**Please provide feedback:** Since you are one of the first to read this
document and use the API V4, please don't hesitate to provide any feedback at
developers@betterplace.org.

**Mailing list for service announcements:** Please send an email to tjo@betterplace.org
to subscribe to the api-v4-mailing list to receive service announcements about updates
and scheduled downtimes.


## Table of content

### Public API

* General information below
* [**Project** List and Search](sections/project_list.md) – Note: This returns a minimal result set for use in map-views. The extended result set for list-views ist still TODO.
* [**Project** Details](sections/project_details.md)
* [Project **Needs** List](sections/need_list.md)
* [Project **Needs** Details](sections/need_details.md)
* [Project **Blog Post** List](sections/blog_post_list.md)
* [Project **Blog Post** Details](sections/blog_post_details.md)
* [Project **Opinions** List](sections/opinion_list.md)
* [Project **Opinions** Details](sections/opinion_detail.md)
* TODO [Project **Pictures** List](sections/picture_list.md)
* [**Volunteering** List and Search](sections/volunteering_list.md)
* [**Volunteering** Details](sections/volunteering_details.md)
* [**Organisation** List](sections/organisation_list.md)
* [**Organisation** Details](sections/organisation_details.md)
* TODO [**User** Details](sections/user_details.md)
* TODO [**Fundraising Event** List and Search](sections/fundraising_event_list.md)
* TODO [**Fundraising Event** Details](sections/fundraising_event_details.md)


### Client API

This part of the API can only be used in agreement with betterplace.org.
Please [contact someone at betterplace solutions](http://www.betterplace-solutions.de/#buergerzeitung)
for more information.

* [**Client** Details/Statistics](sections/client_details.md)
* [**Client** Donation List](sections/client_donation_list.md)
* [**Client** Project List and Search](sections/project_list.md) – See client section and ⁂1
* [**Client** Project Details](sections/project_details.md) – See client section and ⁂1
* [**Client** Blog Post List](sections/blog_post_list.md) – See client section

*(⁂1) Client projects:* Clients projects are projects on betterplace.org that are
associated with the client-user. This way clients can control what projects
are visible on their plattform.

*Request-URLs:* Clients have to prepend some with the their client-id.
For projects that would be `/clients/PERMALINK/projects.json` and `/clients/PERMALINK/projects/ID.json`.
More information can be found in the description of each request.

*Error Code:* If you request data for a project that is not part of the client
projects, the API will return a `404` HTTP code.

*Usage example:* The local german newspaper "Trierischer Volksfreund"
has it's own donation portal at ["Meine Hilfe zählt"](http://www.volksfreund-servicecenter.de/projekte/) – actually it uses an older api-version but still it's the same idea ;-).


## General information

* All request have to https
* The response format is json, the request-extention .json
* The response language is definde by the URL-language-section (/en/, /de/ (default), …)
* We support [Cross-origin resource sharing (CORS)](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing), so no proxy or JSONP is required
* No Authentication: All api calls are public at the moment but there will be feature that require a authentication in the future.
* All responses are cached for 5 minutes at the moment


### Request parameter format

The `order` and `facet` request parameter accept multiple key-value-parameter.
We use the same convention as the [Google Static Maps API V2](https://developers.google.com/maps/documentation/staticmaps/#URL_Parameters).

Example: `foo:bar|lorem:ipsum`

This way you ma specify a primary and secondaray sort order: `order=rank:ASC|created_at:DESC`

* Split key and value by a colon `:`
* Split multiple key-value-parameter by a pipe `|` (`%7C`)
* [URL encode](http://de.wikipedia.org/wiki/URL-Encoding) all params, so the Pipe becomes `%7C`
* Note that for readability-reasons we don't URL encode the params in this documentation


### Pagination parameter

The following parameters are avaliable for all list views.

<table>
  <tr>
    <th>Type</th>
    <th>Parameter</th>
    <th>Description</th>
    <th>Default</th>
  </tr>
  <tr>
    <th>Request</th>
    <td><code>page</code></td>
    <td>Used to paginate through the list</td>
    <td></td>
  </tr>
  <tr>
    <th>Request</th>
    <td><code>per_page</code></td>
    <td>The number of entries per page</td>
    <td></td>
  </tr>
  <tr>
    <th>Response</th>
    <td><code>total_entries</code></td>
    <td>Count of all entries</td>
    <td></td>
  </tr>
  <tr>
    <th>Response</th>
    <td><code>offset</code></td>
    <td>From which entry on the list continues, based on <code>per_page</code> <-- ???? Offset kann nicht manuell gesetzt werden, warum haben wir ihn dann überhaupt?</td>
    <td>0</td>
  </tr>
  <tr>
    <th>Response</th>
    <td><code>total_pages</code></td>
    <td>Count of all pages, based on <code>per_page</code></td>
    <td></td>
  </tr>
  <tr>
    <th>Response</th>
    <td><code>current_page</code></td>
    <td>What page we are on</td>
    <td>1</td>
  </tr>
  <tr>
    <th>Response</th>
    <td><code>per_page</code></td>
    <td>Number of entries per page</td>
    <td>50</td>
  </tr>
</table>


## HTTP Result Codes and Error Messages

### Error Messages

If an error occurs, a JSON response messages is returned with a `name` and `reason` (optional).
Clients that use the betterplace.org-staging-environment will also see a `backtrace` and `message`.

Example:

```json
{
  "name": "ActiveRecord::RecordNotFound",
  "reason": "Record Not Found",
  "backtrace": [
    "/path/to/file:23:in `method'",
    "/path/to/file:42:in `method2'"
  ],
  "message": "Couldn't find Project with id=666"
}
```

### HTTP Result Codes

The following HTTP result codes can be returned:

* HTTP Code `404` is returned if a requested resource could not be found.

* HTTP Code `400` is returned if a requested resource could not be created or updated,
  if the submitted data was invalid.

* HTTP Code `500` is returned if a software error on the server was encountered.


## Changelog

* 2012-03-12: Several updates to readme, updates to descriptions for clients, updated opinions-docu, added know-issues and changelog sections (@tordans)
* 2012-03-11: Initial version (@betterplace)


## Known issues

Please contact developers@betterplace.org for more information

1. Several documentation pages are empty
1. The `links` to other api-calls dont use the api-subdomain but www instead
1. The `links` to images dont use the asset path asset1 but www instead
1. The pictures-list-docu-page is missing
1. `projects/14/pictures.json` is broken (500)
1. /project/id/opinions.json alsways return all opinions instead of those for the project
1. Not all ressources have a documentation-url as part of the json
1. The response-table does not show the root-documentation for response-elements with sub-elements (for example carrier.name is documented but carrier is not)


## API V1, V2, V3

betterplace.org has three depricated APIs. For more information http://www.betterplace.org/de/api/documentation/welcome


## Example apps

There are no example Apps at this point.
Please send the link to your app to developers@betterplace.


## About betterplace.org

Learn more about betterplace at http://www.betterplace.org/de/how_it_works
