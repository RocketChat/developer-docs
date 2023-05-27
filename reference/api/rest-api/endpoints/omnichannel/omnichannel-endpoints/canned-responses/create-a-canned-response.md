# Create a Canned Response

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Create a new [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `POST`      |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="216">Argument</th><th width="188">Example</th><th width="158">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>shortcut</code></td><td><code>card-declined</code></td><td>Required</td><td>The shortcut to the message snippet.</td></tr><tr><td><code>text</code></td><td><code>reasons for your cardmalfunction</code></td><td>Required</td><td>The message snippet</td></tr><tr><td><code>scope</code></td><td><code>global</code></td><td>Required</td><td>The scope of the canned response</td></tr><tr><td>tags</td><td><code>card</code></td><td>Optional</td><td>The tags for your canned response.</td></tr></tbody></table>

## Example payload

```javascript
{
    "shortcut": "my-new-canned",
    "text": "This is an example",
    "scope": "global",
    "tags": ["tag1", "tag2"]
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/canned-responses \
    -d '{    "shortcut": "my-new-canned", "text": "This is an example", "scope": "global", "tags": ["tag1", "tag2"] }'
```

## Example Result

```javascript
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
