---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 4
parent: The `review` resource
title: Update a review
# vale  on
# markdownlint-enable
---

# Update a review
{: .no_toc }

```shell
PATCH {base_url}/reviews/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the review's unique ID
```

Update an existing `review` in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Write        |

## Path parameters

| Parameter  | Format | Description            |
| :--------- | :----- | :--------------------- |
| `base_url` | string | The server address     |
| `id`       | number | The review's unique ID |

## Request header parameters

| Parameter      | Format | Description                |
| :------------- | :----- | :------------------------- |
| `Content-Type` | string | The parameter content type |

## Request body parameters

| Parameter     | Format | Description                                                                  |
| :------------ | :----- | :--------------------------------------------------------------------------- |
| `source`      | string | The platform providing the rating                                            |
| `score`       | number | The review score calculated on a scale of 1–100, where 100 is highest rating |
| `reviewCount` | number | The total number of reviews contributing to the score                        |

## Response status codes

| Status code  | Description                   |
| :----------- | :---------------------------- |
| 200          | Resource successfully updated |
| 404          | Resource ID not found         |
| ECONNREFUSED | Restart the service           |

<!-- *NOTE* Consider a seperate error page (see Stripe docs) -->

## Example

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X PATCH "http://localhost:3000/reviews/1" \
  -H "Content-Type: application/json" \
  -d '{
    "score": 91,
    "reviewCount": 134,
    "source": "Rotten Tomatoes"
  }'
# Update the review with "id": 1
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
