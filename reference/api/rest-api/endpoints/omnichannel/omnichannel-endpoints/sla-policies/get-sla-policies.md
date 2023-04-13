# Get SLA Policies

Get a list of all SLA policies.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

It supports the [Offset, Count, and Sort Query Parameters](../../../other-important-endpoints/offset-and-count-and-sort-info.md).

{% hint style="info" %}
You are required to have the `manage-livechat-sla` or `view-l-room` permission.
{% endhint %}

| URL                   | Requires Auth | HTTP Method |
| --------------------- | ------------- | ----------- |
| `api/v1/livechat/sla` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                |
| -------------- | -------------- | -------- | -------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                |

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/sla' \
--header 'X-Auth-Token: q2zjkgQt_OmYaBY4nEp50-r7yUAqVIoAqgo0jjBIws5' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```

## Example Result

### Success

```json
{
    "sla": [
        {
            "_id": "641daf3d7718f90c810429c8",
            "name": "Minimal",
            "description": "2m UI creat",
            "dueTimeInMinutes": 2,
            "_updatedAt": "2023-03-24T14:10:05.063Z"
        },
        {
            "_id": "6417f67528384134ed600dc6",
            "name": "Try",
            "description": "Based on 1 min",
            "dueTimeInMinutes": 1,
            "_updatedAt": "2023-03-20T06:00:21.736Z"
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-sla` or `view-l-room` permission.

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
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
