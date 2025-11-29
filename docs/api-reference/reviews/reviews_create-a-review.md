---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 3
parent: The `review` resource
title: Create a review
# vale  on
# markdownlint-enable
---

# Create a review
{: .no_toc }

```shell
POST {base_url}/reviews
# Replace <{base_url}> with <http://localhost:3000>
```

Register a new `review` in the ReelNow database.

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

| Parameter     | Format | Description                                                              |
| :------------ | :----- | :----------------------------------------------------------------------- |
| `movieId`     | number | The movie's unique ID                                                    |
| `source`      | string | The platform providing the rating                                        |
| `score`       | number | The review score calculated on a scale of 1–100, where 100 is highest rating |
| `reviewCount` | number | The total number of reviews contributing to the score                    |
| `id`          | number | The review's unique ID                                                   |

## Response status codes

| Status code   | Description          |
| :------------ | :------------------- |
| 200           | Success              |
| 404           | Resource not found   |
| ECONNREFUSED  | Restart the service  |

<!-- *NOTE* Consider a seperate error page (see Stripe docs) -->

## Example

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X POST "http://localhost:3000/reviews" \
  -H "Content-Type: application/json" \
  -d '{
    "movieId": 15,
    "source": "Rotten Tomatoes",
    "score": 57,
    "reviewCount": 40"
  }'
# Create a new review and add related properties
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 88,
  "movieId": 15,
  "source": "Rotten Tomatoes",
  "score": 57,
  "reviewCount": 40"
}
```
