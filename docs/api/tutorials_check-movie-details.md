---
# markdownlint-disable
# vale  off
layout: default
title: Check movie details
parent: Tutorials
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: Learn how to check movie details
tags:
    - api
categories:
    - api-reference
ai_relevance: high
importance: 7
prerequisites:
    - /api/setting-up-your-environment
    - /api/tutorials
related_pages: []
examples: []
api_endpoints: 
    - 
version: "v1.0"
last_updated: "2025-11-19"
# vale  on
# markdownlint-enable
---

# Tutorial: Check movie details
{: .no_toc }

In this tutorial, you'll learn how to check `/movies{id}` to find movie details, like genre, rating, and reviews.

By enhancing your database with rich movie data, you can:
* Power personalized recommendations.
* Build detailed movie pages.
* Ensure your app has accurate information.

You'll use cURL to send requests and learn how to:

* Find movie details, like genre, rating, and reviews from the JSON response.
* Understand the meaning of each property in [The `movies` resource properties](./movies.md#properties).

This tutorial takes about 15 minutes to complete.

1. TOC
{:toc}

## Before you start

Before you start this tutorial, complete the steps in [Setting up your environment](./setting-up-your-environment.md).

## Step 1: Get a list of movie details

Start by retrieving the full list of movies from the ReelNow database. In your terminal, run the following command:

```shell
curl -X GET http://localhost:3000/movies 
# List all movies
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
  "isIntheatres": false,
  "id": 1
},
{
  "title": "The Lord of the Rings: The Fellowship of the Ring",
  "releaseDate": "2001-12-28",
  "genreId": [2, 3],
  "rating": "PG-13",
  "runtimeMinutes": 228,
  "status": "re-released",
  "isIntheatres": true,
  "id": 2
},
{
  "title": "John Tucker Must Die",
  "releaseDate": "2006-07-28",
  "genreId": 3,
  "rating": "PG-13",
  "runtimeMinutes": 90,
  "status": "archived",
  "isIntheatres": false,
  "id": 3
},
{
  "title": "Black Phone 2",
  "releaseDate": "2025-10-17",
  "genreId": 6
  "rating": "R",
  "runtimeMinutes": 114,
  "status": "released",
  "isIntheatres": true,
  "id": 4
}
```

## Step 2: Find details for a specific movie

Next, find the title and status of the movie with ID = 2 and confirm whether it is currently playing in theatres.

To focus on a specific movie, use the `movies/{id}` endpoint.

In your terminal, run the following command:

```shell
curl -X GET http://localhost:3000/movies/2 
# Get details for the movie with ID = 2
```

This returns details for the movie with ID = 2:

```js
{
  "title": "The Lord of the Rings: The Fellowship of the Ring",
  "releaseDate": "2001-12-28",
  "genreId": [2, 3],
  "rating": "PG-13",
  "runtimeMinutes": 228,
  "status": "re-released",
  "isIntheatres": true,
  "id": 2
}
```

## Step 3: Understand movie properties

To understand what each property means, check the description under [The `movies` resource properties](./movies.md#properties).

Based on [The `movies` resource properties](./movies.md#properties), the JSON response for the movie with ID = 2 shows that:

* The movie's name is `The Lord of the Rings: The Fellowship of the Ring`.
* It is currently being re-released in theatres, as shown by the `status` and `isInTheatres` fields.

## Next steps

Now that you’ve checked movie details, try experimenting:

* Find which genres the movie `The Lord of the Rings: The Fellowship of the Ring` belongs to.
* Check when `Black Phone 2` will be released in theaters.
* Find the MPA film rating for `Black Phone 2`.

## Related pages

* To learn more about the `movie` resource, see [The `movie` resource](./movies.md).
* To try another tutorial in the series, see [Tutorials](./tutorials.md).