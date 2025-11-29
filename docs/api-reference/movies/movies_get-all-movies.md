---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 1
parent: The `movie` resource
title: Get all movies
# vale  on
# markdownlint-enable
---

# Get all movies
{: .no_toc }

```shell
GET {base_url}/movies
# Replace <{base_url}> with <http://localhost:3000>
```

Get all `movies` registered in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description          |
| :------------- | :------------------- |
| Authentication | Access token         |
| Access         | Read                 |

## Path parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `base_url`     | string | The server address                           |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code   | Description          |
| :------------ | :------------------- |
| 200           | Success              |
| 404           | Resource not found   |
| ECONNREFUSED  | Restart the service  |

## Example

Here is an example cURL request and `200 OK` response.

### Example request
{: .no_toc }

```shell
curl -X GET http://localhost:3000/movies 
# Get all movies in the database
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
},
{
  "title": "The Lord of the Rings: The Fellowship of the Ring",
  "releaseDate": "2001-12-28",
  "genreId": [2, 3],
  "rating": "PG-13",
  "runtimeMinutes": 228,
  "status": "re-released",
  "isInTheatres": true,
  "id": 2
},
{
  "title": "John Tucker Must Die",
  "releaseDate": "2006-07-28",
  "genreId": 3,
  "rating": "PG-13",
  "runtimeMinutes": 90,
  "status": "archived",
  "isInTheatres": false,
  "id": 3
},
{
  "title": "Black Phone 2",
  "releaseDate": "2025-10-17",
  "genreId": 6
  "rating": "R",
  "runtimeMinutes": 114,
  "status": "released",
  "isInTheatres": true,
  "id": 4
}
```
