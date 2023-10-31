# Register or Update Omnichannel Contact

Register a guest user as a new omnichannel contact.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/omnichannel/contact</code></td><td><code>yes</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="199.33333333333331">Argument</th><th width="207">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token </code><mark style="color:red;"><code>*</code></mark></td><td><code>4WcmeBE4spXx6AxrC</code></td><td>The contact token. Enter a random unique string as the value.</td></tr><tr><td><code>name </code><mark style="color:red;"><code>*</code></mark></td><td><code>Chris</code></td><td>The contact name.</td></tr><tr><td><code>email</code></td><td><code>chris@gmail.com</code></td><td>The contact email.</td></tr><tr><td><code>phone</code></td><td><code>+93334432224444</code></td><td>The contact phone number.</td></tr><tr><td><code>contactManager</code></td><td><code>kim.jane</code></td><td>The contact manager's user name.</td></tr></tbody></table>

## Example Body

```json
{
    "token": "434lxd7iss8yh8c4m80wh",
    "name": "Chris",
    "email": "chris@gmail.com",
    "phone": "+93334432224444",
    "contactManager": {
        "username": "kim.jane"
    }
}
```

## Example Call

{% swagger method="post" path="/api/v1/omnichannel/contact" baseUrl="http://localhost:3000" summary="Register or update contacts" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-Auth-Token" required="true" %}
Auth token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-User-Id" required="true" %}
User ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Example Response

```json
{
    "contact": "7ipCD6NDtkkRDCiNM",
    "success": true
}
```

To update a contact, use the token created for that contact.
