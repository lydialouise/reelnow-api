---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 4
parent: The `movie` resource
title: Update a movie
# vale  on
# markdownlint-enable
---

# Update a movie
{: .no_toc }

```shell
PATCH {base_url}/movies/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the movie's unique ID
```

Update an existing `movie` in the ReelNow database.

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
| `id`           | number | The movie's unique ID                        |

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
curl -X PATCH "http://localhost:3000/movies/1" \
  -H "Content-Type: application/json" \
  -d '{
    "rating": "PG-13",
    "runtimeMinutes": 125,
    "status": "released",
    "releaseDate": "2025-10-17"
  }'
# Update the movie with "id": 1
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 12,
  "title": "Tron: Ares",
  "releaseDate": "2025-10-17",
  "genreId": 1,
  "rating": "PG-13",
  "runtimeMinutes": 125,
  "status": "released"
}
```
