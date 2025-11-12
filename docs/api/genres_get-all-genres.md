---
# markdownlint-disable
# vale  off
layout: default
title: List all genres
parent: The `genre` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: GET all `genre` resources in the database
tags:
    - api
categories:
    - api-reference
ai_relevance: high
importance: 7
prerequisites:
    - /api/genres
related_pages: []
examples: []
api_endpoints: 
    - GET /genres
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# List all genres

```shell
GET {base_url}/genres
# Replace {base_url} with the server address
```

List all `genres` registered in the ReelNow database.

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
curl -X GET http://localhost:3000/genres 
# List all genres
```

### Example `200 OK` response

{: .d-inline-block }

200
{: .label .label-green }

```js
{
    "name": "family",
    "description": "Content suitable for children and adults; typically animated or light-hearted live action.",
    "id": 1
},
{
    "name": "fantasy",
    "description": "Stories set in imaginary worlds or involving magical elements, mythical creatures, or supernatural forces.",
    "id": 2
},
{
    "name": "action",
    "description": "Fast-paced, high-energy films featuring physical stunts, chases, combat, and special effects.",
    "id": 3
},
{
    "name": "sci-fi",
    "description": "Stories centered around futuristic science, technology, space exploration, or parallel realities.",
    "id": 4
},
{
    "name": "comedy",
    "description": "Light-hearted and humorous stories designed to entertain and amuse, often through wit, satire, or playful characters.",
    "id": 5
},
{
    "name": "horror",
    "description": "Atmospheric and suspenseful films that evoke fear or tension through dread, shock, or the supernatural.",
    "id": 6
},
{
    "name": "romance",
    "description": "Emotionally driven stories that explore love, relationships, and human connection, often focusing on personal growth and heartfelt moments.",
    "id": 7
}
```
