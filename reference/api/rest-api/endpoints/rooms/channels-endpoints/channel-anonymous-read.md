# Channel Anonymous Read

Gets the messages in public channels to an anonymous user, if the server has the setting `Accounts_AllowAnonymousRead` enabled.&#x20;

<table><thead><tr><th width="163">HTTP Method</th><th width="339">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.anonymousread</code></td><td><code>no</code></td></tr></tbody></table>

## Query Parameters

This endpoint supports the [#pagination](../../../#pagination "mention") parameters, alongside the  [#query-and-fields](../../../#query-and-fields "mention") parameters.

<table><thead><tr><th width="234.33333333333331">Key</th><th width="236">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>testChannel</code></td><td>The channel room ID or name. You must enter at least one of these parameters.</td></tr></tbody></table>

## Example Call

```bash
curl -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.anonymousread?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
    "messages": [
        {
            "_id": "xadufzmxzYQp4H9py",
            "alias": "test",
            "msg": "Example message",
            "attachments": [],
            "parseUrls": true,
            "bot": {
                "i": "MnQyfhWt5LqZotyfc"
            },
            "groupable": false,
            "ts": "2018-10-05T01:10:47.524Z",
            "u": {
                "_id": "rocket.cat",
                "username": "rocket.cat",
                "name": "Rocket.Cat"
            },
            "rid": "GENERAL",
            "_updatedAt": "2018-10-05T13:42:51.163Z",
            "reactions": {
                ":grin:": {
                    "usernames": [
                        "marcos.defendi"
                    ]
                }
            },
            "mentions": [],
            "channels": [],
            "starred": {
                "_id": "KPkEYwKKBKZnEEPpt"
            }
        },
        {
            "_id": "id-1538701845987",
            "rid": "GENERAL",
            "msg": "This message was edited via API",
            "alias": "Gruggy",
            "emoji": ":smirk:",
            "avatar": "http://res.guggy.com/logo_128.png",
            "attachments": [
                {
                    "collapsed": false,
                    "color": "#ff0000",
                    "text": "Yay for gruggy!",
                    "ts": "2016-12-09T16:53:06.761Z",
                    "message_link": "https://google.com",
                    "thumb_url": "http://res.guggy.com/logo_128.png",
                    "author_name": "Bradley Hilton",
                    "author_link": "https://rocket.chat/",
                    "author_icon": "https://avatars.githubusercontent.com/u/850391?v=3",
                    "title": "Attachment Example",
                    "title_link": "https://youtube.com",
                    "title_link_download": true,
                    "image_url": "http://res.guggy.com/logo_128.png",
                    "audio_url": "http://www.w3schools.com/tags/horse.mp3",
                    "video_url": "http://www.w3schools.com/tags/movie.mp4",
                    "fields": [
                        {
                            "short": true,
                            "title": "Test",
                            "value": "Testing out something or other"
                        },
                        {
                            "short": true,
                            "title": "Another Test",
                            "value": "[Link](https://google.com/) something and this and that."
                        }
                    ]
                }
            ],
            "ts": "2018-10-05T01:10:45.994Z",
            "u": {
                "_id": "rocketchat.internal.admin.test",
                "username": "rocketchat.internal.admin.test",
                "name": "RocketChat Internal Admin Test"
            },
            "_updatedAt": "2018-10-05T01:10:47.064Z",
            "editedBy": {
                "_id": "rocketchat.internal.admin.test",
                "username": "rocketchat.internal.admin.test"
            },
            "editedAt": "2018-10-05T01:10:46.384Z",
            "reactions": {
                ":smile:": {
                    "usernames": [
                        "rocketchat.internal.admin.test"
                    ]
                },
                ":squid:": {
                    "usernames": [
                        "rocketchat.internal.admin.test"
                    ]
                },
                ":bee:": {
                    "usernames": [
                        "rocketchat.internal.admin.test"
                    ]
                },
                ":ant:": {
                    "usernames": [
                        "rocketchat.internal.admin.test"
                    ]
                }
            },
            "mentions": [],
            "channels": [],
            "urls": []
        },
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.2.0   | Added       |
