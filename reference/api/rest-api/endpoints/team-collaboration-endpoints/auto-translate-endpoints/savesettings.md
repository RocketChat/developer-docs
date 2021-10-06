---
description: Saves settings about autotranslate.
---

# Save Settings

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/autotranslate.saveSettings` | `yes` | `POST` |

## Payload

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `7aDSXtjMA3KPLxLjt` | Required | The room's id to apply setting. |
| `field` | `autoTranslate` Or `autoTranslateLanguage` | Required | The setting to apply to user's subscription. |
| `value` | `true` Or `en` | Required | Boolean if the setting is `autoTranslate` and a string \(the language\) if the setting is `autoTranslateLanguage`. |
| `defaultLanguage` | `en` | Optional | The default language. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: Z3cpiYN6CNK2oXWKv" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/autotranslate.saveSettings \
     -d '{ "roomId": "7aDSXtjMA3KPLxLjt", "field": "autoTranslate", "value": true }'
```

## Example Result

```javascript
{
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 1.3.0 | Added |

