# Add a User to a Room

Add User To a Room.

| Name            | Requires Auth | Permission | Setting |
| --------------- | ------------- | ---------- | ------- |
| `addUserToRoom` | Yes           |            |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example                                                                                                                                                                           | Required | Description                             |
| -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | --------------------------------------- |
| `data`   | <p></p><pre class="language-postman_json"><code class="lang-postman_json"> {
            "rid": "64f0f82c21c26843a68c1f7ba",
            "username": "rodriq"
    }
</code></pre> | Required | An object of the `roomid` and `userId.` |

## Example Call

```javascript
{
    "msg": "method",
    "method": "addUserToRoom",
    "id": "2",
    "params": [
        {
	"rid":"64f0f82c2c26843a68c1f7ba",
        "username":"rodriq"
	}
    ]
}
```

## **Example Response**

### **Success**

```json
{
"msg":"result",
"id":"2"
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}
