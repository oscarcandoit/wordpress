---
url: https://developer.wordpress.org/block-editor/how-to-guides/platform
scraped_at: 2025-10-20T03:12:47.487Z
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/platform/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Development Platform


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)Development Platform

Search

# Development Platform

## In this article

Table of Contents

- [UI components](https://developer.wordpress.org/block-editor/how-to-guides/platform/#ui-components)
- [Development scripts](https://developer.wordpress.org/block-editor/how-to-guides/platform/#development-scripts)
- [Block Editor](https://developer.wordpress.org/block-editor/how-to-guides/platform/#block-editor)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/platform/#wp--skip-link--target)

The Gutenberg Project is not only building a better editor for WordPress, but also creating a platform to build upon. This platform consists of a set of JavaScript packages and tools that you can use in your web application. [View the list of packages available on npm](https://www.npmjs.com/org/wordpress).

## [UI components](https://developer.wordpress.org/block-editor/how-to-guides/platform/\#ui-components)

The [WordPress Components package](https://developer.wordpress.org/block-editor/reference-guide/components/) contains a set of UI components you can use in your project. See the [WordPress Storybook site](https://wordpress.github.io/gutenberg/) for an interactive guide to the available components and settings.

Here is a quick example, how to use components in your project.

Install the dependency:

```bash
npm install --save @wordpress/components

```

Usage in React:

```jsx
import { Button } from '@wordpress/components';

function MyApp() {
    return <Button>Hello Button</Button>;
}

```

Many components include CSS to add style, you will need to include for the components to appear correctly. The component stylesheet can be found in `node_modules/@wordpress/components/build-style/style.css`, you can link directly or copy and include it in your project.

## [Development scripts](https://developer.wordpress.org/block-editor/how-to-guides/platform/\#development-scripts)

The [`@wordpress/scripts` package](https://developer.wordpress.org/block-editor/reference-guide/packages/packages-scripts/) is a collection of reusable scripts for JavaScript development — includes scripts for building, linting, and testing — all with no additional configuration files.

Here is a quick example, on how to use `wp-scripts` tool in your project.

Install the dependency:

```bash
npm install --save-dev @wordpress/scripts

```

You can then add a scripts section to your package.json file, for example:

```json
    "scripts": {
        "build": "wp-scripts build",
        "format": "wp-scripts format",
        "lint:js": "wp-scripts lint-js",
        "start": "wp-scripts start"
    }

```

You can then use `npm run build` to build your project with all the default webpack settings already configured, likewise for formatting and linting. The `start` command is used for development mode. See the [`@wordpress/scripts` package](https://developer.wordpress.org/block-editor/reference-guide/packages/packages-scripts/) for full documentation.

For more info, see the [Getting Started with JavaScript tutorial](https://developer.wordpress.org/block-editor/how-to-guides/javascript/js-build-setup/) in the Block Editor Handbook.

## [Block Editor](https://developer.wordpress.org/block-editor/how-to-guides/platform/\#block-editor)

The [`@wordpress/block-editor` package](https://developer.wordpress.org/block-editor/packages/packages-block-editor/) allows you to create and use standalone block editors.

You can learn more by reading the [tutorial “Building a custom block editor”](https://developer.wordpress.org/block-editor/how-to-guides/platform/custom-block-editor/).

First published

March 9, 2021

Last updated

January 29, 2024

Edit article

[Improve it on GitHub: Development Platform](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/platform/README.md)

[PreviousExtending the Query Loop blockPrevious: Extending the Query Loop block](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/extending-the-query-loop-block/)

[NextBuilding a custom block editorNext: Building a custom block editor](https://developer.wordpress.org/block-editor/how-to-guides/platform/custom-block-editor/)

Notifications