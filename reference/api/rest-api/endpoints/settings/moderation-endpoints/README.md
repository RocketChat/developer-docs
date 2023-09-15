# Moderation Endpoints

[Moderation](https://docs.rocket.chat/use-rocket.chat/workspace-administration/moderation-dashboard) provides the workspace moderator a way to view & manage the [reported messages and users](../../messaging/chat-endpoints/reportmessage.md) across different channels.

| Url                                              | Short Description                                        | Details Page                                  |
| ------------------------------------------------ | -------------------------------------------------------- | --------------------------------------------- |
| `/api/v1/moderation.reportsByUsers`              | Retrieves all the reported messages grouped by users     | [Link](get-reported-messages.md)              |
| `/api/v1/moderation.user.reportedMessages`       | Retrieve all reported messages of a user.                | [Link](get-a-users-reported-messages.md)      |
| `/api/v1/moderation.reports`                     | Retrieve all the reports of a single message             | [Link](fetch-reports-of-a-message.md)         |
| `/api/v1/moderation.reportInfo`                  | Get more details of a single report.                     | [Link](fetch-info-of-a-report.md)             |
| `/api/v1/moderation.dismissReports`              | Dismiss all the reports of a particular user.            | [Link](dismiss-reports.md)                    |
| `/api/v1/moderation.user.deleteReportedMessages` | Delete all the reports of messages that belongs to user. | [Link](delete-reported-messages-of-a-user.md) |
