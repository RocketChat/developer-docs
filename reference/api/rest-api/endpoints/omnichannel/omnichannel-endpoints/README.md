# Omnichannel Endpoints

## Agent

<table><thead><tr><th width="272">Url</th><th width="276">Short Description</th><th width="323.3333333333333">Details Page</th></tr></thead><tbody><tr><td><code>api/v1/livechat/agents/:agentId/departments</code></td><td>Returns all the departments associated with an agent</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/agents/agents-departments">Link</a></td></tr><tr><td><code>api/v1/livechat/analytics/agents/average-service-time</code></td><td>Retrieves average service time per agent</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/agents/agents-average-service-time">Link</a></td></tr><tr><td><code>api/v1/livechat/analytics/agents/total-service-time</code></td><td>Retrieves total service time sorted by agent</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/agents/agents-total-service-time">Link</a></td></tr><tr><td><code>api/v1/livechat/analytics/agents/available-for-service-history</code></td><td>Retrieves a list of agents and their available time for the provided time frame</td><td><a href="https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/agents/agents-available-for-service-history">Link</a></td></tr></tbody></table>

## Livechat Appearance

| Url                          | Short Description                                   | Details Page                                                                                              |
| ---------------------------- | --------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/appearance` | Retrieves LiveChat widget settings about appearance | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/appearance) |

## Business Hours

| Url                                   | Short Description                                           | Details Page                                                                                                                      |
| ------------------------------------- | ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/business-hour`       | Retrieves all the information of a particular business hour | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/business-hours/business-hour-info)  |
| `api/v1/livechat/business-hours.list` | Retrieves a list of existing business hours                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/business-hours/business-hours-list) |

## Dashboards

| Url                                                                   | Short Description                                       | Details Page                                                                                                                            |
| --------------------------------------------------------------------- | ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/analytics/dashboards/conversation-totalizers`        | Retrieves conversation totalizers for a department      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/conversation-totalizers)       |
| `api/v1/livechat/analytics/dashboards/agents-productivity-totalizers` | Retrieves agent productivity totalizer for a department | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/agent-productivity-totalizers) |
| `api/v1/livechat/analytics/dashboards/chats-totalizers`               | Retrieves chat totalizers for a department              | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/chat-totalizers)               |
| `api/v1/livechat/analytics/dashboards/productivity-totalizers`        | Retrieves productivity totalizers for a department      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/productivity-totalizers)       |
| `api/v1/livechat/analytics/dashboards/charts/chats`                   | Retrieves chats chat for a department                   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/chats-chart)                   |
| `api/v1/livechat/analytics/dashboards/charts/chats-per-agent`         | Retrieves chats per agent for a department chart        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/chats-per-agent-chart)         |
| `api/v1/livechat/analytics/dashboards/charts/agents-status`           | Retrieves agent's statuses chart                        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/agents-statuses-chart)         |
| `api/v1/livechat/analytics/dashboards/charts/chats-per-department`    | Retrieves chats per department chart                    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/chats-per-department-chart)    |
| `api/v1/livechat/analytics/dashboards/charts/timings`                 | Retrieves timing charts                                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/dashboards/timings-charts)                |

## Departments

| Url                                                                | Short Description                                             | Details Page                                                                                                                                  |
| ------------------------------------------------------------------ | ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/department`                                       | Retrieves a list of departments                               | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/get-a-list-of-departments)           |
| `api/v1/livechat/department`                                       | Registers a new department                                    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/register-a-new-department)           |
| `api/v1/livechat/department/:_id`                                  | Retrieves a department's info                                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/get-info-about-a-department)         |
| `api/v1/livechat/department/:_id`                                  | Updates a department                                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/update-a-department)                 |
| `api/v1/livechat/department/:_id`                                  | Removes a department                                          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/remove-a-department)                 |
| `api/v1/livechat/department.autocomplete`                          | Autocompletes department name                                 | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/department-autocomplete)             |
| `api/v1/livechat/department/:departmentId/agents`                  | Retrieves agents of a specific department                     | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/retrieve-agents-of-a-department)     |
| `api/v1/livechat/department/:departmentId/agents`                  | Updates agents of a department                                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/update-agents-of-a-department)       |
| `api/v1/livechat/department.listByIds`                             | Retrieves a list of departments by an array of department ids | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/listing-departments-by-ids)          |
| `api/v1/livechat/departments.available-by-unit/:unitId`            | Retrieves departments available by unit Id                    | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/departments-available-by-unit-id)                           |
| `api/v1/livechat/analytics/departments/amount-of-chats`            | Retrieves the number of incoming chats                        | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/amount-of-chat)                                             |
| `api/v1/livechat/analytics/departments/average-service-time`       | Retrieves average service time                                | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-service-time-by-department)                         |
| `api/v1/livechat/analytics/departments/average-chat-duration-time` | Retrieves average chats duration                              | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-chat-duration-time-by-department)                   |
| `api/v1/livechat/analytics/departments/total-service-time`         | Retrieves total service time                                  | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/total-service-time-by-department)                           |
| `api/v1/livechat/analytics/departments/average-waiting-time`       | Retrieves avg waiting time                                    | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/average-waiting-time-by-department)                         |
| `api/v1/livechat/analytics/departments/total-transferred-chats`    | Retrieves total transferred chats                             | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/total-transferred-chat-by-department)                       |
| `api/v1/livechat/analytics/departments/total-abandoned-chats`      | Retrieves abandoned chats                                     | [Info](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/department/total-abandoned-chats-by-department) |
| `api/v1/livechat/analytics/departments/percentage-abandoned-chats` | Retrieves percentage of abandoned chats                       | [Info](https://developer.rocket.chat/api/rest-api/endpoints/livechat/department-1/percentage-of-abandoned-chats-by-department)                |

## Inquiries

| Url                                  | Short Description                        | Details Page                                                                                                                |
| ------------------------------------ | ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/inquiries.list`     | Lists all of the open livechat inquiries | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiries-list)     |
| `api/v1/livechat/inquiries.take`     | Takes an open inquiry                    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/take-inquiry)       |
| `api/v1/livechat/inquiries.queued`   | Lists queued inquiries                   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiries-queued)   |
| `api/v1/livechat/inquiries.getOne`   | Gets one inquiry by room id              | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiry-get-one)    |
| `api/v1/livechat/inquiry.prioritize` | Sets the priority of an inquiry          | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/inquiries/inquiry-prioritize) |

## Integrations

| Url                                     | Short Description                        | Details Page                                                                                                |
| --------------------------------------- | ---------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/integrations.settings` | Retrieves a list of integration settings | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/integrations) |

## Queue

| Url                     | Short Description          | Details Page                                                                                                  |
| ----------------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/queue` | Retrieves the queued chats | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/livechat-queue) |

## Rooms

| Url                           | Short Description                            | Details Page                                                                                                             |
| ----------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/rooms`       | Retrieves a list of livechat rooms           | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/rooms/livechat-rooms-list) |
| `api/v1/livechat/room.onHold` | Puts an active livechat conversation on hold | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/rooms/room-onhold)         |

## SMS

| Url                                     | Short Description | Details Page                                                                                                       |
| --------------------------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/sms-incoming/:service` | Receives SMS      | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/sms-incoming-twilio) |

## Triggers

| Url                             | Short Description                  | Details Page                                                                                                                      |
| ------------------------------- | ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/triggers`      | Lists all Livechat triggers        | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/triggers/get-the-livechat-triggers) |
| `api/v1/livechat/triggers/:_id` | Retrieves a Livechat Trigger by id | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/triggers/get-a-livechat-trigger)    |

## Upload

| Url                           | Short Description | Details Page |
| ----------------------------- | ----------------- | ------------ |
| `api/v1/livechat/upload/:rid` | post              |              |

## Users

| Url                                | Short Description                   | Details Page                                                                                                                         |
| ---------------------------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/users/:type`      | Gets a list of agents or managers   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel-endpoints/omnichannel-community-edition-endpoints/users)     |
| `api/v1/livechat/users/:type`      | Registers a new agent or manager    | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/users/register-new-agent-or-manager)   |
| `api/v1/livechat/users/:type/:_id` | Gets info about an agent or manager | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/users/get-info-of-an-agent-or-manager) |
| `api/v1/livechat/users/:type/:_id` | Removes an agent or manager         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/users/remove-an-agent-or-manager)      |

## Visitors

| Url                                                                    | Short Description                           | Details Page                                                                                                                                  |
| ---------------------------------------------------------------------- | ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/visitors.info`                                        | Retrieves visitor info by ID                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/visitor-info-by-id)                    |
| `api/v1/livechat/visitors.pagesVisited/:roomId`                        | Retrieves pages visited by livechat visitor | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/get-pages-visited-by-livechat-visitor) |
| `api/v1/livechat/visitors.chatHistory/room/:roomId/visitor/:visitorId` | Retrieves livechat visitor's chat history   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/get-livechat-visitors-chat-history)    |
| `api/v1/livechat/visitors.searchChats/room/:roomId/visitor/:visitorId` | Searches a visitor's chat                   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/search-a-visitors-chat)                |
| `api/v1/livechat/visitors.autocomplete`                                | Autocompletes visitor's name                | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/visitor-autocomplete)                  |
| `api/v1/livechat/visitors.search`                                      | Searches the visitor by the term            | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/visitors/visitors-search)                       |

## Monitors

| Url                               | Short Description              | Details Page                                                                                                             |
| --------------------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/monitors.list`   | Retrieves a list of monitors   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/monitors/list-of-monitors) |
| `api/v1/livechat/monitors.getOne` | Gives the details of a monitor | [Link](https://developer.rocket.chat/api/rest-api/endpoints/omnichannel/omnichannel-endpoints/monitors/get-one-monitor)  |

## Priorities

| Url                                      | Short Description               | Details Page                                        |
| ---------------------------------------- | ------------------------------- | --------------------------------------------------- |
| `api/v1/livechat/priorities`             | Gives a list of priorities      | [Link](priorities/priorities-old/get-priorities.md) |
| `api/v1/livechat/priorities/:priorityId` | Gives the details of a priority | [Link](priorities/priorities-old/get-a-priority.md) |

## Livechat Tags

| Url                           | Short Description          | Details Page                       |
| ----------------------------- | -------------------------- | ---------------------------------- |
| `api/v1/livechat/tags`        | Retrieves a list of tags   | [Link](livechat-tags/get-tags.md)  |
| `api/v1/livechat/tags.getOne` | Retrieves details of a tag | [Link](livechat-tags/get-a-tag.md) |

## Units

| Url                                     | Short Description             | Details Page                                                                                                                   |
| --------------------------------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `api/v1/livechat/units`                 | Create unit                   | [Link](units/create-unit.md)                                                                                                   |
| `api/v1/livechat/units.list`            | Gives a list of units         | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/list-of-unit)          |
| `api/v1/livechat/units.getOne`          | Retrieves details of a unit   | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/get-one-unit)          |
| `api/v1/livechat/unitMonitors.list`     | Gives a list of unit monitors | [Link](https://developer.rocket.chat/api/rest-api/endpoints/livechat/enterprise-edition-endpoints/units/list-of-unit-monitors) |
| `api/v1/livechat/unitMonitors.list/:id` | Update Unit by Id             | [Link](units/update-unit.md)                                                                                                   |
| `api/v1/livechat/unitMonitors.list/:id` | Delete unit using ID          | [Link](units/delete-unit.md)                                                                                                   |

## SLA Policies

| Url                          | Short Description                                   | Details Page                                                                                                            |
| ---------------------------- | --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `api/v1/livechat/sla`        | Get a list of SLA policies and create an SLA policy | [Fetch](sla-policies/get-sla-policies.md), [Create](../../teams-endpoints/create-a-new-team.md)                         |
| `api/v1/livechat/sla/:slaId` | Used to fetch, update and delete an SLA policy      | [Get one](sla-policies/get-an-sla.md), [Update](sla-policies/update-an-sla.md), [Delete](sla-policies/delete-an-sla.md) |
