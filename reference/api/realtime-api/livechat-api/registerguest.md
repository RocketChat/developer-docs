# livechat:registerGuest

<figure><img src="../../../../.gitbook/assets/Deprecated.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
This method is planned to be removed by 7.0.0. Use the [Register Livechat Visitor](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/visitor/register-a-new-livechat-visitor) endpoint instead.&#x20;
{% endhint %}

## DDP message

```javascript
{"msg":"method","method":"livechat:registerGuest","params":[{"token":"TF5rZ7BZ9mZCSq3xN","name":"Guest Name","email":"guest@rocket.chat","department":"3jMKjTQJxCDxwxxtx"}],"id":"5"}
```

## Response

```javascript
{
    userId: 'G3DukvFBhDkDnw6uS',
    visitor: {
     name: 'Guest Name',
     token: 'TF5rZ7BZ9mZCSq3xN',
     username: 'guest-1',
     visitorEmails: [{
      address: 'guest@rocket.chat'
     }]
    }
}
```
