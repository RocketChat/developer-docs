# Create SLA Policy

Create a new SLA Policy.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-sla` permission.
{% endhint %}

| URL                   | Requires Auth | HTTP Method |
| --------------------- | ------------- | ----------- |
| `api/v1/livechat/sla` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                |
| -------------- | -------------- | -------- | -------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                |

## Payload

| Argument           | Example           | Required | Description                 |
| ------------------ | ----------------- | -------- | --------------------------- |
| `name`             | `grand`           | Required | The name of the SLA policy. |
| `description`      | `sla description` | Required | The SLA description.        |
| `dueTimeInMinutes` | 4                 | Required | The SLA due time.           |

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/sla' \
--header 'X-Auth-Token: q2zjkgQt_OmYaBY4nEp50-r7yUAqVIoAqgo0jjBIws5' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "name": "Optimum",
    "description": "OPtimum SLA",
    "dueTimeInMinutes": 4
}'
```

## Example Result

### Success

```json
{
    "sla": {
        "name": "Optimum",
        "description": "Ptimum SLA",
        "dueTimeInMinutes": 4,
        "_id": "641db89a7718f90c810429cc"
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have  `manage-livechat-sla` permission.
* **Invalid Parameter**: Occurs when a required parameter is not passed.
* **Duplicate**: When an SLA is created having the same name or dueTimeInMinutes as an existing SLA.

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

{% tab title="Invalid Parameter" %}
```
{
    "success": false,
    "error": "must have required property 'name' [invalid-params]",
    "errorType": "invalid-params"
}
```
{% endtab %}

{% tab title="Duplicate" %}
```
{
    "success": false,
    "error": "error-duplicated-sla"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
