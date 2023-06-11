---
description: Starts a webrtc audio/video call.
---

# Start Call

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `api/v1/livechat/webrtc.call` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Variables

| Argument | Example             | Required | Description     |
| -------- | ------------------- | -------- | --------------- |
| `rid`    | `zRAeTszXor8CCPceB` | Required | The room `_id`. |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/webrtc.call?rid=123abcxyz123\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "videoCall": {
        "rid": "123abcxyz123",
        "provider": "webrtc",
        "callStatus": "ringing"
    },
    "success": true
}
```
