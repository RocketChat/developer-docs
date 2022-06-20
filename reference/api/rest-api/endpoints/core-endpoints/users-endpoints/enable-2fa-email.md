# Enable 2fa Email

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/users.2fa.enableEmail` | `yes` | `POST` |

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/users.2fa.enableEmail\
```

## Result

### Success

```javascript
{
    "success": true
}
```

