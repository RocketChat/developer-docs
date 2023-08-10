# New

Creates a new import operation;
If an operation was already running, it will be aborted. Any data from previous imports will be cleared automatically.

Requires the `run-import` permission.


| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/import.start` | `yes`         | `POST`      |


## Example Call

```bash
curl -H 'X-Auth-Token: YDthX6agkT6yn96u__5YmLdSCmmTZDndr4zlJmuDADC' \
    -H 'X-User-Id: 7TY57bBj3xQXvf2i2' \
    -H 'Content-Type: application/json' \
    http://localhost:3000/api/v1/import.new \
--data ''
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
