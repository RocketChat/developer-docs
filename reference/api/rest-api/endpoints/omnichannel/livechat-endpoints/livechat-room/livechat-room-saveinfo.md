# Update Livechat Room

Edit a LiveChat room. Update the topic, tags, and other details of a Livechat room.

{% hint style="info" %}
It requires the `view-l-room`  [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/livechat/room.saveInfo</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body

<table><thead><tr><th width="163">Key</th><th width="289">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>guestData</code><mark style="color:red;"><code>*</code></mark></td><td><p>"<code>guestData" : {</code> </p><p><code>"_id": "rbAXPnMktTFbNpwtJ" }</code></p></td><td>An object of the updated <code>guestdata</code>.</td></tr><tr><td><code>roomData</code><mark style="color:red;"><code>*</code></mark></td><td><p>"<code>roomData" : {</code> </p><p><code>"_id": "nf52k8bpJ8y7oHmwk", "topic": "Hmm",</code> </p><p><code>"tags": ["testtags"] }</code></p></td><td>An object of updated <code>roomdata</code>.</td></tr></tbody></table>

**guestData Object**

<table><thead><tr><th width="175">Key</th><th width="257">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>rbAXPnMktTFbNpwtJ</code></td><td>The guest ID.</td></tr><tr><td><code>name</code></td><td><code>john</code></td><td>The name  of the guest.</td></tr><tr><td><code>email</code></td><td><code>john.test@rocket.chat</code></td><td>The email of the guest.</td></tr><tr><td><code>phone</code></td><td><code>4478390282</code></td><td>The contact of the guest. </td></tr><tr><td><code>livechatData</code></td><td><p><code>"livechatData" :</code></p><p><code>{ "id1": "value1", "id2": "value2" }</code></p></td><td>Custom fields information.</td></tr></tbody></table>

**roomData Object**

<table><thead><tr><th width="179">Key</th><th width="268">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>rbAXPnMktTFbNpwtJ</code></td><td>The room ID.</td></tr><tr><td><code>topic</code></td><td><code>Test123</code></td><td>The topic of the room.</td></tr><tr><td><code>tags</code></td><td><code>["testtags"]</code></td><td>An array of tags to be associated with the room.</td></tr><tr><td><code>priorityId</code></td><td><code>5PMgshbQWsoHsYy2c</code></td><td>The priority ID of the room.</td></tr><tr><td><code>slaId</code></td><td><code>6417f67528384134ed600dc6</code></td><td>The SLA priority ID of the room.</td></tr><tr><td><code>livechatData</code></td><td><code>"livechatData" : { "id1": "value1", "id2": "value2"}</code></td><td>Custom fields information.</td></tr></tbody></table>

## Example Body

```javascript
{
"guestData": {
		"_id": "rbAXPnMktTFbNpwtJ"

	},
"roomData": {
		"_id": "nf52k8bpJ8y7oHmwk",
		"topic": "Hmm",
		"tags": ["testtags"]
	}
}
```

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/room.saveInfo' \
--header 'x-auth-token: Wnb_e6wG4a74JiMxpSogmn9iP-K6wGk2F09sDRwLiLq' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--header 'Content-Type: application/json' \
--data '{
"guestData": {
		"_id": "rbAXPnMktTFbNpwtJ"

	},
"roomData": {
		"_id": "nf52k8bpJ8y7oHmwk",
		"topic": "Hmm",
		"tags": ["testtags"]
	}
}'
```

## Example Response

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Room**: Occurs when the given `_id` in `roomData`  object is invalid and doesn't belong to any room in the workspace.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```json
{
    "success": false,
    "error": "error-invalid-room"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 5.3.0   | Added       |
