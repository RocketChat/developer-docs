# Get Units

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gets the list of all Omnichannel units. This requires the `manage-livechat-units` permission.

It supports the [#pagination](../../../../#pagination "mention") parameters, alongside the  [#query-and-fields](../../../../#query-and-fields "mention") parameters.

<table><thead><tr><th width="268.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/units</code></td><td><code>YES</code></td><td><code>GET</code></td></tr></tbody></table>

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```json
{
    "units": [
        {
            "_id": "SB3Z7uuEvd3aKPjnE",
            "name": "12345",
            "visibility": "public",
            "type": "u",
            "numMonitors": 3,
            "numDepartments": 3,
            "_updatedAt": "2022-09-15T14:55:32.338Z"
        },
        {
            "_id": "uiPBkzcau5hrWwBkG",
            "name": "C",
            "visibility": "public",
            "type": "u",
            "numMonitors": 1,
            "numDepartments": 3,
            "_updatedAt": "2022-08-29T20:18:07.442Z"
        },
        {
            "_id": "jsNuTwygAAWFPkt8u",
            "name": "Mtest",
            "visibility": "public",
            "type": "u",
            "numMonitors": 1,
            "numDepartments": 1,
            "_updatedAt": "2022-09-15T11:44:32.103Z"
        },
        {
            "_id": "LnM2rzbknjYSkkd5p",
            "name": "Sales Unit",
            "visibility": "public",
            "type": "u",
            "numMonitors": 1,
            "numDepartments": 2,
            "_updatedAt": "2022-09-15T11:44:15.721Z"
        },
        {
            "_id": "y6TXZeTzn4mAxDhL2",
            "name": "TestDept1",
            "visibility": "public",
            "type": "u",
            "numMonitors": 4,
            "numDepartments": 1,
            "_updatedAt": "2022-08-30T09:55:19.240Z"
        },
        {
            "_id": "xiAnkznAh4RSJ8DQT",
            "name": "abc",
            "visibility": "public",
            "type": "u",
            "numMonitors": 1,
            "numDepartments": 3,
            "_updatedAt": "2023-01-03T10:19:58.219Z"
        },
        {
            "_id": "TGjc7wN84KxQup9cF",
            "name": "business unit test",
            "visibility": "public",
            "type": "u",
            "numMonitors": 3,
            "numDepartments": 1,
            "_updatedAt": "2022-11-21T11:16:01.698Z"
        }
    ],
    "count": 7,
    "offset": 0,
    "total": 7,
    "success": true
}
```
