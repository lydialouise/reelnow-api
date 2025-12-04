---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 3
parent: The `showtime` resource
title: Create a showtime
# vale  on
# markdownlint-enable
---

# Create a showtime
{: .no_toc }

```shell
POST {base_url}/showtimes
# Replace <{base_url}> with <http://localhost:3000>
```

Register a new `showtime` in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Write        |

## Path parameters

| Parameter  | Format | Description        |
| :--------- | :----- | :----------------- |
| `base_url` | string | The server address |

## Request header parameters

| Parameter      | Format | Description                |
| :------------- | :----- | :------------------------- |
| `Content-Type` | string | The parameter content type |

## Request body parameters

| Parameter        | Format | Description                                                        |
| :--------------- | :----- | :----------------------------------------------------------------- |
| `movieId`        | number | The unique ID of the movie                                         |
| `theatreId`      | number | The unique ID of the theatre                                       |
| `date`           | string | The date of the showings in ISO 8601 format                        |
| `times`          | array  | A list of showtimes on the date in 12-hour clock format            |
| `availableSeats` | number | The number of seats currently available for booking at the theatre |
| `id`             | number | The showtime's unique ID                                           |

## Response status codes

| Status code  | Description                   |
| ------------ | ----------------------------- |
| 201          | Resource successfully updated |
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
# Create a new showtime and add related properties

```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 1
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
}
```
