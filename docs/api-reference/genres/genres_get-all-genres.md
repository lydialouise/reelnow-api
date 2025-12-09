---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 1
parent: The `genre` resource
title: Get all genres
# vale  on
# markdownlint-enable
---

# Get all genres
{: .no_toc }

```shell
GET {base_url}/genres
# Replace <{base_url}> with <http://localhost:3000>
```

Get all `genres` registered in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Read         |

## Path parameters

| Parameter  | Format | Description        |
| :--------- | :----- | :----------------- |
| `base_url` | string | The server address |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code  | Description                |
| :----------- | :------------------------- |
| 200          | List successfully returned |
| ECONNREFUSED | Restart the service        |

## Example

Here is an example cURL request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X GET http://localhost:3000/genres 
# Get all genres in the database
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
},
{
    "name": "fantasy",
    "description": "Stories set in imaginary worlds or involving magical elements, mythical creatures, or supernatural forces.",
    "id": 2
},
{
    "name": "action",
    "description": "Fast-paced, high-energy films featuring physical stunts, chases, combat, and special effects.",
    "id": 3
},
{
    "name": "sci-fi",
    "description": "Stories centered around futuristic science, technology, space exploration, or parallel realities.",
    "id": 4
},
{
    "name": "comedy",
    "description": "Light-hearted and humorous stories designed to entertain and amuse, often through wit, satire, or playful characters.",
    "id": 5
},
{
    "name": "horror",
    "description": "Atmospheric and suspenseful films that evoke fear or tension through dread, shock, or the supernatural.",
    "id": 6
},
{
    "name": "romance",
    "description": "Emotionally driven stories that explore love, relationships, and human connection, often focusing on personal growth and heartfelt moments.",
    "id": 7
}
```
