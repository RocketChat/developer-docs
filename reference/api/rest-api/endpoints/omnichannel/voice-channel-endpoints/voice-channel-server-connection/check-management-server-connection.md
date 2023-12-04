# Check Management Server Connection

Check the VoIP management server connection status.

<table><thead><tr><th width="163">HTTP Method</th><th width="334">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/voip/managementServer/checkConnection</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-voip-contact-center-settings`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="187.33333333333331">Key</th><th width="212">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>host</code><mark style="color:red;"><code>*</code></mark></td><td><code>localhost</code></td><td>The hostname of the management server.</td></tr><tr><td><code>port</code><mark style="color:red;"><code>*</code></mark></td><td><code>3000</code></td><td>The port number of the management server.</td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>user1</code></td><td>The user name of the administrator user.</td></tr><tr><td><code>password</code><mark style="color:red;"><code>*</code></mark></td><td><code>idosfiejifc354</code></td><td>The password of the administrator user.</td></tr></tbody></table>

## Example Call <a href="#example-call" id="example-call"></a>

{% code overflow="wrap" %}
```json
curl --location --request GET 'localhost:3000/api/v1/voip/managementServer/checkConnection?host=localhost&port=3000&username=christystha&password=' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--data-raw ''
```
{% endcode %}

## Example Response <a href="#example-result" id="example-result"></a>

```json
{
	"status": "connected" | "connection-error",
	"error?": "string"
}
```
