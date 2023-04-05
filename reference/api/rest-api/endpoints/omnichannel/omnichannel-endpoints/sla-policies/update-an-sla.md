# Update an SLA

Update and existing SLA.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-sla` permission.
{% endhint %}

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `api/v1/livechat/sla/:slaId` | `YES`         | `PUT`       |

## Headers

| Argument       | Example        | Required | Description                 |
| -------------- | -------------- | -------- | --------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated ouser ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                 |

## Path Parameters

| Argument | Example                    | Required | Description                  |
| -------- | -------------------------- | -------- | ---------------------------- |
| `slaId`  | `641daf3d7718f90c810429c8` | Required | The Id of the SLA to update. |

## Payload

| Argument           | Example                   | Required | Description                 |
| ------------------ | ------------------------- | -------- | --------------------------- |
| `name`             | `Minimal updated`         | Optional | The name of the SLA policy. |
| `description`      | `sla description updated` | Optional | The SLA description.        |
| `dueTimeInMinutes` | 7                         | Optional | The SLA due time.           |

## Example Call

```powershell
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/sla/641daf3d7718f90c810429c8' \
--header 'X-Auth-Token: q2zjkgQt_OmYaBY4nEp50-r7yUAqVIoAqgo0jjBIws5' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "name": "Minimal  updated",
    "description": "Minimal SLA updated",
    "dueTimeInMinutes": 7
}'
```

## Example Result

### Success

```json
{
    "sla": {
        "name": "Minimal updated",
        "description": "Minimal SLA updated",
        "dueTimeInMinutes": 7,
        "_updatedAt": "2023-03-24T16:31:34.712Z",
        "_id": "641daf3d7718f90c810429c8"
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-sla` permission.
* **Not Found**: This error gets returned when no SLA is found with the Id provided.

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

{% tab title="Not Found" %}
```json
{
    "success": false,
    "error": "SLA with id gfgfg56g429c8 not found"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
