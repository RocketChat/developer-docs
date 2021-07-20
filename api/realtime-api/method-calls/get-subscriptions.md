# Get Subscriptions

Returns a `result` with a user's subscription collection. You may pass no params or a date param with the timestamp of your last update. If a date is passed the result will only contain changes to the subscriptions.

## Example call

```javascript
{
    "msg": "method",
    "method": "subscriptions/get",
    "id": "42",
    "params": [ { "$date": 1480377601 } ]
}
```

## Response

```javascript
{
    "msg": "result",
    "id": "42",
    "result": [
        ... // subscriptions
    ]
}
```



