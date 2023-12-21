# Save Room Settings

<table><thead><tr><th width="163">HTTP Method</th><th width="290">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.saveRoomSettings</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="226">Key</th><th width="243">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>JZ8Y2dLfYhsg323Rf</code></td><td>The room ID.</td></tr><tr><td><code>roomName</code></td><td><code>Test-Save-Room</code></td><td>The name of the room.</td></tr><tr><td><code>roomDescription</code></td><td><code>This is a test room.</code></td><td>The description of the room.</td></tr><tr><td><code>roomAvatar</code></td><td><code>data:image/jpeg;base64,&#x3C;base64 code of your image></code></td><td>The base64 image.</td></tr><tr><td><code>featured</code></td><td><code>true</code></td><td>Whether the room is featured or not.</td></tr><tr><td><code>roomTopic</code></td><td><code>Discussion Topic</code></td><td>The topic of the room.</td></tr><tr><td><code>roomAnnouncement</code></td><td><code>Important Announcement</code></td><td>The announcement of the room.</td></tr><tr><td><code>roomCustomFields</code></td><td><code>{ "field1": "value1" }</code></td><td>The custom fields of the room.</td></tr><tr><td><code>roomType</code></td><td><code>"c"</code></td><td>The type of the room.</td></tr><tr><td><code>readOnly</code></td><td><code>true</code></td><td>Whether the room is read-only or not.</td></tr><tr><td><code>reactWhenReadOnly</code></td><td><code>true</code></td><td>Whether users can react when the room is read-only.</td></tr><tr><td><code>systemMessages</code></td><td><code>["changed-room-name"]</code></td><td>The system messages that the room supports.</td></tr><tr><td><code>default</code></td><td><code>true</code></td><td>Whether the room is the default room or not.</td></tr><tr><td><code>joinCode</code></td><td><code>"123456"</code></td><td>The join code of the room.</td></tr><tr><td><code>streamingOptions</code></td><td><code>{ "type": "live" }</code></td><td>The streaming options of the room.</td></tr><tr><td><code>retentionEnabled</code></td><td><code>true</code></td><td>Whether retention is enabled for the room or not.</td></tr><tr><td><code>retentionMaxAge</code></td><td><code>30</code></td><td>The maximum age (in days) of messages to be retained in the room.</td></tr><tr><td><code>retentionExcludePinned</code></td><td><code>true</code></td><td>Whether to exclude pinned messages from retention or not.</td></tr><tr><td><code>retentionFilesOnly</code></td><td><code>true</code></td><td>Whether to retain only files in the room or not.</td></tr><tr><td><code>retentionIgnoreThreads</code></td><td><code>true</code></td><td>Whether to ignore threads when retaining messages or not.</td></tr><tr><td><code>retentionOverrideGlobal</code></td><td><code>true</code></td><td>Whether to override the global retention settings for the room or not.</td></tr><tr><td><code>encrypted</code></td><td><code>true</code></td><td>Whether the room is encrypted or not.</td></tr><tr><td><code>favorite</code></td><td><code>{ "favorite": true, "defaultValue": false }</code></td><td>The favorite settings of the room. Whether the room is marked as favorite and whether it is set as the default room.</td></tr></tbody></table>

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/rooms.saveRoomSettings' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "rid": "JZ8Y2dLfYhsg323Rf",
    "roomName": "Test-Save-Room",
    "roomDescription": "This is a test room."
}'
```

## Example Response

### Success

```json
{
    "rid": "JZ8Y2dLfYhsg323Rf",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Room**: Occurs when the given `rid` is invalid.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```
{
    "success": false,
    "error": "The required \"roomId\" or \"roomName\" param provided does not match any group [error-room-not-found]",
    "errorType": "error-room-not-found"
}
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.13.0  | Added       |
