# Get Licenses

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Retrieves a list of all registered licenses in the workspace.

{% hint style="info" %}
It requires `view-privileged-setting` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/licenses.get` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/licenses.maxActiveUsers' \
--header 'x-auth-token: fjiPBhtyFAn5JO3RDdDvKjkXToV2pd4_lb-nkdgJ_Q4' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```json
{
    "licenses": [
        {
            "version": 2,
            "url": "localhost:3000",
            "expiry": "2023-07-13",
            "maxActiveUsers": 25,
            "maxGuestUsers": 125,
            "maxRoomsPerGuest": 1,
            "modules": [
                "auditing",
                "canned-responses",
                "ldap-enterprise",
                "livechat-enterprise",
                "voip-enterprise",
                "omnichannel-mobile-enterprise",
                "engagement-dashboard",
                "push-privacy",
                "scalability",
                "teams-mention",
                "saml-enterprise",
                "oauth-enterprise",
                "device-management",
                "federation",
                "videoconference-enterprise",
                "message-read-receipt"
            ],
            "tag": {
                "name": "Enterprise",
                "color": "#F3BE08"
            },
            "meta": {
                "trial": false,
                "trialEnd": "2023-04-27T23:00:00Z",
                "workspaceId": "63cfe8550c95db00013d7798"
            }
        }
    ],
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No permission:** This occurs when the authenticated user doesn't have `view-privileged-setting` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

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
