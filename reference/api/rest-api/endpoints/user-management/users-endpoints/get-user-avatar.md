# Get User Avatar

<table><thead><tr><th width="163">HTTP Method</th><th width="279">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.getAvatar</code></td><td><code>no</code></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="221.33333333333331">Key</th><th width="225">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark> or <code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>BsNr28znDkG8aeo7W</code> or  <code>bobsmith</code></td><td>The ID or username of the user.</td></tr></tbody></table>

## Example Call

With `userId`:

```bash
curl http://localhost:3000/api/v1/users.getAvatar?userId=BsNr28znDkG8aeo7W
```

With `username`:

```bash
curl http://localhost:3000/api/v1/users.getAvatar?username=bobsmith
```

## Response

You will get the user avatar image or a redirect to the image URL.

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.50.0  | Added       |
