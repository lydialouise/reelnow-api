---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 2
parent: The `showtime` resource
title: Get showtime details
# vale  on
# markdownlint-enable
---

# Get showtime details
{: .no_toc }

```shell
GET {base_url}/showtimes/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the showtime's unique ID
```

Get details for a specific `showtime` registered in the ReelNow database.

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
| `id`           | number | The showtime's unique ID                        |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code   | Description           |
| :------------ | :-------------------- |
| 200           | Success               |
| 404           | Resource ID not found |
| ECONNREFUSED  | Restart the service   |

## Example

Here is an example cURL request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X GET http://localhost:3000/showtimes/1 
# Get details for the showtime with "id": 1
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
}
```
