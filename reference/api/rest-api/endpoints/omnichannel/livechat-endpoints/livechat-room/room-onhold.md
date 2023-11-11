# Put Livechat Room on Hold

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Put an active Livechat conversation on hold.

<table><thead><tr><th width="163">HTTP Method</th><th width="338">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/room.onHold</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body

<table><thead><tr><th width="211.33333333333331">Key</th><th width="249">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>Z7223PfNPwH7ihQPh</code></td><td>Active Livechat room ID.</td></tr></tbody></table>

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/livechat/room.onHold \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d "roomId=Z7223PfNPwH7ihQPh"
```

## Example Response

```json
{
    "success": true
}
```
