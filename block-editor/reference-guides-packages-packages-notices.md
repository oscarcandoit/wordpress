---
url: https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices
scraped_at: 2025-10-20T03:23:02.367Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

@wordpress/notices


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Package Reference](https://developer.wordpress.org/block-editor/reference-guides/packages/)@wordpress/notices

Search

# @wordpress/notices

## In this article

Table of Contents

- [Installation](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices/#installation)
- [Usage](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices/#usage)
- [Contributing to this package](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices/#contributing-to-this-package)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices/#wp--skip-link--target)

State management for notices.

## [Installation](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices/\#installation)

Install the module

```bash
npm install @wordpress/notices

```

_This package assumes that your code will run in an **ES2015+** environment. If you’re using an environment that has limited or no support for such language features and APIs, you should include [the polyfill shipped in `@wordpress/babel-preset-default`](https://github.com/WordPress/gutenberg/tree/HEAD/packages/babel-preset-default#polyfill) in your code._

## [Usage](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices/\#usage)

When imported, the notices module registers a data store on the `core/notices` namespace. In WordPress, this is accessed from `wp.data.dispatch( 'core/notices' )`.

For more information about consuming from a data store, refer to [the `@wordpress/data` documentation on _Data Access and Manipulation_](https://github.com/WordPress/gutenberg/tree/HEAD/packages/data/README.md#data-access-and-manipulation).

For a full list of actions and selectors available in the `core/notices` namespace, refer to the [_Notices Data_ Handbook page](https://github.com/WordPress/gutenberg/tree/HEAD/docs/reference-guides/data/data-core-notices.md).

## [Contributing to this package](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-notices/\#contributing-to-this-package)

This is an individual package that’s part of the Gutenberg project. The project is organized as a monorepo. It’s made up of multiple self-contained software packages, each with a specific purpose. The packages in this monorepo are published to [npm](https://www.npmjs.com/) and used by [WordPress](https://make.wordpress.org/core/) as well as other software projects.

To find out more about contributing to this package or Gutenberg as a whole, please read the project’s main [contributor guide](https://github.com/WordPress/gutenberg/tree/HEAD/CONTRIBUTING.md).

First published

March 9, 2021

Last updated

October 17, 2025

Edit article

[Improve it on GitHub: @wordpress/notices](https://github.com/WordPress/gutenberg/edit/trunk/packages/notices/README.md)

[Previous@wordpress/media-utilsPrevious: @wordpress/media-utils](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-media-utils/)

[Next@wordpress/npm-package-json-lint-configNext: @wordpress/npm-package-json-lint-config](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-npm-package-json-lint-config/)

Notifications