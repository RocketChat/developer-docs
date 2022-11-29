# Palettes

When setting up colors for components, the palette system from fuselage should be used. Palettes offer an easy and semantic way to implement colors using tokens.&#x20;

Tokens work like fuselage components, in the way that only the component itself needs to be updated, not the whole implementation on Rocket.Chat.

The Palette system will also enable the creation of themes, as each theme can have its implementation of the palette (for example a dark theme will have the same groups and tokens, only differing in the value of the tokens).

### How to use colors from Fuselage's Palettes?

Like other components, Palettes can be imported from the Fuselage package.

```
import { Palette } from '@rocket.chat/fuselage';
```

Then is just a simple as accessing the tokens from the groups in \`Palette\`

```
const example = Palette.GroupName['TokenName']

const SurfaceHoverColor = Palette.surface['surface-hover']

const StrokeColor = Palette.stroke['stroke-extra-light']
```

Now the Palette system should handle any changes to the colors in fuselage and deal with changes done by the active theme automatically.
