---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 1
parent: The `showtime` resource
title: Get all showtimes
# vale  on
# markdownlint-enable
---

# Get all showtimes
{: .no_toc }

```shell
GET {base_url}/showtimes
# Replace <{base_url}> with <http://localhost:3000>
```

Get all `showtimes` registered in the ReelNow database.

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

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X GET http://localhost:3000/showtimes 
# Get all showtimes in the database
```

### Example response
{: .no_toc }

{: .d-inline-block }

200
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
},
{
    "movieId": 2,
    "theatreId": 3,
    "date": "2025-11-11",
    "times": [
        "12:30 PM",
        "3:00 PM",
        "6:30 PM",
        "9:00 PM"
    ],
    "availableSeats": 100,
    "id": 2
},
{
    "movieId": 3,
    "theatreId": 3,
    "date": "2025-11-11",
    "times": [
        "12:30 PM",
        "3:00 PM",
        "6:30 PM",
        "9:00 PM"
    ],
    "availableSeats": 50,
    "id": 3
},
{
    "movieId": 4,
    "theatreId": 4,
    "date": "2025-11-11",
    "times": [
        "12:30 PM",
        "3:00 PM",
        "6:30 PM",
        "9:00 PM"
    ],
    "availableSeats": 75,
    "id": 4
}
```
