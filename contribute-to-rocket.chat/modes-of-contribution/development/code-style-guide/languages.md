# Languages

[Vscode](https://code.visualstudio.com/) is the most used and recommended text editor for the Rocket.Chat codebase. Together with the [Prettier plugin](https://code.visualstudio.com/), we have a set of rules defined in the codebase for best formatting.

Specific language configurations are in the [.editorconfig](https://github.com/RocketChat/Rocket.Chat/blob/develop/.editorconfig).

{% hint style="info" %}
We provide a [prettier config](https://github.com/RocketChat/Rocket.Chat/blob/develop/.prettierrc) and [eslint config](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.eslintrc) in our repos, so as long as those plugins are installed on your editor, code style will be automatically followed
{% endhint %}

## TypeScript

The eslint takes charge of formatting all the javascript and typescript code.&#x20;

The Rocket.Chat codebase has migrated to using only typescript `.ts` files.

Convention for Typescript, React and Components are specified in the Fuselage Conventions page.

{% content-ref url="../../../../fuselage/conventions.md" %}
[conventions.md](../../../../fuselage/conventions.md)
{% endcontent-ref %}

## Go

Any Go related piece of code should be formatted with the [gofmt](https://pkg.go.dev/cmd/gofmt) formatter.

## Shell Script

Any Shell related piece of code should be formatted with the [shfmt](https://github.com/mvdan/sh) formatter.
