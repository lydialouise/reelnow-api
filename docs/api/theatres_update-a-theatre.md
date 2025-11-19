---
# markdownlint-disable
# vale  off
layout: default
title: Update a theatre
parent: The `theatre` resource
nav_order: 
has_children: false
has_toc: true
# tags used by AI files
description: PATCH a `theatre` resource in the database
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
    - PATCH /theatres/{id}
version: "v1.0"
last_updated: "2025-11-20"
# vale  on
# markdownlint-enable
---

# Update a theatre
{: .no_toc }

```shell
PATCH {base_url}/theatres/{id}
# Replace {base_url} with the server address
```

<!-- *NOTE* explain what server address is (localhost) in setting-up-your-environment page. -->

Update an existing `theatre` in the ReelNow database.

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
| `id`           | number | The theatre's unique ID                        |

## Request header parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `Content-Type` | string | The parameter content type                   |

## Request body parameters

| Parameter     | Format  | Description                                               |
| :------------ | :------ | :-------------------------------------------------------- |
| `name`        | string  | The theatre's name                                        |
| `address`     | string  | The theatre's street address                              |
| `city`        | string  | The city where the theatre is located                     |
| `state`       | string  | The province where the theatre is located                 |
| `postalCode`  | string  | The theatre's postal code                                 |
| `phone`       | string  | The theatre's phone number                                |
| `website`     | string  | The theatre's website URL                                 |


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
curl -X PATCH "http://localhost:3000/theatres/1" \
  -H "Content-Type: application/json" \
  -d '{
    "phone": "987-654-3210",
    "website": "https://cineplexdowntown-new.example.com"
  }'
# Update the phone number and website for the theatre with ID = 1
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
  "phone": "987-654-3210",
  "website": "https://cineplexdowntown-new.example.com"
}
```
