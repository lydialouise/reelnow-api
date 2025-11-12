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

```shell
GET {base_url}/movies
# Replace {base_url} with the server address
```

List all `movies` registered in the ReelNow database.

## Requirements

| Requirement    | Description          |
| -------------- | -------------------- |
| Authentication | Access token         |
| Permission     | Read                 |

## Request parameters

| Parameter      | Format | Description                                  |
| -------------- | ------ | -------------------------------------------- |
| `base_url`     | string | The server address                           |

### Headers

_None_

### Body

_None_

## Response status codes

| Status code   | Description          |
| ------------- | -------------------- |
| 200           | Success              |
| 404           | Resource not found   |
| ECONNREFUSED  | Restart the service  |

## Example

Here is an example cURL request and `200 OK` response.

### Example `cURL` request

```shell
curl -X GET http://localhost:3000/movies 
# List all movies
```

### Example `200 OK` response

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
  "isInTheaters": false,
  "id": 1
},
{
  "title": "The Lord of the Rings: The Fellowship of the Ring",
  "releaseDate": "2001-12-28",
  "genreId": [2, 3],
  "rating": "PG-13",
  "runtimeMinutes": 228,
  "status": "re-released",
  "isInTheaters": true,
  "id": 2
},
{
  "title": "John Tucker Must Die",
  "releaseDate": "2006-07-28",
  "genreId": 3,
  "rating": "PG-13",
  "runtimeMinutes": 90,
  "status": "archived",
  "isInTheaters": false,
  "id": 3
},
{
  "title": "Black Phone 2",
  "releaseDate": "2025-10-17",
  "genreId": 6
  "rating": "R",
  "runtimeMinutes": 114,
  "status": "released",
  "isInTheaters": true,
  "id": 4
}
```
