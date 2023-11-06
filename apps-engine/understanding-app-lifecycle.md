# App Development Lifecycle

Now that we know how to create Rocket.Chat apps and extend their functionalities, let's learn about the lifecycle of the apps. For Rocket.Chat apps, app lifecycle refers to the processes involved in enabling an app and the phases it may undergo. The app goes through the lifecycle phases during runtime in a Rocket.Chat server.&#x20;

To add an app to a Rocket.Chat workspace, you must either download it from our [Marketplace](http://marketplace.rocket.chat) or manually [upload it to the server](https://docs.rocket.chat/extend-rocket.chat-capabilities/rocket.chat-marketplace). Once an app is introduced to Rocket.Chat, it goes through several phases.&#x20;

Apart from the typical app development phases such as the design phase, QA phase, and the release phase, additional Rocket.Chat-specific phases include:

* App Logging
* App Deployment
* App Installation
* App Testing

In many of the lifecycle phases, the app's status will change within the Apps-Engine. In the Rocket.Chat UI, two statuses are displayed, `enabled` and `disabled`. Technically, there are additional statuses that determine the app's current state. This gives developers an insight into an app's phases. The `App` class has a number of extendable methods to provide control over the various aspects of the app's lifecycle.

Here we will learn about the methods that represent the various states of a functioning app:&#x20;

**`Constructed`**: The app has just been created or instantiated. There is little an app can do at this point.&#x20;

**`Initialize`**: During this phase, the app is initialized. Here, the app can obtain configuration from the Apps-Engine, register objects, and extend functionality. It indicates that the app's `initialize()` function was invoked and returned true. This enables the app to govern its internal initialization procedure and override the default one.

{% code overflow="wrap" %}
```typescript
async initialize(configurationExtend: IConfigurationExtend, environmentRead: IEnvironmentRead): Promise<void>
```
{% endcode %}

* **`extendConfiguration`**: This method is executed as part of the app's default initialization procedure. The configuration accessor enables the app to provide robust functionality such as **API Endpoints** and **Slash Commands** using the[ configuration accessor](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_iconfigurationextend.iconfigurationextend.html).

{% code overflow="wrap" %}
```typescript
async extendConfiguration(configuration: IConfigurationExtend, environment: IEnvironmentRead): Promise<void>
```
{% endcode %}

**`Enable`**: If the app parameters are configured correctly, the app will be enabled. This method is executed during the app's activation process. If it returns false, the Apps-Engine stops the enabling process and unloads the app's resources configured during initialization.

* **`Auto_enabled`**: the app’s `onEnable()` function is called, returns true, and the app is enabled automatically (at system startup).&#x20;
* **`Manually_enabled`**: the app’s `onEnable()` function is called, returns true, and the app is enabled by the user (such as installing a new app).&#x20;

{% code overflow="wrap" %}
```typescript
async onEnable (environment: IEnvironmentRead, configurationModify: IConfigurationModify): Promise<boolean>
```
{% endcode %}

**`Disable`**: The app can be disabled, either automatically in response to a system interaction or manually through the marketplace. For instance - when Community workspaces have limitations, the apps will be disabled automatically depending on the limit on the number of apps that can be installed per workspace. If the app is a subscription app, it will be disabled when the subscription expires.

```typescript
async onDisable(configurationModify: IConfigurationModify): Promise<void>
```

Several additional app phases associated with disable are as follows:

<table><thead><tr><th width="340.5">App Phase</th><th>Description</th></tr></thead><tbody><tr><td><code>compiler_error_disabled</code></td><td>An error occurred while attempting to compile the app, which rendered it inoperable. Attempts to re-enable it will fail, as it requires an update.</td></tr><tr><td><code>invalid_license_disabled</code></td><td>The app was disabled because its license was invalid.</td></tr><tr><td><code>invalid_installation_disabled</code></td><td>The app was disabled due to an invalid installation or signature validation.</td></tr><tr><td><code>error_disable</code></td><td>The app was disabled due to an unrecoverable error.</td></tr><tr><td><code>manually_disabled</code></td><td>A user manually disabled the application.</td></tr><tr><td><code>invalid_settings_disabled</code></td><td>The app was disabled due to invalid configuration settings.</td></tr></tbody></table>

**`Install`**: This is only when the application is manually uploaded as a private app or installed through the marketplace. It only occurs once during installation. After installation, you can send messages to the admin notifying them about the availability of the app or send configuration steps and instructions on how to get started to the user who is installing the app.&#x20;

{% code overflow="wrap" %}
```typescript
async onInstall(context: IAppInstallationContext, read: IRead, http: IHttp, persistence: IPersistence, modify: IModify): Promise<void>
```
{% endcode %}

**`Uninstall`**: This phase occurs when a user manually uninstalls an app. This is not feasible to occur automatically. Upon uninstallation, you can use this status to perform housekeeping, notify the server or an external service, or send a message to the user.

{% code overflow="wrap" %}
```typescript
public async onUninstall(context: IAppUninstallationContext, read: IRead, http: IHttp, persistence: IPersistence, modify: IModify): Promise<void>
```
{% endcode %}

**`SettingUpdated`**: For instance, the settings for an app can include tokens to authenticate with third-party services. When a change is made to such settings, the app can respond accordingly. The `onSettingUpdated` method is executed when an administrator modifies a setting provided by the app via the **App Administration Page**. This occurs following the update of a configuration. You can now retrieve the modified value.

{% code overflow="wrap" %}
```typescript
async onSettingUpdated(setting: ISetting, configurationModify: IConfigurationModify, read: IRead, http: IHttp): Promise<void>
```
{% endcode %}

**`PreSettingUpdate`**: This is used to retrieve the before and after values of a modified parameter. Consider, for example, the JIRA app. If the user modifies the server URL, the app can attempt to connect to the new server to perform validations or seamlessly react to the change.&#x20;

{% code overflow="wrap" %}
```typescript
async onPreSettingUpdate(context: ISettingUpdateContext, configurationModify: IConfigurationModify, read: IRead, http: IHttp): Promise<ISetting>
```
{% endcode %}

We have now taken a look at the various states of an app and the methods that represent them. With these methods, you can perform different actions for the states of the apps. In the next section, we will go through some of the app configuration settings when your app is ready to launch.
