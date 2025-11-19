---
# markdownlint-disable
# vale  off
layout: default
title: The `theatre` resource
parent: API reference
nav_order: 
has_children: true
has_toc: false
# tags used by AI files
description: Information about the `theatre` resource
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
    - /theatres
version: "v1.0"
last_updated: "2025-11-11"
# vale  on
# markdownlint-enable
---

# The `theatre` resource
{: .no_toc }

```shell
/theatres
```

The `theatre` resource represents a theatre registered in the ReelNow database.

1. TOC
{:toc}

## Properties

| Property name | Type     | Description                                                |
| ------------- | -------- | ---------------------------------------------------------- |
| `name`        | string   | The theatre's name                                         |
| `address`     | string   | The theatre's street address                               |
| `city`        | string   | The city where the theatre is located                      |
| `province`    | string   | The province where the theatre is located                  |
| `postalCode`  | string   | The theatre's postal code                                  |
| `phone`       | string   | The theatre's phone number                                 |
| `website`     | string   | The theatre's website URL                                  |
| `id`          | number   | The theatre’s unique ID                                    |

## Related endpoints

| Path                                  | Description                                                                 |
| ------------------------------------- | --------------------------------------------------------------------------- |
| `GET` {base_url}/theatres             | [List all theatres](theatres_get-all-theatres.md)                           |
| `GET` {base_url}/theatres/{id}        | [Get details for a specific theatre](theatres_get-theatre-by-id.md)         |
| `POST` {base_url}/theatres            | [Create a theatre](theatres_create-a-theatre.md)                            |
| `PATCH` {base_url}/theatres/{id}      | [Update a theatre](theatres_update-a-theatre.md)                            |
| `DELETE` {base_url}/theatres/{id}     | [Delete a theatre](theatres_delete-a-theatre.md)                            |

