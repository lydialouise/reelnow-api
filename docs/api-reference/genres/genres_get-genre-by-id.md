---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 2
parent: The `genre` resource
title: Get genre details
# vale  on
# markdownlint-enable
---

# Get genre details
{: .no_toc }

```shell
GET {base_url}/genres/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the genre's unique ID
```

Get details for a specific `genre` registered in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description          |
| :------------- | :------------------- |
| Authentication | Access token         |
| Access         | Read                 |

## Path parameters

| Parameter      | Format | Description                                  |
| :------------- | :----- | :------------------------------------------- |
| `base_url`     | string | The server address                           |
| `id`           | number | The genre's unique ID                        |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code   | Description           |
| :------------ | :-------------------- |
| 200           | Success               |
| 404           | Resource ID not found |
| ECONNREFUSED  | Restart the service   |

## Example

Here is an example cURL request and `200 OK` response.

### Example request
{: .no_toc }

```shell
curl -X GET http://localhost:3000/genres/1 
# Get details for the genre with "id": 1
```

### Example response
{: .no_toc }

{: .d-inline-block }

200
{: .label .label-green }

```js
{
    "name": "family",
    "description": "Content suitable for children and adults; typically animated or light-hearted live action.",
    "id": 1
}
```
