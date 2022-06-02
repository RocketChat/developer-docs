# Languages

[Vscode](https://code.visualstudio.com/) is the most used and recommended text editor for the Rocket.Chat codebase. Together with the [Prettier plugin](https://code.visualstudio.com/), we have a set of rules defined in the codebase for best formatting.

Specific language configurations are in the [.editorconfig](https://github.com/RocketChat/Rocket.Chat/blob/develop/.editorconfig).

{% hint style="info" %}
We provide a [prettier config](https://github.com/RocketChat/Rocket.Chat/blob/develop/.prettierrc) and [eslint config](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.eslintrc) in our repos, so as long as those plugins are installed on your editor, code style will be automatically followed&#x20;
{% endhint %}

## JavaScript

The eslint take charge of formatting all the javascript code. The Rocket.Chat codebase has migrated to using only typescript `.ts` files.

Convention for React and Components are specified in the fuselage wiki.

{% embed url="https://github.com/RocketChat/fuselage/wiki/Conventions#react" %}

## TypeScript

The typescript convention is described in the fuselage Wiki

{% embed url="https://github.com/RocketChat/fuselage/wiki/Conventions#typescript" %}

## Go

Any Go related piece of code should be formatted with the [gofmt](https://pkg.go.dev/cmd/gofmt) formatter.

## Shell Script

Any Shell related piece of code should be formatted with the [shfmt](https://github.com/mvdan/sh) formatter.
