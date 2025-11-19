---
# markdownlint-disable
# vale  off
layout: default
title: The `showtime` resource
parent: API reference
nav_order: 
has_children: true
has_toc: false
# tags used by AI files
description: Information about the `showtime` resource
tags: 
    - api
categories:
    - api-reference
ai_relevance: high
importance: 8
prerequisites: []
related_pages: []
examples: []
api_endpoints: 
    - /showtimes
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# The `showtime` resource
{: .no_toc }

```shell
/showtimes
```

The `showtime` resource represents a showtime registered in the ReelNow database.

1. TOC
{:toc}

## Properties

| Property name    | Type   | Description                                                        |
| ---------------- | ------ | ------------------------------------------------------------------ |
| `movieId`        | number | The unique ID of the movie                                         |
| `theatreId`      | number | The unique ID of the theatre                                       |
| `date`           | string | The date of the showings in ISO 8601 format                        |
| `times`          | array  | A list of showtimes on the date in 12-hour clock format            |
| `availableSeats` | number | The number of seats currently available for booking at the theatre |
| `id`             | number | The showtime's unique ID                                           |

## Related endpoints

| Path                                  | Description                                                                 |
| ------------------------------------- | --------------------------------------------------------------------------- |
| `GET` {base_url}/showtimes            | [List all showtimes](showtimes_get-all-showtimes.md)                        |
| `GET` {base_url}/showtimes/{id}       | [Get details for a specific showtime](showtimes_get-showtime-by-id.md)      |
| `POST` {base_url}/showtimes           | [Create a showtime](showtimes_create-a-showtime.md)                         |
| `PATCH` {base_url}/showtimes/{id}     | [Update a showtime](showtimes_update-a-showtime.md)                         |
| `DELETE` {base_url}/showtimes/{id}    | [Delete a showtime](showtimes_delete-a-showtime.md)                         |
