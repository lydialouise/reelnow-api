---
# markdownlint-disable
# vale  off
layout: default
title: Update a movie
parent: The `movie` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: DELETE a `movie` resource in the database
tags:
    - api
categories:
    - api-reference
ai_relevance: high
importance: 7
prerequisites:
    - /api/movies
related_pages: []
examples: []
api_endpoints: 
    - DELETE /movies/{id}
version: "v1.0"
last_updated: "2025-11-20"
# vale  on
# markdownlint-enable
---

# Update a movie
{: .no_toc }

```shell
DELETE {base_url}/movies/{id}
# Replace {base_url} with the server address
```

<!-- *NOTE* explain what server address is (localhost) in setting-up-your-environment page. -->

Delete an existing `movie` in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description          |
| :------------- | :------------------- |
| Authentication | Access token         |
| Access         | Write                |

## Path parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `base_url`     | string | The server address                           |
| `id`           | number | The movie's unique ID                        |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code   | Description          |
| :------------ | :------------------- |
| 200           | Success              |
| 404           | Resource not found   |
| ECONNREFUSED  | Restart the service  |

<!-- *NOTE* See Stripe docs for Error page. Consider setting up like that. -->

## Example

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X DELETE "http://localhost:3000/movies/1"
# Delete the movie with ID = 1
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{}
```
