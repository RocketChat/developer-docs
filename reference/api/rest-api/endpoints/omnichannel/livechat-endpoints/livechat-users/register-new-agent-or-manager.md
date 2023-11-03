# Register New Agent or Manager

Register a new [agent](https://docs.rocket.chat/use-rocket.chat/omnichannel/agents) or [manager](https://docs.rocket.chat/use-rocket.chat/omnichannel/managers).

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/users/:type</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="168">Key</th><th width="178.00000000000003">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type </code><mark style="color:red;"><code>*</code></mark></td><td><code>agent</code></td><td>The type of user that you want to register. The value can either be <code>agent</code> or <code>manager</code>.</td></tr></tbody></table>

## Body

<table><thead><tr><th width="168">Key</th><th width="178.00000000000003">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>john.doe</code></td><td>The user name that you want to register.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/users/agent' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--header 'Content-Type: application/json' \
--data '{
    "username": "john.doe"
}'
```

## Example Response

```json
{
  "user": {
    "_id": "SQafHvoFPuB57NmBD",
    "username": "john.doe"
  },
  "success": true
}
```

## Change Log

<table><thead><tr><th width="305">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.42.0</td><td>Added</td></tr></tbody></table>
