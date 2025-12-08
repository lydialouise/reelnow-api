---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 1
parent: The `review` resource
title: Get all reviews

# vale  on
# markdownlint-enable
---

# Get all reviews
{: .no_toc }

```shell
GET {base_url}/reviews
# Replace <{base_url}> with <http://localhost:3000>
```

Get all `reviews` registered in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Read         |

## Path parameters

| Parameter  | Format | Description        |
| :--------- | :----- | :----------------- |
| `base_url` | string | The server address |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code  | Description                |
| ------------ | -------------------------- |
| 200          | List successfully returned |
| ECONNREFUSED | Restart the service        |

## Example

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X GET http://localhost:3000/reviews 
# Get all reviews in the database
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
