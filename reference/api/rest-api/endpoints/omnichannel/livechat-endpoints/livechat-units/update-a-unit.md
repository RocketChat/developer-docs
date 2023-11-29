# Update a Unit

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/units/:id</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-units`
{% endhint %}

## Path Variables

<table><thead><tr><th width="197.33333333333331">Key</th><th width="228">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>id</code><mark style="color:red;"><code>*</code></mark></td><td><code>4uErt483aPJAg6Xk4</code></td><td>The unit ID.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="221.33333333333331">Key</th><th width="250">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>unitData</code><mark style="color:red;"><code>*</code></mark></td><td><code>{ "unitdata": {...} }</code></td><td>The object containing the unit data.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>unitxx2</code></td><td>The name of the unit that you are creating.</td></tr><tr><td><code>visibility</code><mark style="color:red;"><code>*</code></mark></td><td><code>public</code></td><td>The visibility of the unit. For example, <code>public</code> or <code>private</code>.</td></tr><tr><td><code>unitMonitors</code><mark style="color:red;"><code>*</code></mark></td><td><code>"unitMonitors": [{...}]</code></td><td>The object containing the unit monitors information.</td></tr><tr><td><code>monitorId</code><mark style="color:red;"><code>*</code></mark></td><td><code>GT67Tv6x5p5y5xZWN</code></td><td>The monitor ID that you want to add to the unit.</td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>testerio</code></td><td>The user name of the monitor.</td></tr><tr><td><code>unitDepartments</code><mark style="color:red;"><code>*</code></mark></td><td><code>"unitDepartments": [{...}]</code></td><td>The object containing the department information.</td></tr><tr><td><code>departmentId</code><mark style="color:red;"><code>*</code></mark></td><td><code>CgM4vfNNtj8t4QEMd</code></td><td>The department ID that you want to add to the unit.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request POST 'localhost:3000/api/v1/livechat/units/4uErt483aPJAg6Xk4' \
--header 'x-Auth-token: jx-CrbeqbxPimsZr1UAhO3NsJdU8yB0MVoXkGOKQ3xL' \
--header 'x-user-id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
	"unitData": {
        "name": "unitxx2",
        "visibility": "private"
    },
    "unitMonitors": [{
        "monitorId": "GT67Tv6x5p5y5xZWN",
        "username": "testerio"
    }],
    "unitDepartments": [{
        "departmentId": "CgM4vfNNtj8t4QEMd"
    }]
}'
```
{% endcode %}

## Example Response

```json
{
    "name": "unitxx2",
    "visibility": "private",
    "type": "u",
    "numMonitors": 1,
    "numDepartments": 1,
    "_updatedAt": "2021-12-06T14:40:59.478Z",
    "_id": "o5zNtKy7BcTMgyXtm",
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| `4.2.0` | Added       |
