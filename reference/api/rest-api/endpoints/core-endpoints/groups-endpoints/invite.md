# Group Invite

Invite one user or bulk users to the private group.

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/groups.invite` | `yes`         | `POST`      |

## Invite a user

### Payload

| Argument | Example             | Required | Description                     |
| -------- | ------------------- | -------- | ------------------------------- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required | The private group's id          |
| `userId` | `nSYqWzZ4GsKTX4dyK` | Required | The user id of the invited user |

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.invite \
     -d '{ "roomId": "ByehQjC44FwMeiLbX", "userId": "nSYqWzZ4GsKTX4dyK" }'
```

### Example Result

```javascript
{
  "group": {
    "_id": "ByehQjC44FwMeiLbX",
    "ts": "2016-11-30T21:23:04.737Z",
    "t": "p",
    "name": "testing",
    "username": "testing",
    "u": {
        "_id": "aobEdbYhXfu5hkeqG",
        "username": "testing1"
    },
    "msgs": 1,
    "_updatedAt": "2016-12-09T12:50:51.575Z",
    "lm": "2016-12-09T12:50:51.555Z"
  },
  "success": true
}
```

## Invite bulk users

### Payload

| Argument  | Example                                    | Required | Description                       |
| --------- | ------------------------------------------ | -------- | --------------------------------- |
| `roomId`  | `ByehQjC44FwMeiLbX`                        | Required | The private group's id            |
| `userIds` | `["nSYqWzZ4GsKTX4dyK", "SYqWzZ4Gsasdfgh"]` | Required | The user ids of the invited users |

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.invite \
     -d '{ "roomId": "ByehQjC44FwMeiLbX", "userIds": ["nSYqWzZ4GsKTX4dyK", "SYqWzZ4Gsasdfgh"] }'
```

### Example Result

```javascript
{
  "group": {
    "_id": "ByehQjC44FwMeiLbX",
    "ts": "2016-11-30T21:23:04.737Z",
    "t": "p",
    "name": "testing",
    "usernames": [
      "testing",
      "testing1"
    ],
    "u": {
        "_id": "aobEdbYhXfu5hkeqG",
        "username": "testing1"
    },
    "msgs": 1,
    "_updatedAt": "2016-12-09T12:50:51.575Z",
    "lm": "2016-12-09T12:50:51.555Z"
  },
  "success": true
}
```

## Error

If you are an administrator and try to invite a user to a private group, of which you are not a member, then you will get an error:

```javascript
{
  "success": false,
  "error": "Not allowed [error-not-allowed]",
  "errorType": "error-not-allowed",
  "details": {
    "method": "addUsersToRoom"
  }
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
