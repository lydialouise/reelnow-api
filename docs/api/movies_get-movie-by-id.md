---
# markdownlint-disable
# vale  off
layout: default
title: Get details for a specific movie
parent: The `movie` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: GET a specific `movie` resource in the database
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
    - GET /movies/{id}
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# Get details for a specific movie

```shell
GET {base_url}/genres/{id}
# Replace {base_url} with the server address
# Replace {id} with the movie's unique ID
```

Get details for a specific `movie` registered in the ReelNow database.

## Requirements

| Requirement    | Description          |
| -------------- | -------------------- |
| Authentication | Access token         |
| Permission     | Read                 |

## Request parameters

| Parameter      | Format | Description                                  |
| -------------- | ------ | -------------------------------------------- |
| `base_url`     | string | The server address                           |
| `id`           | number | The movie's unique ID                        |

### Headers

_None_

### Body

_None_

## Response status codes

| Status code   | Description          |
| ------------- | -------------------- |
| 200           | Success              |
| 404           | Resource ID not found   |
| ECONNREFUSED  | Restart the service  |

## Example 

Here is an example cURL request and `200 OK` response.

### Example `cURL` request

```shell
curl -X GET http://localhost:3000/movies/1 
# Get details for the movie with an ID of 1
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
}
```