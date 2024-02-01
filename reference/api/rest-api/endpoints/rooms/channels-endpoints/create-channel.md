# Create Channel

Creates a new public channel, optionally including specified users. The channel creator is always included.

{% hint style="info" %}
Channel naming has restraints following the regex filter `[0-9a-zA-Z-_.]+` by default.

This can be modified in the **Admin** > **General** > **UTF8**. Channel names should not allow for any whitespaces.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="339">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.create</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="184">Key</th><th width="224">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>channelname</code></td><td>The name of the new channel.</td></tr><tr><td><code>members</code></td><td><code>["rocket.cat"]</code></td><td>The users to add to the channel when it is created.</td></tr><tr><td><code>readOnly</code></td><td><code>true</code></td><td>Set if the channel is read-only or not. The default value is <code>false</code>.</td></tr><tr><td><code>excludeSelf</code></td><td><code>true</code></td><td>If set to <code>true</code>, the user calling the endpoint is not automatically added as a member of the group. The default value is <code>false</code>.</td></tr><tr><td><code>customFields</code></td><td><code>{ "type": "default" }</code></td><td>If you have defined custom fields for your workspace, you can provide them in this object parameter.</td></tr><tr><td><code>extraData</code></td><td><p><code>"extraData": { "broadcast": true, "encrypted": false,</code> </p><p><code>"teamId": "658441562dd9f928ad9951aa" }</code></p></td><td><p>Enter the following details for the object:</p><ul><li><code>broadcast</code>: Whether the group should be a broadcast group.</li><li><code>encrypted</code>: Whether the group should be encrypted.</li><li><code>teamId</code>: Enter the team ID for which you want to create a group.</li></ul><p>For more information, see <a href="https://docs.rocket.chat/use-rocket.chat/user-guides/rooms/channels#channel-privacy-and-encryption">Channels</a>.</p></td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.create \
     -d '{ 
          "name": "channelname" }'
```

## Example Response

```json
{
   "channel": {
      "_id": "ByehQjC44FwMeiLbX",
      "name": "channelname",
      "t": "c",
      "usernames": [
         "example"
      ],
      "msgs": 0,
      "u": {
         "_id": "aobEdbYhXfu5hkeqG",
         "username": "example"
      },
      "ts": "2016-05-30T13:42:25.304Z"
   },
   "success": true
}
```

## Change Log

| Version | Description               |
| ------- | ------------------------- |
| 6.4.1   | Added `excludeSelf` param |
| 0.13.0  | Added                     |
