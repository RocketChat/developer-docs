---
description: Apply license to a workspace
---

# Add License

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

You may want to deploy your workspace in an [air-gapped environment](https://docs.rocket.chat/setup-and-configure/rocket.chat-air-gapped-deployment). Since the server has no internet to communicate with the cloud, we provide an enterprise edition license that you can apply manually to upgrade your workspace.

{% hint style="info" %}
It requires `edit-privileged-setting` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/licenses.add` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="154">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="150">Argument</th><th width="400">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>license</code></td><td><code>VFJ0vHf3Jm9AR0minB342MLaHRlZdc3Du5nf0E5Sv0QJ4SUkEIaU2boCYaDsxQ2N1UL4uhLjCF9M7iCZ/yxafJjxbHvOu1D5rOfdgO4RKlAGE9tGHDidowiw9crJyXVb16jPHHoeh7nFcI1gxbwGKcB1c4SdFXgQYYb8RCCFMQ64pdZUiXIIq/nUXxU8gEgT3sjJ9u2+Dw5ukDLX3SG2AFq1hLoPSZqsP6giSOKBXTx9t8qVrT5COEn4CWCaVdApOdWC2nsROTJPJPbyjdZ9uSXQEr4raeHZXgtb9L3u2+wUej7NwDJ+C9+/6jUjmUD+CZyvpiv1YBWFudCjsgm8chrtzab70ndw1hjSXVMiuO00/wcHg8aTwZ7GSUA+OH1h1DCG4Bxrd94eZwZxEOgQtP01aNaM/RyYaleib88o6zjD0oDDISaN7nwv6F85v7FfRPEWAVZ5HUNVWxiqJqx/fAGvr9tTwtfnBwpcZXssJytefriAqDsslZYTl7FzAxryo9pDioNSozLMwhCfAVm0VdIt0Ma4s0i72eUtgRnvAAq1bZK6UkE0zE8xMQjOykoiCoQLzwza+g762AQo=</code></td><td>Required</td><td>The EE license</td></tr></tbody></table>

## Example Payload

```json
{
    "license":"VFJ0vHf3Jm9AR0minB342MLaHRlZdc3Du5nf0E5Sv0QJ4SUkEIaU2boCYaDsxQ2N1UL4uhLjCF9M7iCZ/yxafJjxbHvOu1D5rOfdgO4RKlAGE9tGHDidJR9crJyXVb16jPHHvLSkUFzb7HoIq/nUXxU8gEgT3uJ9u2+Dw5ukDLX3SG2AFq1hLoPSZqsP6giSOKBXTx9t8qVrT5COEn4CWCaVdApOdWC2nsROTJPJPbyjdZ9uSXQEr4raeHZXgtb9L3u2+wUej7NwDJ+C9+/6jUjmUD+CZyvpiv1YBWFudCjsgm8chrtzab70ndw1hjSXVMiuO00/wcHg8aTwZ7GSUA+OH1h1DCG4Bxrd94eZwZxEOgQtP01aNaM/RyYaleib88o6zjD0oDDISaN7nwv6F85v7FfRPEWAVZ5HUNVWxiqJqx/fEgYHpxBC3iDWcb/cexjofti/FwqOC4JRowGaGJ/n+WGl0sg1YEjULZdM759sw8VSwDDQ7Tv2H66/mSGwtP/zAGvr9tTwtfnBwpcZXssJytefriAqDsslZYTl7FzAxryo9pDioNSozLMwhCfAVm0VdIt0Ma4s0i72eUtgRnvAAq1bZK6UkE0zE8xMQjOykoiCoQLzwza+g762AQo="
}
```

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/licenses.add' \
--header 'x-auth-token: fjiPBhtyFAn5JO3RDdDvKjkXToV2pd4_lb-nkdgJ_Q4' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--data '{
    "license":"VFJ0vHf3Jm9AR0minB342MLaHRlZdc3Du5nf0E5Sv0QJ4SUkEIaU2boCYaDsxQ2N1UL4uhLjCF9M7iCZ/yxafJjxbHvOu1D5rOfdgO4RKlAGE9tGHDidJR9crJyXVb16jPHHvLSkUFzb7HoIq/nUXxU8gEgT3uJ9u2+Dw5ukDLX3SG2AFq1hLoPSZqsP6giSOKBXTx9t8qVrT5COEn4CWCaVdApOdWC2nsROTJPJPbyjdZ9uSXQEr4raeHZXgtb9L3u2+wUej7NwDJ+C9+/6jUjmUD+CZyvpiv1YBWFudCjsgm8chrtzab70ndw1hjSXVMiuO00/wcHg8aTwZ7GSUA+OH1h1DCG4Bxrd94eZwZxEOgQtP01aNaM/RyYaleib88o6zjD0oDDISaN7nwv6F85v7FfRPEWAVZ5HUNVWxiqJqx/fEgYHpxBC3iDWcb/cexjofti/FwqOC4JRowGaGJ/n+WGl0sg1YEjULZdM759sw8VSwDDQ7Tv2H66/mSGwtP/zAGvr9tTwtfnBwpcZXssJytefriAqDsslZYTl7FzAxryo9pDioNSozLMwhCfAVm0VdIt0Ma4s0i72eUtgRnvAAq1bZK6UkE0zE8xMQjOykoiCoQLzwza+g762AQo="
}'
```

## Example Result

### Success

```json
{
    "success": true
}
```

{% hint style="info" %}
A successful response only means the license provided follows the accepted format. Check your [workspace log](https://docs.rocket.chat/use-rocket.chat/workspace-administration/info) or [administration info](https://docs.rocket.chat/use-rocket.chat/workspace-administration/info) to confirm if the license is valid and was applied to your workspace. Alternatively, you can check [confirm-enterprise-license.md](confirm-enterprise-license.md "mention").
{% endhint %}

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No permission:** This occurs when the authenticated user doesn't have `edit-privileged-setting` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No permission" %}
```json
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.10.0  | Added       |
