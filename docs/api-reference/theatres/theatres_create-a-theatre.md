---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 3
parent: The `theatre` resource
title: Create a theatre
# vale  on
# markdownlint-enable
---

# Create a theatre
{: .no_toc }

```shell
POST {base_url}/theatres
# Replace <{base_url}> with <http://localhost:3000>
```

Register a new `theatre` in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Write        |

## Path parameters

| Parameter  | Format | Description        |
| :--------- | :----- | :----------------- |
| `base_url` | string | The server address |

## Request header parameters

| Parameter      | Format | Description                |
| :------------- | :----- | :------------------------- |
| `Content-Type` | string | The parameter content type |

## Request body parameters

| Parameter    | Format | Description                               |
| :----------- | :----- | :---------------------------------------- |
| `name`       | string | The theatre's name                        |
| `address`    | string | The theatre's street address              |
| `city`       | string | The city where the theatre is located     |
| `state`      | string | The province where the theatre is located |
| `postalCode` | string | The theatre's postal code                 |
| `phone`      | string | The theatre's phone number                |
| `website`    | string | The theatre's website URL                 |
| `id`         | number | The theatre’s unique ID                   |

## Response status codes

| Status code  | Description                   |
| ------------ | ----------------------------- |
| 201          | Resource successfully updated |
| ECONNREFUSED | Restart the service           |

<!-- *NOTE* Consider a seperate error page (see Stripe docs) -->

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

# Create a new theatre and add related properties
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
