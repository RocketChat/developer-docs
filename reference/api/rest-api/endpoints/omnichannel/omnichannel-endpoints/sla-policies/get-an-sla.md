# Get an SLA

Get details of an SLA policy.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-sla` or `view-l-room` permission.
{% endhint %}

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `api/v1/livechat/sla/:slaId` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                 |
| -------------- | -------------- | -------- | --------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated ouser ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                 |

## Path Parameters

| Argument | Example                    | Required | Description                 |
| -------- | -------------------------- | -------- | --------------------------- |
| `slaId`  | `641daf3d7718f90c810429c8` | Required | The Id of the SLA to fetch. |

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/sla/641daf3d7718f90c810429c8' \
--header 'X-Auth-Token: q2zjkgQt_OmYaBY4nEp50-r7yUAqVIoAqgo0jjBIws5' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```

## Example Result

### Success

```json
{
    "_id": "641daf3d7718f90c810429c8",
    "name": "Minimal",
    "description": "2m UI creat",
    "dueTimeInMinutes": 2,
    "_updatedAt": "2023-03-24T14:10:05.063Z",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-sla` or `view-l-room` permission.
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
```
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
