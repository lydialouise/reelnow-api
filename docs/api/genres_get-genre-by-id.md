---
# markdownlint-disable
# vale  off
layout: default
title: Get details for a specific genre
parent: The `genre` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: GET a specific `genre` resource in the database
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
    - GET /genres/{id}
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# Get details for a specific genre

```shell
GET {base_url}/genres/{id}
# Replace {base_url} with the server address
# Replace {id} with the genre's unique ID
```

Get details for a specific `genre` registered in the ReelNow database.

## Requirements

| Requirement    | Description          |
| -------------- | -------------------- |
| Authentication | Access token         |
| Permission     | Read                 |

## Request parameters

| Parameter      | Format | Description                                  |
| -------------- | ------ | -------------------------------------------- |
| `base_url`     | string | The server address                           |
| `id`           | number | The genre's unique ID                        |

### Headers

_None_

### Body

_None_

## Response status codes

| Status code   | Description           |
| ------------- | --------------------- |
| 200           | Success               |
| 404           | Resource ID not found |
| ECONNREFUSED  | Restart the service   |

## Example

Here is an example cURL request and `200 OK` response.

### Example `cURL` request

```shell
curl -X GET http://localhost:3000/genres/1 
# Get details for the genre with an ID of 1
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
}
```
