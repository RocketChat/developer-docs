# Accessibility

Some best practices for code thinking about a11y

In general, we encourage our team while developing to make sure that all focusable elements are accessible through tab navigation. There are a few elements that are focusable by default:&#x20;

* Buttons
* Inputs
* Links

### Working with Forms

Currently, we use `react-hook-form` library together with your visual components to help us build our forms on Rocket.Chat. But in order to achieve a good experience beyond visuals we should have some practices in mind to build accessible forms.

#### Labeling an input correctly

One of the most common issues of a11y is not adding the proper label for an input. In order to add a label to the input, make sure to use `for` attribute to connect them.

```tsx
// All React Components mentioned are part of fuselage
<form >
    <Field>
        <FieldLabel htmlFor='myInputId'>My Label</FieldLabel>
        <FieldRow>
            <TextInput id='myInputId' />
        </FieldRow>
    </Field>
</form>
```

In huge applications, it is hard to maintain unique IDs with strings, so you can use `useUniqueId` provided from `@rocket.chat/fuselage-hooks` to generate unique IDs and use them on your inputs

#### Adding a description to the input

Some inputs are not clear about what information should be entered or its necessary to give more information about it. Visually it's not enough, we have to tell screen readers that information as well, so we can take advantage of `aria-describedby` to add that.

```tsx
// All React Components mentioned are part of fuselage
<form >
    <Field>
        <FieldLabel htmlFor='myInputId'>My Label</FieldLabel>
        <FieldRow>
            <TextInput id='myInputId' aria-describedby='myInputId-hint'>
        </FieldRow>
        <FieldHint id='myInputId-hint'>This information is super important to be found by screen readers</FieldHint>
    </Field>
</form>
```

#### Making an input required

Some inputs are not clear about what information should be entered or its necessary to give more information about it. Visually it's not enough, we have to tell screen readers that information as well, so we can take advantage of `aria-describedby` to add that.

```tsx
// All React Components mentioned are part of fuselage
<form >
    <Field>
        <FieldLabel htmlFor='myInputId'>My Label</FieldLabel>
        <FieldRow>
            <TextInput id='myInputId' aria-describedby='myInputId-hint'>
        </FieldRow>
        <FieldHint id='myInputId-hint'>This information is super important to be found by screen readers</FieldHint>
    </Field>
</form>
```

#### Adding validation

```tsx
// Consider all components as part of fuselage package
// Controller is provided by react-hook-form
import { Controller } from 'react-hook-form' 
import { TextInput } from @rocket.chat/fuselage

<form >
    <TextInput />
</form>
```

### Testing

We already use Playwright to run visual testing and we encourage you to add some a11y violation testing as well
