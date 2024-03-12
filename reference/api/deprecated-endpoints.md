# Deprecated Endpoints

The methods and endpoints of the **Rest API** and **Realtime API** that have been depreciated are listed below.

## REST API

### Endpoints to be removed

<table data-full-width="false"><thead><tr><th width="190">Endpoint</th><th width="184">Release deprecated</th><th width="171">Planned removal</th><th>Description</th></tr></thead><tbody><tr><td><a href="https://developer.rocket.chat/reference/api/rest-api/endpoints/miscellaneous/licenses/get-licenses"><code>/licenses.get</code></a></td><td>6.5.0</td><td>7.0.0</td><td>The endpoint is replaced by <code>/licenses.info</code></td></tr><tr><td><a href="https://developer.rocket.chat/reference/api/rest-api/endpoints/miscellaneous/licenses/confirm-enterprise-license"><code>/licenses.isEnterprise</code></a></td><td>6.5.0</td><td>7.0.0</td><td>The endpoint is replaced by <code>/licenses.info</code></td></tr><tr><td><a href="https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-room/update-room-visitor-info"><code>/livechat/room.visitor</code></a></td><td>6.5.0</td><td>7.0.0</td><td>The endpoint will be removed.</td></tr><tr><td><a href="https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-inquiries/inquiries-queued"><code>/livechat/inquiries.queued</code></a></td><td>5.4.1</td><td>7.0.0</td><td>The endpoint is replaced by <code>/livechat/inquiries.queuedForUser</code></td></tr></tbody></table>

### Removed endpoints

The following endpoints have been removed:

| Endpoint                 | Release deprecated | Release removed |
| ------------------------ | ------------------ | --------------- |
| `/livechat/office-hours` |                    | 5.0.0           |
| `/v1/info`               | 1.0.0              | 1.12.0          |
| `/emoji.custom`          | 1.0.0              | 1.12.0          |
| `/permissions.list`      | 0.73.0             | 1.11.0          |
| `/permissions`           | 0.66.0             | 0.69.0          |
| `/channels.cleanHistory` | 0.64.0             | 0.67.0          |
| `/user.roles`            | 0.63.0             | 0.66.0          |

### Renamed endpoints

The following endpoints have been replaced:

| Endpoint                                          | Renamed endpoint                                                                                                                                                                                     | Release |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| `/livechat/business-hours.list`                   | [`/livechat/business-hours`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/business-hours/get-business-hours)                                        | 5.0.0   |
| `/livechat/departments.available-by-unit/:unitId` | [`/livechat/units/:unitId/departments/available`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-units/get-available-departments-by-unit-id) | 5.0.0   |
| `/livechat/departments.by-unit/:unitId`           | [`/livechat/units/:unitId/departments`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-units/get-departments-by-unit-id)                     | 5.0.0   |
| `/livechat/monitors.list`                         | [`/livechat/monitors`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-monitors/get-list-of-monitors)                                         | 5.0.0   |
| `/livechat/units.getOne`                          | [`/livechat/monitors/:username`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-monitors/get-a-monitor)                                      | 5.0.0   |
| `/livechat/priorities.list`                       | [`/livechat/priorities`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-priorities/get-priorities)                                           | 5.0.0   |
| `/livechat/priority.getOne`                       | [`/livechat/priorities/:priorityId`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-priorities/get-a-priority)                               | 5.0.0   |
| `/livechat/tags.list`                             | [`/livechat/tags`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-tags/get-list-of-tags)                                                     | 5.0.0   |
| `/livechat/tags.getOne`                           | [`/livechat/tags/:tagId`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-tags/get-a-tag)                                                     | 5.0.0   |
| `/livechat/units.list`                            | [`/livechat/units`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-units/get-list-of-units)                                                  | 5.0.0   |
| `/livechat/units.getOne`                          | [`/livechat/units/:unitId`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-units/get-a-unit)                                                 | 5.0.0   |
| `/livechat/unitMonitors.list`                     | [`/livechat/units/:unitId/monitors`](https://developer.rocket.chat/reference/api/rest-api/endpoints/omnichannel/livechat-endpoints/livechat-units/get-list-of-unit-monitors)                         | 5.0.0   |

### Changes in parameters

<table data-full-width="true"><thead><tr><th width="209">Parameter</th><th width="179">Endpoints affected</th><th width="190">Release deprecated</th><th width="159">Planned removal</th><th>Description</th></tr></thead><tbody><tr><td><code>query</code> and <code>fields</code> <a href="https://developer.rocket.chat/reference/api/rest-api#query-and-fields">query parameters</a></td><td>All endpoints</td><td>5.0.0</td><td>7.0.0</td><td>The parameters are removed to avoid malicious queries. Check the endpoints for alternatives.</td></tr><tr><td><code>role</code></td><td><code>roles.getUsersInRole</code></td><td>4.6.0</td><td>7.0.0</td><td>The parameter will stop being interpreted as the role name as a fallback (enter the role ID instead).</td></tr><tr><td><code>roleName</code></td><td><code>roles.addUserToRole</code></td><td>4.6.0</td><td>7.0.0</td><td>The parameter will stop being accepted (use the <code>roleId</code>  parameter instead).</td></tr><tr><td><code>roleName</code></td><td><code>roles.removeUserFromRole</code></td><td>4.6.0</td><td>7.0.0</td><td>The parameter will stop being accepted (use the <code>roleId</code>  parameter instead).</td></tr><tr><td><code>appId</code></td><td><code>oauth-apps.get</code></td><td>6.0.0</td><td>7.0.0</td><td>The parameter will stop being accepted (use the <code>clientId</code> or <code>_id</code> parameters instead).</td></tr></tbody></table>

## Realtime API

<table><thead><tr><th width="270">Method</th><th width="236.33333333333331">Release deprecated</th><th>Release removed</th></tr></thead><tbody><tr><td><code>reportMessage</code></td><td>6.2.0</td><td>7.0.0</td></tr><tr><td><code>livechat:getDepartmentForwardRestrictions</code></td><td>5.2.0</td><td>7.0.0</td></tr><tr><td><code>livechat:getFirstRoomMessage</code></td><td>5.2.0</td><td>7.0.0</td></tr><tr><td><code>cleanChannelHistory</code></td><td>0.64.0</td><td>0.67.0</td></tr><tr><td><code>addOAuthApp</code></td><td>6.0.0</td><td>6.0.0</td></tr><tr><td><code>canAccessRoom</code></td><td>4.1.1</td><td>5.0.0</td></tr></tbody></table>

The following methods are replaced:

<table><thead><tr><th width="182">Method</th><th width="180">Release deprecated</th><th width="158">Planned removal</th><th>Description</th></tr></thead><tbody><tr><td><code>inserOrUpdateUser</code></td><td>6.7.0</td><td>7.0.0</td><td>Users upsert won't be allowed anymore (the method will be completely removed).</td></tr><tr><td><a href="https://developer.rocket.chat/reference/api/realtime-api/method-calls/messages/delete-message"><code>deleteMessage</code></a></td><td>6.2.0</td><td>7.0.0</td><td>Replaced by <a href="https://developer.rocket.chat/reference/api/rest-api/endpoints/messaging/chat-endpoints/delete"><code>chat.delete</code></a> endpoint.</td></tr><tr><td><a href="https://developer.rocket.chat/reference/api/realtime-api/method-calls/users/list-custom-emoji"><code>listEmojiCustom</code></a></td><td>5.4.3</td><td>7.0.0</td><td>Replaced by <a href="https://developer.rocket.chat/reference/api/rest-api/endpoints/content-management/custom-emoji-endpoints/list-custom-emojis"><code>emoji-custom.list</code></a> endpoint.</td></tr><tr><td><a href="https://developer.rocket.chat/reference/api/realtime-api/method-calls/rooms/delete-rooms"><code>eraseRoom</code></a></td><td>5.4.0</td><td>7.0.0</td><td>Replaced by <a href="https://developer.rocket.chat/reference/api/rest-api/endpoints/rooms/rooms-endpoints/delete-room"><code>rooms.delete</code></a> endpoint.</td></tr><tr><td><a href="https://developer.rocket.chat/reference/api/realtime-api/method-calls/check-username-availability"><code>checkUsernameAvailability</code></a></td><td>5.4.0</td><td>7.0.0</td><td>Replaced by <code>users.checkUsernameAvailability</code> endpoint.</td></tr><tr><td><a href="https://developer.rocket.chat/reference/api/realtime-api/method-calls/rooms/load-history-5-1"><code>roomNameExists</code></a></td><td>5.1.0</td><td>7.0.0</td><td>Replaced by rooms.nameExists endpoint.</td></tr><tr><td></td><td></td><td></td><td></td></tr></tbody></table>
