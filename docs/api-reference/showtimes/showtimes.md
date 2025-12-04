---
# markdownlint-disable
# vale  off
has_children: true
has_toc: false
layout: default
nav_order: 4
parent: API reference
title: The `showtime` resource
# vale  on
# markdownlint-enable
---

# The `showtime` resource

```shell
/showtimes
```

The `showtime` resource represents a showtime registered in the ReelNow database.

## Properties

| Property name    | Type     | Description                                                        |
| :--------------- | :------- | :----------------------------------------------------------------- |
| `movieId`        | number   | The movie's unique ID                                              |
| `theatreId`      | number   | The theatre's unique ID                                            |
| `date`           | string   | The date of the showings in ISO 8601 format                        |
| `times`          | string[] | A list of showtimes on the date in 12-hour clock format            |
| `availableSeats` | number   | The number of seats currently available for booking at the theatre |
| `id`             | number   | The showtime's unique ID                                           |

## Related endpoints

| Path                               | Description                                             |
| :--------------------------------- | :------------------------------------------------------ |
| `GET` {base_url}/showtimes         | [Get all showtimes](showtimes_get-all-showtimes.md)     |
| `GET` {base_url}/showtimes/{id}    | [Get showtime details](showtimes_get-showtime-by-id.md) |
| `POST` {base_url}/showtimes        | [Create a showtime](showtimes_create-a-showtime.md)     |
| `PATCH` {base_url}/showtimes/{id}  | [Update a showtime](showtimes_update-a-showtime.md)     |
| `DELETE` {base_url}/showtimes/{id} | [Delete a showtime](showtimes_delete-a-showtime.md)     |
