# Take Inquiry

Join an open inquiry.

<table><thead><tr><th width="163">HTTP Method</th><th width="347">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/inquiries.take</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="201">Key</th><th width="243">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>inquiryId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The inquiry ID.</td></tr><tr><td><code>userId</code></td><td><code>yuhehQjCfsd876sfd</code></td><td>The user's (agent) ID who is taking the inquiry. This is an optional parameter.</td></tr></tbody></table>

{% hint style="info" %}
If the `userId` is provided, the user must have the `view-l-room` permission.
{% endhint %}

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/livechat/inquiries.take \
     -d '{ 
          "inquiryId": "ByehQjC44FwMeiLbX"}'
```

## Example Response

```json
{
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.2.0   | Added       |
