---
description: Starts a webrtc audio/video call.
---

# Start Call

Start a WebRTC audio/video call in a room.

<table><thead><tr><th width="163">HTTP Method</th><th width="317">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/webrtc.call</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="170">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>zRAeTszXor8CCPceB</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/webrtc.call?rid=123abcxyz123\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "videoCall": {
        "rid": "123abcxyz123",
        "provider": "webrtc",
        "callStatus": "ringing"
    },
    "success": true
}
```
