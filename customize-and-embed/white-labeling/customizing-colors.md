---
description: Ensure your Rocket.Chat workspace has a unique color palette.
---

# Customizing Colors

{% hint style="info" %}
Customizing colors are applicable from Rocket.Chat `v 6.0`
{% endhint %}

One of the key aspects of white-labeling your Rocket.Chat workspace is the ability to customize colors. This feature allows you to ensure that your Rocket.Chat workspace aligns with your brand's color palette, further enhancing the sense of brand consistency and identity.

Rocket.Chat provides a comprehensive list of color variables that you can adjust to match your brand's color scheme. These variables control various workspace elements, including stroke colors, surface colors, font colors, status colors, shadow colors, and button colors.

Colors are customizable through the custom CSS field in the admin panel. Go to **Administration** > **Workspace** > **Settings** > **Layout** > **Custom CSS**.

## **Token name**

```css
button-background-primary-default
```

## **Token anatomy**

* `button`: UI elements it's responsible for.
* `background`: part of this UI element.
* `primary`: type of UI element.
* `default`: state of this UI element.

## **Overwrite existing variables**

Append `!important` if you want to overwrite existing CSS fields. This is due to the [CSS specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) rules. For details, refer to [!important](https://developer.mozilla.org/en-US/docs/Web/CSS/important).&#x20;

```css
.rcx-sidebar--main {
  --rcx-color-surface-sidebar: #5c030c !important;
}
```

## **Variable list**

```css
.rcx-content--main {
--rcx-color-stroke-extra-light: #2F343D;
--rcx-color-stroke-light: #333842;
--rcx-color-stroke-medium: #404754;
--rcx-color-stroke-dark: #9EA2A8;
--rcx-color-stroke-extra-dark: #CBCED1;
--rcx-color-stroke-extra-light-highlight: #87CBFC;
--rcx-color-stroke-highlight: #3976D1;
--rcx-color-stroke-extra-light-error: #F49AA6;
--rcx-color-stroke-error: #BB3E4E;
--rcx-color-surface-light: #262931;
--rcx-color-surface-tint: #1F2329;
--rcx-color-surface-room: #1F2329;
--rcx-color-surface-neutral: #2D3039;
--rcx-color-surface-disabled: #24272E;
--rcx-color-surface-hover: #1A1E23;
--rcx-color-surface-selected: #3C3F44;
--rcx-color-surface-dark: #E4E7EA;
--rcx-color-font-white: #2F343D;
--rcx-color-font-disabled: #3E4146;
--rcx-color-font-hint: #9EA2A8;
--rcx-color-font-secondary-info: #9EA2A8;
--rcx-color-font-default: #E4E7EA;
--rcx-color-font-titles-labels: #F2F3F5;
--rcx-color-font-info: #739EDE;
--rcx-color-font-danger: #CF6E7A;
--rcx-color-status-background-info: #A8C3EB;
--rcx-color-status-background-success: #C1EBDD;
--rcx-color-status-background-warning: #FEEFBE;
--rcx-color-status-background-warning-2: #4E4731;
--rcx-color-status-background-danger: #FFBDC5;
--rcx-color-status-background-service-1: #FCE3CF;
--rcx-color-status-font-on-info: #739EDE;
--rcx-color-status-font-on-success: #58AD90;
--rcx-color-status-font-on-warning: #C7AA66;
--rcx-color-status-font-on-warning-2: #FFFFFF;
--rcx-color-status-font-on-danger: #D88892;
--rcx-color-status-font-on-service-1: #CA9163;
--rcx-color-status-font-on-service-2 : #C393D2;
--rcx-color-badge-background-level-1: #484C51;
--rcx-color-badge-background-level-2: #3070CF;
--rcx-color-badge-background-level-3: #A9642D;
--rcx-color-badge-background-level-4: #BB3E4E;
--rcx-color-shadow-elevation-1: rgba(9, 9, 9, 0.35);
--rcx-color-shadow-elevation-2x: rgba(9, 9, 9, 0.3);
--rcx-color-shadow-elevation-2y: rgba(9, 9, 9, 0.45);
--rcx-color-button-background-primary-default: #3976D1;
--rcx-color-button-background-primary-hover: #295EAE;
--rcx-color-button-background-primary-press: #245399;
--rcx-color-button-background-primary-focus: #3976D1;
--rcx-color-button-background-primary-keyfocus: #3976D1;
--rcx-color-button-background-primary-disabled: #1D3963;
--rcx-color-button-background-secondary-default: #2F343D;
--rcx-color-button-background-secondary-hover: #3A404B;
--rcx-color-button-background-secondary-press: #454C59;
--rcx-color-button-background-secondary-focus: #2F343D;
--rcx-color-button-background-secondary-keyfocus: #2F343D;
--rcx-color-button-background-secondary-disabled: #2F343D;
--rcx-color-button-background-secondary-danger-default: #2F343D;
--rcx-color-button-background-secondary-danger-hover: #3A404B;
--rcx-color-button-background-secondary-danger-press: #454C59;
--rcx-color-button-background-secondary-danger-focus: #2F343D;
--rcx-color-button-background-secondary-danger-keyfocus: #2F343D;
--rcx-color-button-background-secondary-danger-disabled: #2F343D;
--rcx-color-button-background-danger-default: #BB3E4E;
--rcx-color-button-background-danger-hover: #95323F;
--rcx-color-button-background-danger-press: #822C37;
--rcx-color-button-background-danger-focus: #BB3E4E;
--rcx-color-button-background-danger-keyfocus: #BB3E4E;
--rcx-color-button-background-danger-disabled: #3D2126;
--rcx-color-button-background-success-default: #1D7256;
--rcx-color-button-background-success-hover: #175943;
--rcx-color-button-background-success-press: #134937;
--rcx-color-button-background-success-focus: #1D7256;
--rcx-color-button-background-success-keyfocus: #1D7256;
--rcx-color-button-background-success-disabled: #1E4B40;
--rcx-color-button-font-on-secondary: #E4E7EA;
--rcx-color-button-font-on-secondary-danger: #C14454;
--rcx-color-button-font-on-success: #FFFFFF;
--rcx-color-button-font-on-primary-disabled: #6C727A;
--rcx-color-button-font-on-secondary-disabled: #6C727A;
--rcx-color-button-font-on-secondary-danger-disabled: #613339;
--rcx-color-button-font-on-danger-disabled: #757575;
--rcx-color-button-font-on-success-disabled: #757575;
}
.rcx-sidebar--main {
--rcx-color-stroke-medium: #324677;
--rcx-color-surface-tint: #262931;
--rcx-color-surface-hover: #1B1D22;
--rcx-color-surface-selected: #31363F;
--rcx-color-button-background-secondary-default: #0D0F11;
--rcx-color-button-background-secondary-press: #2C313A;
--rcx-color-button-background-secondary-focus: #0D0F11;
--rcx-color-user-presence-online: #1CBF89;
--rcx-color-user-presence-busy: #C14454;
--rcx-color-user-presence-away: #AC892F;
--rcx-color-user-presence-offline: #6C727A;
--rcx-color-button-icon-disabled-color: #6C727A;
}
```

By adjusting the color variables, you can ensure that your Rocket.Chat workspace aligns perfectly with your brand identity, providing a consistent and engaging user experience.
