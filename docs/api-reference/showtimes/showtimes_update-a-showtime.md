---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 4
parent: The `showtime` resource
title: Update a showtime
# vale  on
# markdownlint-enable
---

# Update a showtime
{: .no_toc }

```shell
PATCH {base_url}/showtimes/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the showtime's unique ID
```

Update an existing `showtime` in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Write        |

## Path parameters

| Parameter  | Format | Description              |
| :--------- | :----- | :----------------------- |
| `base_url` | string | The server address       |
| `id`       | number | The showtime's unique ID |

## Request header parameters

| Parameter      | Format | Description                |
| :------------- | :----- | :------------------------- |
| `Content-Type` | string | The parameter content type |

## Request body parameters

| Parameter        | Format | Description                                                        |
| :--------------- | :----- | :----------------------------------------------------------------- |
| `movieId`        | number | The movie's unique ID                                              |
| `theatreId`      | number | The theatre's unique ID                                            |
| `date`           | string | The date of the showings in ISO 8601 format                        |
| `times`          | array  | A list of showtimes on the date in 12-hour clock format            |
| `availableSeats` | number | The number of seats currently available for booking at the theatre |

## Response status codes

| Status code  | Description                   |
| ------------ | ----------------------------- |
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
# Update the showtime with "id": 1
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
