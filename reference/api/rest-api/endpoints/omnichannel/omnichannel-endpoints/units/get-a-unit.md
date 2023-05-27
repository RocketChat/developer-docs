# Get a Unit

![](../../../../../../../.gitbook/assets/enterprise.jpg)

Get details of a unit.

{% hint style="info" %}
This requires the `manage-livechat-units` permission
{% endhint %}

<table><thead><tr><th width="342.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/units/:unitId</code></td><td><code>YES</code></td><td><code>GET</code></td></tr></tbody></table>

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Parameter

| Argument | Example             | Required | Description |
| -------- | ------------------- | -------- | ----------- |
| `unitId` | `sriw2wmP2Zz2pPrre` | Required | Unit ID     |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units/sriw2wmP2Zz2pPrre \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "_id": "LnM2rzbknjYSkkd5p",
    "name": "Sales Unit",
    "visibility": "public",
    "type": "u",
    "numMonitors": 1,
    "numDepartments": 2,
    "_updatedAt": "2022-09-15T11:44:15.721Z",
    "success": true
}
```
