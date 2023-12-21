# Delete Room

Delete a room from the workspace.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.delete</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="208.33333333333331">Key</th><th width="253">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/rooms.delete' \
-H 'x-auth-token: Bln_vcvvbA9a9j2_GV0QdV52d-xoyLkNoOyPcD4cars' \
-H 'x-user-id: 5fRTXMt7DMJbpPJfh' \
-H 'Content-Type: application/json' \
-d '{
    "roomId":"64adb09baa5ad4273bfc0cbf"
}'
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
| 5.4.0   | Added       |
