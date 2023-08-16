# Color Palette

When establishing color schemes for components, it's essential to leverage Fuselage's palette system. This system provides a straightforward and meaningful approach to integrating colors through **tokens**. **Tokens** function similarly to [Fuselage components](componentization.md), allowing updates to be made solely within the component, rather than requiring changes across the entire Rocket.Chat implementation. Additionally, the palette system facilitates the creation of diverse themes, as each theme can possess its palette implementation. For instance, a dark theme can share the same token groups while differing in token values, enabling versatile and consistent theming.

### How to use the Palette System

**On Box component**

```jsx
<Box bg='status-background-info' color='status-font-on-info' />
```

To enhance simplicity and mitigate the risk of token misuse, a convenient shortcut exists that automatically applies the appropriate prefixes. When using surface tokens with the `bg` prop and font tokens with the `color` prop, you have the option to exclude the `surface-` and `font-` prefixes.&#x20;

```jsx
<Box bg='neutral' color='default' />
```

Alternatively, you can use the longer form:

```jsx
<Box bg='surface-neutral' color='font-default' />
```

**In Rocket.Chat and/or Fuselage - React Components**

Similar to other components, you can import the Palette from the Fuselage package using:

```jsx
import { Palette } from '@rocket.chat/fuselage';
```

Accessing tokens from the `Palette` becomes straightforward. For instance:

```jsx
const SurfaceHoverColor = Palette.surface['surface-hover'];
const StrokeColor = Palette.stroke['stroke-extra-light'];
```

By using the Palette system, any color modifications within Fuselage are automatically managed. This system also seamlessly adapts to changes introduced by the active theme, providing a streamlined and automated approach to color management.

#### On Fuselage .scss files

When working within a .scss file within the Fuselage package, you can seamlessly integrate tokens into your styles using the following approach:

```scss
@use '/packages/fuselage/src/styles/colors.scss'; // Use relative path

.example {
    color: colors.font(titles-labels);
    background-color: colors.surface(neutral);
    border: 1px solid colors.stroke(extra-light);
}
```

By incorporating the tokens provided by the `colors.scss` file, you can easily apply color styles to your components and ensure consistency with Fuselage's color palette.
