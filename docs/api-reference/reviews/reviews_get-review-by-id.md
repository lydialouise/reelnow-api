---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 2
parent: The `review` resource
title: Get review details
# tags used by AI files
# vale  on
# markdownlint-enable
---

# Get review details
{: .no_toc }

```shell
GET {base_url}/reviews/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the review's unique ID
```

Get details for a specific `review` registered in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Read         |

## Path parameters

| Parameter  | Format | Description            |
| :--------- | :----- | :--------------------- |
| `base_url` | string | The server address     |
| `id`       | number | The review's unique ID |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code  | Description                    |
| :----------- | :----------------------------- |
| 200          | Resource successfully returned |
| 404          | Resource ID not found          |
| ECONNREFUSED | Restart the service            |

## Example

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X GET http://localhost:3000/reviews/1 
# Get details for the review with "id": 1
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
