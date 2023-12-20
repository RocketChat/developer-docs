# Convert Channel to Team

<table><thead><tr><th width="163">HTTP Method</th><th width="337">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.convertToTeam</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `create-team`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="229.33333333333331">Argument</th><th width="220">Example</th><th>Description</th></tr></thead><tbody><tr><td><code>channelName</code><mark style="color:red;"><code>*</code></mark> or <code>channelId</code><mark style="color:red;"><code>*</code></mark></td><td><code>team01</code> or <code>b8ae982d286c3d1</code></td><td>The channel's name.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.channels.convertToTeam
     -d '{ 
          "channelName": "team-01" }'
```

## Example Response

```json
{
    "team": {
        "_id": "612b8ae982d286c3d1f5db31",
        "name": "team01",
        "type": 0,
        "createdAt": "2021-08-29T13:26:01.750Z",
        "createdBy": {
            "_id": "JxemcN9PDCdfzJeZr",
            "username": "ren.baek"
        },
        "_updatedAt": "2021-08-29T13:26:01.750Z",
        "roomId": "GwktYAajqw4RiWiBK"
    },
    "success": true
}
```
