# Update Department

Update the details of a specific department.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>PUT</code></td><td><code>/api/v1/livechat/department/:_id</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:&#x20;

* `manage-livechat-departments`
* `add-livechat-department-agents`
{% endhint %}

## Path Variables

<table><thead><tr><th width="192.33333333333331">Key</th><th width="246">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>iTfLCX3qqwKgf5uqg</code></td><td>The department ID that you want to update.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="205">Key</th><th width="227">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>department</code><mark style="color:red;"><code>*</code></mark></td><td><p><code>{ "department":</code> </p><p><code>{ ... } }</code></p></td><td>The object which takes the department details.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>testDept</code></td><td>The name of the department you are creating.</td></tr><tr><td><code>email</code><mark style="color:red;"><code>*</code></mark></td><td><code>abc@testdept.com</code></td><td>The email ID associated with the department.</td></tr><tr><td><code>enabled</code><mark style="color:red;"><code>*</code></mark></td><td><code>false</code></td><td>Whether you want to enable the department. The value can be boolean <code>true</code> or <code>false</code>.</td></tr><tr><td><code>showOnRegistration</code><mark style="color:red;"><code>*</code></mark></td><td><code>false</code></td><td><p>You can let visitors choose the department they want to talk to. The option will appear to your customer in the Live Chat widget.</p><p>The value can be boolean <code>true</code> or <code>false</code>.</p></td></tr><tr><td><code>showOnOfflineForm</code><mark style="color:red;"><code>*</code></mark></td><td><code>false</code></td><td>If you want your department to be displayed during off-business hours. <br>The value can be boolean <code>true</code> or <code>false</code>.</td></tr><tr><td><code>description</code></td><td><code>Test department</code></td><td>A description of your department.</td></tr><tr><td><code>agents</code></td><td><p><code>{ "agents":</code> </p><p><code>{ ... } }</code></p></td><td>The object with the agent details that you want to add to the department.</td></tr><tr><td><code>agentId</code></td><td><code>SQafHvoFPuB57NmBD</code></td><td>The agent ID that you want to assign to the department.</td></tr></tbody></table>

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X PUT \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/department/iTfLCX3qqwKgf5uqg \
    -d '{"department": {
            "enabled": true, 
            "name": "new from api - live", 
            "showOnRegistration": true}, 
    "agents": [{
            "agentId": "SQafHvoFPuB57NmBD", 
            "username": "john.doe"}] }'
```

## Example Response

```json
{
  "department": {
    "_id": "iTfLCX3qqwKgf5uqg",
    "enabled": true,
    "name": "new from api - live",
    "description": null,
    "numAgents": 1,
    "showOnRegistration": true,
    "_updatedAt": "2016-12-13T17:30:02.643Z"
  },
  "agents": [
    {
      "_id": "DDjZbhTF74n3NBuWK",
      "agentId": "SQafHvoFPuB57NmBD",
      "departmentId": "iTfLCX3qqwKgf5uqg",
      "username": "john.doe",
      "count": 0,
      "order": 0,
      "_updatedAt": "2016-12-13T17:30:02.656Z"
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.42.0  | Added       |
