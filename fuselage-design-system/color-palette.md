# Color Palette

When setting up colors for components, the palette system from fuselage must be used. The Palette system offers an easy and semantic way to implement colors using tokens.&#x20;

Tokens work like fuselage components, in the way that only the component itself needs to be updated, not the whole implementation on Rocket.Chat.

The Palette system will also enable the creation of themes, as each theme can have its implementation of the palette (for example a dark theme will have the same groups and tokens, only differing in the value of the tokens).



### How to use the Palette system

#### On Box component:

```jsx
<Box bg='status-background-info' color='status-font-on-info' />
```

In order to ease and minimize wrong usage of tokens, there's a shortcut that adds automatically the correct prefixes:&#x20;

when using **surface** tokens on `bg` and **font** tokens on `color` you can omit the _surface-_ and _font-_ prefixes (preferred way):

```jsx
<Box bg='neutral' color='default' />
```

But you can also use the long term:

```jsx
<Box bg='surface-neutral' color='font-default' />
```



#### On Rocket.chat and/or Fuselage - React components:

Like other components, the Palette can be imported from the Fuselage's package.

```jsx
import { Palette } from '@rocket.chat/fuselage';
```

Then is just a simple as accessing the tokens from the groups in \`Palette\`

```jsx
const example = Palette.GroupName['TokenName']

const SurfaceHoverColor = Palette.surface['surface-hover']

const StrokeColor = Palette.stroke['stroke-extra-light']
```

Now the Palette system should handle any changes to the colors in fuselage and deal with changes done by the active theme automatically.



#### On Fuselage .scss files:

If you are styling on a .scss file inside fuselage, you can use the tokens as shown below:

```scss
@use '/packages/fuselage/src/styles/colors.scss'; // relative path

.example {
    color: colors.font(titles-labels);
    background-color: colors.surface(neutral);
    border: 1px solid colors.stroke(extra-light);
};
```



_See theme() function - WIP_
