# List Custom Emoji

Returns a list of [custom emoji ](https://docs.rocket.chat/use-rocket.chat/workspace-administration/custom-emoji)registered in the workspace.

| Name              | Requires Auth | Permission | Setting |
| ----------------- | ------------- | ---------- | ------- |
| `listEmojiCustom` | Yes           |            |         |

### Example Call

```javascript
{
    "msg": "method",
    "method": "listEmojiCustom",
    "id": "42",
    "params": []
}
```

### Example Response

```javascript
{
    "msg": "result",
    "id": "42",
    "result": [
        {
            "_id": "64a4ac9c7d04b8fc25af9c9d",
            "name": "hola",
            "aliases": [
                "smiley"
            ],
            "extension": "png",
            "_updatedAt": {
                "$date": 1688513692757
            }
        }
    ]
}
```

## The Emoji Object

The `emoji` is defined as:

* `_id`: The emoji id
* `name`: The emoji friendly name
* `aliases`: A collection of alias for the emoji. The alias is used to identify the emoji on the text and for fast reference from typing( `:emoji-alias:`) .
* `extension`: The emoji file extension
* `_updatedAt`: The date when the emoji was updated to the server

## Showing the emoji image

To show the custom emoji images, you simply need to request this URL:

> ${ path }/emoji-custom/${ encoded(name) } }.${ extension }.

Example:

```javascript
{
    "_id": "emoji-id",
    "name": "Emoji Name",
    "aliases": [ "emoji-alias" ],
    "extension": "png",
    "_updatedAt": { "$date": 1480377601 }
}
```

The URL to access this emoji will be:

`http://yourhost.com/emoji-custom/Emoji%20Name.png`
