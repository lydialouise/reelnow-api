---
# markdownlint-disable
# vale  off
layout: default
nav_order: 4
parent: Tutorials
title: Filter movies by audience
# vale  on
# markdownlint-enable
---

# Filter movies by audience
{: .no_toc }

Filter by genre and rating to find age-appropriate films for your viewers. 👪 Combine multiple query parameters to filter movies for specific audiences so you can build age-appropriate movie listings and curated content experiences.

You'll learn how to:

* Get a list of genres in the database
* Filter movies by genre and rating

This tutorial takes about 15 minutes to complete.

1. TOC
{:toc}

## Before you start

Before starting this tutorial, you'll need to:

* [Prepare your environment](../getting-started.md#step-1-prepare-your-environment)
* [Start the API service](../getting-started.md#step-2-start-the-api-service)
* [Understand the base URL for API calls](../getting-started.md#step-3-understand-the-base-url-for-api-calls)

## Step 1: Get a list of genres in the database

Start by retrieving the full list of genres from the ReelNow database. In your terminal, run the following command:

```shell
curl -X GET http://localhost:3000/genres 
# Get all genres in the database
```

This returns a list of all genres currently in the database:

```js
{
  "name": "family",
  "description": "Content suitable for children and adults; typically animated or light-hearted live action.",
  "id": 1
},
{
  "name": "fantasy",
  "description": "Stories set in imaginary worlds or involving magical elements, mythical creatures, or supernatural forces.",
  "id": 2
},
{
  "name": "action",
  "description": "Fast-paced, high-energy films featuring physical stunts, chases, combat, and special effects.",
  "id": 3
},
{
  "name": "sci-fi",
  "description": "Stories centered around futuristic science, technology, space exploration, or parallel realities.",
  "id": 4
},
{
  "name": "comedy",
  "description": "Light-hearted and humorous stories designed to entertain and amuse, often through wit, satire, or playful characters.",
  "id": 5
},
{
  "name": "horror",
  "description": "Atmospheric and suspenseful films that evoke fear or tension through dread, shock, or the supernatural.",
  "id": 6
},
{
  "name": "romance",
  "description": "Emotionally driven stories that explore love, relationships, and human connection, often focusing on personal growth and heartfelt moments.",
  "id": 7
},
{
  "name": "thriller",
  "description": "Tense, suspense-filled stories that keep audiences guessing.",
  "id": 8
}
```

You'll use the genre `"id":` values to filter movies based on audience.

## Step 2: Filter movies by genre and rating

Next, use the `genreId` and `rating` query parameters to find movies with genres and [MPA film ratings](https://www.motionpictures.org/film-ratings/) that are appropriate for young children to watch without parental supervision.

For this purpose, you'll:

* Exclude movies with `"genreId": 6` (horror)
* Include only movies with `"rating": ["G", "PG"]` (General Audiences, Parental Guidance Suggested)

In your terminal, run the following command:

```shell
curl -X GET "http://localhost:3000/movies?genreId=1&genreId=2&genreId=3genreId=4&genreId=5&&genreId=7&genreId=8&rating=G&rating=PG"
# Get movies with "genreId": [1, 2, 3, 4, 5, 7, 8] and "rating"=["G", "PG"]
```

This returns all non-horror movies intended for general audiences:

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
}
```

## Next steps

Now that you understand filtering with query parameters, try experimenting:

* Find all comedies that are appropriate for teenagers.
* Discover which R-rated movies are currently in theatres.

## Further reading

* [The `genre` resource](../api-reference/genres/genres.md)
* [MPA film ratings](https://www.motionpictures.org/film-ratings/)
* [Tutorials](index.md)
