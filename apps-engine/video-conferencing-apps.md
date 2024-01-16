# Video Conferencing Apps

Rocket.Chat provides flexibility and control over your video conferencing capabilities with apps in the marketplace, such as [**Jitsi**](https://www.rocket.chat/apps/jitsi-meet)**,** [**BigBlueButton**](https://www.rocket.chat/apps/bigbluebutton)**,** [**Pexip**](https://www.rocket.chat/apps/pexip)**,** and [**Google Meet**](https://www.rocket.chat/apps/google-meet). You can integrate with a video conferencing provider of your choice and according to your organizational needs.

You can also configure video conferencing options for your app using the Apps-Engine event interfaces provided for video conferencing. In this topic, we will consider the Jitsi Meet app for Rocket.Chat as an example to understand how you can implement the video conferencing functionality.

{% hint style="info" %}
Here, we are only going through the `IVideoConfProvider` interface methods that are implemented in the Jitsi app. Refer to the complete Jitsi app code files [here](https://github.com/RocketChat/Apps.Jitsi).
{% endhint %}

In the [`videoConfProvider.ts`](https://github.com/RocketChat/Apps.Jitsi/blob/master/src/videoConfProvider.ts) file, the TypeScript class `JitsiProvider` is defined which implements the [`IVideoConfProvider`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/videoConfProviders\_IVideoConfProvider.IVideoConfProvider.html) interface from the Apps-Engine definition. This class serves as the provider for integrating the Rocket.Chat app with the Jitsi video conferencing service. Let's break down its key functionalities:

* **Configuration settings**

Various settings are defined as follows, including the Jitsi domain, title prefix, suffix, Chrome extension ID, token settings, and the Jitsi app ID and secret:

{% code title="videoConfProvider.ts" %}
```typescript
export class JitsiProvider implements IVideoConfProvider {
	public domain = 'meet.jit.si';
	public titlePrefix = 'RocketChat';
	public titleSuffix = '';
	public ssl = true;
	public chromeExtensionId = '';
	public name = 'Jitsi';
	public useToken = false;
	public jitsiAppId = '';
	public jitsiAppSecret = '';
	public limitTokenToRoom = false;
	public tokenAuditor = '';
	public tokenExpiration = '';
```
{% endcode %}

We also have the following [`capabilities`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/videoConfProviders\_IVideoConfProvider.IVideoConfProvider.html#capabilities) property that indicates whether the microphone, camera, and title are enabled:

{% code title="videoConfProvider.ts" %}
```typescript
public capabilities = {
    mic: true,
    cam: true,
    title: true,
};
```
{% endcode %}

* **Constructor**

The following constructor takes an instance of the [`JitsiApp`](https://github.com/RocketChat/Apps.Jitsi/blob/master/src/JitsiApp.ts) class as a parameter, indicating that the `JitsiProvider` is associated with a specific instance of the Rocket.Chat app.

{% code title="videoConfProvider.ts" %}
```typescript
constructor(private readonly app: JitsiApp) {}
```
{% endcode %}

* **Verify configuration settings**

Next, in this code file, we are using the following [`isFullyConfigured`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/videoConfProviders\_IVideoConfProvider.IVideoConfProvider.html#isFullyConfigured) method to check the configuration of the integration by verifying the Jitsi domain. Also, if token authentication is enabled, it checks for the Jitsi application ID and secret:

{% code title="videoConfProvider.ts" %}
```typescript
public async isFullyConfigured(): Promise<boolean> {
	if (!this.domain) {
		return false;  }
	if (this.useToken) {
		return Boolean(this.jitsiAppId && this.jitsiAppSecret);
	}
	return true;
}
```
{% endcode %}

* **Generate URL**

The following [`generateUrl`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/videoConfProviders\_IVideoConfProvider.IVideoConfProvider.html#generateUrl) method generates the URL for joining a Jitsi conference room. It includes the protocol and domain from the configuration settings. The room identifier is retrieved from the  [`getRoomIdentification`](https://github.com/RocketChat/Apps.Jitsi/blob/8c06f5102961c6808eaea66c2a454fb3bc7a8638/src/videoConfProvider.ts#L57) method.

{% code title="videoConfProvider.ts" %}
```typescript
public async generateUrl(call: VideoConfData): Promise<string> {
	const protocol = this.ssl ? 'https' : 'http';
	const name = this.getRoomIdentification(call);
	return `${protocol}://${this.domain}/${name}`;
}
```
{% endcode %}

* **Customize URL**

To customize the Jitsi meeting room URL, additional settings are configured in this section of the code. It includes the Chrome extension ID, the custom title of the call or the default title, audio/video settings, and token generation. All these configurations are combined, and the URL string is generated.

This method uses the [`IVideoConferenceOptions`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/videoConfProviders\_IVideoConferenceOptions.IVideoConferenceOptions.html) interface to configure the audio/video properties and the [`IVideoConferenceUser`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/videoConferences\_IVideoConferenceUser.IVideoConferenceUser.html) interface to get the user details.

{% code title="videoConfProvider.ts" overflow="wrap" lineNumbers="true" fullWidth="true" %}
```typescript
public async customizeUrl(call: VideoConfDataExtended, user: IVideoConferenceUser, options: IVideoConferenceOptions): Promise<string> {
	const configs: string[] = [];
	//Chrome extension ID
	if (this.chromeExtensionId) {
		configs.push(`config.desktopSharingChromeExtId=${encodeURIComponent(`"${this.chromeExtensionId}"`)}`);
	}
	//Call title - custom or default
	const title = call.providerData?.customCallTitle || call.title;
	if (title) {		
		configs.push(`config.callDisplayName=${encodeURIComponent(`"${title}"`)}`);
	}
	//Audio and video options
	if (options.mic !== undefined) {
		configs.push(`config.startWithAudioMuted=${options.mic ? 'false' : 'true'}`);
	}
	if (options.cam !== undefined) {
		configs.push(`config.startWithVideoMuted=${options.cam ? 'false' : 'true'}`);
	}
	//Token generation
	const token = await this.generateToken(call, user);

	// If it's not using a generated token, include extra settings openly
	if (!token) {
		if (user) {
			configs.push(`userInfo.displayName=${encodeURIComponent(`"${user.name}"`)}`);
		}
	}
	if (user) {
		configs.push(`config.prejoinPageEnabled=false`);
		configs.push(`config.prejoinConfig.enabled=false`);
	}
	//Combine the above configurations and generate URL
	const configHash = configs.join('&');
	const tokenParam = token ? `?jwt=${token}` : '';
	const url = `${call.url}${tokenParam}#${configHash}`;

	return url;
}
```
{% endcode %}

The `videoConfProvider.ts` file is imported into the main [`JitsiApp.ts`](https://github.com/RocketChat/Apps.Jitsi/blob/master/src/JitsiApp.ts) file to integrate the video conference configuration. This is an example of how you can use the video conference event interfaces to implement this feature in your app.

You can also refer to the [Big Blue Button app code](https://github.com/RocketChat/Apps.BigBlueButton) for another example of a video conferencing app.
