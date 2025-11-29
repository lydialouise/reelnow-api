---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 4
parent: The `genre` resource
title: Update a genre
# vale  on
# markdownlint-enable
---

# Update a genre
{: .no_toc }

```shell
PATCH {base_url}/genres/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the genre's unique ID
```

Update an existing `genre` in the ReelNow database.

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
| `id`           | number | The genre's unique ID                        |

## Request header parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `Content-Type` | string | The parameter content type                   |

## Request body parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `name`         | string | The name of the genre                        |
| `description`  | string | A short description of the genre             |

## Response status codes

| Status code   | Description          |
| :------------ | :------------------- |
| 200           | Success              |
| 404           | Resource not found   |
| ECONNREFUSED  | Restart the service  |

<!-- *NOTE* Consider a seperate error page (see Stripe docs) -->

## Example

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X PATCH "http://localhost:3000/genres/1" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Thriller",
    "description": "Edge-of-your-seat stories full of tension and suspense."
  }'
# Update the genre with "id": 1
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "name": "thriller",
  "description": "Edge-of-your-seat stories full of tension and suspense.",
  "id": 3
}
```
