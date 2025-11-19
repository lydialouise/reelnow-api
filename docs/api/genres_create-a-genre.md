---
# markdownlint-disable
# vale  off
layout: default
title: Update a genre
parent: The `genre` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: PATCH a `genre` resource in the database
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
    - PATCH /genres
version: "v1.0"
last_updated: "2025-11-20"
# vale  on
# markdownlint-enable
---

# Update a genre
{: .no_toc }

```shell
PATCH {base_url}/genres
# Replace {base_url} with the server address
```

<!-- *NOTE* explain what server address is (localhost) in setting-up-your-environment page. -->

Update an existing `genre` in the ReelNow database.

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

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `name`         | string | The name of the genre                        |
| `description`  | string | A short description of the genre             |

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
curl -X POST "http://localhost:3000/genres" \
  -H "Content-Type: application/json" \
  -d '{"name":"thriller","description":"Tense, suspense-filled stories that keep audiences guessing."}'
# Create a genre
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "name": "thriller",
  "description": "Tense, suspense-filled stories that keep audiences guessing.",
  "id": 8
}
```
