---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 5
parent: The `theatre` resource
title: Delete a theatre
# vale  on
# markdownlint-enable
---

# Delete a theatre
{: .no_toc }

```shell
DELETE {base_url}/theatres/{id}
# Replace <{base_url}> with <http://localhost:3000>
```

Delete an existing `theatre` in the ReelNow database.

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

_None_

## Request body parameters

_None_

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
curl -X DELETE "http://localhost:3000/theatres/1"
# Delete the theatre with "id": 1
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{}
```
