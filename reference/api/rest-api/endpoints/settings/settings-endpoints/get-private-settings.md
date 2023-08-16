# Get private settings

List all private settings. Learn how this can be used in configuring your server in [this guide](https://docs.rocket.chat/setup-and-configure/rocket.chat-environment-configuration/environment-variables).

| URL                | Requires Auth | HTTP Method |
| ------------------ | ------------- | ----------- |
| `/api/v1/settings` | `yes`         | `GET`       |

## Example Call

{% tabs %}
{% tab title="Curl" %}
```url
curl --location --request GET 'http://localhost:3000/api/v1/settings' \
--header 'X-Auth-Token: w4KGA2YwTmz4k0cEwa58F6T-gyN4p4MLLWPDfDE8Sgi' \
--header 'X-User-Id: g8aroJivN5R32TxCm'
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
var myHeaders = new Headers();
myHeaders.append("X-Auth-Token", "w4KGA2YwTmz4k0cEwa58F6T-gyN4p4MLLWPDfDE8Sgi");
myHeaders.append("X-User-Id", "g8aroJivN5R32TxCm");

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("http://localhost:3000/api/v1/settings", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```
{% endtab %}

{% tab title="Python" %}
```python
import http.client

conn = http.client.HTTPSConnection("localhost", 3000)
payload = ''
headers = {
  'X-Auth-Token': 'w4KGA2YwTmz4k0cEwa58F6T-gyN4p4MLLWPDfDE8Sgi',
  'X-User-Id': 'g8aroJivN5R32TxCm'
}
conn.request("GET", "/api/v1/settings", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```
{% endtab %}
{% endtabs %}

## Example Result

### Sucess

```javascript
{
  "settings": [
          { "_id": "API_Allow_Infinite_Count", "value": true },
          { "_id": "API_CORS_Origin", "value": "*" }
  ],
  "count": 50,
  "offset": 0,
  "total": 299,
  "success": true
}
```

### Errors

The following error can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}
