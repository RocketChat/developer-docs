# Register or Update Omnichannel Contact

Register a guest user as a new omnichannel contact.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/omnichannel/contact</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body

<table><thead><tr><th width="199.33333333333331">Argument</th><th width="207">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token </code><mark style="color:red;"><code>*</code></mark></td><td><code>4WcmeBE4spXx6AxrC</code></td><td>The contact token. Enter a random unique string as the value.</td></tr><tr><td><code>name </code><mark style="color:red;"><code>*</code></mark></td><td><code>Chris</code></td><td>The contact name.</td></tr><tr><td><code>email</code></td><td><code>chris@gmail.com</code></td><td>The contact email.</td></tr><tr><td><code>phone</code></td><td><code>+93334432224444</code></td><td>The contact phone number.</td></tr><tr><td><code>contactManager</code></td><td><code>kim.jane</code></td><td>The contact manager's user name.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://local:host/api/v1/omnichannel/contact' \
--header 'X-Auth-Token: b5BKhblglC5OU0AfB_Tl9dKmOb0zXUvWK-nhNT_aE8V' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--header 'Content-Type: application/json' \
--data-raw '{
    "token": "434lxd7iss8yh8c4m80wh",
    "name": "Chris",
    "email": "chris@gmail.com",
    "phone": "+91123456788",
    "contactManager": {
        "username": "kim.jane"
    }
}'
```
{% endcode %}

## Example Response

```json
{
    "contact": "7ipCD6NDtkkRDCiNM",
    "success": true
}
```

To update a contact, use the contact token created in the response.
