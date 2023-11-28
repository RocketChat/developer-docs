# Get a Tag

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Get the details of a specific tag.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/tags/:tagId</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `view-l-room`
* `manage-livechat-tags`
{% endhint %}

## Path Variables

<table><thead><tr><th width="214.33333333333331">Key</th><th width="245">Example</th><th>Description</th></tr></thead><tbody><tr><td><code>tagId</code><mark style="color:red;"><code>*</code></mark></td><td><code>pXkCRLGxD34y2FEZq</code></td><td>The tag ID.</td></tr></tbody></table>

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/tags/:tagId\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Example Response

```json
{
    "_id": "nNJntq2n6GBdR8JC4",
    "name": "331",
    "numDepartments": 2,
    "departments": [
        "kxL4qaa29SMpy3ZXG",
        "WRY3EFGAT9Xh5NFBv"
    ],
    "_updatedAt": "2022-11-28T07:17:31.973Z",
    "description": "test",
    "success": true
}
```
