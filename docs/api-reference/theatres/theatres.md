---
# markdownlint-disable
# vale  off
has_children: true
has_toc: false
layout: default
nav_order: 5
parent: API reference
title: The `theatre` resource
# vale  on
# markdownlint-enable
---

# The `theatre` resource

```shell
/theatres
```

The `theatre` resource represents a theatre registered in the ReelNow database.

## Properties

| Property name | Type   | Description                               |
| :------------ | :----- | :---------------------------------------- |
| `name`        | string | The theatre's name                        |
| `address`     | string | The theatre's street name and number      |
| `city`        | string | The city where the theatre is located     |
| `province`    | string | The province where the theatre is located |
| `postalCode`  | string | The theatre's postal code                 |
| `phone`       | string | The theatre's phone number                |
| `website`     | string | The theatre's website URL                 |
| `id`          | number | The theatre’s unique ID                   |

## Related endpoints

| Path                              | Description                                          |
| :-------------------------------- | :--------------------------------------------------- |
| `GET` {base_url}/theatres         | [Get all theatres](theatres_get-all-theatres.md)     |
| `GET` {base_url}/theatres/{id}    | [Get theatre details](theatres_get-theatre-by-id.md) |
| `POST` {base_url}/theatres        | [Create a theatre](theatres_create-a-theatre.md)     |
| `PATCH` {base_url}/theatres/{id}  | [Update a theatre](theatres_update-a-theatre.md)     |
| `DELETE` {base_url}/theatres/{id} | [Delete a theatre](theatres_delete-a-theatre.md)     |
