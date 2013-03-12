# The betterplace.org API Version 4 (beta)

This is the latest API for betterplace.org. It's a REST-style API that returns
JSON for serialization.
It incorporates some ideas from hypermedia apis like the link-strukture.

**Still under development:** This API is still unter development for
the new mobile feature of betterplace.org

**Please provide feedback:** Since you are one of the first to read this
document and use the API V4, please don't hesitate to provide any feedback at
developers@betterplace.org.


## Table of content

### Public API

* General information below
* [**Project** List and Search](sections/project_list.md) – Note: This returns a minimal result-set for use in map-views. The extended result set for list-views ist still TOOD.
* [**Project** Details](sections/project_details.md)
* [Project **Needs** List](sections/need_list.md)
* [Project **Needs** Details](sections/need_details.md)
* [Project **Blogpost** List](sections/blog_post_list.md)
* [Project **Blogpost** Details](sections/blog_post_details.md)
* TODO [Project **Opinions** List](sections/opinion_list.md)
* TODO [Project **Pictures** List](sections/picture_list.md)
* [**Volunteering** List and Search](sections/volunteering_list.md)
* [**Volunteering** Details](sections/volunteering_details.md)
* [**Organisation** List](sections/organisation_list.md)
* [**Organisation** Details](sections/organisation_details.md)
* TODO [**User** Details](sections/user_details.md)
* TODO [**Fundraising Event** List and Search](sections/fundraising_event_list.md)
* TODO [**Fundraising Event** Details](sections/fundraising_event_details.md)


### Client API

* [**Client** Details/Statistics](sections/client_details.md)
* [**Client** Donations List](sections/client_donation_list.md)

This part of the API can only be used in agreement with betterplace.org.
Please [contact someone at betterplace solutions](http://www.betterplace-solutions.de/#buergerzeitung)
for more information.

*Example:* The local german newspaper "Trierischer Volksfreund"
has it's own donation portal at ["Meine Hilfe zählt"](http://www.volksfreund-servicecenter.de/projekte/).

*Client projects:* Clients projects are projects on betterplace.org that are
associated with the client-user. This way clients can control what projects
are visible on their plattform.

*Request-URLs:* Clients have to prepend all request with the their client-id.
For projects that would be `/clients/PERMALINK/projects.json` and `/clients/PERMALINK/projects/ID.json`

*Error Code:* If you request data for a project that is not part of the client
projects, the API will return a `404` HTTP code.


## General information

* All request have to https
* The response format is json, the request-extention .json
* We support [Cross-origin resource sharing (CORS)](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing), so no proxy or JSONP is required
* No Authentication: All api calls are public at the moment but there will be feature that require a authentication in the future.


## Request parameter format

The `order` and `facet` request parameter accept multiple key-value-parameter.
We use the same convention as the [Google Static Maps API V2](https://developers.google.com/maps/documentation/staticmaps/#URL_Parameters).

Example: `foo:bar|lorem:ipsum`

This way you ma specify a primary and secondaray sort order: `order=rank:ASC|created_at:DESC`

* Split key and value by a colon `:`
* Split multiple key-value-parameter by a pipe `|` (`%7C`)
* [URL encode](http://de.wikipedia.org/wiki/URL-Encoding) all params, so the Pipe becomes `%7C`
* Note that for readability-reasons we don't URL encode the params in this documentation


## Pagination parameter

The following parameters are avaliable for all list views.

### Pagination request parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>page</code></td>
    <td>Used to paginate through the list</td>
  </tr>
  <tr>
    <td><code>per_page</code></td>
    <td>The number of entries per page</td>
  </tr>
</table>

### Pagination response parameter

<table>
  <tr>
    <th>Parameter</th>
    <th>Description</th>
    <th>Default</th>
  </tr>
  <tr>
    <td><code>total_entries</code></td>
    <td>Count of all entries</td>
    <td>-</td>
  </tr>
  <tr>
    <td><code>offset</code></td>
    <td>From which entry on the list continues, based on <code>per_page</code> <-- ???? Offset kann nicht manuell gesetzt werden, warum haben wir ihn dann überhaupt?</td>
    <td>0</td>
  </tr>
  <tr>
    <td><code>total_pages</code></td>
    <td>Count of all pages, based on <code>per_page</code></td>
    <td>-</td>
  </tr>
  <tr>
    <td><code>current_page</code></td>
    <td>What page we are on</td>
    <td>1</td>
  </tr>
  <tr>
    <td><code>per_page</code></td>
    <td>Number of entries per page</td>
    <td>50</td>
  </tr>
</table>


## HTTP Result Codes and Error Messages

### Error Messages

If an error occurs, a JSON response messages is returned to the client. In the
JSON error messages the backtrace and message attributes are only included in
the development or test environments. A message like this may be returned, if a
resource couldn't be found (and the HTTP result code would be 404):

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

- HTTP Code `404` is returned if a requested resource could not be found.

- HTTP Code `400` is returned if a requested resource could not be created or updated, if the
  submitted data was invalid.

- HTTP Code `500` is returned if a software error on the server was encountered.


## API V1, V2, V3

betterplace.org has three depricated APIs. For more information http://www.betterplace.org/de/api/documentation/welcome


## Example apps

There are no example Apps at this point.
Please send the link to your app to developers@betterplace.


## About betterplace.org

Learn more about betterplace at http://www.betterplace.org/de/how_it_works
