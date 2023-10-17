# Lifecycle of a running app

App lifecycle refers to the processes involved in enabling an app and the stages it may undergo. The app can connect to some of these processes in order to modify or extend the configuration of the Apps Engine; these are the phases an application goes through while running inside a server — it is more of a lifecycle during runtime.&#x20;

In many of these lifecycle stages, the application's status will change within the Apps Engine. On the Rocket.Chat, only two stages are displayed: enabled and disabled. But technically, there are additional statuses that determine the app's current state. This is useful for developers because it provides insight into the app's phases and how to control various aspects of an app operating on a Rocket.Chat server.&#x20;

The `App` class has a number of extendable methods that provide control over various aspects of the app's lifecycle.

The following methods represent the various states of a functioning application:&#x20;

**`Constructed`**: The application has just been created or instantiated. There is little an app can do at this point.&#x20;

**`Initialize`**: During this phase, the application is initialized. Here, the application can obtain configuration from the Apps Engine, register objects, and extend functionality. It indicates that the application's initialize() function was invoked and returned true. `initialize` enables the App to govern its internal initialization procedure and override the default one.

{% code overflow="wrap" %}
```typescript
async initialize(configurationExtend: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void>
```
{% endcode %}

* **`extendConfiguration`**: This method is executed as part of the application's default initialization procedure. The configuration accessor enables the application to provide robust functionality such as **API Endpoints** and **Slash Commands** using the[ configuration accessor](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_iconfigurationextend.iconfigurationextend.html).

{% code overflow="wrap" %}
```typescript
async extendConfiguration(configuration: IConfigurationExtend, environment: IEnvironmentRead): Promise<void>
```
{% endcode %}

**`Enable`**: The app determines whether it is enabled or not. If the parameters are configured correctly, the app will be enabled. This method is executed during the app's activation process. If it returns false, the Apps Engine stops the enabling process and unloads the app's resources configured during initialization.

* **`Auto_enabled`**: the app’s `onEnable()` was called, returned true, and was done automatically (system startup).&#x20;
* **`Manually_enabled`**: the app’s `onEnable()` was called, returned true, and was done by the user (such as installing a new one).&#x20;

{% code overflow="wrap" %}
```typescript
async onEnable (environment: IEnvironmentRead, configurationModify: IConfigurationModify): Promise<boolean>
```
{% endcode %}

**`Disable`**: The application can be disabled, either automatically in response to a system interaction or manually through the marketplace. For instance - when Community workspaces have limitations, the apps will be disabled automatically depending on the cap on the number of apps that can be installed per workspace. If the app is a subscription app, it will be disabled when the subscription expires.

```typescript
async onDisable(configurationModify: IConfigurationModify): Promise<void>
```

Several additional app phases associated with disable are as follows:

<table><thead><tr><th width="340.5">App Phase</th><th>Meaning</th></tr></thead><tbody><tr><td><code>compiler_error_disabled</code></td><td>An error occurred while attempting to compile the app, which rendered it inoperable. Attempts to re-enable it will fail, as it requires an update.</td></tr><tr><td><code>invalid_license_disabled</code></td><td>The app was disabled because its license was invalid.</td></tr><tr><td><code>invalid_installation_disabled</code></td><td>The app was disabled due to an invalid installation or signature validation.</td></tr><tr><td><code>error_disable</code></td><td>The app was disabled due to an unrecoverable error.</td></tr><tr><td><code>manually_disabled</code></td><td>A user manually disabled the application.</td></tr><tr><td><code>invalid_settings_disabled</code></td><td>The app was disabled due to invalid configuration settings.</td></tr></tbody></table>

**`Install`**: This is only when the application is manually uploaded as a private app or installed through the marketplace. It only occurs once during installation. Upon installation, you can send messages to the admin notifying them about the availability of the application or send the user who is installing configuration steps and instructions on how to get started in a direct message.&#x20;

{% code overflow="wrap" %}
```typescript
async onInstall(context: IAppInstallationContext, read: IRead, http: IHttp, persistence: IPersistence, modify: IModify): Promise<void>
```
{% endcode %}

**`Uninstall`**: This phase occurs when a user manually uninstalls an application. This is not feasible to occur automatically. Upon uninstallation, you can use this status to perform housekeeping, notify the server or an external service, or send a message to the user.

{% code overflow="wrap" %}
```typescript
public async onUninstall(context: IAppUninstallationContext, read: IRead, http: IHttp, persistence: IPersistence, modify: IModify): Promise<void>
```
{% endcode %}

**`SettingUpdated`**: Tokens to authenticate with third-party services, etc., can be the settings for an application. When a change is made to one of these settings, the application can respond accordingly. The onSettingUpdated method is executed when an administrator modifies a setting provided by the App via the App Administration Page. This occurs following the update of a configuration. You can now retrieve the modified value.

{% code overflow="wrap" %}
```typescript
async onSettingUpdated(setting: ISetting, configurationModify: IConfigurationModify, read: IRead, http: IHttp): Promise<void>
```
{% endcode %}

**`PreSettingUpdate`**: This is used to retrieve the before and after values of the modified parameter. Consider, for example, the JIRA app. If the user modifies the server URL, the application can attempt to connect to the new server to perform validations or seamlessly react to the change.&#x20;

{% code overflow="wrap" %}
```typescript
async onPreSettingUpdate(context: ISettingUpdateContext, configurationModify: IConfigurationModify, read: IRead, http: IHttp): Promise<ISetting>
```
{% endcode %}

