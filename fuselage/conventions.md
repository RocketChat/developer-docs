# Conventions

The code conventions for Rocket.Chat provides guidelines for writing clear, concise, and consistent code. By following these guidelines, you can write code that is easy to read, understand, and maintain.

### TypeScript General Tips

1. **Don't use CommonJS features**

Avoid utilizing CommonJS features such as the `require` function and the `module` object alongside ES module constructs like `import` and `export`. Our preference lies with ES modules due to their enhanced portability and user-friendly nature. However, it's worth noting that unlike CommonJS, synchronous conditional imports aren't feasible in ES modules.

```tsx
// commonjs.ts

// It works
if (condition) {
  const foo = require('foo');
  module.exports = foo;
} else {
  module.exports = {};
}
```

```tsx
// esmodule.ts

// This is invalid and will not compile
if (condition) {
  import foo from 'foo';
  export default foo;
} else {
  export default {};
}
```

2. **Prefer `import type` over `import`**

Prioritize using `import type` over the standard `import` statement. While the regular `import` works for both JavaScript and TypeScript and has runtime implications, it can lead to the inclusion of module output code (either the original JavaScript or the transpiled TypeScript) in the bundle. This behavior might not be desired in certain cases. However, the `import type` construct is specific to TypeScript compilation and helps avoid unnecessary inclusion of code in the bundle.

```tsx
// Foo.ts
export class Foo {
  bar: string;

  constructor(bar: string) {
    this.bar = bar;
  }
}
```

```tsx
// Bar.ts
export class Bar {
  foo: Foo;

  constructor(foo: Foo) {
    this.foo = foo;
  }
}
```

```tsx
// index.ts
import { Foo } from './Foo';
import type { Bar } from './Bar';

declare const foo: Foo;
declare const bar: Bar;
```

```tsx
// index.js (transpiled from index.ts)
import { Foo } from './Foo';
```

3. **Know the difference between `type` and `interface`**

The `interface` construct in TypeScript bears resemblance to the class `construct` in JavaScript, with a key distinction: an `interface` serves as a type declaration, while a `class` functions as a class declaration.

```tsx
interface IThing {
  prop: string;
  method(): void;
}

class Thing implements IThing {
  public prop = 'foo';

  method(): void {
    console.log('bar');
  }
}
```

The `type` construct is a TypeScript construct similar to the `interface` construct.

```tsx
type IThing = {
  prop: string;
  method(): void;
};

class Thing implements IThing {
  public prop = 'foo';

  method(): void {
    console.log('bar');
  }
}
```

Nonetheless, the `type` construct offers greater flexibility compared to the `interface` construct. For instance, the `type` construct permits the declaration of union types, as demonstrated by:

```typescript
type Foo = string | number;
```

While [`interface` was indeed lighter for TypeScript Compiler (tsc](https://ncjamieson.com/prefer-interfaces/)), it remains beneficial to employ `type` when not dealing with a class. Moreover, they exhibit differences in handling generic types. For instance, the `interface` construct enables the declaration of a generic type:

```typescript
interface IFoo<T> {
  prop: T;
}
```

However, the `type` construct also supports this, and when combined with conditional types, it can radically reshape the entire type structure:

```typescript
type Foo<T> = T extends string
  ? { foo: number; }
  : { bar: number; };
```

This versatility empowers the `type` construct to offer a more adaptable approach than the `interface` construct.

4. **Avoid using classes as namespaces**.&#x20;

Refrain from utilizing this pattern:

```typescript
// foo.ts
class Foo {
  bar(): void {
    // ...ts
  }
}

export const foo = new Foo();

// index.ts
import { foo } from './foo';

foo.bar();
```

When the `foo` singleton functions as a mere namespace housing functions and variables, opt for the following approach using the module itself as the singleton:

```typescript
// foo.ts
export function bar(): void {
  // ...
}

// index.ts
import * as foo from './foo';

foo.bar();
```

The sole valid scenario for employing a class as a namespace is when you need to manage state within the singleton:

```typescript
// foo.ts
class Foo {
  baz: number;
  bar(): void {
    // ... perform actions referencing and modifying `this.baz`
  }
}

export const foo = new Foo();

// index.ts
import { foo } from './foo';

foo.bar();
```

In this context, using a class is reasonable because it provides an effective abstraction for encapsulating state and offering a controlled interface for modifying it.

5. **Avoid using the `any` type except when it's used as a constraint.**

Refrain from using `any` under most circumstances. Instead, adhere to this model:

* `unknown` serves as the universal type, encompassing all potential values.
* `any` should not be seen as an actual type, but rather as a means to disable TypeScript's type checking.

Using `any` is discouraged as it indicates a lack of awareness regarding the type of value being manipulated and implies indifference toward type safety. In contrast, working with `unknown` necessitates type narrowing, leading to more robust code.

For instance, consider these scenarios:

```typescript
// Avoid using any
declare const foo: any;

foo.bar(); // No compilation error

// Prefer using unknown
declare const bar: unknown;

bar.baz(); // Compilation error

const hasBaz = (bar: unknown): bar is { baz(): void } => 
  typeof bar === 'object' && bar !== null && 'baz' in bar && (typeof (bar as { baz: unknown }).baz === 'function')

if (hasBaz(bar)) {
  bar.baz(); // No compilation error
}
```

A \n important exception to this rule is when you're dealing with a generic type constraint like a function:

```tsx
type X<F> = F extends (x: unknown) => void ? true : false;
type Y<F> = F extends (x: any) => void ? true : false;

type A = X<(x: string) => void>; // `false`, because x is not `unknown`
type B = Y<(x: string) => void>; // `true`, because x is anything
```

### Migrating from JavaScript

**TypeScript is a superset of JavaScript**

TypeScript is an extension of JavaScript, meaning that when transitioning from JavaScript to TypeScript, you can employ the identical syntax used in JavaScript. It's worth noting that a significant portion of the errors flagged by tools like TypeScript Compiler (tsc) and eslint are intended to ensure adherence to best practices. However, some of these errors can be overlooked or ignored, especially when they don't hinder the functionality of your code.&#x20;

**JSDoc**

When the `allowJs` option is enabled in the tsconfig.json configuration file, you can harness the power of JSDoc comments to document types within your JavaScript code. This proves especially valuable during the gradual transition from JavaScript to TypeScript, particularly when TypeScript Compiler (tsc) struggles to deduce types accurately. Take the following JavaScript code as an example:

```javascript
// module.js
/**
 * @typedef {Object} Foo
 * @property {string} bar
 * @property {string} qux
 */
export const foo = {
  bar: 'baz'
};

foo.qux = 'quux';
```

Here, tsc would initially infer the type of `foo` as `{ bar: string }`, inadvertently ignoring the `qux` property. To rectify this, you can introduce a JSDoc comment to explicitly define the type, enabling TypeScript to grasp the full structure.

Alternatively, you can use the `@type` tag along with a syntax resembling TypeScript's `type` construct:

```javascript
// module.js
/**
 * @type {{ bar: string; qux: string }}
 */
export const foo = {
  bar: 'baz'
};

foo.qux = 'quux';
```

Both approaches aid in bridging the gap between JavaScript and TypeScript, ensuring that the types are accurately documented and recognized by the TypeScript compiler.

**Declare a `*.d.ts` file**

It's strongly advised to create a _.d.ts file as a starting point when migrating significant JavaScript modules to TypeScript. Although this transition can be complex, having a dedicated declaration file (_.d.ts) for your module is crucial. TypeScript utilizes these files to manage imports and exports, essentially serving as the "interface of a module."

A module's large size might indicate the need for decomposition into smaller, more manageable modules. Crafting a \*.d.ts file simplifies the planning process and enhances your understanding of the module's structure, surpassing the utility of JSDoc comments. As a result, this approach is highly recommended for commencing the conversion of JavaScript modules to TypeScript.

Here's an example of a \*.d.ts file for a hypothetical module:

```tsx
// hugeModule.d.ts
export function foo(): void; // maybe it will be placed in another module
export function bar(): void; // maybe it will be placed in another module
```

### React

{% hint style="info" %}
Most of the recommendations here are based on [Alex Kondov's Tao of React](https://alexkondov.com/tao-of-react/).
{% endhint %}

#### Components

1. **Prefer functional components**

React initially introduced class components to leverage JavaScript class syntax for managing state and component lifecycles. However, class components have significant drawbacks:

* They tend to be verbose.
* They often involve a misuse of the inheritance mechanism through extends and super.

Hooks were introduced to provide an alternative approach to declaring state and effects. They maintain the core concept of the component's render function without the need for classes, streamlining the development process.

2. **Declare one component per file**

While [colocation](https://kentcdodds.com/blog/colocation) is a commendable concept, it's not consistently followed for React components within a single file. The main reason is that we've noticed people misusing this approach before. It might start with something as straightforward as adding a basic modal component alongside a page component, but it can quickly lead to a confusing jumble of components that becomes difficult to manage.

3. **Name components**

Failing to name a component is a common mistake that can lead to prolonged debugging efforts. It results in less informative error stacks and challenges while navigating components in React Dev Tools. There are two approaches to properly name a component:

* By writing a non-anonymous function:

```tsx
const Foo = () => {
  return <div>Foo</div>;
};

console.log('The component name is:', Foo.name);
```

* By using the `displayName` property:

```tsx
const Foo = memo(() => {
  return <div>Foo</div>;
});

Foo.displayName = 'Foo'; // `Foo.name` is `undefined`

console.log('The component name is:', Foo.displayName);
```

3. **Use default export at the end of file**

While named exports are often preferred, using default export enhances code readability, especially when dealing with Higher Order Components (HOCs) like `memo` and `forwardRef`, and it aligns neatly with code splitting using `lazy`.

```tsx
// Component.tsx

import { memo } from 'react';

type ComponentProps = {
  name: string;
};

// It is NOT a anonymous function
const Component = (props: ComponentProps) => {
  return <div>Hello, {props.name}</div>;
};

export default memo(Component); // the component name is preserved
```

```tsx
// index.ts

import { lazy } from 'react';

const Component = lazy(() => import('./Component'));
```

The same example based on named exports is less readable:

```tsx
// Component.tsx

import { memo } from 'react';

type ComponentProps = {
  name: string;
};

// It is a anonymous function
export const Component = memo((props: ComponentProps) => {
  return <div>Hello, {props.name}</div>;
});

Component.displayName = 'Component'; // needed for React Dev Tools
```

```tsx
// index.ts

import { lazy } from 'react';

const Component = lazy(async () => {
  const { Component } = await import('./Component');
  return { default: Component }; // you need to reconstruct the default export
});
```

4. **Extract helper functions**

A drawback associated with the adoption of React Hooks is the tendency for individuals to define helper functions within the component. This is facilitated by the fact that there is no requirement to pass arguments; instead, variables from the encompassing scope can be directly accessed and used.

```tsx
const Component = () => {
  const value = useMyHook();

  const isValueOK = () => value === 'OK';

  return isValueOK() ? <>OK</> : null;
};
```

Typically, effective helper functions adhere to the principle of being  [pure](https://en.wikipedia.org/wiki/Pure\_function), which makes them simpler to debug. However, when you bind variables into the helper's scope, you're making it impure. Furthermore, with each rendering cycle, the function value gets redefined. While this process is efficient in terms of CPU and memory usage, it can lead to scenarios where you must rely on techniques like `useCallback` to prevent unnecessary re-renders of child components that receive your helper function as a prop.

Here's the ideal case:

```tsx
const isValueOK = (value) => value === 'OK';

const Component = () => {
  const value = useMyHook();

  return isValueOK(value) ? <>OK</> : null;
};
```
