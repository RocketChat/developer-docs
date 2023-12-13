# Update Agents of Department

Update the agents of a specific department.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/livechat/department/:_id/agents</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `manage-livechat-departments`
* `add-livechat-department-agents`
{% endhint %}

## Path Variables

<table><thead><tr><th width="223.33333333333331">Key</th><th width="235">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>CAJioQNAvLnYWTy8i</code></td><td>The department ID.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="187">Key</th><th width="229">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>upsert</code><mark style="color:red;"><code>*</code></mark></td><td><code>{"upsert": [ {} ] }</code></td><td>The object that contains the agent details.</td></tr><tr><td><code>agentId</code><mark style="color:red;"><code>*</code></mark></td><td><code>6523d369024dde0</code></td><td>The agent ID.</td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>username22</code></td><td>The user name of the agent.</td></tr><tr><td><code>count</code></td><td><code>11</code></td><td>The number of chats served by the agent. Enter a value if you want to reset the stored value.<br>Note: This field is used by the routing algorithm to determine the agents that have served the least number of chats and assign new chats to them.</td></tr><tr><td><code>order</code></td><td><code>1</code></td><td>The order in which agents are assigned to the chats.</td></tr><tr><td><code>remove</code><mark style="color:red;"><code>*</code></mark></td><td><code>[]</code></td><td>The object containing the details of the agent that you want to remove.</td></tr></tbody></table>

{% hint style="info" %}
The agents in `upsert` will be assigned to the department. In case the agents are already there, their information will be updated. The agents in the `remove` key will be unassigned from the department.
{% endhint %}

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/department/649230d479f5c6e276cf4a12/agents' \
--header 'X-Auth-Token: oKUJdR1jFvJ7kNEIYBq' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--header 'Content-Type: application/json' \
--data '{
    "upsert": [{
        "agentId": "6529401b024dde05d3f1cd85",
        "username": "kim"
    }],
    "remove": []
}'
```
{% endcode %}

## Example Response

```json
{
    "success": true
}
```
