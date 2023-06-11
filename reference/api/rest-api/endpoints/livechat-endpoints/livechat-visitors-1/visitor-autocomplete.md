---
description: Autocompletes visitor's name
---

# Visitor Autocomplete

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/visitors.autocomplete` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Parameters

| Argument | Example | Required |
| :--- | :--- | :--- |
| `selector` | `{ "exceptions" : [], "conditions" : {}}` | Required |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department?text=&onlyMyDepartments=true \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "items": [
        {
            "_id": "kZqHZAzCgGCnHhzny",
            "username": "guest-446",
            "name": "ASM.Purchasing.Software Sourcing",
            "custom_name": "guest-446 - ASM.Purchasing.Software Sourcing"
        },
        {
            "_id": "aN2CtBZdbPytsvpqj",
            "username": "guest-143",
            "name": "testing",
            "custom_name": "guest-143 - testing"
        },
        {
            "_id": "AW4NYEKLgpezDwx5b",
            "username": "guest-189",
            "name": "testtt",
            "custom_name": "guest-189 - testtt"
        },
        {
            "_id": "KhFxJyLawdeM47sSy",
            "username": "guest-529",
            "name": "user-one",
            "custom_name": "guest-529 - user-one"
        },
        {
            "_id": "YeX9qdMqXLqQi3irt",
            "username": "guest-526",
            "name": "user-two",
            "custom_name": "guest-526 - user-two"
        },
        {
            "_id": "5EHZy4m3KtSKPHFdD",
            "username": "guest-8",
            "name": "vinicius",
            "custom_name": "guest-8 - vinicius"
        }
    ],
    "success": true
```

