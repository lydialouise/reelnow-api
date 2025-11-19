---
# markdownlint-disable
# vale  off
layout: default
title: Update a showtime
parent: The `showtime` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: PATCH a `showtime` resource in the database
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
    - PATCH /showtimes/{id}
version: "v1.0"
last_updated: "2025-11-20"
# vale  on
# markdownlint-enable
---

# Update a showtime
{: .no_toc }

```shell
PATCH {base_url}/showtimes/{id}
# Replace {base_url} with the server address
```

<!-- *NOTE* explain what server address is (localhost) in setting-up-your-environment page. -->

Update an existing `showtime` in the ReelNow database.

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
| `id`           | number | The showtime's unique ID                     |

## Request header parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `Content-Type` | string | The parameter content type                   |

## Request body parameters

| Parameter        | Format  | Description                                                        |
| :--------------- | :------ | :----------------------------------------------------------------- |
| `movieId`        | number  | The unique ID of the movie                                         |
| `theatreId`      | number  | The unique ID of the theatre                                       |
| `date`           | string  | The date of the showings in ISO 8601 format                        |
| `times`          | array   | A list of showtimes on the date in 12-hour clock format            |
| `availableSeats` | number  | The number of seats currently available for booking at the theatre |

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
curl -X PATCH "http://localhost:3000/showtimes/1" \
  -H "Content-Type: application/json" \
  -d '{
    "times": [
      "1:00 PM",
      "4:00 PM",
      "7:30 PM"
    ],
    "availableSeats": 120
  }'
# Update the showtime with ID = 1
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 1,
  "movieId": 1,
  "theatreId": 1,
  "date": "2025-11-11",
  "times": [
    "1:00 PM",
    "4:00 PM",
    "7:30 PM"
  ],
  "availableSeats": 120
}
```
