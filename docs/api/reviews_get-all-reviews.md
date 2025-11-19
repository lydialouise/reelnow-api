---
# markdownlint-disable
# vale  off
layout: default
title: List all reviews
parent: The `review` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: GET all `review` resources in the database
tags:
    - api
categories:
    - api-reference
ai_relevance: high
importance: 7
prerequisites:
    - /api/reviews
related_pages: []
examples: []
api_endpoints: 
    - GET /reviews
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# List all reviews
{: .no_toc }

```shell
GET {base_url}/reviews
# Replace {base_url} with the server address
```

List all `reviews` registered in the ReelNow database.

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
curl -X GET http://localhost:3000/reviews 
# List all reviews
```

### Example response
{: .no_toc }

{: .d-inline-block }

200
{: .label .label-green }

```js
{
    "movieId": 1,
    "source": "Rotten Tomatoes",
    "score": null,
    "reviewCount": null,
    "id": 1
},
{
    "movieId": 2,
    "source": "Rotten Tomatoes",
    "score": 92,
    "reviewCount": 236,
    "id": 2
},
{
    "movieId": 3,
    "source": "IMDB",
    "score": 57,
    "reviewCount": 92000,
    "id": 3
},
{
    "movieId": 4,
    "source": "IMDB",
    "score": 63,
    "reviewCount": 27000,
    "id": 4
}
```
