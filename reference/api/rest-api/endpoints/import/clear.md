# Clear
Abort any import operation currently in progress;
Clear any remaining data that may have been left by any previous operation;

Requires the `run-import` permission.


| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/import.clear` | `yes`         | `POST`      |


## Example Call

```bash
curl -H 'X-Auth-Token: YDthX6agkT6yn96u__5YmLdSCmmTZDndr4zlJmuDADC' \
     -H 'X-User-Id: 7TY57bBj3xQXvf2i2' \
     -H 'Content-Type: application/json' \
     http://localhost:3000/api/v1/import.clear \
     -d ''
```

## Example Result

```javascript
{
   "success": true
}
```

## Change Log

| Version | Description                                                                                        |
| ------- | -------------------------------------------------------------------------------------------------- |
| 6.3.0   | Added                                                                                              |
