---
# markdownlint-disable
# vale  off
has_children: false
has_toc: true
layout: default
nav_order: 5
parent: The `review` resource
title: Delete a review
# vale  on
# markdownlint-enable
---

# Delete a review
{: .no_toc }

```shell
DELETE {base_url}/reviews/{id}
# Replace <{base_url}> with <http://localhost:3000>
```

Delete an existing `review` in the ReelNow database.

1. TOC
{:toc}

## Permissions

| Permission     | Description  |
| :------------- | :----------- |
| Authentication | Access token |
| Access         | Write        |

## Path parameters

| Parameter  | Format | Description            |
| :--------- | :----- | :--------------------- |
| `base_url` | string | The server address     |
| `id`       | number | The review's unique ID |

## Request header parameters

_None_

## Request body parameters

_None_

## Response status codes

| Status code  | Description                   |
| :----------- | :---------------------------- |
| 200          | Resource successfully deleted |
| 404          | Resource ID not found         |
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
curl -X DELETE "http://localhost:3000/reviews/1"
# Delete the review with "id": 1
```

### Example response
{: .no_toc }

{: .d-inline-block }

200 OK
{: .label .label-green }

```js
{}
```
