---
# markdownlint-disable
# vale  off
has_children: true
has_toc: false
layout: default
nav_order: 2
parent: API reference
title: The `movie` resource
# vale  on
# markdownlint-enable
---

# The `movie` resource

```shell
/movies
```

The `movie` resource represents a movie registered in the ReelNow database.

## Properties

| Property         | Type     | Description                                                         |
| :--------------- | :------- | :------------------------------------------------------------------ |
| `title`          | string   | The name of the movie                                               |
| `releaseDate`    | string   | The movie's theatre release date                                    |
| `genreId`        | number[] | A list of genre IDs associated with the movie                       |
| `rating`         | string   | The [MPA film rating](https://www.motionpictures.org/film-ratings/) |
| `runtimeMinutes` | number   | The movie's length in minutes                                       |
| `status`         | string   | The release status                                                  |
| `isInTheatres`   | boolean  | The flag showing whether the movie is in theatres                   |
| `id`             | number   | The movie's unique ID                                               |

## Related endpoints

| Path                            | Description                                    |
| :------------------------------ | :--------------------------------------------- |
| `GET` {base_url}/movies         | [Get all movies](movies_get-all-movies.md)     |
| `GET` {base_url}/movies/{id}    | [Get movie details](movies_get-movie-by-id.md) |
| `POST` {base_url}/movies        | [Create a movie](movies_create-a-movie.md)     |
| `PATCH` {base_url}/movies/{id}  | [Update a movie](movies_update-a-movie.md)     |
| `DELETE` {base_url}/movies/{id} | [Delete a movie](movies_delete-a-movie.md)     |
