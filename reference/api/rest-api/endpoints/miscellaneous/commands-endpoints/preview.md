---
description: Fetches the command's preview data or executes the preview item
---

# Get command's preview data

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/commands.preview` | `yes`         | `GET`       |

### Payload

| Argument  | Example             | Required                      | Description                             |
| --------- | ------------------- | ----------------------------- | --------------------------------------- |
| `command` | `unmute`            | Required                      | The name of the command to be executed. |
| `roomId`  | `ByehQjC44FwMeiLbX` | Required                      | The ID of the room.                     |
| `params`  | `@user123`          | Optional Default: `undefined` | Parameters of the command if required.  |

##
