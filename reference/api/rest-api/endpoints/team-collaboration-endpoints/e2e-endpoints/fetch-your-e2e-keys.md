---
description: Retrieves E2E keys of logged in user
---

# Fetch your E2E Keys

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/e2e.fetchMyKeys` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/e2e.fetchMyKeys\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
{
    "public_key": "{\"alg\":\"RSA-OAEP-256\",\"e\":\"AQAB\",\"ext\"AN2Q\"}",
    "private_key": "{\"$binary\":\"xdNrwywNqmAxTWCvVeNEZL0pDPtmSlLblyqLhr7T18sA3KKzv/5s/7FFVQGoKRa8j6F1SUjFFblKPynkcuIvSyzsGs1lfKnkq5k2N32WciNptOnWkNkPDJJuvuRFiL/UffVT7edwyeNL+jW4tJdyucS/r25rPcaRuMM/kFcCdyZM0D22kYDEGV+SZe+Ju8ft/fFhfHYQ42drb2U/2awb6X2V3edoqilipw1x+1AZa0zLB/2FvRlpsev27Etbw4uvARzBP4iIXAhRPLnUh4EwyTwBbug9hKlv0fk0Gzr7fBCHg9TAGRyS97HuUPlC+NL4mPm0i95koy1FwGw==\"}",
    "success": true
}
```

### Error

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}
{% endtabs %}

