---
description: Autocompletes visitor's name
---

# Visitor Autocomplete

**Under development**

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
| `text` |  | Required |
| `onlyMyVisitors` | `true` | Required |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department?text=&onlyMyDepartments=true \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript

```

