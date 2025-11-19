---
# markdownlint-disable
# vale  off
layout: default
title: Create a theatre
parent: The `theatre` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: POST a `theatre` resource in the database
tags:
    - api
categories:
    - api-reference
ai_relevance: high
importance: 7
prerequisites:
    - /api/theatres
related_pages: []
examples: []
api_endpoints: 
    - POST /theatres
version: "v1.0"
last_updated: "2025-11-19"
# vale  on
# markdownlint-enable
---

# Create a theatre
{: .no_toc }

```shell
POST {base_url}/theatres
# Replace {base_url} with the server address
```

<!-- *NOTE* explain what server address is (localhost) in setting-up-your-environment page. -->

Register a new `theatre` in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description          |
| :------------- | :------------------- |
| Authentication | Access token         |
| Access         | Write                |

## Path parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `base_url`     | string | The server address                           |

## Request header parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `Content-Type` | string | The parameter content type                   |

## Request body parameters

| Parameter     | Format  | Description                                               |
| ------------- | ------- | --------------------------------------------------------- |
| `name`        | string  | The theatre's name                                        |
| `address`     | string  | The theatre's street address                              |
| `city`        | string  | The city where the theatre is located                     |
| `state`       | string  | The province where the theatre is located                 |
| `postalCode`  | string  | The theatre's postal code                                 |
| `phone`       | string  | The theatre's phone number                                |
| `website`     | string  | The theatre's website URL                                 |
| `id`          | number  | The theatre’s unique ID                                   |

## Response status codes

| Status code   | Description          |
| :------------ | :------------------- |
| 200           | Success              |
| 404           | Resource not found   |
| ECONNREFUSED  | Restart the service  |

<!-- *NOTE* See Stripe docs for Error page. Consider setting up like that. -->

## Example

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X POST "http://localhost:3000/theatres" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Cineplex Downtown",
    "address": "123 Main St",
    "city": "Montreal",
    "province": "QC",
    "postalCode": "H3A 1B2",
    "phone": "123-456-7890",
    "website": "https://cineplexdowntown.example.com"
  }'

# Create a theatre
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 1,
  "name": "Cineplex Downtown",
  "address": "123 Main St",
  "city": "Montreal",
  "province": "QC",
  "postalCode": "H3A 1B2",
  "phone": "123-456-7890",
  "website": "https://cineplexdowntown.example.com"
}
```
