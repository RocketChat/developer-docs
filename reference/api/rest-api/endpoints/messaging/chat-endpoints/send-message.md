# Send message

The difference between `chat.postMessage` and `chat.sendMessage` is that `chat.sendMessage` allows for passing a value for `_id` and the other one doesn't. Also, `chat.sendMessage` only sends it to one channel whereas the other one allows for sending to more than one channel at a time.

{% hint style="info" %}
**IMPORTANT**

You can only send `alias` and `avatar` properties if your user has the `message-impersonate` permission. We implemented this rule to avoid users impersonating other users. By default, only the `bot` role has this permission, but that can be changed in Administration -> Permissions -> `message-impersonate.`
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/chat.sendMessage` | `yes`         | `POST`      |

## Payload

<table><thead><tr><th width="173">Argument</th><th>Example</th><th width="138">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>message</code></td><td><p><code>{</code> </p><p><code>"rid": "64f0f82c2c26843a68c1f7ba",</code> </p><p><code>"msg": "Sample message"</code></p><p><code>}</code></p></td><td>Required</td><td>A message object containing all message data.</td></tr><tr><td><code>previewUrls</code> </td><td><code>['https://google.com', 'https://rocket.chat']</code></td><td>Optional</td><td>An array to define which URL previews should be retrieved from each message.</td></tr></tbody></table>

**Some important things to note about `previewUrls`  include:**

* If the `previewUrls` array is empty, no URL will be previewed.
* If the `previewUrls` parameter isn't sent, all URLs (up to a maximum of five external URLs) will be previewed.
* If the message contains attachments or quotes, no URL is previewed.
* Internal URLs are not considered in the `previewUrls` array.
* A maximum of five external URLs is previewed  per message. If there are more than 5 external URLs, no URL is previewed.

{% hint style="warning" %}
URLs that include the same text as the [**Site URL**](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/general#general-settings) are referred to as Internal URLs.
{% endhint %}

#### Message Object

<table><thead><tr><th width="174">Argument</th><th width="196">Example</th><th width="122">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code></td><td><code>ByehQjC44FwMeiLbX</code></td><td>Optional</td><td>The _id of message.</td></tr><tr><td><code>rid</code></td><td><code>ByehQjC44FwMeiLbX</code></td><td>Required</td><td>The room id of where the message is to be sent.</td></tr><tr><td><code>tmid</code></td><td><code>ByehQCh2435MeiLbX</code></td><td>Optional</td><td>The message's id to create a thread.</td></tr><tr><td><code>msg</code></td><td><code>Sample message</code></td><td>Optional</td><td>The text of the message to send, is optional because of attachments.</td></tr><tr><td><code>alias</code></td><td><code>Some Name</code></td><td>Optional</td><td>This will cause the message's name to appear as the given alias, but your username will still display. Require the <code>impersonate-other-user</code> role</td></tr><tr><td><code>emoji</code></td><td><code>:smirk:</code></td><td>Optional</td><td>If provided, this will make the avatar on this message be an emoji. <a href="http://emoji.codes/">Emoji Cheetsheet</a></td></tr><tr><td><code>tshow</code></td><td><code>true</code></td><td>Optional</td><td>Used when replying in a thread. Message will be sent in channel also if value is <code>true</code></td></tr><tr><td><code>avatar</code></td><td><code>http://site.com/logo.png</code></td><td>Optional</td><td>If provided, this will make the avatar use the provided image url. Require the <code>impersonate-other-user</code> role</td></tr><tr><td><code>attachments</code></td><td><code>[{}]</code></td><td>Optional</td><td>See the below section, <a href="send-message.md#attachments-detail">Attachments Detail</a>, for details.</td></tr><tr><td><code>blocks</code></td><td><code>[{}]</code></td><td>Optional</td><td>Add message blocks, see blocks details below.</td></tr><tr><td><code>customFields</code></td><td><code>{"priority": "high"}</code></td><td>Optional</td><td>You can add custom fields for messages. For example, set priorities for messages.<br><br>You must enable this option and define the validation in the workspace settings. See the <a href="https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/message">Message</a> settings for further information.</td></tr></tbody></table>

### Blocks Detail

A message block is an array of objects with any of the following properties. A Blocks can have many sections:

* type
* text
* fields

### Attachments Detail

The attachment is an array of objects with any of the following properties. One attachment can have many sections, including:

* General
* Author Information
* Title Information
* Image
* Audio
* Video
* Table/Fields

<table><thead><tr><th>Property</th><th width="177">Example</th><th width="117">Section</th><th>Description</th></tr></thead><tbody><tr><td><code>color</code></td><td><code>#ff0000</code></td><td>General</td><td>The color you want the order on the left side to be, any value <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-color">background-css</a> supports.</td></tr><tr><td><code>text</code></td><td><code>Sample attachment text</code></td><td>General</td><td>The text to display for this attachment, it is different than the message's text.</td></tr><tr><td><code>ts</code></td><td><code>2016-12-09T16:53:06.761Z</code></td><td>General</td><td>Displays the time next to the <code>text</code> portion.</td></tr><tr><td><code>thumb_url</code></td><td><code>https://site.com/img.png</code></td><td>General</td><td>An image that displays to the left of the <code>text</code>, looks better when this is relatively small.</td></tr><tr><td><code>message_link</code></td><td><code>https://rocket.chat</code></td><td>General</td><td>Only applicable if the <code>ts</code> is provided, as it makes the time clickable to this link.</td></tr><tr><td><code>collapsed</code></td><td><code>false</code></td><td>General</td><td>Causes the image, audio, and video sections to be hiding when collapsed is true.</td></tr><tr><td><code>author_name</code></td><td><code>Bradley Hilton</code></td><td>Author</td><td>Name of the author.</td></tr><tr><td><code>author_link</code></td><td><code>https://bit.ly/</code></td><td>Author</td><td>Providing this makes the author name clickable and points to this link.</td></tr><tr><td><code>author_icon</code></td><td><code>https://site.com/img.png</code></td><td>Author</td><td>Displays a tiny icon to the left of the Author's name.</td></tr><tr><td><code>title</code></td><td><code>Attachment Title</code></td><td>Title</td><td>Title to display for this attachment, displays under the author.</td></tr><tr><td><code>title_link</code></td><td><code>https://youtube.com</code></td><td>Title</td><td>Providing this makes the title clickable, pointing to this link.</td></tr><tr><td><code>title_link_download</code></td><td><code>true</code></td><td>Title</td><td>When this is true, a download icon appears and clicking this saves the link to file.</td></tr><tr><td><code>image_url</code></td><td><code>https://site.com/img.png</code></td><td>Image</td><td>The image to display, will be "big" and easy to see.</td></tr><tr><td><code>audio_url</code></td><td><code>https://site.com/aud.mp3</code></td><td>Audio</td><td>Audio file to play, only supports what <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio">html audio</a> does.</td></tr><tr><td><code>video_url</code></td><td><code>https://site.com/vid.mp4</code></td><td>Video</td><td>Video file to play, only supports what <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video">html video</a> does.</td></tr><tr><td><code>fields</code></td><td><code>[{}]</code></td><td>Fields</td><td>An array of <a href="send-message.md#attachment-field-objects">Attachment Field Objects</a>.</td></tr></tbody></table>

#### Attachment Field Objects

The field property of the attachments allows for "tables" or "columns" to be displayed on messages.

<table><thead><tr><th width="159">Property</th><th width="154">Example</th><th width="187">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>short</code></td><td>true</td><td>Optional Default: <code>false</code></td><td>Whether this field should be a short field.</td></tr><tr><td><code>title</code></td><td><code>Status</code></td><td>Required</td><td>The title of this field.</td></tr><tr><td><code>value</code></td><td><code>online</code></td><td>Required</td><td>The value of this field, displayed underneath the title value.</td></tr></tbody></table>

## Message Object Example

{% tabs %}
{% tab title="Message with Attachments" %}
{% code overflow="wrap" %}
```json
{
   "message": {
      "rid": "Xnb2kLD2Pnhdwe3RH",
      "msg": "Sample message",
      "alias": "Gruggy",
      "emoji": ":smirk:",
      "avatar": "http://res.guggy.com/logo_128.png",
      "attachments": [{
            "color": "#ff0000",
            "text": "Yay for gruggy!",
            "ts": "2016-12-09T16:53:06.761Z",
            "thumb_url": "http://res.guggy.com/logo_128.png",
            "message_link": "https://google.com",
            "collapsed": false,
            "author_name": "Bradley Hilton",
            "author_link": "https://rocket.chat/",
            "author_icon": "https://avatars.githubusercontent.com/u/850391?v=3",
            "title": "Attachment Example",
            "title_link": "https://youtube.com",
            "title_link_download": true,
            "image_url": "http://res.guggy.com/logo_128.png",
            "audio_url": "http://www.w3schools.com/tags/horse.mp3",
            "video_url": "http://www.w3schools.com/tags/movie.mp4",
            "fields": [{
              "short": true,
              "title": "Test",
              "value": "Testing out something or other"
            },{
              "short": true,
              "title": "Another Test",
              "value": "[Link](https://google.com/) something and this and that."
            }]
      }]
  }
}
```
{% endcode %}
{% endtab %}

{% tab title="Message with Blocks" %}
```json
{
   "message":{
      "rid":"GENERAL",
      "blocks":[
         {
            "type":"section",
            "text":{
               "type":"mrkdwn",
               "text":"*Text example* Normal message `code` here"
            }
         },
         {
            "type":"divider"
         },
         {
            "type":"section",
            "fields":[
               {
                  "type":"mrkdwn",
                  "text":"*Field 1*"
               },
               {
                  "type":"mrkdwn",
                  "text":"Field 2"
               }
            ]
         }
      ]
   }
}
```
{% endtab %}
{% endtabs %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/chat.sendMessage \
     -d '{"message": { "rid": "Xnb2kLD2Pnhdwe3RH", "msg": "This is a test!" }}'
```

## Example Call with PreviewURLs

{% code overflow="wrap" %}
```json
curl -L -X POST 'http://localhost:3000/api/v1/chat.sendMessage' \
-H 'x-auth-token: wrhSO31BO6Zn6G5Aa_bj-kMmImONHDjXrOwGtBpQIPM' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ' \
-H 'Content-Type: application/json' \
     -d '{
   "message": {
      "rid": "64f0f82c2c26843a68c1f7ba",
      "msg": "This is a list of links! https://google.com https://hola.org/ https://www.usepayday.com/ https://www.getbumpa.com/ https://www.atlassian.com/software/jira https://writing-demo.dev.rocket.chat"
   },
   "previewUrls": [
      "https://google.com",
      "https://writing-demo.dev.rocket.chat",
      "https://hola.org/",
      "https://www.usepayday.com/",
      "https://www.getbumpa.com/",
      "https://www.atlassian.com/software/jira"
   ]
}'
```
{% endcode %}

## Example Result

```javascript
{
    "message": {
        "rid": "GENERAL",
        "msg": "123456789",
        "ts": "2018-03-01T18:02:26.825Z",
        "u": {
            "_id": "i5FdM4ssFgAcQP62k",
            "username": "rocket.cat",
            "name": "test"
        },
        "unread": true,
        "mentions": [],
        "channels": [],
        "_updatedAt": "2018-03-01T18:02:26.828Z",
        "_id": "LnCSJxxNkCy6K9X8X"
    },
    "success": true
}
```

## Change Log

| Version | Description                         |
| ------- | ----------------------------------- |
| 2.4.0   | Added validation on user's identity |
| 0.60.0  | Added                               |
| 6.4.0   | Add `previewUrls` param             |
