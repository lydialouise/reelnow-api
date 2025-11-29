---
# markdownlint-disable
# vale  off
layout: default
nav_order: 1
parent: Tutorials
title: Check movie details
# vale  on
# markdownlint-enable
---

Tutorials

# Check movie details
{: .no_toc }

Check `/movies{id}` to find movie information, like genre, rating, and reviews. 📋 Enhance your database with rich movie data to power personalized recommendations, build detailed movie pages, and ensure your app has accurate information.

You'll learn how to:

* Get a list of movies in the database
* Find details for a specific movie
* Understand movie properties

This tutorial takes about 15 minutes to complete.

1. TOC
{:toc}

## Before you start

Before starting this tutorial, you'll need to:

* [Prepare your environment](../getting-started.md#step-1-prepare-your-environment)
* [Start the API service](../getting-started.md#step-2-start-the-api-service)
* [Understand the base URL for API calls](../getting-started.md#step-3-understand-the-base-url-for-api-calls)

## Step 1: Get a list of movies in the database

Start by retrieving the full list of movies from the ReelNow database. In your terminal, run the following command:

```shell
curl -X GET http://localhost:3000/movies 
# Get all movies in the database
```

This returns a list of all movies currently in the database:

```js
{
  "title": "Zootopia 2",
  "releaseDate": "2025-11-26",
  "genreId": [1, 5],
  "rating": "PG",
  "runtimeMinutes": 107,
  "status": "upcoming",
  "isInTheatres": false,
  "id": 1
},
{
  "title": "The Lord of the Rings: The Fellowship of the Ring",
  "releaseDate": "2001-12-28",
  "genreId": [2, 3],
  "rating": "PG-13",
  "runtimeMinutes": 228,
  "status": "re-released",
  "isInTheatres": true,
  "id": 2
},
{
  "title": "John Tucker Must Die",
  "releaseDate": "2006-07-28",
  "genreId": 3,
  "rating": "PG-13",
  "runtimeMinutes": 90,
  "status": "archived",
  "isInTheatres": false,
  "id": 3
},
{
  "title": "Black Phone 2",
  "releaseDate": "2025-10-17",
  "genreId": 6
  "rating": "R",
  "runtimeMinutes": 114,
  "status": "released",
  "isInTheatres": true,
  "id": 4
}
```

## Step 2: Find details for a specific movie

Next, find the title and status of the movie with `"id": 2` and confirm whether it's currently playing in theatres.

To focus on a specific movie, use the `movies/{id}` endpoint.

In your terminal, run the following command:

```shell
curl -X GET http://localhost:3000/movies/2
# Get details for the movie with "id": 1
```

This returns details for the movie with `"id": 2`:

```js
{
  "title": "The Lord of the Rings: The Fellowship of the Ring",
  "releaseDate": "2001-12-28",
  "genreId": [2, 3],
  "rating": "PG-13",
  "runtimeMinutes": 228,
  "status": "re-released",
  "isInTheatres": true,
  "id": 2
}
```

## Step 3: Understand movie properties

To understand what each property means, check the description under [The `movies` resource properties](./movies.md#properties).

Based on these properties:

* What's the movie title?
* Is the movie currently playing in theatres?

Observe the JSON response for the movie with `"id": 2`:

* The movie's `title` is `The Lord of the Rings: The Fellowship of the Ring`.
* The `isInTheatres` status is `true`.

## Next steps

Now that you know how to check movie details, try experimenting:

* Find which genres the movie The Lord of the Rings: The Fellowship of the Ring belongs to.
* Check when Zootopia 2 will be released in theatres.
* Find the [MPA film rating](https://www.motionpictures.org/film-ratings/) for Black Phone 2.

## Further reading

* [The `movie` resource](../api-reference/movies/movies.md)
* [MPA film rating](https://www.motionpictures.org/film-ratings/)
* [Tutorials](index.md)
