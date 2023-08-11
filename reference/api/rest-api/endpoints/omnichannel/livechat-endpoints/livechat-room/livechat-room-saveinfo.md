# LiveChat Room SaveInfo

Edit a LiveChat room. Update the topic, tags, and other details of a LiveChat room.

{% hint style="info" %}
It requires the `view-l-room`  [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `api/v1/livechat/room.saveInfo` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="140">Argument</th><th width="171">Example</th><th width="109">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>guestData</code></td><td><p></p><pre class="language-postman_json"><code class="lang-postman_json"> {			
 	"_id": "rbAXPnMktTFbNpwtJ"
}
</code></pre></td><td>Required</td><td>An object of the updated  <code>guestdata</code></td></tr><tr><td><code>roomData</code></td><td><p></p><pre class="language-postman_json"><code class="lang-postman_json"> {
"_id": "nf52k8bpJ8y7oHmwk",
"topic": "Hmm",
"tags": ["testtags"]
}
</code></pre></td><td>Required</td><td>An object of updated <code>roomdata</code> </td></tr></tbody></table>

**guestData Object**

<table><thead><tr><th width="140">Argument</th><th width="171">Example</th><th width="109">Required</th><th>Description</th></tr></thead><tbody><tr><td>_id</td><td><code>rbAXPnMktTFbNpwtJ</code></td><td>Required</td><td>The user id.</td></tr><tr><td>name</td><td><code>funke</code></td><td>Optional</td><td>The name  of the user</td></tr><tr><td>email</td><td><code>funke.test@rocket.chat</code></td><td>Optional</td><td>The email of the user</td></tr><tr><td>phone</td><td><code>4478390282</code></td><td>Optional</td><td>The contact of the guest. </td></tr><tr><td><code>livechatData</code></td><td><p></p><pre class="language-postman_json"><code class="lang-postman_json">{
  "id1": "value1",
  "id2": "value2",
  ......
}
</code></pre></td><td>Optional</td><td>Custom-fields information</td></tr></tbody></table>

**roomData Object**

<table><thead><tr><th width="140">Argument</th><th width="171">Example</th><th width="109">Required</th><th>Description</th></tr></thead><tbody><tr><td>_id</td><td><code>rbAXPnMktTFbNpwtJ</code></td><td>Required</td><td>The room id.</td></tr><tr><td>topic</td><td><code>Test123</code></td><td>Optional</td><td>The topic of the room.</td></tr><tr><td>tags</td><td><code>["testtags"]</code></td><td>Optional</td><td>An array of tags to be associated with the room.</td></tr><tr><td>priorityId</td><td><code>5PMgshbQWsoHsYy2c</code></td><td>Optional</td><td>The priorityId of the room</td></tr><tr><td>slaId</td><td><code>6417f67528384134ed600dc6</code></td><td>Optional</td><td>The slaId of the room</td></tr><tr><td><code>livechatData</code></td><td><p></p><pre class="language-postman_json"><code class="lang-postman_json">{
  "id1": "value1",
  "id2": "value2",
  ......
}
</code></pre></td><td>Optional</td><td>Custom-fields information</td></tr></tbody></table>

## Example Payload

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

```bash
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

## Example Result

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
```javascript
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
