# Get statistics

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/statistics` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/statistics\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
{
    "_id": "CkkifK3kpAdyF2Rm4",
    "wizard": {
        "organizationType": "enterprise",
        "industry": "technologyServices",
        "size": "1",
        "language": "en",
        "serverType": "privateTeam",
        "registerServer": true
    },
    "uniqueId": "dvH7yKdbSTABY5guM",
    "installedAt": "2019-03-06T22:18:03.324Z",
    "version": "3.18.0",
    "totalUsers": 232,
    "activeUsers": 143,
    "activeGuests": 2,
    "nonActiveUsers": 66,
    "appUsers": 21,
    "onlineUsers": 20,
    "awayUsers": 0,
    "busyUsers": 0,
    "totalConnectedUsers": 20,
    "offlineUsers": 212,
    "userLanguages": {
        "none": 215,
        "es": 1,
        "en": 10,
        "ru": 2,
        "pt-br": 4
    },
    "totalRooms": 3314,
    "totalChannels": 92,
    "totalPrivateGroups": 200,
    "totalDirect": 287,
    "totalLivechat": 2735,
    "totalDiscussions": 104,
    "totalThreads": 132,
    "teams": {
        "totalTeams": 24,
      
        ]
    },
    "uniqueOSOfYesterday": {
        "year": 2021,
        "month": 9,
        "day": 29,
        "data": [
            {
                "count": 3,
                "time": 2007,
                "name": "Windows",
                "version": "10"
            },
            {
                "count": 7,
                "time": 628,
                "name": "Mac OS",
                "version": "10.16.0"
            }
        ]
    },
    "uniqueOSOfLastWeek": {
        "year": 2021,
        "month": 9,
        "day": 29,
        "data": [
            {
                "count": 264,
                "time": 1119984,
                "name": "Windows",
                "version": "10"
            },
            {
                "count": 156,
                "time": 198570,
                "name": "Mac OS",
                "version": "10.15.7"
            },
            {
                "count": 5,
                "time": 886,
                "name": "android",
                "version": "11"
            },
            {
                "count": 410,
                "time": 643397,
                "name": "Mac OS",
                "version": "10.16.0"
            },
            {
                "count": 2,
                "time": 138,
                "name": "ios",
                "version": "14.7.1"
            },
            {
                "count": 3,
                "time": 5247,
                "name": "ios",
                "version": "14.5"
            },
            {
                "count": 40,
                "time": 127555,
                "name": "Linux",
                "version": "x86_64"
            },
            {
                "count": 9,
                "time": 723,
                "name": "Mac OS",
                "version": "10.13.6"
            },
            {
                "count": 9,
                "time": 13480,
                "name": "android",
                "version": "10"
            },
            {
                "count": 19,
                "time": 24189,
                "name": "ios",
                "version": "14.4"
            }
        ]
    },
    "uniqueOSOfLastMonth": {
        "year": 2021,
        "month": 9,
        "day": 29,
        "data": [
            {
                "count": 1,
                "time": 363,
                "name": "Android",
                "version": "8.0.0"
            },
            {
                "count": 3,
                "time": 5247,
                "name": "ios",
                "version": "14.5"
            },
            {
                "count": 1,
                "time": 74,
                "name": "iOS",
                "version": "14.7"
            },
            {
                "count": 1743,
                "time": 2652572,
                "name": "Mac OS",
                "version": "10.16.0"
            },
            {
                "count": 2,
                "time": 546,
                "name": "android",
                "version": "8.0.0"
            },
            {
                "count": 1416,
                "time": 6519160,
                "name": "Windows",
                "version": "10"
            },
            {
                "count": 2,
                "time": 202,
                "name": "android",
                "version": "7.1.2"
            },
            {
                "count": 179,
                "time": 600121,
                "name": "Linux",
                "version": "x86_64"
            },
            {
                "count": 316,
                "time": 288448,
                "name": "ios",
                "version": "14.4"
            },
            {
                "count": 50,
                "time": 87472,
                "name": "Mac OS",
                "version": "10.13.6"
            },
            {
                "count": 5,
                "time": 886,
                "name": "android",
                "version": "11"
            },
            {
                "count": 23,
                "time": 2794,
                "name": "ios",
                "version": "14.7.1"
            },
            {
                "count": 13,
                "time": 837,
                "name": "ios",
                "version": "15.0"
            },
            {
                "count": 2,
                "time": 1319,
                "name": "Android",
                "version": "10"
            },
            {
                "count": 1022,
                "time": 1554166,
                "name": "Mac OS",
                "version": "10.15.7"
            },
            {
                "count": 27,
                "time": 23468,
                "name": "android",
                "version": "10"
            }
        ]
    },
    "apps": {
        "engineVersion": "1.27.1",
        "enabled": true,
        "totalInstalled": 28,
        "totalActive": 23,
        "totalFailed": 0
    },
    "services": {
        "ldap": {
            "users": 0,
            "enabled": false,
            "loginFallback": true,
            "encryption": "plain",
            "mergeUsers": false,
            "syncRoles": false,
            "syncRolesAutoRemove": false,
            "syncData": false,
            "syncChannels": false,
            "syncAvatar": true,
            "groupFilter": false,
            "backgroundSync": {
                "enabled": false,
                "interval": "Every 24 hours",
                "newUsers": true,
                "existingUsers": true
            },
            "ee": {
                "syncActiveState": "disable",
                "syncTeams": false,
                "syncRoles": false
            }
        },
        "saml": {
            "enabled": false,
            "users": 0,
            "signatureValidationType": "Either",
            "generateUsername": false,
            "updateSubscriptionsOnLogin": false,
            "syncRoles": false
        },
        "cas": {
            "enabled": false,
            "users": 0,
            "allowUserCreation": true,
            "alwaysSyncUserData": true
        },
        "oauth": {
            "apple": {
                "enabled": true,
                "users": 0
            },
            "dolphin": {
                "enabled": false,
                "users": 0
            },
            "drupal": {
                "enabled": false,
                "users": 0
            },
            "facebook": {
                "enabled": true,
                "users": 0
            },
            "github": {
                "enabled": false,
                "users": 0
            },
            "githubEnterprise": {
                "enabled": false,
                "users": 0
            },
            "gitlab": {
                "enabled": false,
                "users": 0
            },
            "google": {
                "enabled": true,
                "users": 22
            },
            "linkedin": {
                "enabled": false,
                "users": 0
            },
            "meteor": {
                "enabled": false,
                "users": 0
            },
            "nextcloud": {
                "enabled": false,
                "users": 0
            },
            "tokenpass": {
                "enabled": false,
                "users": 0
            },
            "twitter": {
                "enabled": false,
                "users": 0
            },
            "wordpress": {
                "enabled": false,
                "users": 0
            },
            "custom": {
                "Custom": {
                    "enabled": false,
                    "mergeRoles": false,
                    "users": 0
                },
                "Testoauth": {
                    "enabled": false,
                    "mergeRoles": false,
                    "users": 0
                }
            }
        }
    },
    "integrations": {
        "totalIntegrations": 0,
        "totalIncoming": 0,
        "totalIncomingActive": 0,
        "totalOutgoing": 0,
        "totalOutgoingActive": 0,
        "totalWithScriptEnabled": 0
    },
    "pushQueue": 0,
    "enterprise": {
        "modules": [
            "auditing",
            "canned-responses",
            "ldap-enterprise",
            "livechat-enterprise",
            "omnichannel-mobile-enterprise",
            "engagement-dashboard",
            "push-privacy",
            "scalability",
            "teams-mention"
        ],
        "tags": [
            "enterprise",
            "Gold"
        ]
    },
    "createdAt": "2021-09-30T00:12:01.636Z",
    "_updatedAt": "2021-09-30T00:12:01.636Z",
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}

