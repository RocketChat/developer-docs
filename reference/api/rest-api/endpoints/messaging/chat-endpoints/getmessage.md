# Get Message

Retrieves a single chat message for the message ID. You must have permission to access the room where the message is.

| URL                       | Requires Auth | HTTP Method |
| ------------------------- | ------------- | ----------- |
| `/api/v1/chat.getMessage` | `yes`         | `GET`       |

## Path Variables

<table><thead><tr><th width="169">Argument</th><th>Example</th><th width="162">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>msgId</code></td><td><code>7aDSXtjMA3KPLxLjt</code></td><td>Required</td><td>The ID of the message to get.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/chat.getMessage?msgId=7aDSXtjMA3KPLxLjt
```

## Example Result

```json
{
  "message": {
    "_id": "7aDSXtjMA3KPLxLjt",
    "rid": "GENERAL",
    "msg": "This is a test!",
    "ts": "2016-12-14T20:56:05.117Z",
    "u": {
      "_id": "y65tAmHs93aDChMWu",
      "username": "graywolf336"
    }
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.47.0  | Added       |
