# Get Avatars

Avatars are fetched from the server for each room and user, giving the client control over the size and format of the returned image.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/avatar/{subject}</code></td><td><code>no</code></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="163">Key</th><th width="250">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>subject</code><mark style="color:red;"><code>*</code></mark></td><td><code>alice</code>, <code>@general</code></td><td><p>Name of the user or channel. </p><p>Channels are always preceded by an @ symbol. Rooms that are DMs are always represented by the other participant's user avatar.</p></td></tr></tbody></table>

## Query Parameters

The following query parameters are optional.

<table><thead><tr><th width="190.33333333333331">Key</th><th width="224">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>format</code></td><td><code>png</code></td><td><p>Format of the image requested. </p><p>The values can be one of: <code>jpg</code>, <code>jpeg</code>, <code>png</code>.</p></td></tr><tr><td><code>size</code></td><td><code>50</code></td><td>Width and height of the image. Default: 200</td></tr><tr><td><code>rc_uid</code></td><td><code>aobEdbYhXfu5hkeqG</code></td><td>User ID for authenticating is only required if <code>Accounts_AvatarBlockUnauthenticatedAccess</code> is enabled.</td></tr><tr><td><code>rc_token</code></td><td><code>9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq</code></td><td>User auth token for authenticating is only required if <code>Accounts_AvatarBlockUnauthenticatedAccess</code> is enabled.</td></tr></tbody></table>

## Example Call

```bash
curl http://localhost:3000/avatar/alice?size=50
```

## Notes

* This is a RESTful endpoint that sits separately from the [REST API](../../) in the server codebase and behaves slightly differently.
* The `rc_uid` and `rc_token` can alternately be provided as cookies (already present in the web interface), but not as auth headers.
* When requesting the avatar of a user, if they have a custom avatar set, this will override the user's choices of format or size.
* If no uploaded avatar exists for a user, a default one will be generated for them based on the initial of their username in a randomly colored square.
  * If `UI_Use_Name_Avatar` is set AND the user has a real name set; the generated avatar will be based on their actual name instead of the username.
* If no format is requested, or the format requested isn't supported, the format returned will be SVG.
