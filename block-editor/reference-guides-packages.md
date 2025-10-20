---
url: https://developer.wordpress.org/block-editor/reference-guides/packages
scraped_at: 2025-10-20T03:54:09.277Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/packages/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Package Reference


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)Package Reference

Search

# Package Reference

## In this article

Table of Contents

- [Using the packages via WordPress global](https://developer.wordpress.org/block-editor/reference-guides/packages/#using-the-packages-via-wordpress-global)
- [Using the packages via npm](https://developer.wordpress.org/block-editor/reference-guides/packages/#using-the-packages-via-npm)
- [Testing JavaScript code from a specific major WordPress version](https://developer.wordpress.org/block-editor/reference-guides/packages/#testing-javascript-code-from-a-specific-major-wordpress-version)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/packages/#wp--skip-link--target)

WordPress exposes a list of JavaScript packages and tools for WordPress development.

## [Using the packages via WordPress global](https://developer.wordpress.org/block-editor/reference-guides/packages/\#using-the-packages-via-wordpress-global)

JavaScript packages are available as a registered script in WordPress and can be accessed using the `wp` global variable.

If you wanted to use the `PlainText` component from the block editor module, first you would specify `wp-block-editor` as a dependency when you enqueue your script:

```php
wp_enqueue_script(
    'my-custom-block',
    plugins_url( $block_path, __FILE__ ),
    array( 'react', 'wp-blocks', 'wp-block-editor', 'wp-i18n' )
);

```

After the dependency is declared, you can access the module in your JavaScript code using the global `wp` like so:

```js
const { PlainText } = wp.blockEditor;

```

## [Using the packages via npm](https://developer.wordpress.org/block-editor/reference-guides/packages/\#using-the-packages-via-npm)

All the packages are also available on [npm](https://www.npmjs.com/org/wordpress) if you want to bundle them in your code.

Using the same `PlainText` example, you would install the block editor module with npm:

```bash
npm install @wordpress/block-editor --save

```

Once installed, you can access the component in your code using:

```js
import { PlainText } from '@wordpress/block-editor';

```

## [Testing JavaScript code from a specific major WordPress version](https://developer.wordpress.org/block-editor/reference-guides/packages/\#testing-javascript-code-from-a-specific-major-wordpress-version)

There is a way to quickly install a version of the individual WordPress package used with a given WordPress major version using [npm distribution tags](https://docs.npmjs.com/cli/v8/commands/npm-dist-tag) (example for WordPress `5.8.x`):

```bash
npm install @wordpress/block-editor@wp-5.8

```

It’s also possible to update all existing WordPress packages in the project with a single command:

```bash
npx @wordpress/scripts packages-update --dist-tag=wp-5.8

```

All major WordPress versions starting from `5.7.x` are supported (e.g., `wp-5.7` or `wp-6.0`). Each individual dist-tag always points to the latest bug fix release for that major version line.

First published

March 9, 2021

Last updated

July 8, 2025

Edit article

[Improve it on GitHub: Package Reference](https://github.com/WordPress/gutenberg/edit/trunk/docs/reference-guides/packages.md)

[PreviousZStackPrevious: ZStack](https://developer.wordpress.org/block-editor/reference-guides/components/z-stack/)

[Next@wordpress/a11yNext: @wordpress/a11y](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-a11y/)

Notifications