# stream-room-messages

Stream room messages.

## Payload Parameters

<table><thead><tr><th>Argument</th><th>Example</th><th width="152">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code></td><td><code>64a1f373376181965ab77f54</code></td><td>Required</td><td>The room id</td></tr><tr><td><code>back-compatibility</code></td><td><code>false</code></td><td>Required</td><td>Boolean to set back-compatibility.</td></tr></tbody></table>

## Example Call

```javascript

{
    "msg": "sub",
    "id": "89494",
    "name": "stream-room-messages",
    "params":[
        "64a1f373376181965ab77f54",
        false
    ]
}

```

## Example Response

```javascript
{
    "msg":"ready",
    "subs":[
        "89494"
    ]
}
```
