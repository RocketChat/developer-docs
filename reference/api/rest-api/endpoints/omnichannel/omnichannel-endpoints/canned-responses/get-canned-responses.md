# Get Canned Responses

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Get a list of [canned responses](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses). It supports the [Offset, Count, and Sort Query Parameters](../../../other-important-endpoints/offset-and-count-and-sort-info.md).

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                 |
| -------------- | -------------- | -------- | --------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated  user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                 |



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
            "_id": "646c747ca8c3a3ba32d0e2e8",
            "shortcut": "Denied",
            "text": "This is an example",
            "scope": "global",
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo"
            },
            "_createdAt": "2023-05-23T08:08:28.241Z",
            "_updatedAt": "2023-05-23T08:08:28.241Z"
        },
        {
            "_id": "646c6ed9a8c3a3ba32d0e2db",
            "shortcut": "my-new-canned",
            "text": "This is an example",
            "scope": "global",
            "tags": [
                "failed",
                "card"
            ],
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo"
            },
            "_createdAt": "2023-05-23T07:44:25.912Z",
            "_updatedAt": "2023-05-23T07:44:25.912Z"
        },
        {
            "_id": "646c7350a8c3a3ba32d0e2e0",
            "shortcut": "my-new-canned-",
            "text": "This is an example",
            "scope": "hi",
            "tags": [
                "failed",
                "card"
            ],
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo"
            },
            "_createdAt": "2023-05-23T08:03:28.148Z",
            "_updatedAt": "2023-05-23T08:03:28.148Z"
        }
    ],
    "count": 3,
    "offset": 0,
    "total": 3,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
