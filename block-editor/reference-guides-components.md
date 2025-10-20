---
url: https://developer.wordpress.org/block-editor/reference-guides/components
scraped_at: 2025-10-20T03:54:15.230Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/components/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Component Reference


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)Component Reference

Search

# Component Reference

## In this article

Table of Contents

- [Installation](https://developer.wordpress.org/block-editor/reference-guides/components/#installation)
- [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/#usage)
  - [Popovers](https://developer.wordpress.org/block-editor/reference-guides/components/#popovers)
  - [TypeScript](https://developer.wordpress.org/block-editor/reference-guides/components/#typescript)
- [Docs & examples](https://developer.wordpress.org/block-editor/reference-guides/components/#docs-examples)
- [Contributing to this package](https://developer.wordpress.org/block-editor/reference-guides/components/#contributing-to-this-package)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/components/#wp--skip-link--target)

This package includes a library of generic WordPress components to be used for creating common UI elements shared between screens and features of the WordPress dashboard.

## [Installation](https://developer.wordpress.org/block-editor/reference-guides/components/\#installation)

```bash
npm install @wordpress/components --save

```

_This package assumes that your code will run in an **ES2015+** environment. If you’re using an environment that has limited or no support for such language features and APIs, you should include [the polyfill shipped in `@wordpress/babel-preset-default`](https://github.com/WordPress/gutenberg/tree/HEAD/packages/babel-preset-default#polyfill) in your code._

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/components/\#usage)

Within Gutenberg, these components can be accessed by importing from the `components` root directory:

```jsx
/**
 * WordPress dependencies
 */
import { Button } from '@wordpress/components';

export default function MyButton() {
    return <Button>Click Me!</Button>;
}

```

Many components include CSS to add styles, which you will need to load in order for them to appear correctly. Within WordPress, add the `wp-components` stylesheet as a dependency of your plugin’s stylesheet. See [wp\_enqueue\_style documentation](https://developer.wordpress.org/reference/functions/wp_enqueue_style/#parameters) for how to specify dependencies.

In non-WordPress projects, link to the `build-style/style.css` file directly, it is located at `node_modules/@wordpress/components/build-style/style.css`.

### [Popovers](https://developer.wordpress.org/block-editor/reference-guides/components/\#popovers)

By default, the `Popover` component will render within an extra element appended to the body of the document.

If you want to precisely control where the popovers render, you will need to use the `Popover.Slot` component.

The following example illustrates how you can wrap a component using a

`Popover` and have those popovers render to a single location in the DOM.

```jsx
/**
 * External dependencies
 */
import { Popover, SlotFillProvider } from '@wordpress/components';

/**
 * Internal dependencies
 */
import { MyComponentWithPopover } from './my-component';

const Example = () => {
    <SlotFillProvider>
        <MyComponentWithPopover />
        <Popover.Slot />
    </SlotFillProvider>;
};

```

### [TypeScript](https://developer.wordpress.org/block-editor/reference-guides/components/\#typescript)

This package exposes its own types for the components it exports, however it doesn’t export its own types for component props. If you need to extract the props type, please use `React.ComponentProps` to get the types from the element.

```tsx
import type { ComponentProps } from 'react';
import { Button } from '@wordpress/components';

export default function MyButton( props: ComponentProps< typeof Button > ) {
    return <Button { ...props }>Click Me!</Button>;
}

```

## [Docs & examples](https://developer.wordpress.org/block-editor/reference-guides/components/\#docs-examples)

You can browse the components docs and examples at [https://wordpress.github.io/gutenberg/](https://wordpress.github.io/gutenberg/)

## [Contributing to this package](https://developer.wordpress.org/block-editor/reference-guides/components/\#contributing-to-this-package)

This is an individual package that’s part of the Gutenberg project. The project is organized as a monorepo. It’s made up of multiple self-contained software packages, each with a specific purpose. The packages in this monorepo are published to [npm](https://www.npmjs.com/) and used by [WordPress](https://make.wordpress.org/core/) as well as other software projects.

To find out more about contributing to this package or Gutenberg as a whole, please read the project’s main [contributor guide](https://github.com/WordPress/gutenberg/tree/HEAD/CONTRIBUTING.md).

This package also has its own [contributing information](https://github.com/WordPress/gutenberg/tree/HEAD/packages/components/CONTRIBUTING.md) where you can find additional details.

First published

March 9, 2021

Last updated

January 6, 2025

Edit article

[Improve it on GitHub: Component Reference](https://github.com/WordPress/gutenberg/edit/trunk/packages/components/README.md)

[PreviousAvailable Styles OptionsPrevious: Available Styles Options](https://developer.wordpress.org/block-editor/reference-guides/theme-json-reference/styles-versions/)

[NextBaseFieldNext: BaseField](https://developer.wordpress.org/block-editor/reference-guides/components/base-field/)

Notifications