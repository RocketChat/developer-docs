# Get Tags

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Get a list of all tags. It supports the [#pagination](../../../../#pagination "mention") parameters.

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `api/v1/livechat/tags` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

<pre class="language-bash"><code class="lang-bash">curl --location --request GET 'http://localhost:3000/api/v1/livechat/tags\
<strong>--header 'X-Auth-Token: myauth-token' \
</strong>--header 'X-User-Id: myuser-name'
</code></pre>

## Result

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
}js
```
