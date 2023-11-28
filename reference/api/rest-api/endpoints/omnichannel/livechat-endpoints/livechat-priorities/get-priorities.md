# Get List of Priorities

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-priorities` or `view-l-room permission`.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/priorities</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention") parameters.

## Example Call

```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/priorities\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-id'
```

## Example Response

### Success

```json
{
    "priorities": [
        {
            "_id": "64007cc2fa0ed7dd905092e3",
            "i18n": "Lowest",
            "sortItem": 5,
            "dirty": false
        },
        {
            "_id": "64007cc2fa0ed7dd905092e4",
            "i18n": "Low",
            "sortItem": 4,
            "dirty": false
        },
        {
            "_id": "64007cc2fa0ed7dd905092e5",
            "i18n": "Medium",
            "sortItem": 3,
            "dirty": false
        },
        {
            "_id": "64007cc2fa0ed7dd905092e6",
            "i18n": "High",
            "sortItem": 2,
            "dirty": false
        },
        {
            "_id": "64007cc2fa0ed7dd905092e7",
            "i18n": "Highest",
            "sortItem": 1,
            "dirty": false
        }
    ],
    "count": 5,
    "offset": 0,
    "total": 5,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-priorities` or `view-l-room` permission.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "error-not-authorized"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
