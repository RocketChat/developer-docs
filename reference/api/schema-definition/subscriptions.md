# Subscriptions

The subscription object contains information about the room and the user in relation to it.

This is stored in the `rocketchat_subscription` collection on MongoDB.

<details>

<summary>Interface</summary>

```typescript
interface ISubscription {
	u: Pick<IUser, '_id' | 'username' | 'name'>;
	v?: Pick<IUser, '_id' | 'username' | 'name'>;
	rid: RoomID;
	open: boolean;
	ts: Date;

	name: string;

	alert?: boolean;
	unread: number;
	t: RoomType;
	ls: Date;
	f?: boolean;
	lr: Date;
	hideUnreadStatus?: true;
	hideMentionStatus?: true;
	teamMain?: boolean;
	teamId?: string;

	userMentions: number;
	groupMentions: number;

	broadcast?: true;
	tunread?: Array<string>;
	tunreadGroup?: Array<string>;
	tunreadUser?: Array<string>;

	prid?: RoomID;

	roles?: IRole['_id'][];

	onHold?: boolean;
	encrypted?: boolean;
	E2EKey?: string;
	E2ESuggestedKey?: string;
	unreadAlert?: 'default' | 'all' | 'mentions' | 'nothing';

	fname?: string;

	code?: unknown;
	archived?: boolean;
	audioNotificationValue?: string;
	desktopNotifications?: 'all' | 'mentions' | 'nothing';
	mobilePushNotifications?: 'all' | 'mentions' | 'nothing';
	emailNotifications?: 'all' | 'mentions' | 'nothing';
	userHighlights?: string[];
	blocked?: unknown;
	blocker?: unknown;
	autoTranslate?: boolean;
	autoTranslateLanguage?: string;
	disableNotifications?: boolean;
	muteGroupMentions?: boolean;
	ignored?: IUser['_id'][];

	department?: unknown;

	desktopPrefOrigin?: 'subscription' | 'user';
	mobilePrefOrigin?: 'subscription' | 'user';
	emailPrefOrigin?: 'subscription' | 'user';

	/* @deprecated */
	customFields?: Record<string, any>;
}

```

</details>

You can check the `ISubscription` interface here.

{% embed url="https://github.com/RocketChat/Rocket.Chat/blob/develop/packages/core-typings/src/ISubscription.ts" %}

## Subscription Object

<details>

<summary>Example Object</summary>

```json
{
  "_id": "GuZJ5YcMHe4iRDbMm",
  "open": true,
  "alert": true,
  "unread": 1,
  "userMentions": 1,
  "groupMentions": 0,
  "ts": {
    "$date": "2023-02-06T14:17:44.985Z"
  },
  "rid": "GENERAL",
  "name": "general",
  "t": "c",
  "u": {
    "_id": "6LMJ5Lu5YsBaqsJvE",
    "username": "user1"
  },
  "_updatedAt": {
    "$date": "2023-02-06T14:17:44.985Z"
  }
}
```

</details>

### Fields

<table data-header-hidden><thead><tr><th width="232.33333333333331">Field</th><th width="191">Data Type</th><th>Description</th></tr></thead><tbody><tr><td>_id</td><td>string</td><td>Unique identifier for the subscription</td></tr><tr><td>u</td><td>object</td><td>Information about the user associated with the subscription (_id, username, name)</td></tr><tr><td>v</td><td>object </td><td>Information about the visitor associated with the subscription (_id, username, name)</td></tr><tr><td>rid</td><td>string</td><td>ID of the room associated with the subscription</td></tr><tr><td>open</td><td>boolean</td><td>Indicates if the room is open for the user(defaults to false on direct messages). This is used by the clients to determine whether the user can see this subscription in their list since you can hide rooms from being visible without leaving them.</td></tr><tr><td>ts</td><td>Date</td><td>The timestamp the room was created at, so this should equal the room's <code>ts</code> field</td></tr><tr><td>name</td><td>string</td><td>Name of the subscription</td></tr><tr><td>alert</td><td>boolean</td><td>Indicates if there is an alert for the subscription to be displayed to the user.</td></tr><tr><td>unread</td><td>number</td><td>Number of unread messages in the subscription. <code>NOTE</code>: The <em>unread</em> counter value depends on your settings in the <strong>Administration</strong> > <strong>Workspace</strong> > <strong>Settings</strong> > <strong>General</strong>.</td></tr><tr><td>t</td><td>string</td><td>Type of room associated with the subscription (e.g., "c" for channel, "d" for direct message. See <a data-mention href="./#rooms">#rooms</a> )</td></tr><tr><td>ls</td><td>Date</td><td>Timestamp of the last seen activity in the subscription</td></tr><tr><td>f</td><td>boolean</td><td>Indicates if the subscription is a favorite</td></tr><tr><td>lr</td><td>Date</td><td>Timestamp of the last reply in a thread</td></tr><tr><td>hideUnreadStatus</td><td>boolean</td><td>Whether the subscribed room should be marked as containing unread messages in the UI or not</td></tr><tr><td>hideMentionStatus</td><td>boolean</td><td>Indicates if the mention status is hidden</td></tr><tr><td>teamMain</td><td>boolean</td><td>Whether this subscription points to the main room of a team or not</td></tr><tr><td>teamId</td><td>string</td><td>(Optional) ID of the team associated with the subscription, if the subscription points to a team room</td></tr><tr><td>userMentions</td><td>number</td><td>Number of unread mentions to the user in the room</td></tr><tr><td>groupMentions</td><td>number</td><td>Number of unread mentions to a group which the user is part of (e.g <code>@all</code>, <code>@here</code>)</td></tr><tr><td>broadcast</td><td>boolean</td><td>Indicates if the subscription is a broadcast</td></tr><tr><td>tunread</td><td>Array&#x3C;string></td><td>(Optional) List of ids of unread threads</td></tr><tr><td>tunreadGroup</td><td>Array&#x3C;string></td><td>(Optional)List of thread ids that contain an unread mention to a group that the user is part of</td></tr><tr><td>tunreadUser</td><td>Array&#x3C;string></td><td>(Optional) List of thread ids that contain an unread mention to the user</td></tr><tr><td>prid</td><td>string</td><td> Parent room id. This will only be available if this is a subscription to a discussion</td></tr><tr><td>roles</td><td>Array&#x3C;string></td><td>Array of role IDs associated with the subscription</td></tr><tr><td>onHold</td><td>boolean</td><td>Omnichannel) Whether or not this room has been put on hold</td></tr><tr><td>encrypted</td><td>boolean</td><td>Indicates if the subscription is encrypted</td></tr><tr><td>E2EKey</td><td>string</td><td>Encryption key for the subscription</td></tr><tr><td>E2ESuggestedKey</td><td>string</td><td>Suggested encryption key for the subscription</td></tr><tr><td>unreadAlert</td><td>string</td><td>Type of alert for unread messages in the subscription ('default', 'all', 'mentions', 'nothing')</td></tr><tr><td>fname</td><td>string</td><td>Friendly name of the subscription</td></tr><tr><td>code</td><td>unknown</td><td>Unknown data type</td></tr><tr><td>archived</td><td>boolean</td><td>Indicates if the subscription is archived</td></tr><tr><td>audioNotificationValue</td><td>string</td><td>Value for audio notifications</td></tr><tr><td>desktopNotifications</td><td>string ('all', 'mentions', 'nothing')</td><td>Desktop notification preferences for the subscription</td></tr><tr><td>mobilePushNotifications</td><td>string ('all', 'mentions', 'nothing')</td><td>Mobile push notification preferences for the subscription</td></tr><tr><td>emailNotifications</td><td>string ('all', 'mentions', 'nothing')</td><td>Email notification preferences for the subscription</td></tr><tr><td>userHighlights</td><td>Array&#x3C;string></td><td>Array of user IDs to highlight in the subscription</td></tr><tr><td>blocked</td><td>unknown</td><td>Unknown data type</td></tr><tr><td>blocker</td><td>unknown</td><td>Unknown data type</td></tr><tr><td>autoTranslate</td><td>boolean</td><td>Indicates if auto-translation is enabled for the subscription</td></tr><tr><td>autoTranslateLanguage</td><td>string</td><td>Language code for auto-translation in the subscription</td></tr><tr><td>disableNotifications</td><td>boolean</td><td>Indicates if notifications are disabled for the subscription</td></tr><tr><td>muteGroupMentions</td><td>boolean</td><td>Indicates if group mentions are muted for the subscription</td></tr><tr><td>ignored</td><td>Array&#x3C;string></td><td>Array of user IDs to ignore in the subscription</td></tr><tr><td>department</td><td>unknown</td><td>Unknown data type</td></tr><tr><td>desktopPrefOrigin</td><td>string ('subscription', 'user')</td><td>Origin of the desktop preference (subscription or user)</td></tr><tr><td>mobilePrefOrigin</td><td>string ('subscription', 'user')</td><td>Origin of the mobile preference (subscription or user)</td></tr><tr><td>emailPrefOrigin</td><td>string ('subscription', 'user')</td><td>Origin of the email preference (subscription or user)</td></tr><tr><td>customFields</td><td>Record&#x3C;string, any></td><td>Custom fields associated with the subscription</td></tr></tbody></table>

{% hint style="info" %}
Notes about customFields:

* customFields inherits from room's customFields for channels (Room Type: c = chanel) and groups (Room Type: p = group) and changes with room's customFields
* customFields inherits from user's customFields for Direct Messages (Room Type: d = direct) and changes with user's customFields. Note that users of Direct Messages room will have own customFields.
{% endhint %}
