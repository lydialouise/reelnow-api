---
# markdownlint-disable
# vale  off
layout: default
title: Update a review
parent: The `review` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: PATCH a `review` resource in the database
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
    - PATCH /reviews/{id}
version: "v1.0"
last_updated: "2025-11-20"
# vale  on
# markdownlint-enable
---

# Update a review
{: .no_toc }

```shell
PATCH {base_url}/reviews/{id}
# Replace {base_url} with the server address
```

<!-- *NOTE* explain what server address is (localhost) in setting-up-your-environment page. -->

Update an existing `review` in the ReelNow database.

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
| `id`           | number | The review's unique ID                        |

## Request header parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `Content-Type` | string | The parameter content type                   |

## Request body parameters

| Parameter      | Format | Description                                                             |
| :------------- | :----- | :---------------------------------------------------------------------- |
| `source`      | string | The platform providing the rating                                        |
| `score`       | number | The review score calculated on a scale of 1–100, where 100 is highest rating |
| `reviewCount` | number | The total number of reviews contributing to the score                    |

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
curl -X PATCH "http://localhost:3000/reviews/12" \
  -H "Content-Type: application/json" \
  -d '{
    "score": 91,
    "reviewCount": 134,
    "source": "Rotten Tomatoes"
  }'
# Update the review with ID = 12
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 12,
  "movieId": 5,
  "source": "Rotten Tomatoes",
  "score": 91,
  "reviewCount": 134
}
```
