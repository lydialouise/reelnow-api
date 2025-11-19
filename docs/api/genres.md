---
# markdownlint-disable
# vale  off
layout: default
title: The `genre` resource
parent: API reference
nav_order: 
has_children: true
has_toc: false
# tags used by AI files
description: Information about the `genre` resource
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
    - /genres
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# The `genre` resource
{: .no_toc }

```shell
/genres
```

The `genre` resource represents the genre of a movie registered in the ReelNow database.

1. TOC
{:toc}

## Properties

| Property name | Type        | Description                         |
| ------------- | ----------- | ----------------------------------- |
| `name`        | string      | The name of the genre               |
| `description` | string      | A short description of the genre     |
| `id`          | number      | The genre's unique ID               |

## Related endpoints

| Path                             | Description                         |
| -------------------------------- | ----------------------------------- |
| `GET` {base_url}/genres          | [List all genres](genres_get-all-genres.md) |
| `GET` {base_url}/genres/{id}     | [Get details for a specific genre](genres_get-genre-by-id.md) |
