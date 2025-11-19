---
# markdownlint-disable
# vale  off
layout: default
title: Get details for a specific review
parent: The `review` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: GET a specific `review` resource in the database
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
    - GET /reviews/{id}
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# Get details for a specific review
{: .no_toc }

```shell
GET {base_url}/reviews/{id}
# Replace {base_url} with the server address
# Replace {id} with the review's unique ID
```

Get details for a specific `review` registered in the ReelNow database.

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
| `id`           | number | The review's unique ID                        |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code   | Description           |
| ------------- | --------------------- |
| 200           | Success               |
| 404           | Resource ID not found |
| ECONNREFUSED  | Restart the service   |

## Example

Here is an example cURL request and `200 OK` response.

### Example request
{: .no_toc }

```shell
curl -X GET http://localhost:3000/reviews/1 
# Get details for the review with ID = 1
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
```
