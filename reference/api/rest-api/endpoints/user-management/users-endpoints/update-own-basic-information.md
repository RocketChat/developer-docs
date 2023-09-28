# Update Own Basic Information

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `/api/v1/users.updateOwnBasicInfo` | `yes`         | `POST`      |

{% hint style="warning" %}
* For changing email or password, you must confirm it using [TOTP](../../authentication-endpoints/rest-two-factor-authentication.md). If you don't have [2FA enabled](../../authentication-endpoints/rest-two-factor-authentication.md#calling-an-endpoint-with-two-factor) (token code or email), TOTP will require the [current password method](https://developer.rocket.chat/reference/api/rest-api/endpoints/authentication-endpoints/rest-two-factor-authentication#request-new-headers-1).
* If you add the `currentPassword` encrypted in SHA256 to the payload, the request wont require TOTP again.
* Before saving custom fields,  you must define them in [workspace admin settings](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/account-settings#registration).&#x20;
{% endhint %}

## Payload

| Argument                                                                                             | Example                                                                                                                                                                                                                                                                                                                                                                                                                                     | Required                       | Description                                              |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ | -------------------------------------------------------- |
| `data`                                                                                               | <pre><code> "data": {
        "email": "funke.olasupo@rocket.chat",
        "newPassword": "va77n796vi7ca32",
        "currentPassword": "aai87908856615052ee58e557a294589088d53bc90a228915e7d7687ea250f3b4b1581d6e53",    "nickname": "baby girl",
        "bio": "Auspicious baby",
        "username": "roxie",
        "name": "Funke Olasupo",
       "statusType":"offline",
        "statusText":"On a vacation"
    }
</code></pre> | Required                       | An object of user data to be updated                     |
| <p></p><pre class="language-postman_json"><code class="lang-postman_json">customFields
</code></pre> | <p></p><pre class="language-postman_json"><code class="lang-postman_json">{ twitter: '@example' }
</code></pre>                                                                                                                                                                                                                                                                                                                             | Optional, Default: `undefined` | Any custom fields the user should have on their account. |

**Data Object**

| Argument                            | Example                                                                 | Required | Description                                                                       |
| ----------------------------------- | ----------------------------------------------------------------------- | -------- | --------------------------------------------------------------------------------- |
| `email`                             | `example@example.com`                                                   | Optional | The email address for the user.                                                   |
| `name`                              | `Example User`                                                          | Optional | The display name of the user.                                                     |
| `username`                          | `example`                                                               | Optional | The username for the user.                                                        |
| `currentPassword`                   | `5994471abb01112afcc18159f6cc74b4f511b99806da59b3caf5a9c173cacfc5@w0rd` | Optional | The password for the user encrypted in SHA256.                                    |
| `newPassword`                       | `passw0rd`                                                              | Optional | The new password for the user                                                     |
| `bio`                               | <pre><code>Auspicious baby
</code></pre>                                | Optional | The bio of the user                                                               |
| <pre><code>statusType
</code></pre> | `offline`                                                               | Optional | The status type of the user. It can be  `online` , `busy` ,  `away` or `offline`. |
| <pre><code>statusText
</code></pre> | `On a vacation`                                                         | Optional | The status text of the user.                                                      |
| `nickname`                          | `cakebaby`                                                              | Optional | The nickname of the user                                                          |

## Example Payload

```json
{
    "data": {
        "email": "funke.olasupo@rocket.chat",
        "newPassword": "testbb",
        "currentPassword": "aa856615052ee58e557a2945d53bc90a228915e7d7687ea250f3b4b1581d6e53",    "nickname": "baby girl",
        "bio": "Auspicious baby",
        "username": "roxie",
        "name": "Funke Olasupo",
        "statusType":"offline",
        "statusText":"On a vacation"
       
    },
    "customFields": {}
}
```

## Example Call   &#x20;

```bash
 curl -L -X POST 'http://localhost:3000/api/v1/users.updateOwnBasicInfo' \
-H 'x-auth-token: nwH90MZqosB_BxeXNvny8MCa_PqDEY18vO9LDCFpNuB' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ' \
-H 'Content-Type: application/json' \
--data-raw '{
    "data": {
        "email": "funke.olasupo@rocket.chat",
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

## Example Result

```javascript
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
                        "address": "funke.olasupo@rocket.chat",
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
                "address": "funke.olasupo@rocket.chat",
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
            "JKa7R9zu2DinBhBN9",
            "bfeqKDqQRxYM2tGXz",
            "6NS2ZhZXQFvmEfxMe",
            "huQs44zbCmozm4XtW",
            "M58HfkJqaKbD2piHh",
            "RcS8FunJvXFJJEP4j",
            "JbX6GtLKsaTWqd5st",
            "wgd7CYLyiMWgWSY5e",
            "G8KgwWSRLua9bZETT",
            "thzWsW9EKns2QMxkc",
            "wYmpBgzn6rj3ET8J2",
            "WDuJLFkjwk6L7LdFC",
            "KoZ9KAKnQo3Z5iC5p",
            "64adb09baa5ad4273bfc0cbf",
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
            "versionUpdate-6_0_1": {
                "id": "versionUpdate-6_0_1",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.0.1"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.0.1",
                "modifiers": [],
                "read": true
            },
            "versionUpdate-6_1_0": {
                "id": "versionUpdate-6_1_0",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.1.0"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.1.0",
                "modifiers": []
            },
            "versionUpdate-6_1_1": {
                "id": "versionUpdate-6_1_1",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.1.1"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.1.1",
                "modifiers": []
            },
            "versionUpdate-6_1_3": {
                "id": "versionUpdate-6_1_3",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.1.3"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.1.3",
                "modifiers": []
            },
            "versionUpdate-6_1_4": {
                "id": "versionUpdate-6_1_4",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.1.4"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.1.4",
                "modifiers": []
            },
            "versionUpdate-6_1_5": {
                "id": "versionUpdate-6_1_5",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.1.5"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.1.5",
                "modifiers": []
            },
            "versionUpdate-6_1_6": {
                "id": "versionUpdate-6_1_6",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.1.6"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.1.6",
                "modifiers": []
            },
            "versionUpdate-6_1_7": {
                "id": "versionUpdate-6_1_7",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.1.7"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.1.7",
                "modifiers": []
            },
            "versionUpdate-6_2_2": {
                "id": "versionUpdate-6_2_2",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.2.2"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.2.2",
                "modifiers": []
            },
            "versionUpdate-6_2_3": {
                "id": "versionUpdate-6_2_3",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.2.3"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.2.3",
                "modifiers": []
            },
            "versionUpdate-6_2_4": {
                "id": "versionUpdate-6_2_4",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.2.4"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.2.4",
                "modifiers": []
            },
            "versionUpdate-6_2_5": {
                "id": "versionUpdate-6_2_5",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.2.5"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.2.5",
                "modifiers": []
            },
            "versionUpdate-6_2_6": {
                "id": "versionUpdate-6_2_6",
                "priority": 10,
                "title": "Update_your_RocketChat",
                "text": "New_version_available_(s)",
                "textArguments": [
                    "6.2.6"
                ],
                "link": "https://github.com/RocketChat/Rocket.Chat/releases/tag/6.2.6",
                "modifiers": []
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
        "bio": "Auspicious baby",
        "nickname": "baby girl"
    },
    "success": true
}
```

## Change Log

| Version | Description                            |
| ------- | -------------------------------------- |
| 0.62.2  | Added as `user.updateOwnBasicInfo`     |
| 6.4.0   | Add `bio` and `statusType` parameters. |
