# Convert Team to Channel

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/teams.convertToChannel</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="175.33333333333331">Key</th><th width="237">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark></td><td><code>612b8ae982d286c3d1f5</code></td><td>The team ID that you want to convert to a channel.</td></tr></tbody></table>

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/teams.convertToChannel\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name' \
-d "teamId=612b8ae982d286c3d1f5db31"
```

## Example Response

### Success

```json
{
    "success": true
}
```

### Errors

The following error can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **Missing Team ID or Name**: Requires a valid Team ID or Name for the request to be made.
* **Invalid Team ID**: Requires a valid Team ID for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Missing Team ID or Name" %}
```javascript
{
    "success": false,
    "error": "missing-teamId-or-teamName"
}
```
{% endtab %}

{% tab title="Invalid Team ID" %}
```javascript
{
    "success": false,
    "error": "team-does-not-exist"
}
```
{% endtab %}
{% endtabs %}
