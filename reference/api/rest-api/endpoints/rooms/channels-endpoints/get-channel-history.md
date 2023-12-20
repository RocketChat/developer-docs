# Get Channel History

Retrieves the messages from a channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="325">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.history</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="212">Key</th><th width="234">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>latest</code></td><td><code>2016-09-30T13:42:25.304Z</code></td><td>The end of time range of messages to retrieve. The default value is the current date and time.</td></tr><tr><td><code>oldest</code></td><td><code>2016-05-30T13:42:25.304Z</code></td><td>The start of the time range of messages to retrieve</td></tr><tr><td><code>inclusive</code></td><td><code>true</code></td><td>Whether messages which land on the latest and oldest dates should be included. The default value is <code>false</code>.</td></tr><tr><td><code>offset</code></td><td><code>10</code></td><td>The offset of the list messages to retrieve. By default, the value is <code>0</code>.</td></tr><tr><td><code>count</code></td><td><code>100</code></td><td>The number of messages to retrieve. By default, the value is <code>20</code>.</td></tr><tr><td><code>unreads</code></td><td><code>false</code></td><td>Whether the number of unread messages should be included. The default value is <code>false</code>.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.history?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
  "messages": [
    {
      "_id": "AkzpHAvZpdnuchw2a",
      "rid": "ByehQjC44FwMeiLbX",
      "msg": "hi",
      "ts": "2016-12-09T12:50:51.555Z",
      "u": {
        "_id": "y65tAmHs93aDChMWu",
        "username": "testing"
      },
      "_updatedAt": "2016-12-09T12:50:51.562Z"
    },
    {
      "_id": "vkLMxcctR4MuTxreF",
      "t": "uj",
      "rid": "ByehQjC44FwMeiLbX",
      "ts": "2016-12-08T15:41:37.730Z",
      "msg": "testing2",
      "u": {
        "_id": "bRtgdhzM6PD9F8pSx",
        "username": "testing2"
      },
      "groupable": false,
      "_updatedAt": "2016-12-08T16:03:25.235Z"
    },
    {
      "_id": "bfRW658nEyEBg75rc",
      "t": "uj",
      "rid": "ByehQjC44FwMeiLbX",
      "ts": "2016-12-07T15:47:49.099Z",
      "msg": "testing",
      "u": {
        "_id": "nSYqWzZ4GsKTX4dyK",
        "username": "testing1"
      },
      "groupable": false,
      "_updatedAt": "2016-12-07T15:47:49.099Z"
    },
    {
      "_id": "pbuFiGadhRZTKouhB",
      "t": "uj",
      "rid": "ByehQjC44FwMeiLbX",
      "ts": "2016-12-06T17:57:38.635Z",
      "msg": "testing",
      "u": {
        "_id": "y65tAmHs93aDChMWu",
        "username": "testing"
      },
      "groupable": false,
      "_updatedAt": "2016-12-06T17:57:38.635Z"
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description             |
| ------- | ----------------------- |
| 0.75.0  | Added `offset` property |
| 0.47.0  | Added                   |
