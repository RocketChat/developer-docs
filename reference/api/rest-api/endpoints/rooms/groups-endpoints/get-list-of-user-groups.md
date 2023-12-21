# Get List of User Groups

Lists all of the groups/channels of any users.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.listAll</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-room-administration`
{% endhint %}

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") parameters, alongside the field parameter for[#query-and-fields](../../../#query-and-fields "mention").

## Example Call

This example shows a list of groups filtered by `customFields.companyId` starting with `org1` using a regular expression.

{% code overflow="wrap" %}
```bash
curl -H "X-Auth-Token: 8-gard51USVYskZ7AAqFF3SZuwg24VIdn9-HchYersg" \
     -H "X-User-Id: 3WpJQkDHhrWPBvXuW" \
     http://localhost:3000/api/v1/groups.listAll?query=%7B%20%22customFields.companyId%22%3A%20%7B%20%22%24regex%22%3A%20%22%5Eorg1%22%7D%20%7D
```
{% endcode %}

## Example Response

```json
{
    "groups": [
        {
            "_id": "xA52DRDM7dqx2PfTp",
            "name": "private1",
            "fname": "private1",
            "t": "p",
            "msgs": 0,
            "u": {
                "_id": "3WpJQkDHhrWPBvXuW",
                "username": "admin"
            },
            "customFields": {
                "companyId": "org1"
            },
            "ts": "2018-01-21T21:05:06.729Z",
            "ro": false,
            "sysMes": true,
            "_updatedAt": "2018-01-21T21:05:06.729Z"
        }
    ],
    "offset": 0,
    "count": 1,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description                    |
| ------- | ------------------------------ |
| 0.62.0  | Add 'query' parameter support. |
| 0.59.0  | Added                          |
