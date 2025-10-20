---
url: https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block
scraped_at: 2025-10-20T03:17:08.280Z
---

[Skip to content](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Get started with create-block


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Getting Started](https://developer.wordpress.org/block-editor/getting-started/)[Block Development Environment](https://developer.wordpress.org/block-editor/getting-started/devenv/)Get started with create-block

Search

# Get started with create-block

## In this article

Table of Contents

- [Quick start](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#quick-start)
  - [Installation](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#installation)
  - [Basic usage](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#basic-usage)
- [Alternate implementations](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#alternate-implementations)
  - [Interactive mode](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#interactive-mode)
  - [Quick start mode using options](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#quick-start-mode-using-options)
  - [Using templates](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#using-templates)
- [Additional resources](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#additional-resources)

[↑ Back to top](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/#wp--skip-link--target)

Custom blocks for the Block Editor in WordPress are typically registered using plugins and are defined through a specific set of files. The [`@wordpress/create-block`](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-create-block/) package is an officially supported tool to scaffold the structure of files needed to create and register a block. It generates all the necessary code to start a project and integrates a modern JavaScript build setup (using [`wp-scripts`](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-scripts/)) with no configuration required.

The package is designed to help developers quickly set up a block development environment following WordPress best practices.

## [Quick start](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/\#quick-start)

### [Installation](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/\#installation)

Start by ensuring you have Node.js and `npm` installed on your computer. Review the [Node.js development environment](https://developer.wordpress.org/block-editor/getting-started/devenv/nodejs-development-environment/) guide if not.

You can use `create-block` to scaffold a block just about anywhere and then [use `wp-env`](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/) from the inside of the generated plugin folder. This will create a local WordPress development environment with your new block plugin installed and activated.

If you have your own [local WordPress development environment](https://developer.wordpress.org/block-editor/getting-started/devenv/#local-wordpress-environment) already set up, navigate to the `plugins/` folder using the terminal.

Run the following command to scaffold an example block plugin:

```bash
npx @wordpress/create-block@latest todo-list
cd todo-list

```

The `slug` provided ( `todo-list`) defines the folder name for the scaffolded plugin and the internal block name.

Navigate to the Plugins page of our local WordPress installation and activate the “Todo List” plugin. The example block will then be available in the Editor.

### [Basic usage](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/\#basic-usage)

The `create-block` assumes you will use modern JavaScript (ESNext and JSX) to build your block. This requires a build step to compile the code into a format that browsers can understand. Luckily, the `wp-scripts` package handles this process for you. Refer to the [Get started with wp-scripts](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-scripts) for an introduction to this package.

When `create-block` scaffolds the block, it installs `wp-scripts` and adds the most common scripts to the block’s `package.json` file. By default, those include:

```json
{
    "scripts": {
        "build": "wp-scripts build",
        "format": "wp-scripts format",
        "lint:css": "wp-scripts lint-style",
        "lint:js": "wp-scripts lint-js",
        "packages-update": "wp-scripts packages-update",
        "plugin-zip": "wp-scripts plugin-zip",
        "start": "wp-scripts start"
    }
}

```

These scripts can then be run using the command `npm run {script name}`. The two scripts you will use most often are `start` and `build` since they handle the build step.

When working on your block, use the `npm run start` command. This will start a development server and automatically rebuild the block whenever any code change is detected.

When you are ready to deploy your block, use the `npm run build` command. This optimizes your code and makes it production-ready.

See the `wp-scripts` [package documentation](https://developer.wordpress.org/block-editor/packages/packages-scripts/) for more details about each available script.

## [Alternate implementations](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/\#alternate-implementations)

### [Interactive mode](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/\#interactive-mode)

For developers who prefer a more guided experience, the `create-block` package provides an interactive mode. Instead of manually specifying all options upfront, like the `slug` in the above example, this mode will prompt you for inputs step-by-step.

To use this mode, run the command:

```bash
npx @wordpress/create-block@latest

```

Follow the prompts to configure your block settings interactively.

### [Quick start mode using options](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/\#quick-start-mode-using-options)

If you’re already familiar with the `create-block` [options](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-create-block/#options) and want a more streamlined setup, you can use quick start mode. This allows you to pass specific options directly in the command line, eliminating the need for interactive prompts.

For instance, to quickly create a block named “my-block” with a namespace of “my-plugin” that is a Dynamic block, use this command:

```bash
npx @wordpress/create-block@latest --namespace="my-plugin" --slug="my-block" --variant="dynamic"

```

### [Using templates](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/\#using-templates)

The `create-block` package also supports the use of templates, enabling you to create blocks based on predefined configurations and structures. This is especially useful when you have a preferred block structure or when you’re building multiple blocks with similar configurations.

To use a template, specify the `--template` option followed by the template name or path:

```bash
npx @wordpress/create-block --template="my-custom-template"

```

Templates must be set up in advance so the `create-block` package knows where to find them. Learn more in the `create-block` [documentation](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-create-block/#template), and review the [External Project Templates](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-create-block/packages-create-block-external-template/) guide.

## [Additional resources](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/\#additional-resources)

- [Using the create-block tool](https://learn.wordpress.org/tutorial/using-the-create-block-tool/) (Learn WordPress tutorial)
- [@wordpress/create-block](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-create-block/) (Official documentation)
- [@wordpress/scripts](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-scripts/) (Official documentation)

First published

October 17, 2023

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Get started with create-block](https://github.com/WordPress/gutenberg/edit/trunk/docs/getting-started/devenv/get-started-with-create-block.md)

[PreviousGet started with wp-envPrevious: Get started with wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/)

[NextGet started with wp-scriptsNext: Get started with wp-scripts](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-scripts/)

Notifications