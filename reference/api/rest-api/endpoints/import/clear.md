# Clear
Abort any import operation currently in progress;
Clear any remaining data that may have been left by any previous operation;

Requires the `run-import` permission.


| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/import.clear` | `yes`         | `POST`      |


## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/import.clear
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
