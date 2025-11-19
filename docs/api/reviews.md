---
# markdownlint-disable
# vale  off
layout: default
title: The `review` resource
parent: API reference
nav_order: 
has_children: true
has_toc: false
# tags used by AI files
description: Information about the `review` resource
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
    - /reviews
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---
# The `review` resource
{: .no_toc }

```shell
/reviews
```

The `review` resource represents a review registered in the ReelNow database.

1. TOC
{:toc}

## Properties

| Property name | Type   | Description                                                              |
| ------------- | ------ | ------------------------------------------------------------------------ |
| `movieId`     | number | The movie's unique ID                                                    |
| `source`      | string | The platform providing the rating                                        |
| `score`       | number | The review score calculated on a scale of 1–100, where 100 is highest rating |
| `reviewCount` | number | The total number of reviews contributing to the score                    |
| `id`          | number | The review's unique ID                                                   |


## Related endpoints

| Path                                   | Description                                                          |
| -------------------------------------- | -------------------------------------------------------------------- |
| `GET` {base_url}/reviews               | [List all reviews](reviews_get-all-reviews.md)                       |
| `GET` {base_url}/reviews/{id}          | [Get details for a specific review](reviews_get-review-by-id.md)     |
| `POST` {base_url}/reviews              | [Create a review](reviews_create-a-review.md)                        |
| `PATCH` {base_url}/reviews/{id}        | [Update a review](reviews_update-a-review.md)                        |
| `DELETE` {base_url}/reviews/{id}       | [Delete a review](reviews_delete-a-review.md)                        |