# Get Call Center Queue Membership Subscription Information

<table><thead><tr><th width="163">HTTP Method</th><th width="337">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/voip/queues.getMembershipSubscription</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `inbound-voip-calls`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="205.33333333333331">Key</th><th width="231">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>extension</code><mark style="color:red;"><code>*</code></mark></td><td><code>1293</code></td><td>The phone extension for VoIP.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```json
curl --location --request GET 'localhost:3000/api/v1/voip/queues.getMembershipSubscription' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "extension": "1293"
}'
```
{% endcode %}

## Example Response <a href="#example-result" id="example-result"></a>

```json
{
	"queues" : {
        "name": "event.queue",
        "loggedin": "event.loggedin",
        "available": "event.available",
        "callers": "event.available",
        "holdtime": "event.holdtime",
        "talktime": "event.talktime",
        "longestholdtime": "event.logestholdtime"
    },
	"extension": "1293"
}
```
