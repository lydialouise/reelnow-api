---
# markdownlint-disable
# vale  off
has_children: true
has_toc: false
layout: default
nav_order: 3
parent: API reference
title: The `review` resource
# vale  on
# markdownlint-enable
---

# The `review` resource

```shell
/reviews
```

The `review` resource represents a review registered in the ReelNow database.

## Properties

| Property name | Type   | Description                                                                  |
| :------------ | :----- | :--------------------------------------------------------------------------- |
| `movieId`     | number | The movie's unique ID                                                        |
| `source`      | string | The platform providing the rating                                            |
| `score`       | number | The review score calculated on a scale of 1–100, where 100 is highest rating |
| `reviewCount` | number | The total number of reviews contributing to the score                        |
| `id`          | number | The review's unique ID                                                       |

## Related endpoints

| Path                             | Description                                       |
| :------------------------------- | :------------------------------------------------ |
| `GET` {base_url}/reviews         | [Get all reviews](reviews_get-all-reviews.md)     |
| `GET` {base_url}/reviews/{id}    | [Get review details](reviews_get-review-by-id.md) |
| `POST` {base_url}/reviews        | [Create a review](reviews_create-a-review.md)     |
| `PATCH` {base_url}/reviews/{id}  | [Update a review](reviews_update-a-review.md)     |
| `DELETE` {base_url}/reviews/{id} | [Delete a review](reviews_delete-a-review.md)     |
