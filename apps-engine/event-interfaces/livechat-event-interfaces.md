# Livechat - Event Interfaces

The table below contains all of the livechat-related events, as well as the purpose of each event. If you want to execute actions based on livechat events, you may use any of the events mentioned below as an event interface.&#x20;

| Interface                       | Purpose                                                                                                         |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| `IDepartment`                   | Handler called to provide the details of a department.                                                          |
| `ILivechatEventContext`         | Handler called to provide the context of the livechat event such as agent and room.                             |
| `ILivechatMessage`              | Handler called to provide the message details of a livechat such as visitor and token.                          |
| `ILivechatRoom`                 | Handler called to provide the details of the livechat room.                                                     |
| `ILivechatRoomClosedHandler`    | Handler called after a livechat room is closed.                                                                 |
| `ILivechatTransferData`         | Handler called when the livechat data is transferred from a current room to the targeted agent and department.  |
| `ILivechatTransferEventContext` | Handler called to provide the context of the livechat data transferred.                                         |
| `IPostLivechatAgentAssigned`    | Handler called after the assignment of a livechat agent.                                                        |
| `IPostLivechatAgentUnassigned`  | Handler called after the unassignment of a livechat agent.                                                      |
| `IPostLivechatGuestSaved`       | Handler called after the guest info gets saved.                                                                 |
| `IPostLivechatRoomClosed`       | Handler called after a livechat room is closed.                                                                 |
| `IPostLivechatRoomSaved`        | Handler called after the room info gets saved.                                                                  |
| `IPostLivechatRoomStarted`      | Handler called after a livechat room starts.                                                                    |
| `IPostLivechatRoomTransferred`  | Handler called after a livechat room gets transferred.                                                          |
| `IVisitor`                      | Handler called to provide the details of a visitor.                                                             |
| `IVisitorEmail`                 | Handler called to provide the details of a visitor email address.                                               |
| `IVisitorPhone`                 | Handler called to provide the details of a visitor phone number.                                                |
