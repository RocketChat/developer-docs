# Start

Creates a new import operation;
If an operation was already running, it will be aborted. Any data from previous imports will be cleared automatically.

Requires the `run-import` permission.


| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/import.start` | `yes`         | `POST`      |


## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/import.start
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
