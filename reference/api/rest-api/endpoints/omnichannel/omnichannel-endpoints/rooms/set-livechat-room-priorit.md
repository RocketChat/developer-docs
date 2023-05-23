# Set Livechat room Priority

Set the priority of a Live Chat room.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `view-l-room` permission.
{% endhint %}

| URL                                  | Requires Auth | HTTP Method |
| ------------------------------------ | ------------- | ----------- |
| `api/v1/livechat/room/:rid/priority` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                 |
| -------------- | -------------- | -------- | --------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated ouser ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                 |

## Path Parameters

| Argument | Example             | Required | Description                   |
| -------- | ------------------- | -------- | ----------------------------- |
| `rid`    | `tcbbSmWSLR5uo5PBW` | Required | The Id of the Live Chat room. |

## Payload

| Argument     | Example                    | Required | Description                    |
| ------------ | -------------------------- | -------- | ------------------------------ |
| `priorityId` | `64007cc2fa0ed7dd905092e6` | Required | The Id of the priority to set. |

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/room/tcbbSmWSLR5uo5PBW/priority' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "priorityId": "64007cc2fa0ed7dd905092e6"
}'
```

## Example Result

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `view-l-room` permission.
* **Invalid Parameter**: Gets returned when no priority Id is sent in the body.
* **Invalid priority**: This error gets returned when no Priority is found with the Id provided.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "error-not-authorized"
}
```
{% endtab %}

{% tab title="Unable to Update" %}
```json
{
    "success": false,
    "error": "must have required property 'priorityId' [invalid-params]",
    "errorType": "invalid-params"
}
```
{% endtab %}

{% tab title="Invalid Priority" %}
```json
{
    "success": false,
    "error": "error-invalid-priority"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
