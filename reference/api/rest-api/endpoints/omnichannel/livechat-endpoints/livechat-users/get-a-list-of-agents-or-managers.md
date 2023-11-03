# Get List of Agents or Managers

Get a list of agents or managers.&#x20;

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/users/:type</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="167.00000000000003">Key</th><th width="162">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type </code><mark style="color:red;"><code>*</code></mark></td><td><code>agent</code></td><td>The type of user. The value can either be <code>agent</code> or <code>manager</code>.</td></tr></tbody></table>

## Query Parameters

The [#pagination](../../../../#pagination "mention") query parameters are supported and optional.

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/users/agent' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--data ''
```

## Example Response

```json
{
    "users": [
        {
            "_id": "XLzGrYF9L2miSpPHP",
            "username": "dialog.bot",
            "status": "offline",
            "statusLivechat": "not-available",
            "name": "Dialog Bot",
            "emails": [
                {
                    "address": "dialog.bot@test.com",
                    "verified": true
                }
            ],
            "livechat": null,
            "departments": []
        },
        {
            "_id": "rbAXPnMktTFbNpwtJ",
            "username": "john.doe",
            "status": "offline",
            "statusLivechat": "available",
            "name": "John Doe",
            "emails": [
                {
                    "address": "john.doe@gmail.com",
                    "verified": true
                }
            ],
            "livechat": {
                "maxNumberSimultaneousChat": ""
            },
            "departments": [
                "64181a0728384134ed600dcc"
            ]
        },
        {
            "_id": "hFDuCPam7sWziWFYa",
            "username": "hookdeck.write",
            "status": "offline",
            "statusLivechat": "not-available",
            "name": "Hookdeck Write",
            "emails": [
                {
                    "address": "hookdeckwrite@gmail.com",
                    "verified": true
                }
            ],
            "livechat": null,
            "departments": []
        },
        {
            "_id": "stjxrXYBWy3EcDugH",
            "username": "rocket.agent",
            "status": "offline",
            "statusLivechat": "not-available",
            "name": "Rocket Agent",
            "emails": [
                {
                    "address": "rocket.agent@rocket.chat",
                    "verified": false
                }
            ],
            "livechat": {
                "maxNumberSimultaneousChat": ""
            },
            "departments": [
                "64181a0728384134ed600dcc"
            ]
        }
```

## Change Log

<table><thead><tr><th width="264">Version</th><th width="376">Description</th></tr></thead><tbody><tr><td>2.2.0</td><td>Added support to pagination</td></tr><tr><td>0.42.0</td><td>Added</td></tr></tbody></table>
