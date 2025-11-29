---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 3 
parent: The `genre` resource
title: Create a genre
# vale  on
# markdownlint-enable
---

# Create a genre
{: .no_toc }

```shell
PATCH {base_url}/genres
# Replace <{base_url}> with <http://localhost:3000>
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
curl -X POST "http://localhost:3000/genres" \
  -H "Content-Type: application/json" \
  -d '{"name":"thriller","description":"Tense, suspense-filled stories that keep audiences guessing."}'
# Create a new genre and add related properties
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{
  "id": 8
  "name": "thriller",
  "description": "Tense, suspense-filled stories that keep audiences guessing.",
}
```
