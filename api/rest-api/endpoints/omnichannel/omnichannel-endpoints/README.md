# Omnichannel Endpoints

## Agent

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/agents/:agentId/departments` |  |  |
| `livechat/analytics/agents/average-service-time` | Retrieves average service time per agent | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/agent-analytics/agents-average-service-time) |
| `livechat/analytics/agents/total-service-time` | Retrieves total service time sorted by agent | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/agent-analytics/agents-total-service-time) |
| `livechat/analytics/agents/available-for-service-history` | Retrieves a list of agents and their available time for the provided time frame | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/agent-analytics/agents-available-for-service-time) |

## Livechat Appearance 

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/appearance` | \`\` |  |

## Business Hours

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/business-hour` |  |  |
| `api/v1/livechat/business-hours.list` | Retrieves a list of existing business hours | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/business-hours/business-hours-list) |

## Dashboards

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/analytics/dashboards/conversation-totalizers` |  |  |
| `livechat/analytics/dashboards/agents-productivity-totalizers` |  |  |
| `livechat/analytics/dashboards/chats-totalizers` |  |  |
| `livechat/analytics/dashboards/productivity-totalizers` |  |  |
| `livechat/analytics/dashboards/charts/chats` |  |  |
| `livechat/analytics/dashboards/charts/chats-per-agent` |  |  |
| `livechat/analytics/dashboards/charts/agents-status` |  |  |
| `livechat/analytics/dashboards/charts/chats-per-department` |  |  |
| `livechat/analytics/dashboards/charts/timings` |  |  |

## Message

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/department` | `get` | \`\` |
| `livechat/department` | `post` | \`\` |
| `livechat/department/:_id` | `get` | \`\` |
| `livechat/department/:_id` | `put` | \`\` |
| `livechat/department/:_id` | `delete` | \`\` |
| `livechat/department.autocomplete` | `get` | \`\` |
| `livechat/department/:departmentId/agents` | `get` | \`\` |
| `livechat/department/:departmentId/agents` | `post` | \`\` |
| `livechat/department.listByIds` | get |  |

## Facebook

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/facebook` | post |  |

## Inquiries

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/inquiries.list` | `get` | \`\` |
| `livechat/inquiries.take` | `post` | \`\` |
| `livechat/inquiries.queued` | `get` | \`\` |
| `livechat/inquiries.getOne` | `get` |  |

## Integrations

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/integrations.settings` | `get` | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-community-edition-endpoints/integrations) |

## Messages

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/messages.external/:roomId` | `get` |  |

## Office Hours

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/office-hours` | Get omnichannel office hours | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-community-edition-endpoints/office-hours) |

## Queue

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/queue` | `get` | \`\` |

## Rooms

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/rooms` | get |  |

## SMS

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/sms-incoming/:service` | post |  |

## Triggers

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/triggers` | `get` | \`\` |
| `livechat/triggers/:_id` | get |  |

## Upload

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/upload/:rid` | post |  |



## Users

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/users/:type` | Get a list of agents or managers | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-community-edition-endpoints/users) |
| `livechat/users/:type` | `post` | \`\` |
| `livechat/users/:type/:_id` | `get` | \`\` |
| `livechat/users/:type/:_id` | `delete` |  |

## Visitors

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/visitors.info` | `get` | \`\` |
| `livechat/visitors.pagesVisited/:roomId` | `get` | \`\` |
| `livechat/visitors.chatHistory/room/:roomId/visitor/:visitorId` | `get` | \`\` |
| `livechat/visitors.searchChats/room/:roomId/visitor/:visitorId` | `get` | \`\` |
| `livechat/visitors.autocomplete` | `get` | \`\` |
| `livechat/visitors.search` | `get` |  |

## Agent Analytics

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/analytics/agents/average-service-time` | Retrieves average service time per agent | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/agent-analytics/agents-average-service-time) |
| `livechat/analytics/agents/total-service-time` | Retrieves total service time sorted by agent | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/agent-analytics/agents-total-service-time) |
| `livechat/analytics/agents/available-for-service-history` | Retrieves a list of agents and their available time for the provided time frame | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/agent-analytics/agents-available-for-service-time) |

## Departments Analytics

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/departments.available-by-unit/:unitId` |  Retrieves departments available by unit Id | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/departments-available-by-unit-id) |
| `livechat/analytics/departments/amount-of-chats` | Retrieves the number of incoming chats | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/amount-of-chat) |
| `/livechat/analytics/departments/average-service-time` | Retrieves average service time | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-service-time-by-department) |
| `/livechat/analytics/departments/average-chat-duration-time` | Retrieves average chats duration | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-chat-duration-time-by-department) |
| `/livechat/analytics/departments/total-service-time` | Retrieves total service time | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/total-service-time-by-department) |
| `/livechat/analytics/departments/average-waiting-time` | Retrieves avg waiting time | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-waiting-time-by-department) |
| `/livechat/analytics/departments/total-transferred-chats` | total transferred chats | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/total-transferred-chat-by-department) |
| `/livechat/analytics/departments/total-abandoned-chats` | total abandoned chats | [Info](https://docs.rocket.chat/api/rest-api/methods/livechat/total-abandoned-chats-by-department) |
| `/livechat/analytics/departments/percentage-abandoned-chats` | Retrieves percentage of abandoned chats | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/percentage-of-abandoned-chats-by-department) |

## Inquiries

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `api/v1/livechat/inquiry.prioritize` | Sets the priority of an inquiry | [Info](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-enterprise-edition-endpoints/inquiry-prioritize) |

## Monitors

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `api/v1/livechat/monitors.list` | Retrieves a list of monitors | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/monitors/list-of-monitors) |
| `api/v1/livechat/monitors.getOne` | Gives the details of a monitor | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/monitors/get-one-monitor) |

## Priorities

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `livechat/priorities.list` | Gives a list of priorities | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-enterprise-edition-endpoints/priorities/list-of-priorities) |
| `livechat/priority.getOne` | Gives the details of a priority | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-enterprise-edition-endpoints/priorities/get-one-priority) |

## Room On-hold

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `api/v1/livechat/room.onHold` | Puts an active livechat conversation on hold | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-enterprise-edition-endpoints/room-onhold) |

## Livechat Tags

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `api/v1/livechat/tags.list` | Retrieves a list of tags | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/livechat-tags/list-of-tags) |
| `livechat/tags.getOne` | Retrieves details of a tag | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/livechat-tags/get-one-tag) |

## Units

| Url | Short Description | Details Page |
| :--- | :--- | :--- |
| `api/v1/livechat/units.list` | Gives a list of units | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/list-of-unit) |
| `api/v1/livechat/units.getOne` | Retrieves details of a unit | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/get-one-unit) |
| `api/v1/livechat/unitMonitors.list` | Gives a list of unit monitors | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/list-of-unit-monitors) |



