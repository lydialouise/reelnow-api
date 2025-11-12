---
# markdownlint-disable
# vale  off
layout: default
title: The `movie` resource
parent: API reference
nav_order: 
has_children: true
has_toc: false
# tags used by AI files
description: Information about the `movie` resource
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
    - /movies
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# The `movie` resource

```shell
/movies
```

The `movie` resource represents a movie registered in the ReelNow database.

## Properties

| Property         | Type        | Description                                          |
| ---------------- | ----------- | ---------------------------------------------------- |
| `title`          | string      | The name of the movie                                |
| `releaseDate`    | string      | The movie theater release date                       |
| `genreId`        | number      | The genre's unique ID                                |
| `rating`         | string      | The Motion Picture Association film rating           |
| `runtimeMinutes` | number      | The length of the movie in minutes                   |
| `status`         | string      | The release status                                   |
| `isInTheaters`   | boolean     | The flag showing whether the movie is in theaters    |
| `id`             | number      | The movie's unique ID                                |

## Related endpoints

| Path                                 | Description                         |
| ------------------------------------ | ----------------------------------- |
| `GET` {base_url}/movies                | [List all movies](movies_get-all-movies.md)                    |
| `GET` {base_url}/movies/{id}           | [Get details for a specific movie](movies_get-movie-by-id.md)    |
| `GET` {base_url}/movies/{id}/reviews   | [List reviews for a specific movie](movies_get-reviews-by-id.md)   |
| `GET` {base_url}/movies/{id}/showtimes | [List showtimes for a specific movie](movies_get-showtimes-by-id.md) |
