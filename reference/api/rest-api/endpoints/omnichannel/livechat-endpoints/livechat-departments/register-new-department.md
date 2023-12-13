# Register New Department

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/department</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="205">Key</th><th width="227">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>department</code><mark style="color:red;"><code>*</code></mark></td><td><p><code>{ "department":</code> </p><p><code>{ ... } }</code></p></td><td>The object which takes the department details.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>testDept</code></td><td>The name of the department you are creating.</td></tr><tr><td><code>email</code><mark style="color:red;"><code>*</code></mark></td><td><code>abc@testdept.com</code></td><td>The email ID associated with the department.</td></tr><tr><td><code>enabled</code><mark style="color:red;"><code>*</code></mark></td><td><code>false</code></td><td>Whether you want to enable the department. The value can be boolean <code>true</code> or <code>false</code>.</td></tr><tr><td><code>showOnRegistration</code><mark style="color:red;"><code>*</code></mark></td><td><code>false</code></td><td><p>You can let visitors choose the department they want to talk to. The option will appear to your customer in the Live Chat widget.</p><p>The value can be boolean <code>true</code> or <code>false</code>.</p></td></tr><tr><td><code>showOnOfflineForm</code><mark style="color:red;"><code>*</code></mark></td><td><code>false</code></td><td>If you want your department to be displayed during off-business hours. <br>The value can be boolean <code>true</code> or <code>false</code>.</td></tr><tr><td><code>description</code></td><td><code>Test department</code></td><td>A description of your department.</td></tr><tr><td><code>agents</code></td><td><p><code>{ "agents":</code> </p><p><code>{ ... } }</code></p></td><td>The object with the agent details that you want to add to the department.</td></tr><tr><td><code>agentId</code></td><td><code>SQafHvoFPuB57NmBD</code></td><td>The agent ID that you want to assign to the department.</td></tr><tr><td><code>count</code></td><td><code>11</code></td><td>The number of chats served by the agent. Enter a value if you want to reset the stored value.<br>Note: This field is used by the routing algorithm to determine the agents that have served the least number of chats and assign new chats to them.</td></tr><tr><td><code>order</code></td><td><code>1</code></td><td>The order in which the agents are assigned to chats.</td></tr></tbody></table>

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/department \
    -d '{
         "department": 
            {"enabled": false, 
             "showOnRegistration": true, 
             "name": "new from api", 
             "email": "john@doe.com", 
             "showOnOfflineForm": true }, 
         "agents": [{ 
             "agentId": "SQafHvoFPuB57NmBD" }] }'
```

## Example Response

```json
{
  "department": {
    "enabled": false,
    "name": "new from api",
    "numAgents": 1,
    "showOnRegistration": true,
    "_updatedAt": "2016-12-13T17:22:19.109Z",
    "_id": "iTfLCX3qqwKgf5uqg"
  },
  "agents": [
    {
      "agentId": "SQafHvoFPuB57NmBD",
      "count": 0,
      "order": 0,
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description                       |
| ------- | --------------------------------- |
| 1.0.0   | New fields for department updated |
| 0.42.0  | Added                             |
