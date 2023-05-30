# Get instances

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `api/v1/instances.get` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/instances.get\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
{
    "instances": [
        {
            "_id": "vQZbiEj9fChaa9kjw",
            "_createdAt": "2021-09-01T18:29:30.430Z",
            "_updatedAt": "2021-09-30T11:20:44.678Z",
            "extraInformation": {
                "host": "10.42.15.191",
                "port": "3000",
                "os": {
                    "type": "Linux",
                    "platform": "linux",
                    "arch": "x64",
                    "release": "4.15.0-109-generic",
                    "uptime": 36801050,
                    "loadavg": [
                        8.66,
                        9.46,
                        9.89
                    ],
                    "totalmem": 270450634752,
                    "freemem": 105877463040,
                    "cpus": 32
                },
                "nodeVersion": "v12.22.1"
            },
            "name": "rocket.chat",
            "pid": 1
        }
    ],
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

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
