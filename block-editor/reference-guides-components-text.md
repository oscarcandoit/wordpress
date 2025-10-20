---
url: https://developer.wordpress.org/block-editor/reference-guides/components/text
scraped_at: 2025-10-20T03:20:05.787Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/text/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Text


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)Text

Search

# Text

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/text/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/text/#props)
  - [adjustLineHeightForInnerControls](https://developer.wordpress.org/block-editor/reference-guides/components/text/#adjustlineheightforinnercontrols)
  - [align](https://developer.wordpress.org/block-editor/reference-guides/components/text/#align)
  - [color](https://developer.wordpress.org/block-editor/reference-guides/components/text/#color)
  - [display](https://developer.wordpress.org/block-editor/reference-guides/components/text/#display)
  - [ellipsis](https://developer.wordpress.org/block-editor/reference-guides/components/text/#ellipsis)
  - [ellipsizeMode](https://developer.wordpress.org/block-editor/reference-guides/components/text/#ellipsizemode)
  - [highlightCaseSensitive](https://developer.wordpress.org/block-editor/reference-guides/components/text/#highlightcasesensitive)
  - [highlightEscape](https://developer.wordpress.org/block-editor/reference-guides/components/text/#highlightescape)
  - [highlightSanitize](https://developer.wordpress.org/block-editor/reference-guides/components/text/#highlightsanitize)
  - [highlightWords](https://developer.wordpress.org/block-editor/reference-guides/components/text/#highlightwords)
  - [isBlock](https://developer.wordpress.org/block-editor/reference-guides/components/text/#isblock)
  - [isDestructive](https://developer.wordpress.org/block-editor/reference-guides/components/text/#isdestructive)
  - [limit](https://developer.wordpress.org/block-editor/reference-guides/components/text/#limit)
  - [lineHeight](https://developer.wordpress.org/block-editor/reference-guides/components/text/#lineheight)
  - [numberOfLines](https://developer.wordpress.org/block-editor/reference-guides/components/text/#numberoflines)
  - [optimizeReadabilityFor](https://developer.wordpress.org/block-editor/reference-guides/components/text/#optimizereadabilityfor)
  - [size](https://developer.wordpress.org/block-editor/reference-guides/components/text/#size)
  - [truncate](https://developer.wordpress.org/block-editor/reference-guides/components/text/#truncate)
  - [upperCase](https://developer.wordpress.org/block-editor/reference-guides/components/text/#uppercase)
  - [variant](https://developer.wordpress.org/block-editor/reference-guides/components/text/#variant)
  - [weight](https://developer.wordpress.org/block-editor/reference-guides/components/text/#weight)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/text/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`Text` is a core component that renders text in the library, using the library’s typography system.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#usage)

`Text` can be used to render any text-content, like an HTML `p` or `span`.

```jsx
import { __experimentalText as Text } from '@wordpress/components';

function Example() {
    return <Text>Code is Poetry</Text>;
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#props)

### [adjustLineHeightForInnerControls](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#adjustlineheightforinnercontrols)

**Type**: `"large"`, `"medium"`, `"small"`, `"xSmall"`

Automatically calculate the appropriate line-height value for contents that render text and Control elements (e.g. `TextInput`).

```jsx
import { __experimentalText as Text, TextInput } from '@wordpress/components';

function Example() {
    return (
        <Text adjustLineHeightForInnerControls={"small"}>
            Lorem ipsum dolor sit amet, consectetur
            <TextInput value="adipiscing elit..." />
        </Text>
    );
}

```

### [align](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#align)

**Type**: `CSSProperties['textAlign']`

Adjusts the text alignment.

```jsx
import { __experimentalText as Text } from '@wordpress/components';

function Example() {
    return (
        <Text align="center" isBlock>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit...
        </Text>
    );
}

```

### [color](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#color)

**Type**: `CSSProperties['color']`

Adjusts the text color.

### [display](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#display)

**Type**: `CSSProperties['display']`

Adjusts the CSS display.

### [ellipsis](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#ellipsis)

**Type**: `string`

The ellipsis string when `truncate` is set.

### [ellipsizeMode](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#ellipsizemode)

**Type**: `"auto"`, `"head"`, `"tail"`, `"middle"`

Determines where to truncate. For example, we can truncate text right in the middle. To do this, we need to set `ellipsizeMode` to `middle` and a text `limit`.

- `auto`: Trims content at the end automatically without a `limit`.
- `head`: Trims content at the beginning. Requires a `limit`.
- `middle`: Trims content in the middle. Requires a `limit`.
- `tail`: Trims content at the end. Requires a `limit`.

### [highlightCaseSensitive](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#highlightcasesensitive)

**Type**: `boolean`

Escape characters in `highlightWords` which are meaningful in regular expressions.

### [highlightEscape](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#highlightescape)

**Type**: `boolean`

Determines if `highlightWords` should be case sensitive.

### [highlightSanitize](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#highlightsanitize)

**Type**: `boolean`

Array of search words. String search terms are automatically cast to RegExps unless `highlightEscape` is true.

### [highlightWords](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#highlightwords)

**Type**: `any[]`

Letters or words within `Text` can be highlighted using `highlightWords`.

```jsx
import { __experimentalText as Text } from '@wordpress/components';

function Example() {
    return (
        <Text highlightWords={ [ 'pi' ] }>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ex
            neque, vulputate a diam et, luctus convallis lacus. Vestibulum ac
            mollis mi. Morbi id elementum massa. Suspendisse interdum auctor
            ligula eget cursus. In fermentum ultricies mauris, pharetra
            fermentum erat pellentesque id.
        </Text>
    );
}

```

### [isBlock](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#isblock)

**Type**: `boolean`

Sets `Text` to have `display: block`.

Note: text truncation only works when `isBlock` is `false`.

### [isDestructive](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#isdestructive)

**Type**: `boolean`

Renders a destructive color.

### [limit](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#limit)

**Type**: `number`

Determines the max characters when `truncate` is set.

### [lineHeight](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#lineheight)

**Type**: `CSSProperties['lineHeight']`

Adjusts all text line-height based on the typography system.

### [numberOfLines](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#numberoflines)

**Type**: `number`

Clamps the text content to the specific `numberOfLines`, adding the `ellipsis` at the end.

### [optimizeReadabilityFor](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#optimizereadabilityfor)

**Type**: `CSSProperties['color']`

The `Text` color can be adapted to a background color for optimal readability. `optimizeReadabilityFor` can accept CSS variables, in addition to standard CSS color values (e.g. Hex, RGB, HSL, etc…).

```jsx
import { __experimentalText as Text, View } from '@wordpress/components';

function Example() {
    const backgroundColor = 'blue';

    return (
        <View css={ { backgroundColor } }>
            <Text optimizeReadabilityFor={ backgroundColor }>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            </Text>
        </View>
    );
}

```

### [size](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#size)

**Type**: `CSSProperties['fontSize']`, `TextSize`

Adjusts text size based on the typography system. `Text` can render a wide range of font sizes, which are automatically calculated and adapted to the typography system. The `size` value can be a system preset, a `number`, or a custom unit value ( `string`) such as `30em`.

```jsx
import { __experimentalText as Text } from '@wordpress/components';

function Example() {
    return <Text size="largeTitle">Code is Poetry</Text>;
}

```

### [truncate](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#truncate)

**Type**: `boolean`

Enables text truncation. When `truncate` is set, we are able to truncate the long text in a variety of ways.

Note: text truncation won’t work if the `isBlock` property is set to `true`

```jsx
import { __experimentalText as Text } from '@wordpress/components';

function Example() {
    return (
        <Text truncate>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ex
            neque, vulputate a diam et, luctus convallis lacus. Vestibulum ac
            mollis mi. Morbi id elementum massa. Suspendisse interdum auctor
            ligula eget cursus. In fermentum ultricies mauris, pharetra
            fermentum erat pellentesque id.
        </Text>
    );
}

```

### [upperCase](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#uppercase)

**Type**: `boolean`

Uppercases the text content.

### [variant](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#variant)

**Type**: `"muted"`

Adjusts style variation of the text.

```jsx
import { __experimentalText as Text } from '@wordpress/components';

function Example() {
    return <Text variant="muted">Code is Poetry</Text>;
}

```

### [weight](https://developer.wordpress.org/block-editor/reference-guides/components/text/\#weight)

**Type**: `CSSProperties['fontWeight']`, `TextWeight`

Adjusts font-weight of the text.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Text](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/text/README.md)

[PreviousTextHighlightPrevious: TextHighlight](https://developer.wordpress.org/block-editor/reference-guides/components/text-highlight/)

[NextTextareaControlNext: TextareaControl](https://developer.wordpress.org/block-editor/reference-guides/components/textarea-control/)

Notifications