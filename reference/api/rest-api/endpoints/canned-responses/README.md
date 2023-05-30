---
description: This is an enterprise feature.
---

# Canned Responses

<figure><img src="../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Get a list of canned responses. It supports the [Offset, Count, and Sort Query Parameters](../pagination.md).

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `GET`       |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/canned-responses
```

## Example Result

```javascript
{
  "cannedResponses": [
    {
      "_id": "QZXvWyo3niwWREZ4g",
      "shortcut": "my-new-canned",
      "text": "This is an example",
      "scope": "global",
      "tags": [
        "tag1",
        "tag2",
      ],
      "createdBy": {
        "_id": "9L3wuBXKpbAWdfgx8",
        "username": "rafael.ferreira"
      },
      "_createdAt": "2021-05-26T18:58:48.855Z",
      "_updatedAt": "2021-05-26T18:58:48.855Z"
    }
  ],
  "count": 1,
  "offset": 0,
  "total": 1,
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |

## Get the canned response info

Retrieve the visitor info

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses/:_id` | `yes`         | `GET`       |

## Path Parameter

| Argument | Example           | Required | Description               |
| -------- | ----------------- | -------- | ------------------------- |
| `_id`    | EwmbZ9nLSx7kFamYB | Required | The canned response's id. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/canned-responses/EwmbZ9nLSx7kFamYB
```

## Example Result

```javascript
{
  "cannedResponse": {
    "_id": "EwmbZ9nLSx7kFamYB",
    "shortcut": "user",
    "text": "Meu 32423423423423423",
    "scope": "user",
    "userId": "9L3wuBXKpbAWdfgx8",
    "createdBy": {
      "_id": "9L3wuBXKpbAWdfgx8",
      "username": "rafael.ferreira"
    },
    "_createdAt": "2021-05-26T18:59:17.929Z",
    "_updatedAt": "2021-05-26T18:59:17.929Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |

## Register a new canned response

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `POST`      |

## Example payload

```javascript
{
    "shortcut": "my-new-canned",
    "text": "This is an example",
    "scope": "global",
    "tags": ["tag1", "tag2"]
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/canned-responses \
    -d '{    "shortcut": "my-new-canned", "text": "This is an example", "scope": "global", "tags": ["tag1", "tag2"] }'
```

## Example Result

```javascript
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |

## Update a canned response

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `POST`      |

## Example payload

```javascript
{
    "_id": "N5D2posu4fCqamjae",
    "shortcut": "my-new-canned",
    "text": "This is an example",
    "scope": "global",
    "tags": ["tag1", "tag2"]
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/canned-responses \
    -d '{    "_id": "N5D2posu4fCqamjae", "shortcut": "my-new-canned", "text": "This is an example", "scope": "global", "tags": ["tag1", "tag2"] }'
```

## Example Result

```javascript
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |

## Delete a canned response

Retrieve the visitor info

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `DELETE`    |

## Query Parameter

| Argument | Example           | Required | Description               |
| -------- | ----------------- | -------- | ------------------------- |
| `_id`    | EwmbZ9nLSx7kFamYB | Required | The canned response's id. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X DELETE \
     http://localhost:3000/api/v1/canned-responses?_id=N5D2posu4fCqamjae
```

## Example Result

```javascript
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
