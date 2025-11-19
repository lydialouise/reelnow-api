---
# markdownlint-disable
# vale  off
layout: default
title: List all movies
parent: The `movie` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: GET all `movie` resources in the database
tags: 
    - api
categories:
    - api-reference
ai_relevance: high
importance: 8
prerequisites:
    - /api/movies
related_pages: []
examples: []
api_endpoints: 
    - GET /movies
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# List all movies
{: .no_toc }

```shell
GET {base_url}/movies
# Replace {base_url} with the server address
```

List all `movies` registered in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description          |
| -------------- | -------------------- |
| Authentication | Access token         |
| Access         | Read                 |

## Path parameters

| Parameter      | Format | Description                                  |
| -------------- | ------ | -------------------------------------------- |
| `base_url`     | string | The server address                           |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code   | Description          |
| ------------- | -------------------- |
| 200           | Success              |
| 404           | Resource not found   |
| ECONNREFUSED  | Restart the service  |

## Example

Here is an example cURL request and `200 OK` response.

### Example request
{: .no_toc }

```shell
curl -X GET http://localhost:3000/movies 
# List all movies
```

### Example response
{: .no_toc }

{: .d-inline-block }

200
{: .label .label-green }

```js
{
  "title": "Zootopia 2",
  "releaseDate": "2025-11-26",
  "genreId": [1, 5],
  "rating": "PG",
  "runtimeMinutes": 107,
  "status": "upcoming",
  "isIntheatres": false,
  "id": 1
},
{
  "title": "The Lord of the Rings: The Fellowship of the Ring",
  "releaseDate": "2001-12-28",
  "genreId": [2, 3],
  "rating": "PG-13",
  "runtimeMinutes": 228,
  "status": "re-released",
  "isIntheatres": true,
  "id": 2
},
{
  "title": "John Tucker Must Die",
  "releaseDate": "2006-07-28",
  "genreId": 3,
  "rating": "PG-13",
  "runtimeMinutes": 90,
  "status": "archived",
  "isIntheatres": false,
  "id": 3
},
{
  "title": "Black Phone 2",
  "releaseDate": "2025-10-17",
  "genreId": 6
  "rating": "R",
  "runtimeMinutes": 114,
  "status": "released",
  "isIntheatres": true,
  "id": 4
}
```
