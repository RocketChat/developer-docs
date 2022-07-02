# Call Center Endpoints

## Call Center Registration Information

| **URL**                                               | **Description**                                              | **Details Page**                         |
| ----------------------------------------------------- | ------------------------------------------------------------ | ---------------------------------------- |
| `/v1/connector.extension.getRegistrationInfoByUserId` | Use this endpoint to get the  registration information by ID | [Link](./#voip-registration-information) |

## Call Center Query Summary

| **URL**                          | **Description**                                      | **Details Page**              |
| -------------------------------- | ---------------------------------------------------- | ----------------------------- |
| `/api/v1/voip/queues.getSummary` | Use this endpoint to get the VoIP query summary data | [Link](./#voip-query-summary) |

## Call Center Queue Membership Information

| **URL**                          | **Description**                                         | **Details Page**                 |
| -------------------------------- | ------------------------------------------------------- | -------------------------------- |
| `/api/v1/voip/queues.getSummary` | Use this endpoint to get the VoIP queue membership data | [Link](./#voip-queue-membership) |

## Call Center Queue Membership Subscription

| **URL**                                     | **Description**                                                      | **Details Page**                 |
| ------------------------------------------- | -------------------------------------------------------------------- | -------------------------------- |
| `/v1/voip/queues.getMembershipSubscription` | Use this endpoint to get the VoIP queue membership subscription data | [Link](./#voip-queue-membership) |

## Call Center Create Visitor

| **URL**                    | **Description**                            | **Details Page**          |
| -------------------------- | ------------------------------------------ | ------------------------- |
| `/api/v1/livechat/visitor` | Use this endpoint to create a VoIP visitor | [Link](./#create-visitor) |

## Call Center Events

### Send Call Center Events

| **URL**               | **Description**                        | **Details Page**            |
| --------------------- | -------------------------------------- | --------------------------- |
| `/api/v1/voip/events` | Use this endpoint to send VoIP events  | [Link](./#send-voip-events) |

## Call Center Extension(s)&#x20;

### Get Call Center Extension

| **URL**                         | **Description**                                          | **Details Page**                 |
| ------------------------------- | -------------------------------------------------------- | -------------------------------- |
| `/api/v1/omnichannel/extension` | Use this endpoint to retrieve VoIP extension information | [Link](./#fetch-voip-extensions) |
|                                 |                                                          |                                  |

### Get Call Center Extensions

| **URL**                                             | **Description**                               | **Details Page**                 |
| --------------------------------------------------- | --------------------------------------------- | -------------------------------- |
| `/api/v1/omnichannel/extensions?count=10&offset=10` | Use this endpoint to retrieve VoIP extensions | [Link](./#fetch-voip-extensions) |

## Call Center Agent Extension

| **URL**                           | **Description**                                               | **Details Page**            |
| --------------------------------- | ------------------------------------------------------------- | --------------------------- |
| `/v1/omnichannel/agent/extension` | Use this endpoint to create, update and delete VoIP extension | [Link](./#agent-extensions) |

## Call Center Server Connection

### Check Management Server Connection&#x20;

| **URL**                                                                     | **Description**                                                | **Details Page**                              |
| --------------------------------------------------------------------------- | -------------------------------------------------------------- | --------------------------------------------- |
| `/api/v1/voip/managementServer/checkConnection?host&port&username&password` | Use this endpoint to check Management Server Connection Status | [Link](./#check-management-server-connection) |

### Check Call Server Connection

| **URL**                                                                                       | **Description**                                          | **Details Page**                        |
| --------------------------------------------------------------------------------------------- | -------------------------------------------------------- | --------------------------------------- |
| `/api/v1/voip/callServer/checkConnection?websocketUrl=wss://omni-asterisk.dev.rocket.chat/ws` | Use this endpoint to check Call Server Connection Status | [Link](./#check-call-server-connection) |

## Call Center Room

### Create Call Center Room (s)

| **URL**                                                                              | **Description**                       | **Details Page**            |
| ------------------------------------------------------------------------------------ | ------------------------------------- | --------------------------- |
| `/api/v1/voip/room?token=867ad6a09fc4af29f6f1f2a9cf1deaba&agentId=6vHSSqdBHdm2R4gfi` | Use this endpoint to create VoIP room | [Link](./#create-voip-room) |

### Get Call Center Room by ID

| **URL**               | **Description**                                           | **Details Page**                 |
| --------------------- | --------------------------------------------------------- | -------------------------------- |
| `/api/v1/voip/events` | Use this endpoint to retrieve VoIP room information by ID | [Link](./#fetch-voip-room-by-id) |

### Close Call Center Room

| **URL**                   | **Description**                               | **Details Page**           |
| ------------------------- | --------------------------------------------- | -------------------------- |
| `/api/v1/voip/room.close` | Use this endpoint close the VoIP conversation | [Link](./#close-voip-room) |
