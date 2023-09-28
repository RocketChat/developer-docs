---
description: Get the details of a priority
---

# Get a Priority

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `manage-livechat-priorities` or `view-l-room permission`.
{% endhint %}

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `livechat/priorities/:priorityId` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variables

| Argument     | Example                    | Required | Description |
| ------------ | -------------------------- | -------- | ----------- |
| `priorityId` | `64007cc2fa0ed7dd905092e3` | Required | Priority ID |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/livechat/priorities/64007cc2fa0ed7dd905092e3' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```

## Result

```javascript
{
    "_id": "64007cc2fa0ed7dd905092e3",
    "i18n": "Lowest",
    "sortItem": 5,
    "dirty": false,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-priorities` or `view-l-room` permission.
* **Not Found**: This error gets returned when no Priority is found with the Id provided.

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
    "error": "Priority with id :priorityId not found"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `6.0.0` | Added       |
