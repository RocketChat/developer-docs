# Languages

To maintain consistency and readability across the project, Rocket.Chat has established specific coding conventions and formatting rules. This guide provides a brief overview of these guidelines, focusing on the use of different languages and formatting tools in the Rocket.Chat codebase.

Rocket.Chat primarily uses [Visual Studio Code ](https://code.visualstudio.com/)(VSCode) as its text editor of choice due to its wide usage and versatility. To ensure uniformity in code formatting, Rocket.Chat employs the [Prettier plugin](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode). As long as you use it, the code style will be automatically adhered to Rocket.Chat standards. Specific language configurations are in the [.editorconfig](https://github.com/RocketChat/Rocket.Chat/blob/develop/.editorconfig).

{% hint style="info" %}
We provide a [prettier config](https://github.com/RocketChat/Rocket.Chat/blob/develop/.prettierrc) and [eslint config](https://github.com/RocketChat/Rocket.Chat/blob/develop/apps/meteor/.eslintrc) in our repos, so as long as those plugins are installed on your editor, code style will be automatically followed
{% endhint %}

_**TypeScript**_: ESLint is responsible for formatting all JavaScript and TypeScript code. Rocket.Chat has transitioned to using only TypeScript (`.ts`) files in its codebase. Conventions for TypeScript, React, and Components are specified in the Fuselage [conventions.md](../../../fuselage/conventions.md "mention"), ensuring that all contributors follow the same standards.

**Go**: For code written in Go, the the [gofmt](https://pkg.go.dev/cmd/gofmt) formatter should be used to ensure proper formatting.&#x20;

**Shell Script**: For Shell-related code, the [shfmt](https://github.com/mvdan/sh) formatter should be used.&#x20;

These formatters help maintain a consistent style across different languages used in the Rocket.Chat codebase.

Contributing to Rocket.Chat involves more than just writing code; it's about adhering to established conventions and maintaining a consistent style across the project. By using tools like VSCode, Prettier, ESLint, gofmt, and shfmt, developers can ensure their contributions align with the existing codebase. This consistency not only makes the code easier to read and understand but also facilitates collaboration among contributors from around the world. Happy coding!

{% hint style="info" %}
For a comprehensive understanding of Rocket.Chat's coding conventions and style, refer to and [code-style-guide.md](code-style-guide.md "mention").
{% endhint %}
