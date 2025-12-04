---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 2
parent: The `movie` resource
title: Get movie details
# vale  on
# markdownlint-enable
---

# Get movie details
{: .no_toc }

```shell
GET {base_url}/genres/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the movie's unique ID
```

Get details for a specific `movie` registered in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Read         |

## Path parameters

| Parameter  | Format | Description           |
| :--------- | :----- | :-------------------- |
| `base_url` | string | The server address    |
| `id`       | number | The movie's unique ID |

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

Here is an example cURL request and `200 OK` response.

### Example request
{: .no_toc }

```shell
curl -X GET http://localhost:3000/movies/1 
# Get details for the movie with "id": 1
```

### Example response
{: .no_toc }

{: .d-inline-block }

200
{: .label .label-green }

```js
{
  "title": "Zootopia 2",
  "releaseDate": "2025-11-26",
  "genreId": [1, 5],
  "rating": "PG",
  "runtimeMinutes": 107,
  "status": "upcoming",
  "isInTheatres": false,
  "id": 1
}
```
