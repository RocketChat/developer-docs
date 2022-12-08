---
description: Retrieves last 1000 lines of server logs
---

# Get stdout queue

{% hint style="info" %}
User needs `view-logs permission`
{% endhint %}

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/stdout.queue` | `Yes`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request GET 'http://localhost:3000//api/v1/stdout.queue' \
--header 'X-User-Id: d26x6zSkaPSe5gCyy' \
--header 'X-Auth-Token: Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU' \
--header 'Content-Type: application/json' \
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
{
    "queue": [
        {
            "id": "logid-226",
            "string":"[34mI20211006-12:06:31.464(0) [39mException in defer callback: Error: getaddrinfo ENOTFOUND null\n    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:66:26)\n    at GetAddrInfoReqWrap.callbackTrampoline (internal/async_hooks.js:126:14) {\n  errno: 'ENOTFOUND',\n  code: 'EDNS',\n  syscall: 'getaddrinfo',\n  hostname: 'null',\n  command: 'CONN'\n}\n",
            "ts": "2021-10-06T12:06:31.464Z"
        },
        {
            "id": "logid-227",
            "string":"[34mI20211006-12:06:41.485(0) [39mException in defer callback: Error: getaddrinfo ENOTFOUND null\n    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:66:26)\n    at GetAddrInfoReqWrap.callbackTrampoline (internal/async_hooks.js:126:14) {\n  errno: 'ENOTFOUND',\n  code: 'EDNS',\n  syscall: 'getaddrinfo',\n  hostname: 'null',\n  command: 'CONN'\n}\n",
            "ts": "2021-10-06T12:06:41.485Z"
        },
        {
            "id": "logid-228",
            "string":"[34mI20211006-12:06:45.507(0) [39mException in defer callback: Error: getaddrinfo ENOTFOUND null\n    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:66:26)\n    at GetAddrInfoReqWrap.callbackTrampoline (internal/async_hooks.js:126:14) {\n  errno: 'ENOTFOUND',\n  code: 'EDNS',\n  syscall: 'getaddrinfo',\n  hostname: 'null',\n  command: 'CONN'\n}\n",
            "ts": "2021-10-06T12:06:45.507Z"
        },
        {
            "id": "logid-229",
            "string":"[34mI20211006-12:06:55.552(0) [39mException in defer callback: Error: getaddrinfo ENOTFOUND null\n    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:66:26)\n    at GetAddrInfoReqWrap.callbackTrampoline (internal/async_hooks.js:126:14) {\n  errno: 'ENOTFOUND',\n  code: 'EDNS',\n  syscall: 'getaddrinfo',\n  hostname: 'null',\n  command: 'CONN'\n}\n",
            "ts": "2021-10-06T12:06:55.552Z"
        },
        {
            "id": "logid-230",
            "string":"[34mI20211006-12:06:59.579(0) [39mException in defer callback: Error: getaddrinfo ENOTFOUND null\n    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:66:26)\n    at GetAddrInfoReqWrap.callbackTrampoline (internal/async_hooks.js:126:14) {\n  errno: 'ENOTFOUND',\n  code: 'EDNS',\n  syscall: 'getaddrinfo',\n  hostname: 'null',\n  command: 'CONN'\n}\n",
            "ts": "2021-10-06T12:06:59.579Z"
        },
        {
            "id": "logid-231",
            "string":"[34mI20211006-12:07:01.610(0) [39mException in defer callback: Error: getaddrinfo ENOTFOUND null\n    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:66:26)\n    at GetAddrInfoReqWrap.callbackTrampoline (internal/async_hooks.js:126:14) {\n  errno: 'ENOTFOUND',\n  code: 'EDNS',\n  syscall: 'getaddrinfo',\n  hostname: 'null',\n  command: 'CONN'\n}\n",
            "ts": "2021-10-06T12:07:01.610Z"
        },
        {
            "id": "logid-1143",
            "string":"[34mI20211014-00:00:11.033(0) [39m    maxGuestUsers -> 5\n",
            "ts": "2021-10-14T00:00:11.033Z"
        },
        .
        .
        .
        {
            "id": "logid-1144",
            "string":"[34mI20211014-00:00:11.034(0) [39m maxRoomsPerGuest -> 1\n",
            "ts": "2021-10-14T00:00:11.034Z"
        },
        {
            "id": "logid-1145",
            "string":"[34mI20211014-00:00:11.036(0) [39m          modules -> enterprise:*\n",
            "ts": "2021-10-14T00:00:11.036Z"
        },
        {
            "id": "logid-1146",
            "string":"[34mI20211014-00:00:11.037(0) [39m-------------------------\n",
            "ts": "2021-10-14T00:00:11.037Z"
        },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

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
