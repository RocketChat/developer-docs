# Get Conversation by Departments

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

View the metrics of omnichannel conversations in your workspace during a selected time range based on their departments.&#x20;

| URL                                                                 | Requires Auth | HTTP Method |
| ------------------------------------------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/analytics/dashboards/conversations-by-department` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                             |
| -------------- | -------------- | -------- | ------------------------------------------------------- |
| `X-User-Id`    | `myuser-id`    | Required | Your userId (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)  |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/priorities\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-id'
```

## Result

```javascript
{
    "priorities": [
        {
            "_id": "64007cc2fa0ed7dd905092e3",
            "i18n": "Lowest",
            "sortItem": 5,
            "dirty": false
        },
        {
            "_id": "64007cc2fa0ed7dd905092e4",
            "i18n": "Low",
            "sortItem": 4,
            "dirty": false
        },
        {
            "_id": "64007cc2fa0ed7dd905092e5",
            "i18n": "Medium",
            "sortItem": 3,
            "dirty": false
        },
        {
            "_id": "64007cc2fa0ed7dd905092e6",
            "i18n": "High",
            "sortItem": 2,
            "dirty": false
        },
        {
            "_id": "64007cc2fa0ed7dd905092e7",
            "i18n": "Highest",
            "sortItem": 1,
            "dirty": false
        }
    ],
    "count": 5,
    "offset": 0,
    "total": 5,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.4.0   | Added       |
