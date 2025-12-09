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

Filter by genre and rating to find age-appropriate films for your viewers. 👪 Combine multiple query parameters to filter movies for specific audiences, customize movie listings, and curate content experiences.

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

* Include movies with `"genreId": 1` (family)
* Include movies with `"rating": ["G", "PG"]` (General Audiences, Parental Guidance Suggested)

Use the `_like` query operator to match a substring inside a field type that may contain multiple values, like an array.

| Field type | Sample field        | Query example     | Description                                        |
| :--------- | :------------------ | :---------------- | :------------------------------------------------- |
| Scalar     | `"rating": "PG"`    | `?rating=PG`      | Matches exactly `"PG"`                             |
| Array      | `"genreId": [1, 5]` | `?genreId_like=1` | Matches any movie where `"1"` appears in the array |

In your terminal, run the following command:

```shell
curl -X GET "http://localhost:3000/movies?genreId_like=1&rating_like=G&rating_like=PG"
# Get movies with "genreId": 1 and "rating"="G" or "rating"="PG"
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

Now that you know how to filter using query parameters and operators, try experimenting:

* Find all comedies that are appropriate for teenagers.
* Discover which R-rated movies are currently in theatres.

## Further reading

* [The `genre` resource](../api-reference/genres/genres.md)
* [MPA film ratings](https://www.motionpictures.org/film-ratings/)
* [Tutorials](index.md)
