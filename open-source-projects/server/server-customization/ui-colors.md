# UI Colors

In Rocket.Chat, you can customize colors by adjusting [layout settings](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/layout) in workspace administration. Developers are encouraged to use defined variables in their work instead of hard coding colors. This allows site owners to change the color scheme with consistent results.&#x20;

{% hint style="info" %}
See the [theme variables file](https://github.com/RocketChat/Rocket.Chat/tree/develop/apps/meteor/app/theme/client/imports/general) for the currently available color settings.&#x20;
{% endhint %}

These settings are accessible as variables in `Less files`, provided the files were compiled using the `addPackageAsset` method of `rocketchat-theme`.

## Color Scheme

The Rocket.Chat color scheme comprises three sets of color settings:  [Alpha](ui-colors.md#alpha-colors), [Major](ui-colors.md#major-colors), and [Minor](ui-colors.md#minor-colors) Colors. Additional variations are created in Less but aren't exposed to settings. The naming of these settings isn't tied to specific components; instead, they reflect a visual hierarchy that promotes consistent color use in new components and theme development.

### Alpha Colors

Semi-transparent black or white used in components to add shading or tinting to the background color. This is useful for denoting selected or disabled states. The use of these semi-transparent colors allows site owners to easily change color scheme without defining variations for every component state individually.

* transparent-dark
* transparent-darker
* transparent-light
* transparent-lighter

#### Alpha Colors Example

![Alpha colors example colors](../../../.gitbook/assets/alpha-colors.png)

### Major Colors

The primary palette of the app.&#x20;

{% hint style="info" %}
Contributions and modifications to components should make use of these colors.
{% endhint %}

* content-background-color **#FFFFFF**
* primary-background-color **#04436A**
* primary-font-color **#444444**
* primary-action-color **#1d74f5**
* secondary-background-color **#F4F4F4**
* secondary-font-color **#A0A0A0**
* secondary-action-color **#DDDDDD**
* component-color **#f2f3f5**
* success-color **#4dff4d**
* pending-color **#FCB316**
* error-color **#BC2031**
* selection-color **#02ACEC**
* attention-color **#9C27B0**

### Minor Colors

Minor colors designated for specific use cases will inherently derive their properties from the major colors as the default behavior. However, administrators seeking more intricate management of the color scheme can opt to utilize these minor colors.

* tertiary-background-color _defaults to component-color_
* tertiary-font-color _defaults to transparent-light_
* link-font-color _defaults to primary-action-color_
* info-font-color _defaults to secondary-font-color_
* custom-scrollbar-color _defaults to transparent-dark_
* status-online _defaults to success-color_
* status-away _defaults to pending-color_
* status-busy _defaults to error-color_
* status-offline _defaults to transparent-darker_

### Dark UI

Computed colors enable owners to select a dark user interface (UI) with appropriate contrast. For instance, in a light UI, the disabled state might darken an element, while in a dark UI, it should lighten. This is achieved through mixins that blend the color with the background's contrast, rather than using darkening or lightening functions.&#x20;

{% hint style="success" %}
See [this example](https://codepen.io/owlandfox/pen/EyJROO) of form input states that dynamically contrast to both dark and light backgrounds.
{% endhint %}

Developers are advised to incorporate mixins and computed colors in their contributions, instead of hard-coding variations. This ensures a consistent balance and contrast of colors, irrespective of how the scheme settings may be changed by owners.

## Default Colors

These examples show the implementation of the default color scheme with the main components of the Rocket.Chat UI.

### Side Nav

![Side nav example colors](../../../.gitbook/assets/side-nav.png)

### Account Box

![Account Box example colors](../../../.gitbook/assets/account-box.png)

### Flex Nav

![Flex nav example colors](../../../.gitbook/assets/flex-nav.png)

### Message Box

![Message box example colors](../../../.gitbook/assets/message-box.png)

### Settings Page

![Settings page example colors](../../../.gitbook/assets/settings-page.png)

{% hint style="info" %}
The user interface (UI) is currently undergoing active development. Component refactoring is anticipated to alter and, optimistically, enhance the use of colors. The immediate objective is to centralize the application of colors and styles, laying the groundwork for the subsequent creation of a unified style guide for Rocket.Chat.
{% endhint %}
