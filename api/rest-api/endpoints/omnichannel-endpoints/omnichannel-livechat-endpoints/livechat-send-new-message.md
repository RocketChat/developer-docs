---
description: Send a new Livechat message
---

# Livechat Send New Message

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/message` | `no` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `token` | `iNKE8a6k6cjbqWhWd` | Required | Visitor `token`. |
| `rid` | `zRAeTszXor8CCPceB` | Required | Room `_id`. |
| `msg` | `sending livechat message..` | Required | Message `text`. |
| `_id` |  | Optional | Message `_id`. |
| `agent` |  | Optional | Room `agent`. |

## Example payload

```javascript
{
  "token": "iNKE8a6k6cjbqWhWd",
  "rid": "zRAeTszXor8CCPceB",
  "msg": "sending livechat message.."
}
```

## Example Call

```bash
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/message \
     -d '{"token": "iNKE8a6k6cjbqWhWd", "rid": "zRAeTszXor8CCPceB", "msg": "sending livechat message.."}'
```

## Example Result

```javascript
{
  "message": {
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "msg": "sending livechat message..",
    "u": {
      "_id": "iNKE8a6k6cjbqWhWd",
      "username": "guest-4",
      "name": "Livechat Visitor"
    },
    "ls": "2018-09-14T13:31:33.201Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.70.0 | Added |

## Updates a Livechat message

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/message/:_id` | `no` | `PUT` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `_id` | `ZKWP8LfGnRHQ3ozWa` | Required | Message `_id`. |
| `token` | `iNKE8a6k6cjbqWhWd` | Required | Visitor `token`. |
| `rid` | `zRAeTszXor8CCPceB` | Required | Room `_id`. |
| `msg` | `editing a livechat message..` | Required | Message `text`. |

## Example payload

```javascript
{
  "token": "iNKE8a6k6cjbqWhWd",
  "rid": "zRAeTszXor8CCPceB",
  "msg": "editing a livechat message.."
}
```

## Example Call

```bash
curl -X PUT \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/message/ZKWP8LfGnRHQ3ozWa \
     -d '{"token": "iNKE8a6k6cjbqWhWd", "rid": "zRAeTszXor8CCPceB", "msg": "editing a livechat message.."}'
```

## Example Result

```javascript
{
  "message": {
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "msg": "editing livechat message..",
    "u": {
      "_id": "YgEoq2djbGdjjZnsL",
      "username": "guest-4",
      "name": "Livechat Visitor"
    },
    "ls": "2018-09-14T13:31:33.201Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.70.0 | Added |

## Removes a Livechat message

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/message/:_id` | `no` | `DELETE` |

## Payload

| Argument | Example | Required | Descriptio |
| :--- | :--- | :--- | :--- |
| `_id` | `ZKWP8LfGnRHQ3ozWa` | Required | Message `_id`. |

## Example Call

```bash
curl -X DELETE \
     http://localhost:3000/api/v1/livechat/message/ZKWP8LfGnRHQ3ozWa
```

## Example Result

```javascript
{
  "message": {
    "_id": "ZKWP8LfGnRHQ3ozWa",
    "ls": "2018-09-14T13:31:33.279Z"
  },
  "success": true
}
```

## 



