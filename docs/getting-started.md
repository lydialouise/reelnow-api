---
# markdownlint-disable
# vale  off
layout: page
nav_order: 2
title: Getting started
# vale  on
# markdownlint-enable
---

# Getting started
{: .no_toc }

Find everything you need to start using the ReelNow API in 15 minutes or less. Learn how to prepare your environment, start the API service, and make your first API call.

1. TOC
{:toc}

## Step 1: Prepare your environment

Before using ReelNow, you'll need:

* A [GitHub](https://github.com/) account
* Command-line [Git](https://docs.github.com/en/get-started/quickstart/set-up-git)
* A fork and clone of the [reelnow-api repository](https://github.com/lydialouise/reelnow-api)
* The [json-server](https://www.npmjs.com/package/json-server) app version 0.17.4 or higher
* A current or LTS version of [node.js](https://nodejs.org/en/download)

## Step 2: Start the API service

You'll use the json-server app to test API calls locally.

From a terminal, start the `json-server` app by running the following command:

```shell
cd <your-github-workspace>/reelnow-api/api
# Replace <your-github-workspace> with your actual path

json-server -w reelnow-db-source.json
```

Confirm that the JSON server output matches the following:

```shell
\{^_^}/ hi!

Loading reelnow-db-source.json
Done

Resources
http://localhost:3000/movies
http://localhost:3000/reviews
http://localhost:3000/showtimes
http://localhost:3000/theatres
http://localhost:3000/genres

Home
http://localhost:3000
```

## Step 3: Understand the base URL for API calls

The `{base_url}` variable is used when making API calls and represents the main address of the API.

To test API calls locally, replace `{base_url}` with `http://localhost:3000`.

## Step 4: Make your first API call

In a terminal, run the following command:

```shell
curl -X GET http://localhost:3000/genres/1
# Get details for the genre with "id": 1
```

This returns a JSON object for the genre with `"id": 1`:

```json
{
    "name": "family",
    "description": "Content suitable for children and adults; typically animated or light-hearted live action.",
    "id": 1
}
```

## Next steps

Now that you’ve made your first API call, you're ready to get started with [Tutorials](./tutorials.md).

## Further reading

* [About the ReelNow API](index.md)
