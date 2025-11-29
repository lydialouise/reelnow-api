---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 3
parent: The `movie` resource
title: Create a movie
# vale  on
# markdownlint-enable
---

# Create a movie
{: .no_toc }

```shell
POST {base_url}/movies
# Replace <{base_url}> with <http://localhost:3000>
```

Register a new `movie` in the ReelNow database.

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

| Parameter        | Format  | Description                                          |
| :--------------- | :------ | :--------------------------------------------------- |
| `title`          | string  | The name of the movie                                |
| `releaseDate`    | string  | The movie theatre release date                       |
| `genreId`        | number  | The genre's unique ID                                |
| `rating`         | string  | The Motion Picture Association film rating           |
| `runtimeMinutes` | number  | The length of the movie in minutes                   |
| `status`         | string  | The release status                                   |
| `isInTheatres`   | boolean | The flag showing whether the movie is in theatres    |
| `id`             | number  | The movie's unique ID                                |

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
curl -X POST "http://localhost:3000/movies" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Inception",
    "releaseDate": "2010-07-16",
    "genreId": 4,
    "rating": "PG-13",
    "runtimeMinutes": 148,
    "status": "released",
    "isInTheatres": false
  }'
# Create a new movie and add related properties
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 15,
  "title": "Inception",
  "releaseDate": "2010-07-16",
  "genreId": 4,
  "rating": "PG-13",
  "runtimeMinutes": 148,
  "status": "released",
  "isInTheatres": false
}
```
