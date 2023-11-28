# Get List of Tags

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/tags</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `view-l-room`
* `manage-livechat-tags`
{% endhint %}

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention") parameters.

## Example Call

```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/tags\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Example Response

```json
{
    "tags": [
        {
            "_id": "nNJntq2n6GBdR8JC4",
            "name": "331",
            "numDepartments": 2,
            "departments": [
                "kxL4qaa29SMpy3ZXG",
                "WRY3EFGAT9Xh5NFBv"
            ],
            "_updatedAt": "2022-11-28T07:17:31.973Z",
            "description": "xfgh"
        },
        {
            "_id": "bhA8DPhSdeBEJ2C94",
            "name": "QA-Passed",
            "numDepartments": 0,
            "departments": [],
            "_updatedAt": "2022-08-30T12:14:54.173Z"
        },
        {
            "_id": "b8mvKqZXiAw36pDqE",
            "name": "VoIP",
            "description": "voip test",
            "numDepartments": 0,
            "departments": [],
            "_updatedAt": "2022-03-01T06:27:43.113Z"
        },
        {
            "_id": "GR6zxTM5PMHxGwud6",
            "name": "t1",
            "description": "test1",
            "numDepartments": 1,
            "departments": [
                "kxL4qaa29SMpy3ZXG"
            ],
            "_updatedAt": "2023-01-04T14:02:29.038Z"
        }
    ],
    "count": 4,
    "offset": 0,
    "total": 4,
    "success": true
}
```
