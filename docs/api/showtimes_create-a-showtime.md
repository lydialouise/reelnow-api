---
# markdownlint-disable
# vale  off
layout: default
title: Create a showtime
parent: The `showtime` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: POST a `showtime` resource in the database
tags:
    - api
categories:
    - api-reference
ai_relevance: high
importance: 7
prerequisites:
    - /api/showtimes
related_pages: []
examples: []
api_endpoints: 
    - POST /showtimes
version: "v1.0"
last_updated: "2025-11-19"
# vale  on
# markdownlint-enable
---

# Create a showtime
{: .no_toc }

```shell
POST {base_url}/showtimes
# Replace {base_url} with the server address
```

<!-- *NOTE* explain what server address is (localhost) in setting-up-your-environment page. -->

Register a new `showtime` in the ReelNow database.

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

| Parameter        | Format  | Description                                                        |
| ---------------- | ------- | ------------------------------------------------------------------ |
| `movieId`        | number  | The unique ID of the movie                                         |
| `theatreId`      | number  | The unique ID of the theatre                                       |
| `date`           | string  | The date of the showings in ISO 8601 format                        |
| `times`          | array   | A list of showtimes on the date in 12-hour clock format            |
| `availableSeats` | number  | The number of seats currently available for booking at the theatre |
| `id`             | number  | The showtime's unique ID                                           |


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
curl -X POST "http://localhost:3000/showtimes" \
  -H "Content-Type: application/json" \
  -d '{
    "movieId": 1,
    "theatreId": 1,
    "date": "2025-11-11",
    "times": [
      "12:30 PM",
      "3:00 PM",
      "6:30 PM",
      "9:00 PM"
    ],
    "availableSeats": 150
  }'
# Create showtime for a specific movie at a specific theatre on a given date

```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "movieId": 1,
  "theatreId": 1,
  "date": "2025-11-11",
  "times": [
    "12:30 PM",
    "3:00 PM",
    "6:30 PM",
    "9:00 PM"
  ],
  "availableSeats": 150,
  "id": 1
}
```
