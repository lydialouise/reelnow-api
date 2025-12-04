---
# markdownlint-disable
# vale  off
has_children: true
has_toc: false
layout: default
nav_order: 1
parent: API reference
title: The `genre` resource
# vale  on
# markdownlint-enable
---

# The `genre` resource

```shell
/genres
```

The `genre` resource represents the genre of a movie registered in the ReelNow database.

## Properties

| Property name | Type   | Description                      |
| :------------ | :----- | :------------------------------- |
| `name`        | string | The name of the genre            |
| `description` | string | A short description of the genre |
| `id`          | number | The genre's unique ID            |

## Related endpoints

| Path                         | Description                                    |
| :--------------------------- | :--------------------------------------------- |
| `GET` {base_url}/genres      | [Get all genres](genres_get-all-genres.md)     |
| `GET` {base_url}/genres/{id} | [Get genre details](genres_get-genre-by-id.md) |
