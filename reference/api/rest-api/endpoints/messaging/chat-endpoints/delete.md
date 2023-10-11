---
description: Chat Message Delete
---

# Chat Message Delete

| URL                   | Requires Auth | HTTP Method |
| --------------------- | ------------- | ----------- |
| `/api/v1/chat.delete` | `yes`         | `POST`      |

## Payload

| Argument | Example             | Required                  | Description                                                    |
| -------- | ------------------- | ------------------------- | -------------------------------------------------------------- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required                  | The room id of where the message is to delete.                 |
| `msgId`  | `7aDSXtjMA3KPLxLjt` | Required                  | The message id to delete.                                      |
| `asUser` | `true`              | Optional Default: `false` | Whether the message should be deleted as the user who sent it. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/chat.delete \
     -d '{ "roomId": "ByehQjC44FwMeiLbX", "msgId": "7aDSXtjMA3KPLxLjt", "asUser": true }'
```

## Example Result

### Success

```javascript
{
    "_id": "jEnjsxuoDJamGjbH2",
    "ts": "1696533809813",
    "message": {
        "_id": "jEnjsxuoDJamGjbH2",
        "rid": "6GFJ3tbmHiyHbahmC",
        "u": {
            "_id": "5fRTXMt7DMJbpPJfh",
            "username": "test.funke",
            "name": "TestFunke"
        }
    },
    "success": true
}
```

### Errors

The following errors can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Room Id does not match**: Occurs when the room id provided does not match where the message is from

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Room Id does not match" %}
```
{
    "success": false,
    "error": "The room id provided does not match where the message is from."
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
