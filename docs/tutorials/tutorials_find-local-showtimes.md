---
# markdownlint-disable
# vale  off
layout: default
nav_order: 2
parent: Tutorials
title: Find local showtimes
# vale  on
# markdownlint-enable
---

# Find local showtimes
{: .no_toc }

Find `/showtimes` to help audiences see what's playing at nearby theatres. 🕓 Power local showtime listings, help users plan movie nights, and keep your apps current with all screenings.

You'll learn how to:

* Get a list of showtimes in the database
* Find details for a specific showtime
* Understand showtime properties

This tutorial takes about 15 minutes to complete.

1. TOC
{:toc}

## Before you start

Before starting this tutorial, you'll need to:

* [Prepare your environment](../getting-started.md#step-1-prepare-your-environment)
* [Start the API service](../getting-started.md#step-2-start-the-api-service)
* [Understand the base URL for API calls](../getting-started.md#step-3-understand-the-base-url-for-api-calls)

## Step 1: Get a list of showtimes in the database

Start by retrieving the full list of showtimes from the ReelNow database. In your terminal, run the following command:

```shell
curl -X GET http://localhost:3000/showtimes 
# Get all showtimes in the database
```

This returns a list of all showtimes currently in the database:

```js
{
  "movieId": 1,
  "theatreId": 1,
  "date": "2025-12-15",
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
  "theatreId": 2,
  "date": "2025-12-31",
  "times": [
    "12:30 PM",
    "3:00 PM",
    "6:30 PM",
    "9:00 PM"
  ],
  "availableSeats": 150,
  "id": 2
}
```

## Step 2: Find showtimes for a specific movie

Next, find out where and when the movie with `"id": 1` is playing in theatres. To focus on a specific movie, use the `movieId` query parameter.

In your terminal, run the following command:

```shell
curl -X GET "http://localhost:3000/showtimes?movieId=1"
# Get showtimes for the movie with "id": 1
```

This returns all showtimes for the movie with `"id": 1`:

```js
{
  "movieId": 1,
  "theatreId": 1,
  "date": "2025-12-15",
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

## Step 3: Understand movie properties

To understand what each property means, check the description under [The `showtimes` resource properties](../api-reference/showtimes/showtimes.md).

Based on these properties:

* When are the showtimes for the movie with `"id": 1` on December 15, 2025?
* How many seats are available for the movie with `"id": 1` on December 15, 2025?

Observe the JSON response for the movie with `"id": 1`:

* The `times` property displays four showtimes at `["12:30 PM", "3:00 PM", "6:30 PM", "9:00 PM"]` on `"date": "2025-12-15"`.
* The `availableSeats` property on `"date": "2025-12-15"` shows 50 seats available.

## Next steps

Now that you know how to check movie details, try experimenting:

* Find out which movies are playing at the theatre with `"id": 1` on New Year's Eve.
* Find the number of `availableSeats` for Zootopia 2 on January 15, 2026.

## Further reading

* [The `showtime` resource](../api-reference/movies/movies.md)
* [Tutorials](index.md)
