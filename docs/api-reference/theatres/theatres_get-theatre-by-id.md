---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 2
parent: The `theatre` resource
title: Get theatre details
# vale  on
# markdownlint-enable
---

# Get theatre details
{: .no_toc }

```shell
GET {base_url}/theatres/{id}
# Replace <{base_url}> with <http://localhost:3000>
# Replace <{id}> with the theatre's unique ID
```

Get details for a specific `theatre` registered in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Read         |

## Path parameters

| Parameter  | Format | Description             |
| :--------- | :----- | :---------------------- |
| `base_url` | string | The server address      |
| `id`       | number | The theatre's unique ID |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code  | Description                    |
| :----------- | :----------------------------- |
| 200          | Resource successfully returned |
| 404          | Resource ID not found          |
| ECONNREFUSED | Restart the service            |

## Example

Here is an example `cURL` request and `200 OK` response.

### Example request
{: .no_toc }

{: .d-inline-block }

cURL
{: .label .label-purple }

```shell
curl -X GET http://localhost:3000/theatres/1 
# Get details for the theatre with "id": 1
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
}
```
