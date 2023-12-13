# Update Own Basic Information

<table><thead><tr><th width="163">HTTP Method</th><th width="263">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/users.updateOwnBasicInfo</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
* To change your email or password, you must confirm it using [TOTP](../../authentication-endpoints/rest-two-factor-authentication.md). If you don't have [2FA enabled](../../authentication-endpoints/rest-two-factor-authentication.md#calling-an-endpoint-with-two-factor) (token code or email), TOTP will require the [current password method](https://developer.rocket.chat/reference/api/rest-api/endpoints/authentication-endpoints/rest-two-factor-authentication#request-new-headers-1).
* If you add the `currentPassword` encrypted in SHA256 to the payload, the request won't require TOTP again.
* Before saving custom fields, you must define them in [workspace admin settings](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/account-settings#registration).&#x20;
{% endhint %}

## Body Parameters

<table><thead><tr><th width="214.33333333333331">Key</th><th width="237">Example</th><th>Description</th></tr></thead><tbody><tr><td><code>data</code><mark style="color:red;"><code>*</code></mark></td><td><code>"data": {}</code></td><td>An object of user data to be updated with the following parameters.</td></tr><tr><td><code>email</code></td><td><code>example@example.com</code></td><td>The email address for the user.</td></tr><tr><td><code>name</code></td><td><code>Example User</code></td><td>The display name of the user.</td></tr><tr><td><code>username</code></td><td><code>example</code></td><td>The username for the user.</td></tr><tr><td><code>currentPassword</code></td><td><code>5994471abb01112afcc18159f6cc74b4f511b99806da59b3caf5a9c173cacfc5@w0rd</code></td><td>The password for the user encrypted in SHA256.</td></tr><tr><td><code>newPassword</code></td><td><code>passw0rd</code></td><td>The new password for the user.</td></tr><tr><td><code>bio</code></td><td><code>Engineer</code></td><td>The bio of the user.</td></tr><tr><td><code>statusType</code></td><td><code>offline</code></td><td>The status type of the user. It can be  <code>online</code> , <code>busy</code> ,  <code>away</code> or <code>offline</code>.</td></tr><tr><td><code>statusText</code></td><td><code>On a vacation</code></td><td>The status text of the user.</td></tr><tr><td><code>nickname</code></td><td><code>cakebaby</code></td><td>The nickname of the user.</td></tr><tr><td><code>customFields</code></td><td><code>{ "twitter": "@example" }</code></td><td>Any custom fields the user should have on their account.</td></tr></tbody></table>

## Example Call   &#x20;

```powershell
 curl -L -X POST 'http://localhost:3000/api/v1/users.updateOwnBasicInfo' \
-H 'x-auth-token: nwH90MZqosB_BxeXNvny8MCa_PqDEY18vO9LDCFpNuB' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ' \
-H 'Content-Type: application/json' \
--data-raw '{
    "data": {
        "email": "funke@test.com",
        "newPassword": "testbb",
        "currentPassword": "aa856615052ee58e557a2945d53bc90a228915e7d7687ea250f3b4b1581d6e53",    "nickname": "baby girl",
        "bio": "Auspicious baby",
        "username": "roxie",
        "name": "Funke Olasupo",
        "statusType":"offline",
        "statusText":"On a vacation"
       
    },
    "customFields": {}
}'
```

## Example Response

```json
{
    "user": {
        "_id": "rbAXPnMktTFbNpwtJ",
        "createdAt": "2023-02-20T13:42:07.119Z",
        "services": {
            "password": {
                "bcrypt": "$2b$10$E9ppW3T2itbMEcDvOdWBR.NXiW3YbifRHwBhjVkt26r1XS8yNhh6u"
            },
            "email2fa": {
                "enabled": true,
                "changedAt": "2023-02-20T13:42:07.118Z"
            },
            "resume": {
                "loginTokens": [
                    {
                        "when": "2023-09-16T09:27:10.959Z",
                        "hashedToken": "A1jmsVCHHH2SkXHrEJDfumN+VtUP3tcuJ/OGseGrRbA=",
                        "twoFactorAuthorizedHash": "3067196228a830eacd6181a6977fe86a",
                        "twoFactorAuthorizedUntil": "2023-09-19T16:40:58.767Z"
                    },
                    {
                        "when": "2023-09-18T10:37:58.218Z",
                        "hashedToken": "RLdxvu9dDnk6QRwFdaK3my1AoPeGaR5lTkK+zEhTuPk="
                    },
                    {
                        "when": "2023-09-18T10:41:25.814Z",
                        "hashedToken": "zWZ8wW9PNlVuI2Q65vK/9vytaONk1BXxaWcNld4qvEc="
                    }
                ]
            },
            "email": {
                "verificationTokens": [
                    {
                        "token": "lHq_4L8Orgxu2p5NhfVb0V9kA7kO1VaBXA5GmaJiuX3",
                        "address": "funke@test.com",
                        "when": "2023-05-23T18:47:07.142Z"
                    }
                ]
            },
            "totp": {
                "enabled": false
            },
            "passwordHistory": [
                "$2b$10$n1.FV8S2mxz7GzXA392V5OaDa5X0WR1DQ4eGGFKI/wpdhS9sVIC6S",
                "$2b$10$4I68O5mlR.C8dRhtZ4Mj6us6EMwRHNIUqEWQe/nOhISs4e8RtOliW",
                "$2b$10$AU9Ncfd8bO5TpE.5iLMjyujdd6RVJaoeKckVqo3MMO9Ngc3oyMAs2"
            ]
        },
        "username": "roxie",
        "emails": [
            {
                "address": "funke@test.com",
                "verified": true
            }
        ],
        "type": "user",
        "status": "offline",
        "active": true,
        "_updatedAt": "2023-09-19T16:10:58.873Z",
        "__rooms": [
            "GENERAL",
            "siyr2oWQJBjQjhLwr",
            "6GFJ3tbmHiyHbahmC",
            "64f0f82c2c26843a68c1f7ba"
        ],
        "roles": [
            "user",
            "admin",
            "livechat-agent",
            "livechat-manager"
        ],
        "name": "Funke Olasupo",
        "settings": {
            "preferences": {
                "themeAppearence": "light"
            },
            "profile": {}
        },
        "lastLogin": "2023-09-19T16:00:19.657Z",
        "statusConnection": "away",
        "utcOffset": 1,
        "banners": {
            "versionUpdate-6_0_0": {
                "id": "versionUpdate-6_0_0",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.0.0"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.0.0",
                "modifiers": [],
                "read": true
            },
            "versionUpdate-6_2_8": {
                "id": "versionUpdate-6_2_8",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.2.8"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.2.8",
                "modifiers": []
            }
        },
        "statusDefault": "offline",
        "statusText": "On a vacation",
        "operator": true,
        "livechatStatusSystemModified": false,
        "statusLivechat": "available",
        "livechatCount": 8,
        "livechat": {
            "maxNumberSimultaneousChat": ""
        },
        "bio": "Engineer",
        "nickname": ""
    },
    "success": true
}
```

## Change Log

<table><thead><tr><th width="350">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.62.2</td><td>Added as <code>user.updateOwnBasicInfo</code></td></tr><tr><td>6.4.0</td><td>Add <code>bio</code> and <code>statusType</code> parameters.</td></tr></tbody></table>
