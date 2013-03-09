# The Betterplace API Version 4 (BETA) – It is not public yet!

Betterplace has a new version of its API. It's a REST-style API that returns
JSON for serialization.


## Table of content

### Public API

- General information below
- Project
  - [List and Search](sections/project_list.md)
  - [Details](sections/project_details.md)
  - [Project Needs](sections/need_list.md)
  - WIP [Project Opinions](sections/opinion_list.md)
- Volunteering
  - [List and Search](sections/volunteering_list.md)
  - [Details](sections/volunteering_details.md)
- [Organisation Details](sections/organisation_details.md)
- TODO [User Details](sections/user_details.md)


### Client API

This part of the API can only be used in agreement with betterplace.org.
Please [contact our someone at betterplace solutions](http://www.betterplace-solutions.de/#buergerzeitung)
for more information.

*Example:* The local german newspaper "Trierischer Volksfreund"
has it's own donation portal at [http://www.volksfreund-servicecenter.de/projekte/].

*Client projects:* Clients projects are projects on betterplace.org that are
associated with the client-user. This way clients can control what projects
are visible on their plattform.

*Request-URLs:* Clients have to prepend all request with the their client-id.
For projects that would be `/clients/ID/projects.json` and `/clients/ID/projects/ID.json`

- WIP [Statistic](sections/client_details.md)
- [Client Donations](sections/client_donation_list.md)


## Making a request

*TODO*

All requests have to be tunneled through **SSL** and their URLs start with
Betterdocs::Global


## Response formats

- json via .json
- jsonp via .js or .jsonp with an optional `callback`-param

*TODO*


## Request parameter format

The `order` and `facet` request parameter accept multiple key-value-parameter.
We use the same convention as the [Google Static Maps API V2](https://developers.google.com/maps/documentation/staticmaps/#URL_Parameters).

Example: `foo:bar|lorem:ipsum`

* Split key and value by a colon `:`
* Split multiple key-value-parameter by a pipe `|` (`%7C`)
* [URL encode](http://de.wikipedia.org/wiki/URL-Encoding) all params, so the Pipe becomes `%7C`
* Note that for readability-reasons we don't URL encode the params in this documentation


## Authentication

All api calls are public at the moment.
There will be feature that require a authentication in the future.


## API V1, V2, V3

betterplace has three depricated APIs. For more information http://www.betterplace.org/de/api/documentation/welcome


## Example apps

*TODO*


## About betterplace.org

*TODO*
