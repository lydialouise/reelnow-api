---
# markdownlint-disable
# vale  off
layout: default
title: Create a movie
parent: The `movie` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: POST a `movie` resource in the database
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
    - POST /movies
version: "v1.0"
last_updated: "2025-11-19"
# vale  on
# markdownlint-enable
---

# Create a movie
{: .no_toc }

```shell
POST {base_url}/movies
# Replace {base_url} with the server address
```

<!-- *NOTE* explain what server address is (localhost) in setting-up-your-environment page. -->

Register a new `movie` in the ReelNow database.

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

## Request header parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `Content-Type` | string | The parameter content type                   |

## Request body parameters

| Parameter        | Format  | Description                                          |
| :--------------- | :------ | :--------------------------------------------------- |
| `title`          | string  | The name of the movie                                |
| `releaseDate`    | string  | The movie theatre release date                       |
| `genreId`        | number  | The genre's unique ID                                |
| `rating`         | string  | The Motion Picture Association film rating           |
| `runtimeMinutes` | number  | The length of the movie in minutes                   |
| `status`         | string  | The release status                                   |
| `isIntheatres`   | boolean | The flag showing whether the movie is in theatres    |
| `id`             | number  | The movie's unique ID                                |

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
curl -X POST "http://localhost:3000/movies" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Inception",
    "releaseDate": "2010-07-16",
    "genreId": 4,
    "rating": "PG-13",
    "runtimeMinutes": 148,
    "status": "released",
    "isIntheatres": false
  }'
# Create a movie
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 15,
  "title": "Inception",
  "releaseDate": "2010-07-16",
  "genreId": 4,
  "rating": "PG-13",
  "runtimeMinutes": 148,
  "status": "released",
  "isIntheatres": false
}
```
