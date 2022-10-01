# Update setting

Update the value of a setting by passing the settings unique `_id`

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/settings/:_id` | `YES`         | `POST`      |

The `_id` of a setting is the first argument of the `RocketChat.settings.add` method used in `Rocket.Chat/packages/rocketchat-lib/server/startup/settings.js` (among other files). For example, the following code in that `settings.js` file

```javascript
this.add('Accounts_AllowAnonymousRead', false, {
    type: 'boolean',
    public: true
  });
```

means that the setting labeled "Allow anonymous read" in the section "Accounts" has `_id` equal to `'Accounts_AllowAnonymousRead'`. The second argument is the default value (`false`). The third argument specifies the variable's type and whether it is public, hidden, and so on. To set a color, you can send

```
{
  value: '<color-code>',
  editor: 'color'
}
```

And also to trigger a action-button use:

```
{
  execute: true
}
```

## Payload

| Argument  | Example            | Required                  | Description                           |
| --------- | ------------------ | ------------------------- | ------------------------------------- |
| `_id`     | `Livechat_enabled` | Required                  | The setting's `_id` field             |
| `value`   | `true`             | Required                  | The value to update the setting.      |
| `color`   | `<color-code>`     | Optional                  | The color code to update the setting. |
| `editor`  | `true`             | Required if color was set | The editor key, with `color` value.   |
| `execute` | `true`             | Optional                  | To trigger a action-button            |

## Example Call

{% tabs %}
{% tab title="Curl" %}
```bash
curl --location --request POST 'http://localhost:3000/api/v1/settings/Livechat_enabled' \
--header 'X-Auth-Token: w4KGA2YwTmz4k0cEwa58F6T-gyN4p4MLLWPDfDE8Sgi' \
--header 'X-User-Id: g8aroJivN5R32TxCm' \
--header 'Content-type: application/json' \
--data-raw '{ "value": true }'
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
var myHeaders = new Headers();
myHeaders.append("X-Auth-Token", "w4KGA2YwTmz4k0cEwa58F6T-gyN4p4MLLWPDfDE8Sgi");
myHeaders.append("X-User-Id", "g8aroJivN5R32TxCm");
myHeaders.append("Content-type", "application/json");

var raw = JSON.stringify({
  "value": false
});

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("http://localhost:3000/api/v1/settings/Livechat_enabled", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```
{% endtab %}

{% tab title="Python" %}
```python
import http.client
import json

conn = http.client.HTTPSConnection("localhost", 3000)
payload = json.dumps({
  "value": False
})
headers = {
  'X-Auth-Token': 'w4KGA2YwTmz4k0cEwa58F6T-gyN4p4MLLWPDfDE8Sgi',
  'X-User-Id': 'g8aroJivN5R32TxCm',
  'Content-type': 'application/json'
}
conn.request("POST", "/api/v1/settings/Livechat_enabled", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```
{% endtab %}
{% endtabs %}

## Example Result

```javascript
{
  "success": true
}
```

## Example Call

### Setting a color

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/settings/Livechat_enabled \
     -d '{ "value": "#ffffff", "editor": "color"}'
```

## Example Result

```javascript
{
  "success": true
}
```

## Example Call

### Trigger an action

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/settings/Livechat_enabled \
     -d '{ "value": "method", "execute": true}'
```

## Example Result

```javascript
{
  "success": true
}
```

## Change Log

| Version | Description                                       |
| ------- | ------------------------------------------------- |
| 0.65.0  | Added option to set a color and trigger an action |
| 0.42.0  | Added                                             |
