---
description: Sets an asset by name.
---

# Set Asset

{% hint style="info" %}
Requires `manage-assets` permission.
{% endhint %}

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/assets.setAsset` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `asset` | `mylogo.png` | Required | Asset File to upload. |
| `assetName` | `logo` | Required | Type of asset to upload, see examples below. |
| `refreshAllClients` | `true` | Optional | If needs refresh all clients to apply changes immediately. |

`assetName` can be one of these: \[`logo`, `background`, `favicon_ico`, `favicon`, `favicon_16`, `favicon_32`, `favicon_192`, `favicon_512`, `touchicon_180`, `touchicon_180_pre`, `tile_70`, `tile_144`, `tile_150`, `tile_310_square`, `tile_310_wide`, `safari_pinned ]`

## Upload a file

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -F "asset=@mylogo.png" \
     -F "assetName=logo" \
     -F "refreshAllClients=true" \     
     http://localhost:3000/api/v1/assets.setAsset
```

### Example Result

```javascript
{
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.69.0 | Added |

