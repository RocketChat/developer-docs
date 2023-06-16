# Conventions

### TypeScript

#### General tips

**Don't use CommonJS features**

The `require` function and the `module` object are CommonJS features, and should not be mixed with ES modules constructs like `import` and `export`. We prefer ES modules because they are more portable and easier to use. The drawback is that you cannot do "synchronous conditional imports" as you can in CommonJS:

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

**Prefer `import type` over `import`**

The `import` statement is common to both JavaScript and TypeScript, and it's relevant during runtime. If your code is being bundled, the imported module output code (the original JavaScript one or the one transpiled from TypeScript) will end up in the bundle. This is not what you want sometimes. However, `import type` is only available in TypeScript compilation.

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

**Know the difference between `type` and `interface`**

The `interface` construct is a TypeScript construct that is similar to the `class` construct in JavaScript. The difference is that `interface` is a type declaration, and `class` is a class declaration.

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

However, the `type` construct is less restrictive than the `interface` construct. For example, the `type` construct allows you to declare a union type:

```tsx
type Foo = string | number;
```

Despite the fact [`interface` was lighter weight for `tsc`](https://ncjamieson.com/prefer-interfaces/), it's still a good idea to use `type` when you're not dealing with a class. They also are different when generic types are involved. For example, the `interface` construct allows you to declare a generic type:

```tsx
interface IFoo<T> {
  prop: T;
}
```

But `type` allows it too and, combined with conditional types, can make the whole type structure change:

```tsx
type Foo<T> = T extends string
  ? { foo: number; }
  : { bar: number; };
```

This makes it possible to use the `type` construct in a more flexible way than the `interface` construct.

**Don't use classes as namespaces**

Absolutely don't do this:

```tsx
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

if the `foo` singleton is just a namespace holding functions and variables. Instead, consider using the module as the singleton:

```tsx
// foo.ts
export function bar(): void {
  // ...
}

// index.ts
import * as foo from './foo';

foo.bar();
```

The **only** valid use case for using a class as a namespace is when you want to hold state inside the singleton:

```tsx
// foo.ts
class Foo {
  baz: number;
t
  bar(): void {
    // ... do stuff referencing and mutating `this.baz`
  }
}

export const foo = new Foo();

// index.ts
import { foo } from './foo';

foo.bar();
```

It makes sense here because a class is the perfect abstraction for encapsulating state and exposing a restricted interface to mutate it.

**Don't use `any`. Ever. (Unless it's in a constraint)**

The mental model to follow here should be:

* `unknown` is the universal type, representing all possible values.
* `any` is not really a type, but a mechanism to express that `tsc` should not perform any type checking.

Using `any` is a bad practice as it implies that you are not aware of the type of the value you're dealing with **and that you don't care**. At least `unknown` requires type narrowing, which is a good thing.

```tsx
declare const foo: any;

foo.bar(); // no compilation error

declare const bar: unknown;

bar.baz(); // compilation error

const hasBaz = (bar: unknown): bar is { baz(): void } => // type guard
  typeof bar === 'object' && bar !== null && 'baz' in bar && (typeof (bar as { baz: unknown }).baz === 'function')

if (hasBaz(bar)) {
  bar.baz(); // no compilation error
}
```

The notable exception to this rule is when you're dealing with a generic type constraint like a function:

```tsx
type X<F> = F extends (x: unknown) => void ? true : false;
type Y<F> = F extends (x: any) => void ? true : false;

type A = X<(x: string) => void>; // `false`, because x is not `unknown`
type B = Y<(x: string) => void>; // `true`, because x is anything
```

#### Migrating from JavaScript

**TypeScript is a superset of JavaScript**

When migrating from JavaScript to TypeScript, you can use the same syntax as JavaScript. Mostly of the errors from `tsc` and `eslint` are there just to make sure you are doing the right thing and can be ignored. As someone suggested on the internet, "just massage the code until you make it work".

**JSDoc**

If `allowJs` is set to `true` in the `tsconfig.json` file, you can use JSDoc comments to document types on your JavaScript code, which is particularly useful when you are migrating from JavaScript to TypeScript in stages and `tsc` is not able to infer types. Consider the following JavaScript code:

```tsx
export const foo = {
  bar: 'baz'
};

foo.qux = 'quux';
```

`tsc` will infer the type of `foo` to be `{ bar: string }` and ignore the `qux` property. To fix this, you can add the following JSDoc comment to the `module.js` file:

```tsx
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

Alternatively, you can use `@type` and a syntax closer to the `type` construct in TypeScript:

```tsx
/**
 * @type {{ bar: string; qux: string }}
 */
export const foo = {
  bar: 'baz'
};

foo.qux = 'quux';
```

**At least try to declare a `*.d.ts` file**

We know that migrating huge JavaScript modules to TypeScript is a hassle. However, it's also a good idea to have a `*.d.ts` file for your module. This file is used by TypeScript to resolve imports and exports, as they are the "interface of a module". Sometimes the size of a module is code smell, indicating that it's better to split it into smaller modules. Writing a `*.d.ts` file makes it easier to plan and to understand the structure of your module than inserting JSDoc comments, therefore it's the recommended way start converting your JavaScript modules to TypeScript.

```tsx
// hugeModule.d.ts
export function foo(): void; // maybe it will be placed in another module
export function bar(): void; // maybe it will be placed in another module
```

### React

> Most of the recommendations here are based on [Alex Kondov's Tao of React](https://alexkondov.com/tao-of-react/).

#### Components

**Prefer functional components**

Class components were introduced in React to take advantage of the syntactic sugar of JavaScript classes for representing state and effects tied to the component lifecycle. The two major drawbacks of class components are:

* they are verbose;
* they misuse the inheritance mechanism of `extends` and `super`.

Hooks introduced a new way to declare state and effects whilst still addressing that the core of a component is the render function without the inconvenience of having to use classes.

**Declare one component per file**

[Colocation](https://kentcdodds.com/blog/colocation) is a great concept, but we don't apply it when it comes to React components in a single file. There are several reasons for this, but the most important one is that we have seen people abusing it in the past. It can start with a simple modal component as companion of a page component and ending up in a mess of components.

**Name components**

Not naming a component is a common mistake that leads to longer debugging time: the error stack becomes not very helpful and traversing components on React Dev Tools is a pain.

There two ways to name a component:

1.  writing a non-anonymous function:

    ```tsx
    const Foo = () => {
      return <div>Foo</div>;
    };

    console.log('The component name is:', Foo.name);
    ```
2.  using the `displayName` property:

    ```tsx
    const Foo = memo(() => {
      return <div>Foo</div>;
    });

    Foo.displayName = 'Foo'; // `Foo.name` is `undefined`

    console.log('The component name is:', Foo.displayName);
    ```

**Use default export (at the bottom of the file)**

It follows from the previous rule as modules only declare one component that it can be exported as default. Most of time we prefer using named exports, but provides a more readable code when using HOCs like `memo` and `forwardRef` and it ties nicely to `lazy`.

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

**Extract helper functions**

One perceived downside to the introduction of React Hooks is that people often tend to declare helper functions inside the component because you don't need to pass arguments, just hold variables from the scope above:

```tsx
const Component = () => {
  const value = useMyHook();

  const isValueOK = () => value === 'OK';

  return isValueOK() ? <>OK</> : null;
};
```

Usually, good helper functions are [pure](https://en.wikipedia.org/wiki/Pure\_function) (therefore easier to debug) and by binding variables into the helper's scope, you're making it impure. Additionally, each rendering redeclares the function value, which is cheap in terms of CPU/memory, but at the same time you may find yourself in the situation of depending of `useCallback` and other techniques to avoid re-rendering child components receiving your helper as a prop.

Here's the ideal case:

```tsx
const isValueOK = (value) => value === 'OK';

const Component = () => {
  const value = useMyHook();

  return isValueOK(value) ? <>OK</> : null;
};
```
