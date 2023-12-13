# Forgot Password

Send an email to reset your password.

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.forgotPassword</code></td><td><code>no</code></td></tr></tbody></table>

{% hint style="info" %}
Please ensure that you have completed the configuration of the Email; otherwise, your users will not receive the mail normally. Accessible from Administration -> Email.
{% endhint %}

## Body Parameters

<table><thead><tr><th width="199.33333333333331">Key</th><th width="226">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>email</code><mark style="color:red;"><code>*</code></mark></td><td><code>email@rocket.cat</code></td><td>The email to send password reset link.</td></tr></tbody></table>

## Example Call

```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/users.forgotPassword \
      -d '{ 
            "email": "email@rocket.cat" }'
```

## Example Response

```json
{
  "status": "success"
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.64.0  | Added       |
