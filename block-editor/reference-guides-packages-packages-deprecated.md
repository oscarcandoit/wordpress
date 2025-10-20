---
url: https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated
scraped_at: 2025-10-20T03:22:25.605Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

@wordpress/deprecated


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Package Reference](https://developer.wordpress.org/block-editor/reference-guides/packages/)@wordpress/deprecated

Search

# @wordpress/deprecated

## In this article

Table of Contents

- [Installation](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/#installation)
- [Hook](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/#hook)
- [API](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/#api)
  - [default](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/#default)
  - [logged](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/#logged)
- [Contributing to this package](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/#contributing-to-this-package)

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/#wp--skip-link--target)

Deprecation utility for WordPress. Logs a message to notify developers about a deprecated feature.

## [Installation](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/\#installation)

Install the module

```bash
npm install @wordpress/deprecated --save

```

_This package assumes that your code will run in an **ES2015+** environment. If you’re using an environment that has limited or no support for such language features and APIs, you should include [the polyfill shipped in `@wordpress/babel-preset-default`](https://github.com/WordPress/gutenberg/tree/HEAD/packages/babel-preset-default#polyfill) in your code._

## [Hook](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/\#hook)

The `deprecated` action is fired with three parameters: the name of the deprecated feature, the options object passed to deprecated, and the message sent to the console.

_Example:_

```js
import { addAction } from '@wordpress/hooks';

function addDeprecationAlert( message, { version } ) {
    alert( `Deprecation: ${ message }. Version: ${ version }` );
}

addAction(
    'deprecated',
    'my-plugin/add-deprecation-alert',
    addDeprecationAlert
);

```

## [API](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/\#api)

### [default](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/\#default)

Logs a message to notify developers about a deprecated feature.

_Usage_

```js
import deprecated from '@wordpress/deprecated';

deprecated( 'Eating meat', {
    since: '2019.01.01',
    version: '2020.01.01',
    alternative: 'vegetables',
    plugin: 'the earth',
    hint: 'You may find it beneficial to transition gradually.',
} );

// Logs: 'Eating meat is deprecated since version 2019.01.01 and will be removed from the earth in version 2020.01.01. Please use vegetables instead. Note: You may find it beneficial to transition gradually.'

```

_Parameters_

- _feature_ `string`: Name of the deprecated feature.
- _options_ `[DeprecatedOptions]`: Personalisation options

### [logged](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/\#logged)

Object map tracking messages which have been logged, for use in ensuring a message is only logged once.

_Type_

- `Record< string, true >`

## [Contributing to this package](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-deprecated/\#contributing-to-this-package)

This is an individual package that’s part of the Gutenberg project. The project is organized as a monorepo. It’s made up of multiple self-contained software packages, each with a specific purpose. The packages in this monorepo are published to [npm](https://www.npmjs.com/) and used by [WordPress](https://make.wordpress.org/core/) as well as other software projects.

To find out more about contributing to this package or Gutenberg as a whole, please read the project’s main [contributor guide](https://github.com/WordPress/gutenberg/tree/HEAD/CONTRIBUTING.md).

First published

March 9, 2021

Last updated

October 7, 2025

Edit article

[Improve it on GitHub: @wordpress/deprecated](https://github.com/WordPress/gutenberg/edit/trunk/packages/deprecated/README.md)

[Previous@wordpress/experimentsPrevious: @wordpress/experiments](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-experiments/)

[Next@wordpress/docgenNext: @wordpress/docgen](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-docgen/)

Notifications