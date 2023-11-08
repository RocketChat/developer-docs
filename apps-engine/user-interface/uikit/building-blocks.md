# Building Blocks

Here is the list of objects, block elements, and blocks you can use to create interactions for your apps.

## Objects

### Text object

<table><thead><tr><th width="142">Field</th><th width="142">Type</th><th width="143">Required?</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>String</td><td>Yes</td><td>The type of text object that you want to add. The available values are <code>plain_text</code> and <code>mrkdwn</code>.</td></tr><tr><td>text</td><td>String</td><td>Yes</td><td>The actual text.</td></tr><tr><td>emoji</td><td>Boolean</td><td>No</td><td>Works with the <code>plain_text</code> type.</td></tr></tbody></table>

**Example**

```typescript
{
  type: 'plain_text',
  text: 'lorem ipsum 🚀',
  emoji: true,
}
```

### Option object

<table><thead><tr><th width="138">Field</th><th width="152">Type</th><th width="131">Required?</th><th>Description</th></tr></thead><tbody><tr><td>text</td><td>Object</td><td>Yes</td><td>The text that is to be displayed on the menu. The value can either be <code>plain_text</code> or <code>mrkdwn</code>.</td></tr><tr><td>value</td><td>String</td><td>Yes</td><td>The actual value that the option represents.</td></tr></tbody></table>

#### Example

```typescript
{
  value: 'option_1',
  text: {
      type: 'plain_text',
      text: 'lorem ipsum 🚀',
      emoji: true,
    }
}
```

## Block elements

### button

<table><thead><tr><th width="139">Field</th><th width="123">Type</th><th width="122">Required?</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block element, in this case,<code>button</code>.</td></tr><tr><td>text</td><td>Object</td><td>Yes</td><td>The text that is to be displayed on the menu. The value can either be <code>plain_text</code> or <code>mrkdwn</code>.</td></tr><tr><td>value</td><td>String</td><td>No</td><td>A value sent along with the button information when an action is made upon the element.</td></tr><tr><td>url</td><td>String</td><td>No</td><td>A URL that the button points to.</td></tr><tr><td>style</td><td>String</td><td>No</td><td>The style of the button. The value can either be <code>primary</code> or <code>danger</code>.</td></tr><tr><td>actionId</td><td>String</td><td>Yes</td><td>A unique identifier for an action made upon the element.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'button',
  text: {
      type: 'plain_text',
      text: 'danger❗',
      emoji: true,
    },
  actionId: 'button_1_danger',
  style: 'danger',
}
```

### image

<table><thead><tr><th width="127">Field</th><th width="121">Type</th><th width="126">Required?</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block element, in this case, <code>image</code>.</td></tr><tr><td>imageUrl</td><td>String</td><td>Yes</td><td>The URL of the image.</td></tr><tr><td>altText</td><td>String</td><td>Yes</td><td>The text describing the image being displayed.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'image',
  imageUrl: 'https://picsum.photos/200/300',
  altText: 'An image',
}
```

### overflow menu

<table><thead><tr><th width="147">Field</th><th width="125">Type</th><th width="124">Required?</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block element, in this case, <code>overflow</code>.</td></tr><tr><td>options</td><td>Array</td><td>Yes</td><td>An array with the possible options (the <code>options</code> object).</td></tr><tr><td>actionId</td><td>String</td><td>Yes</td><td>A unique identifier for an action made upon the element.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'overflow',
  actionId: 'overflow_1',
  options: [
    {
      value: 'option_1',
      text: {
          type: 'plain_text',
          text: 'lorem ipsum 🚀',
          emoji: true,
        }
    },
    {
      value: 'option_2',
      text: {
          type: 'plain_text',
          text: 'lorem ipsum 🚀',
          emoji: true,
        }
    },
  ],
}
```

### plain text input

<table><thead><tr><th width="159">Field</th><th width="126">Type</th><th width="124">Required?</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block element, in this case, <code>plain_text_input</code>.</td></tr><tr><td>actionId</td><td>String</td><td>Yes</td><td>A unique identifier for an action made upon the element.</td></tr><tr><td>placeholder</td><td>Object</td><td>Yes</td><td>A placeholder text for the input (<code>plain text</code> object).</td></tr><tr><td>initialValue</td><td>String</td><td>No</td><td>The initial value of the field.</td></tr><tr><td>multiline</td><td>Boolean</td><td>No</td><td>A flag that indicates whether the field should be a single line (default) or a larger text area.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'plain_text_input',
  actionId: 'plain_text_input_1',
  placeholder: {
      type: 'plain_text',
      text: 'Enter name',
      emoji: true,
    },
  initialValue: 'John Doe',
  multiline: false,
}
```

### static select menu

<table><thead><tr><th width="160">Field</th><th width="129">Type</th><th width="124">Required?</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block element, in this case, <code>static_select</code>.</td></tr><tr><td>actionId</td><td>String</td><td>Yes</td><td>A unique identifier for an action made upon the element.</td></tr><tr><td>placeholder</td><td>Object</td><td>Yes</td><td>A placeholder text for the input (<code>plain text</code> object).</td></tr><tr><td>initialValue</td><td>String</td><td>No</td><td>The initial value selected (<code>value</code> field from the <code>options</code> object).</td></tr><tr><td>options</td><td>Array</td><td>Yes</td><td>An array with the possible options (the <code>options</code> object).</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'static_select',
  actionId: 'overflow_1',
  initialValue: 'option_2',
  options: [
    {
      value: 'option_1',
      text: {
          type: 'plain_text',
          text: 'lorem ipsum 🚀',
          emoji: true,
        }
    },
    {
      value: 'option_2',
      text: {
          type: 'plain_text',
          text: 'lorem ipsum 🚀',
          emoji: true,
        }
    },
  ],
  placeholder: {
      type: 'plain_text',
      text: 'Select an item',
    },
}
```

### multi-static select menu

<table><thead><tr><th width="166">Field</th><th width="165">Type</th><th width="124">Required?</th><th>Description</th></tr></thead><tbody><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block element, in this case, <code>multi_static_select</code>.</td></tr><tr><td>actionId</td><td>String</td><td>Yes</td><td>A unique identifier for an action made upon the element.</td></tr><tr><td>placeholder</td><td>Object</td><td>Yes</td><td>A placeholder text for the input (<code>plain text</code> object).</td></tr><tr><td>initialValue</td><td>Array of strings</td><td>No</td><td>The initial values selected (<code>value</code> field from the <code>options</code> object).</td></tr><tr><td>options</td><td>Array</td><td>Yes</td><td>An array with the possible options (the <code>options</code> object).</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'multi_static_select',
  actionId: 'overflow_1',
  initialValue: ['option_1' ,'option_2'],
  options: [
    {
      value: 'option_1',
      text: {
          type: 'plain_text',
          text: 'lorem ipsum 🚀',
          emoji: true,
        }
    },
    {
      value: 'option_2',
      text: {
          type: 'plain_text',
          text: 'lorem ipsum 🚀',
          emoji: true,
        }
    },
  ],
  placeholder: {
      type: 'plain_text',
      text: 'Select an item',
    },
}
```

## Blocks

### section

<table><thead><tr><th width="153">Field</th><th width="121">Type</th><th width="125">Required?</th><th>Description</th></tr></thead><tbody><tr><td>blockId</td><td>String</td><td>No</td><td>A unique identifier for the block.</td></tr><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block, in this case,  <code>section</code>.</td></tr><tr><td>text</td><td>Object</td><td>Yes</td><td>The text that is to be displayed on the button. The value can either be <code>plain_text</code> or <code>mrkdwn</code>.</td></tr><tr><td>accessory</td><td>Object</td><td>No</td><td>One element that can be a <code>button element</code>, an <code>image element</code>, or an <code>overflow menu</code>.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'section',
  blockId: 'section_1',
  text: {
      type: 'plain_text',
      text: 'lorem ipsum 🚀',
      emoji: true,
    }
  accessory: { /* one of the accessory elements */ } ,
}
```

{% hint style="info" %}
Notice how the section block and the button element are used in the [Contextual Bar](opening-the-contextual-bar.md) app.
{% endhint %}

### divider

<table><thead><tr><th width="134">Field</th><th width="124">Type</th><th width="124">Required?</th><th>Description</th></tr></thead><tbody><tr><td>blockId</td><td>String</td><td>No</td><td>A unique identifier for the block.</td></tr><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block, in this case, <code>divider</code>.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'divider',
  blockId: 'divider_1',
}
```

### image

<table><thead><tr><th width="158">Field</th><th width="133">Type</th><th width="129">Required?</th><th>Description</th></tr></thead><tbody><tr><td>blockId</td><td>String</td><td>No</td><td>A unique identifier for the block.</td></tr><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block, in this case, <code>image</code>.</td></tr><tr><td>imageUrl</td><td>String</td><td>Yes</td><td>The URL of the image.</td></tr><tr><td>altText</td><td>String</td><td>Yes</td><td>A text describing the image being displayed.</td></tr><tr><td>title</td><td>Object</td><td>No</td><td>The text to be displayed as the image's title. The value can either be <code>plain_text</code> or <code>mrkdwn</code>.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'image',
  blockId: 'image_1',
  imageUrl: 'https://picsum.photos/200/300',
  altText: 'An image',
  title: {
      type: 'plain_text',
      text: 'lorem ipsum 🚀',
      emoji: true,
    }
}
```

### actions

<table><thead><tr><th width="155">Field</th><th width="116">Type</th><th width="121">Required?</th><th>Description</th></tr></thead><tbody><tr><td>blockId</td><td>String</td><td>No</td><td>A unique identifier for the block.</td></tr><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block, in this case, <code>actions</code>.</td></tr><tr><td>elements</td><td>Array</td><td>Yes</td><td>A list of interactive block elements.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'actions',
  blockId: 'actions_1',
  elements: [ /* block elements */ ]
}
```

### context

<table><thead><tr><th width="143">Field</th><th width="129">Type</th><th width="133">Required?</th><th>Description</th></tr></thead><tbody><tr><td>blockId</td><td>String</td><td>No</td><td>A unique identifier for the block.</td></tr><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block, in this case, <code>context</code>.</td></tr><tr><td>elements</td><td>Array</td><td>Yes</td><td>A list of block elements. Allowed elements are <code>plain text object</code> and <code>image element</code>.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'context',
  blockId: 'context_1',
  elements: [ /* block elements */ ]
}
```

### input

<table><thead><tr><th width="138">Field</th><th width="124">Type</th><th width="131">Required?</th><th>Description</th></tr></thead><tbody><tr><td>blockId</td><td>String</td><td>No</td><td>A unique identifier for the block.</td></tr><tr><td>type</td><td>String</td><td>Yes</td><td>The type of the block, in this case, <code>input</code>.</td></tr><tr><td>element</td><td>Array</td><td>Yes</td><td>The input element, that can be <code>plain text input</code>, <code>static select menu</code>, and <code>multi static select menu</code>.</td></tr></tbody></table>

#### Example

```typescript
{
  type: 'input',
  blockId: 'input_1',
  element: { /* input element */ }
}
```

Now that we've seen the different building blocks that can be used for our apps, let's take a look at how to use buttons to initiate a set of actions in the next section.
