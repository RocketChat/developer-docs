---
description: Update call status of an existing webrtc audio/video call.
---

# Update Call Status

| URL                                   | Requires Auth | HTTP Method |
| ------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/webrtc.call/:callId` | `YES`         | `PUT`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variables

| Argument | Example             | Required | Description             |
| -------- | ------------------- | -------- | ----------------------- |
| `callId` | `zRAeTszXor8CCPceB` | Required | The call message `_id`. |

## Example Payload

```javascript
{
    rid: 'abc123xyzabc',
    status: 'ended'
}
```

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/webrtc.call/zRAeTszXor8CCPceB\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name' \
-d '{ "rid": "abc123xyzabc", "status": "ended" }'
```

## Result

```javascript
{
    "status": "ended",
    "success": true
}
```
