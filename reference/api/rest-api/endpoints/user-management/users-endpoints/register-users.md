# Register User

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.register</code></td><td><code>no</code></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="177">Key</th><th width="248">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>rogersmith</code></td><td>The username for the user.</td></tr><tr><td><code>email</code><mark style="color:red;"><code>*</code></mark></td><td><code>roger@example.com</code></td><td>The email for the user.</td></tr><tr><td><code>pass</code><mark style="color:red;"><code>*</code></mark></td><td><code>passw0rd</code></td><td>The password for the user.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Roger Smith</code></td><td>The name of the user. <br>The value can be an empty string  <code>""</code> if <code>Require Name For Signup</code> is disabled in <code>Accounts</code> > <code>Registration</code></td></tr><tr><td><code>secret</code></td><td><code>Jjwjg6gouWLXhMGKW</code></td><td>String appended to secret registration URL.</td></tr></tbody></table>

## Example Call

```bash
curl -H "Content-type:application/json" \
     http://localhost:3000/api/v1/users.register \
     -d '{ 
          "username": "rogersmith", 
          "email": "roger@example.com", 
          "pass": "passw0rd", 
          "name": "Roger Smith"}'
```

## Example Response

```json
{
  "user": {
    "_id": "nSYqWzZ4GsKTX4dyK",
    "type": "user",
    "status": "offline",
    "active": true,
    "name": "Example User",
    "utcOffset": 0,
    "username": "example"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.50.0  | Added       |
