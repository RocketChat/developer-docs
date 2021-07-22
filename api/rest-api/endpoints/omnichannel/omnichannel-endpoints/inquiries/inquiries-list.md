# Inquiries List

Lists all of the open livechat inquiries. It supports the [Offset, Count, and Sort Query Parameters](../../../team-collaboration/offset-and-count-and-sort-info.md).

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.list` | `yes` | `GET` |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `department` | `ByehQjC44FwMeiLbX` | Optional | The department's id or name |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/inquiries.list
```

## Example Result

```javascript
{
    "inquiries": [
          {
            "_id": "GpxfRo8TaPHfsnnC5",
            "rid": "EbQjtCosHJWLQmQYT",
            "name": "Marcos Defendi",
            "ts": "2019-06-11T19:01:57.424Z",
            "department": "jHFgdJyJWstB9M2ik",
            "status": "open"
        },
        {
            "_id": "9dCi64GkwWE389xCm",
            "rid": "ZpjCcbRwPPdnhKWW5",
            "name": "Marcos Defendi",
            "ts": "2019-06-11T19:00:43.124Z",
            "department": "gDDAjeJb7BhHzzEQ8",
            "status": "open"
        }
    ],
    "offset": 0,
    "count": 1,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 1.2.0 | Added |

## 

## Livechat Get one inquiry by room id

Get one inquiry by room id.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/livechat/inquiries.getOne` | `yes` | `GET` |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required | The room's id |

**Note: if the user id is provided, the user must have the `view-l-room` permission.**

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/inquiries.getOne?roomId=ByehQjC44FwMeiLbX
```

## Example Result

```javascript
{
  "inquiry": {
    "_id": "EMXtMA7mPPNkQtWWq",
    "rid": "MA6HRhkEdRGATfEbh",
    "name": "inquiry test",
    "ts": "2019-12-13T18:54:25.352Z",
    "message": "",
    "status": "queued",
    "v": {
      "_id": "rLitbjv7e9WyLBCR4",
      "username": "guest-14",
      "token": "btzu0qdm0sjsn7aqm78kzr",
      "status": "offline"
    },
    "t": "l",
    "_updatedAt": "2019-12-13T19:33:13.255Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 2.4.0 | Added |

