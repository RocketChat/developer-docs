---
permalink: /developer-guides/rest-api/rooms/cleanhistory/
redirect_from:
  - /developer-guides/rest-api/channels/cleanhistory
  - /developer-guides/rest-api/channels/cleanhistory/
description: REST API Clean History Methods
---

# Clean Room History

Cleans up a room, removing messages from the provided time range.

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `/api/v1/rooms.cleanHistory` | `yes` | `POST` |

## Payload

<table>
  <thead>
    <tr>
      <th style="text-align:left">Argument</th>
      <th style="text-align:left">Example</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>roomId</code>
      </td>
      <td style="text-align:left"><code>ByehQjC44FwMeiLbX</code>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">The room&apos;s id</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>latest</code>
      </td>
      <td style="text-align:left"><code>2016-09-30T13:42:25.304Z</code>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">The end of time range of messages to clean</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>oldest</code>
      </td>
      <td style="text-align:left"><code>2016-05-30T13:42:25.304Z</code>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">The start of the time range of messages to clean</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>inclusive</code>
      </td>
      <td style="text-align:left"><code>true</code>
      </td>
      <td style="text-align:left">Optional Default: <code>false</code>
      </td>
      <td style="text-align:left">Whether messages which land on latest and oldest should be included</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>excludePinned</code>
      </td>
      <td style="text-align:left"><code>true</code>
      </td>
      <td style="text-align:left">Optional Default: <code>false</code>
      </td>
      <td style="text-align:left">Whether pinned messages should be deleted</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>filesOnly</code>
      </td>
      <td style="text-align:left"><code>true</code>
      </td>
      <td style="text-align:left">Optional Default: <code>false</code>
      </td>
      <td style="text-align:left">Whether to only delete files and keep messages intact</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>users</code>
      </td>
      <td style="text-align:left"><code>[&quot;vynmera&quot;, &quot;ggazzo&quot;]</code>
      </td>
      <td style="text-align:left">Optional Default: <code>[]</code> (everyone)</td>
      <td style="text-align:left">Specific set of users whose content to delete</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>limit</code>
      </td>
      <td style="text-align:left"><code>10</code>
      </td>
      <td style="text-align:left">
        <p>Optional</p>
        <p>Default: <code>0</code> (all)</p>
      </td>
      <td style="text-align:left">The amount of messages to prune</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ignoreDiscussion</code>
      </td>
      <td style="text-align:left"><code>true</code>
      </td>
      <td style="text-align:left">
        <p>Optional</p>
        <p>Default: <code>true</code>
        </p>
      </td>
      <td style="text-align:left">Determines if messages from discussions should be pruned</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ignoreThreads</code>
      </td>
      <td style="text-align:left"><code>true</code>
      </td>
      <td style="text-align:left">
        <p>Optional</p>
        <p>Default: <code>true</code>
        </p>
      </td>
      <td style="text-align:left">Determines if messages from threads should be pruned</td>
    </tr>
  </tbody>
</table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.cleanHistory \
     -d '{ "roomId": "roomId", "latest": "2016-12-09T13:42:25.304Z", "oldest": "2016-08-30T13:42:25.304Z" }'
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
| 0.64.0 | Added |
| 0.67.0 | Added fields `limit`, `excludePinned`, `filesOnly` and `users` |

