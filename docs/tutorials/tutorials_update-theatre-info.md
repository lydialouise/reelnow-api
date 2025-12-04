---
# markdownlint-disable
# vale  off
layout: default
nav_order: 3
parent: Tutorials
title: Update theatre information
# vale  on
# markdownlint-enable
---

# Update theatre information
{: .no_toc }

Update location and contact information for all theatres to guide audiences to the perfect screen. 📍

You'll learn how to:

* Get a list of theatres in the database
* Update location and contact information for a theatre
* Understand theatre properties

This tutorial takes about 15 minutes to complete.

1. TOC
{:toc}

## Before you start

Before starting this tutorial, you'll need to:

* [Prepare your environment](../getting-started.md#step-1-prepare-your-environment)
* [Start the API service](../getting-started.md#step-2-start-the-api-service)
* [Understand the base URL for API calls](../getting-started.md#step-3-understand-the-base-url-for-api-calls)

## Step 1: Get a list of theatres in the database

Start by retrieving the full list of theatres from the ReelNow database. In your terminal, run the following command:

```shell
curl -X GET http://localhost:3000/theatres 
# Get all theatres in the database
```

This returns a list of all theatres currently in the database:

```js
{
  "name": "Ciniplex Downtown",
  "address": "123 Main St",
  "city": "Montreal",
  "province": "QC",
  "postalCode": "H3A 1B2",
  "phone": "123-456-7890",
  "website": "https://cineplexdowntown.example.com",
  "id": 1
},
{
  "name": "Famous Players",
  "address": "456 Wellington St",
  "city": "Ottawa",
  "province": "ON",
  "postalCode": "K1A 0B1",
  "phone": "123-456-7890",
  "website": "https://famousplayers.example.com",
  "id": 2
},
{
  "name": "Landmark Cinemas",
  "address": "789 Granville St",
  "city": "Vancouver",
  "province": "BC",
  "postalCode": "V6C 1T2",
  "phone": "123-456-7890",
  "website": "https://landmarkcinemas.example.com",
  "id": 3
},
{
  "name": "Cinemark",
  "address": "101 King St",
  "city": "Toronto",
  "province": "ON",
  "postalCode": "M5H 1A1",
  "phone": "123-456-7890",
  "website": "https://cinemark.example.com",
  "id": 4
}
```

## Step 2: Find details for a specific movie

Next, update the phone number and website for the theatre with `"id": 1`.

In your terminal, run the following command:

```shell
curl -X PATCH "http://localhost:3000/theatres/1" \
  -H "Content-Type: application/json" \
  -d '{
    "phone": "987-654-3210",
    "website": "https://cineplexmontreal.example.com"
  }'
# Update details for the theatre with "id": 1
```

This updates the phone number and website for the theatre with `"id": 1`. Other information remains unchanged:

```js
{
  "name": "Ciniplex Downtown",
  "address": "123 Main St",
  "city": "Montreal",
  "province": "QC",
  "postalCode": "H3A 1B2",
  "phone": "987-654-3210",
  "website": "https://cineplexmontreal.example.com",
  "id": 1
}
```

## Step 3: Understand theatre properties

To understand what each property means, check the description under [The `theatre` resource properties](../api-reference/theatres/theatres.md).

Based on these properties:

* What's the theatre name and address?
* What's the updated phone number and website?

Observe the JSON response for the movie with `"id": 2`:

* The theatre `name` is Ciniplex Downtown and `address` is 123 Main St.
* The updated `phone` number is 987-654-3210 and `website` is `https://cineplexmontreal.example.com`.

## Next steps

Now that you know how to update details for a specific resource, try experimenting:

* Update any address properties to reflect a new location.
* Check your updates using the `GET /theatres/{id}` method.

## Further reading

* [The `theatre` resource](../api-reference/theatres/theatres.md)
* [Tutorials](index.md)
