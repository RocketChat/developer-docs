# Livechat - Event Interfaces

The table below contains all of the livechat-related events, as well as the purpose of each event. If you want to execute actions based on livechat events, you may use any of the events mentioned below as an event interface.&#x20;

| Interface                      | Purpose                                                    |
| ------------------------------ | ---------------------------------------------------------- |
| `IPostLivechatAgentAssigned`   | Handler called after the assignment of a livechat agent.   |
| `IPostLivechatAgentUnassigned` | Handler called after the unassignment of a livechat agent. |
| `IPostLivechatGuestSaved`      | Handler called after the guest info gets saved.            |
| `IPostLivechatRoomClosed`      | Handler called after a livechat room is closed.            |
| `IPostLivechatRoomSaved`       | Handler called after the room info gets saved.             |
| `IPostLivechatRoomStarted`     | Handler called after a livechat room starts.               |
| `IPostLivechatRoomTransferred` | Handler called after a livechat room gets transferred.     |
