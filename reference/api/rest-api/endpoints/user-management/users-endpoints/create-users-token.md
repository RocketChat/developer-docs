# Create Users Token

Create a user authentication token. This is the same type of session token a user would get via login and will expire the same way.

{% hint style="warning" %}
To be able to use this endpoint, you must set the [Environment variable](https://docs.rocket.chat/deploy/rocket.chat-environment-configuration/environment-variables) _CREATE\_TOKENS\_FOR\_USERS_=true.
{% endhint %}

{% hint style="info" %}
For SaaS workspaces, [contact support](https://docs.rocket.chat/resources/get-support) to set this variable.
{% endhint %}

{% hint style="info" %}
You are required to have the `user-generate-access-token` permission.
{% endhint %}

Example if you use snaps:

```
    echo "CREATE_TOKENS_FOR_USERS=true" > /var/snap/rocketchat-server/common/create-tokens.env
    sudo systemctl restart snap.rocketchat-server.rocketchat-server.service
```

Create a user authentication token. Requires `user-generate-access-token` permission.

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `/api/v1/users.createToken` | `yes`         | `POST`      |

## Payload

| Argument               | Example             | Required | Description                     |
| ---------------------- | ------------------- | -------- | ------------------------------- |
| `userId` or `username` | `BsNr28znDkG8aeo7W` | Required | The id or username of the user. |

## Example Call - Via userId

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.createToken \
     -d '{ "userId": "BsNr28znDkG8aeo7W" }'
```

## Example Result

```javascript
{
  "data": {
    "userId": "BsNr28znDkG8aeo7W",
    "authToken": "2jdk99wuSjXPO201XlAks9sjDjAhSJmskAKW301mSuj9Sk",
  },
  "success": true
}
```

## Example Call - Via username

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.createToken \
     -d '{ "username": "test" }'
```

## Example Result

```javascript
{
  "data": {
    "userId": "BsNr28znDkG8aeo7W",
    "authToken": "2jdk99wuSjXPO201XlAks9sjDjAhSJmskAKW301mSuj9Sk",
  },
  "success": true
}
```

## Change Log

| Version | Description                                                                             |
| ------- | --------------------------------------------------------------------------------------- |
| 2.1.0   | Added ENV VAR to be able to use this endpoint (process.env.CREATE\_TOKENS\_FOR\_USERS). |
| 0.56.0  | Added                                                                                   |
