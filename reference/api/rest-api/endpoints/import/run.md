# Run

Process the data from the current import operation, creating the users on Rocket.Chat. 
Requires the current import operation state to be `ready`;
Changes the operation state to `importing`;

The endpoint will return success if the conditions to start the process are met, without waiting for it to finish. 

Requires the `run-import` permission.


| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/import.run`   | `yes`         | `POST`      |


**Notes**
1. If an user can not be imported successfully it'll be flagged but the operation will not stop.
2. If an user's email or username is already in use, it'll not be created.
3. Only the users that were imported sucessfully will be removed from the staging area. 

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/import.run
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
