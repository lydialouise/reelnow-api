---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 1
parent: The `theatre` resource
title: Get all theatres
# vale  on
# markdownlint-enable
---

# Get all theatres
{: .no_toc }

```shell
GET {base_url}/theatres
# Replace <{base_url}> with <http://localhost:3000>
```

Get all `theatres` registered in the ReelNow database.

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

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X GET http://localhost:3000/theatres 
# Get all theatres in the database
```

### Example response
{: .no_toc }

{: .d-inline-block }

200
{: .label .label-green }

```js
{
    "name": "Ciniplex Downtown",
    "address": "123 Main St",
    "city": "Montreal",
    "province": "QC",
    "postalCode": "H3A 1B2",
    "phone": "123-456-7890",
    "website": "https://cineplexdowntown.example.com",
    "id": 1
},
{
    "name": "Famous Players",
    "address": "456 Wellington St",
    "city": "Ottawa",
    "province": "ON",
    "postalCode": "K1A 0B1",
    "phone": "123-456-7890",
    "website": "https://famousplayers.example.com",
    "id": 2
},
{
    "name": "Landmark Cinemas",
    "address": "789 Granville St",
    "city": "Vancouver",
    "province": "BC",
    "postalCode": "V6C 1T2",
    "phone": "123-456-7890",
    "website": "https://landmarkcinemas.example.com",
    "id": 3
},
{
    "name": "Cinemark",
    "address": "101 King St",
    "city": "Toronto",
    "province": "ON",
    "postalCode": "M5H 1A1",
    "phone": "123-456-7890",
    "website": "https://cinemark.example.com",
    "id": 4
}
```
