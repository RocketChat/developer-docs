# Get statistics list

{% hint style="info" %}
Selectable statistics about the Rocket.Chat server. It supports the [Offset, Count and Sort Query Parameters](../other-important-endpoints/offset-and-count-and-sort-info.md) along with just the [Fields and Query Parameters](../other-important-endpoints/query-and-fields-info.md). Requires `view-statistics` permission.
{% endhint %}

| URL                      | Requires Auth | HTTP Method |
| ------------------------ | ------------- | ----------- |
| `api/v1/statistics.list` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument | Example                                         | Required | Description                                                                                 |
| -------- | ----------------------------------------------- | -------- | ------------------------------------------------------------------------------------------- |
| `query`  | `{"_id":"v3D4mvobwfznKozH8"}`                   | Required | See [Query Parameter](../other-important-endpoints/query-and-fields-info.md)                |
| `offset` | `0`                                             | Optional | See [Offset Parameter](../other-important-endpoints/offset-and-count-and-sort-info.md)      |
| `count`  | `1`                                             | Optional | See [Count Parameter](../other-important-endpoints/offset-and-count-and-sort-info.md)       |
| `fields` | `{"os":0,"migration":0,"deploy":0,"process":0}` | Optional | See [Fields Parameters](../other-important-endpoints/query-and-fields-info.md)              |
| `sort`   | `{"_id":1}`                                     | Optional | See [Sort Query Parameters](../other-important-endpoints/offset-and-count-and-sort-info.md) |

## Example Call

A request below performs a statistic search for a server instance with `_id: v3D4mvobwfznKozH8` except response fields like `os`, `migration`, `deploy`, `proces`.

```bash
curl -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
     -H "X-User-Id: ew28FnZqipDpvKw3R" \
     "http://localhost:3000/api/v1/statistics.list?query=%7B%22_id%22%3A%22v3D4mvobwfznKozH8%22%7D&fields=%7B%22os%22%3A0%2C%22migration%22%3A0%2C%22deploy%22%3A0%2C%22process%22%3A0%7D"
```

## Result

### Success

```javascript
{
  "statistics": [
    {
      "_id":"v3D4mvobwfznKozH8",
      "uniqueId":"wD4EP3M7FeFzJZgk9",
      "installedAt":"2018-02-18T19:40:45.369Z",
      "version":"0.61.0-develop",
      "totalUsers":88,
      "activeUsers":88,
      "nonActiveUsers":0,
      "onlineUsers":0,
      "awayUsers":1,
      "offlineUsers":87,
      "totalRooms":81,
      "totalChannels":41,
      "totalPrivateGroups":37,
      "totalDirect":3,
      "totlalLivechat":0,
      "totalMessages":2408,
      "totalChannelMessages":730,
      "totalPrivateGroupMessages":1869,
      "totalDirectMessages":25,
      "totalLivechatMessages":0,
      "lastLogin":"2018-02-24T12:44:45.045Z",
      "lastMessageSentAt":"2018-02-23T18:14:03.490Z",
      "lastSeenSubscription":"2018-02-23T17:58:54.779Z",
      "instanceCount":1,
      "createdAt":"2018-02-24T15:13:00.312Z",
      "_updatedAt":"2018-02-24T15:13:00.312Z"
    }
  ],
  "count":1,
  "offset":0,
  "total":1,
  "success":true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}
