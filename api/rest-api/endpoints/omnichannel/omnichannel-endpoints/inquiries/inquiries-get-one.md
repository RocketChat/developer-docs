# Inquiries Get One

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.getOne` | `yes` | `GET` |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `inquiryId` | `ByehQjC44FwMeiLbX` | Optional | The department's id or name |
| `userId` |  |  |  |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/inquiries.list
```

## Example Result

```javascript
{
    "inquiry": {
        "_id": "rQFQMEGeWmntxyYMk",
        "rid": "myPNwjZr4z27Mi7qW",
        "name": "low",
        "ts": "2021-07-22T14:42:40.510Z",
        "department": "CAJioQNAvLnYWTy8i",
        "message": "",
        "status": "taken",
        "v": {
            "_id": "yAivGTq4FcsjpvsdB",
            "username": "guest-536",
            "token": "io5srgou19520h67ex4i2",
            "status": "online"
        },
        "t": "l",
        "queueOrder": 1,
        "estimatedWaitingTimeQueue": 0,
        "estimatedServiceTimeAt": "2021-07-22T14:42:40.510Z",
        "_updatedAt": "2021-07-22T14:45:45.723Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 1.2.0 | Added |

## Livechat take inquiry

Takes an open inquiry.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.take` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `inquiryId` | `ByehQjC44FwMeiLbX` | Required | The inquiry's id |
| `userId` | `ByehQjCfsd876sfd` | Optional | The user's \(agent\) id to take the inquiry. |

**Note: if the user id is provided, the user must have the `view-l-room` permission.**

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/inquiries.take \
     -d '{ "inquiryId": "ByehQjC44FwMeiLbX" }'
```

## Example Result

```javascript
{
    "inquiry": {
        "_id": "wbKmn6pAZ8jyJuANG",
        "rid": "S4wwL9WNY98uoHgJg",
        "message": "test",
        "name": "teste",
        "ts": "2019-06-10T23:09:06.482Z",
        "agents": [
            "hjwGZafNqExtFNmN7",
            "26KdXgrQXhddy2MfQ"
        ],
        "status": "open",
        "v": {
            "_id": "2iZSexGXjW7EJnRwM",
            "username": "guest-3",
            "token": "RtQzkfQYKG4WpNMEW",
            "status": "online"
        },
        "t": "l",
        "_updatedAt": "2019-06-10T23:09:07.480Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 1.2.0 | Added |

## Livechat Get one inquiry by room id

Get one inquiry by room id.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.getOne` | `yes` | `GET` |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required | The room's id |

**Note: if the user id is provided, the user must have the `view-l-room` permission.**

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/inquiries.getOne?roomId=ByehQjC44FwMeiLbX
```

## Example Result

```javascript
{
  "inquiry": {
    "_id": "EMXtMA7mPPNkQtWWq",
    "rid": "MA6HRhkEdRGATfEbh",
    "name": "inquiry test",
    "ts": "2019-12-13T18:54:25.352Z",
    "message": "",
    "status": "queued",
    "v": {
      "_id": "rLitbjv7e9WyLBCR4",
      "username": "guest-14",
      "token": "btzu0qdm0sjsn7aqm78kzr",
      "status": "offline"
    },
    "t": "l",
    "_updatedAt": "2019-12-13T19:33:13.255Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 2.4.0 | Added |

