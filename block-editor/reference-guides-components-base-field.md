---
url: https://developer.wordpress.org/block-editor/reference-guides/components/base-field
scraped_at: 2025-10-20T03:23:22.661Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

BaseField


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)BaseField

Search

# BaseField

## In this article

Table of Contents

- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/#usage)
- [Props](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/#props)
  - [disabled: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/#disabled-boolean)
  - [hasError: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/#haserror-boolean)
  - [isInline: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/#isinline-boolean)
  - [isSubtle: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/#issubtle-boolean)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/#wp--skip-link--target)

This feature is still experimental. “Experimental” means this is an early implementation subject to drastic and breaking changes.

`BaseField` is an internal (i.e., not exported in the `index.js`) primitive component used for building more complex fields like `TextField`. It provides error handling and focus styles for field components. It does _not_ handle layout of the component aside from wrapping the field in a `Flex` wrapper.

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/\#usage)

`BaseField` is primarily used as a hook rather than a component:

```js
function useExampleField( props ) {
    const { as = 'input', ...baseProps } = useBaseField( props );

    const inputProps = {
        as,
        // more cool stuff here
    };

    return { inputProps, ...baseProps };
}

function ExampleField( props, forwardRef ) {
    const { preFix, affix, disabled, inputProps, ...baseProps } =
        useExampleField( props );

    return (
        <View { ...baseProps } disabled={ disabled }>
            { preFix }
            <View autocomplete="off" { ...inputProps } disabled={ disabled } />
            { affix }
        </View>
    );
}

```

## [Props](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/\#props)

### [disabled: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/\#disabled-boolean)

Whether the field is disabled.

- Required: No

### [hasError: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/\#haserror-boolean)

Renders an error style around the component.

- Required: No
- Default: `false`

### [isInline: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/\#isinline-boolean)

Renders a component that can be inlined in some text.

- Required: No
- Default: `false`

### [isSubtle: boolean](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/\#issubtle-boolean)

Renders a subtle variant of the component.

- Required: No
- Default: `false`

First published

May 28, 2021

Last updated

February 9, 2023

Edit article

[Improve it on GitHub: BaseField](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/src/base-field/README.md)

[PreviousComponent ReferencePrevious: Component Reference](https://developer.wordpress.org/block-editor/reference-guides/components/)

[NextAlignmentMatrixControlNext: AlignmentMatrixControl](https://developer.wordpress.org/block-editor/reference-guides/components/alignment-matrix-control/)

Notifications