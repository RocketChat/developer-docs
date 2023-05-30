---
description: Convert a channel to team
---

# Convert channel to team

| URL                              | Requires Auth | HTTP Method |
| -------------------------------- | ------------- | ----------- |
| `/api/v1/channels.convertToTeam` | `yes`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument      | Example              | Required | Description        |
| ------------- | -------------------- | -------- | ------------------ |
| `channelName` | `documentation-team` | Required | The channel's name |
| OR            |                      |          |                    |
| `channelId`   | `ByehQjC44FwMeiLbX`  | Required | The channel's id   |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.channels.convertToTeam
     -d '{ "channelName": "documentation-team" }'
```

## Example Result

```javascript
{
    "team": {
        "_id": "612b8ae982d286c3d1f5db31",
        "name": "documentation-team",
        "type": 0,
        "createdAt": "2021-08-29T13:26:01.750Z",
        "createdBy": {
            "_id": "JxemcN9PDCdfzJeZr",
            "username": "renato.becker"
        },
        "_updatedAt": "2021-08-29T13:26:01.750Z",
        "roomId": "GwktYAajqw4RiWiBK"
    },
    "success": true
}
```
