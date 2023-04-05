# Update Priority

Update an existing Priority.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-priorities` permission.
{% endhint %}

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `livechat/priorities/:priorityId` | `YES`         | `PUT`       |

## Headers

| Argument       | Example        | Required | Description                 |
| -------------- | -------------- | -------- | --------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated ouser ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                 |

## Path Parameters

| Argument     | Example                    | Required | Description                       |
| ------------ | -------------------------- | -------- | --------------------------------- |
| `priorityId` | `641daf3d7718f90c810429c8` | Required | The Id of the Priority to update. |

## Payload

| Argument | Example    | Required | Description               |
| -------- | ---------- | -------- | ------------------------- |
| `name`   | `Very low` | Optional | The name of the Priority. |

## Example Call

```powershell
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/priorities/64007cc2fa0ed7dd905092e3' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "name": "Very low"
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
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-priorities` permission.
* **Unable to Update**: This error gets returned when no Priority is found with the Id provided.
* **Duplicate**: Occurs when the priority to be updated will cause a duplicate.

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
    "error": "error-unable-to-update-priority"
}
```
{% endtab %}

{% tab title="Duplicate" %}
```json
{
    "success": false,
    "error": "error-duplicate-priority-name"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
