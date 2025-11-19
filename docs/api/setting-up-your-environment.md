---
layout: default
title: Setting up your environment
nav_order: 2
has_children: true
has_toc: false
---

# Setting up your environment

To get started using the ReelNow API, you'll need:

* A [GitHub](https://github.com/) account
* A fork of the [`reelnow-api` repository](https://github.com/lydialouise/reelnow-api) cloned to your machine
* Version 0.17.4 or higher of the [`json-server` application](https://www.npmjs.com/package/json-server) installed on your machine
* Command-line [Git](https://docs.github.com/en/get-started/quickstart/set-up-git) installed on your machine
* A current or LTS version of [`node.js`](https://nodejs.org/en/download) installed on your machine

## Step 1: Start the local service

From your terminal (Linux) or in Git Bash (Windows), start the `json-server` application by running the following commands:

```shell
cd <your-github-workspace>/reelnow-api/api
# Replace <your-github-workspace> with your actual path

json-server -w reelnow-db-source.json
```

## Step 2: Confirm that the JSON server is watching the database

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

If the output does not match, see [Troubleshooting](./troubleshooting.md).
