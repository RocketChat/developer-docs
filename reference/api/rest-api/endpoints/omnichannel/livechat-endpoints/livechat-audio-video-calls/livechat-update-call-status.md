# Update Call Status

{% hint style="danger" %}
WebRTC is no longer supported with Omnichannel Livechat. To configure audio/video calls, see [Omnichannel Audio/Video Call Configuration](https://docs.rocket.chat/use-rocket.chat/rocket.chat-conference-call/omnichannel-video-audio-call-configuration).
{% endhint %}

Update the call status of an existing WebRTC audio/video call.

<table><thead><tr><th width="163">HTTP Method</th><th width="310">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>PUT</code></td><td><code>/api/v1/livechat/webrtc.call/:callId</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Path Variables

<table><thead><tr><th width="228.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>callId</code><mark style="color:red;"><code>*</code></mark></td><td><code>zRAeTszXor8CCPceB</code></td><td>The call message <code>_id</code>.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="228.33333333333331">Key</th><th width="243">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>abc123xyzabc</code></td><td>The room ID.</td></tr><tr><td><code>status</code><mark style="color:red;"><code>*</code></mark></td><td><code>ended</code></td><td>The status of the call.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/webrtc.call/zRAeTszXor8CCPceB\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name' \
-d '{ 
    "rid": "abc123xyzabc", 
    "status": "ended" 
}'
```
{% endcode %}

## Example Response

```json
{
    "status": "ended",
    "success": true
}
```
