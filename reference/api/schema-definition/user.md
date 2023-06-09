# User

The **IUser** interface represents the **User** object defining the properties and their types that can be associated with a user. User information is stored in the `users` collection on MongoDB.&#x20;

<details>

<summary>Main Interface</summary>

The main interface of a User object.

```typescript
interface IUser {
	_id: string;
	createdAt: Date;
	roles: IRole['_id'][];
	type: string;
	active: boolean;
	username?: string;
	nickname?: string;
	name?: string;
	services?: IUserServices;
	emails?: IUserEmail[];
	status?: UserStatus;
	statusConnection?: string;
	lastLogin?: Date;
	bio?: string;
	avatarOrigin?: string;
	avatarETag?: string;
	avatarUrl?: string;
	utcOffset?: number;
	language?: string;
	statusDefault?: UserStatus;
	statusText?: string;
	oauth?: {
		authorizedClients: string[];
	};
	_updatedAt: Date;
	e2e?: {
		private_key: string;
		public_key: string;
	};
	requirePasswordChange?: boolean;
	customFields?: {
		[key: string]: any;
	};
	settings?: IUserSettings;
	defaultRoom?: string;
	ldap?: boolean;
	extension?: string;
	inviteToken?: string;
	canViewAllInfo?: boolean;
	phone?: string;
	reason?: string;
	federated?: boolean;
	federation?: {
		avatarUrl?: string;
		searchedServerNames?: string[];
	};
	banners?: {
		[key: string]: {
			id: string;
			priority: number;
			title: string;
			text: string;
			textArguments?: string[];
			modifiers: ('large' | 'danger')[];
			link: string;
			read?: boolean;
		};
	};
	importIds?: string[];
}
```

</details>

For more information and details on the Interface and sub-Interfaces, see the code here

{% embed url="https://github.com/RocketChat/Rocket.Chat/blob/develop/packages/core-typings/src/IUser.ts" %}

## User Object

<details>

<summary>Example Object</summary>

```json
{
    "_id": "gzvcvpov9G4TxbGFS",
    "createdAt": {
        "$date": "2023-03-02T17:59:43.415Z"
    },
    "services": {
        "password": {
            "bcrypt": "$2b$10$u..."
        },
        "email2fa": {
            "enabled": true,
            "changedAt": {
                "$date": "2023-03-02T17:59:43.415Z"
            }
        },
        "resume": {
            "loginTokens": []
        }
    },
    "username": "demouser",
    "emails": [
        {
            "address": "demo@email.com",
            "verified": true
        }
    ],
    "type": "user",
    "status": "offline",
    "active": true,
    "_updatedAt": {
        "$date": "2023-03-02T18:47:15.205Z"
    },
    "__rooms": [
        "GENERAL"
    ],
    "roles": [
        "user"
    ],
    "name": "demouser",
    "requirePasswordChange": false,
    "settings": {},
    "lastLogin": {
        "$date": "2023-03-02T18:14:28.122Z"
    },
    "statusConnection": "offline",
    "e2e": {
        "private_key": "{\"$binary\":\"m4E7yE/...==\"}",
        "public_key": "{\"alg\":\"RSA-OAEP-256\",\"e\":\"AQAB\",\"ext\":true,\"key_ops\":[\"encrypt\"],\"kty\":\"RSA\",\"n\":\"0pbPAF67...w\"}"
    },
    "utcOffset": 1
}
```

</details>

### Fields

The User object has these fields with the following data types.

<table data-header-hidden><thead><tr><th width="236">Field</th><th width="149.33333333333331">Data Type</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code></td><td>string</td><td>The unique identifier for the user.</td></tr><tr><td>createdAt</td><td>Date</td><td>The date and time when the user was created.</td></tr><tr><td>roles</td><td>Array of strings</td><td>An array of role IDs associated with the user. Eg "user", "admin", “livechat-agent”</td></tr><tr><td>type</td><td>string</td><td>The type of user. E.g. “user”, “app” or “bot”</td></tr><tr><td>active</td><td>boolean</td><td>Indicates whether the user is active or not.</td></tr><tr><td>username</td><td>string </td><td>The username of the user.</td></tr><tr><td>nickname</td><td>string </td><td>The nickname of the user.</td></tr><tr><td>name</td><td>string </td><td>The name of the user.</td></tr><tr><td>services</td><td>object </td><td>Additional services associated with the user.</td></tr><tr><td>emails</td><td>Array of objects </td><td>An array of email objects associated with the user.</td></tr><tr><td>status</td><td>string </td><td>The status of the user.</td></tr><tr><td>statusConnection</td><td>string </td><td>The status connection of the user.</td></tr><tr><td>lastLogin</td><td>Date </td><td>The date and time of the user's last login.</td></tr><tr><td>bio</td><td>string </td><td>The biography or description of the user.</td></tr><tr><td>avatarOrigin</td><td>string </td><td>The origin of the user's avatar.</td></tr><tr><td>avatarETag</td><td>string </td><td>The ETag of the user's avatar.</td></tr><tr><td>avatarUrl</td><td>string </td><td>The URL of the user's avatar.</td></tr><tr><td>utcOffset</td><td>number </td><td>The UTC offset of the user's timezone.</td></tr><tr><td>language</td><td>string </td><td>The language preference of the user.</td></tr><tr><td>statusDefault</td><td>string </td><td>The default status of the user.</td></tr><tr><td>statusText</td><td>string </td><td>The custom status text of the user.</td></tr><tr><td>oauth</td><td>object </td><td>OAuth information associated with the user.</td></tr><tr><td>_updatedAt</td><td>Date</td><td>The date and time when the user object was last updated.</td></tr><tr><td>e2e</td><td>object </td><td>End-to-end encryption information associated with the user.</td></tr><tr><td>requirePasswordChange</td><td>boolean </td><td>Indicates whether the user needs to change their password.</td></tr><tr><td>customFields</td><td>object </td><td>Additional custom fields associated with the user.</td></tr><tr><td>settings</td><td>object </td><td>User-specific settings.</td></tr><tr><td>defaultRoom</td><td>string </td><td>The ID of the user's default room.</td></tr><tr><td>ldap</td><td>boolean </td><td>Indicates whether the user is an LDAP user.</td></tr><tr><td>extension</td><td>string </td><td>The extension associated with the user.</td></tr><tr><td>inviteToken</td><td>string </td><td>The token for inviting the user.</td></tr><tr><td>canViewAllInfo</td><td>boolean </td><td>Indicates whether the user can view all information.</td></tr><tr><td>phone</td><td>string </td><td>The phone number associated with the user.</td></tr><tr><td>reason</td><td>string </td><td>The reason associated with the user.</td></tr><tr><td>federated</td><td>boolean </td><td>Indicates whether the user is a federated user.</td></tr><tr><td>federation</td><td>object </td><td>Federation information associated with the user.</td></tr><tr><td>banners</td><td>object </td><td>Banner information associated with the user.</td></tr><tr><td>importIds</td><td>Array of strings </td><td>An array of import IDs associated with the user.</td></tr></tbody></table>
