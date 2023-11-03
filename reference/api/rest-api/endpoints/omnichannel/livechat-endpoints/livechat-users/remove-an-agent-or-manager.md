# Remove Agent or Manager

Remove a user as an agent or a manager.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/livechat/users/:type/:_id</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="158">Key</th><th width="216">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type </code><mark style="color:red;"><code>*</code></mark></td><td><code>agent</code></td><td>The type of user. The value can either be <code>agent</code> or <code>manager</code>.</td></tr><tr><td><code>_id </code><mark style="color:red;"><code>*</code></mark></td><td><code>SQafHvoFPuB57NmBD</code></td><td>The user <code>_id</code>.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost.com/api/v1/livechat/users/agent/PSaBmpB2c9eFaE79q' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--data ''
```

## Example Response

```javascript
{
  "success": true
}
```

## Change Log

<table><thead><tr><th width="298">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.42.0</td><td>Added</td></tr></tbody></table>
