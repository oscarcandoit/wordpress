---
url: https://developer.wordpress.org/block-editor/getting-started/devenv
scraped_at: 2025-10-20T03:12:59.652Z
---

[Skip to content](https://developer.wordpress.org/block-editor/getting-started/devenv/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Block Development Environment


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Getting Started](https://developer.wordpress.org/block-editor/getting-started/)Block Development Environment

Search

# Block Development Environment

## In this article

Table of Contents

- [Code editor](https://developer.wordpress.org/block-editor/getting-started/devenv/#code-editor)
- [Node.js development tools](https://developer.wordpress.org/block-editor/getting-started/devenv/#node-js-development-tools)
- [Local WordPress environment](https://developer.wordpress.org/block-editor/getting-started/devenv/#local-wordpress-environment)

[↑ Back to top](https://developer.wordpress.org/block-editor/getting-started/devenv/#wp--skip-link--target)

This guide will help you set up the right development environment to create blocks and other plugins that extend and modify the Block Editor in WordPress.

A block development environment includes the tools you need on your computer to successfully develop for the Block Editor. The three essential requirements are:

- [Block Development Environment](https://developer.wordpress.org/block-editor/getting-started/devenv/#block-development-environment)
  - [Code editor](https://developer.wordpress.org/block-editor/getting-started/devenv/#code-editor)
  - [Node.js development tools](https://developer.wordpress.org/block-editor/getting-started/devenv/#nodejs-development-tools)
  - [Local WordPress environment](https://developer.wordpress.org/block-editor/getting-started/devenv/#local-wordpress-environment)

To contribute to the Gutenberg project itself, refer to the additional documentation in the [code contribution guide](https://developer.wordpress.org/block-editor/contributors/code/getting-started-with-code-contribution).

## [Code editor](https://developer.wordpress.org/block-editor/getting-started/devenv/\#code-editor)

A code editor is used to write code. You can use whichever editor you’re most comfortable with. The key is having a way to open, edit, and save text files.

If you do not already have a preferred code editor, [Visual Studio Code](https://code.visualstudio.com/) (VS Code) is a popular choice for JavaScript development among Core contributors. It works well across the three major platforms (Windows, Linux, and Mac), is open-source, and is actively maintained by Microsoft. VS Code also has a vibrant community providing plugins and extensions, including many for WordPress development.

## [Node.js development tools](https://developer.wordpress.org/block-editor/getting-started/devenv/\#node-js-development-tools)

Node.js ( `node`) is an open-source runtime environment that allows you to execute JavaScript outside of the web browser. While Node.js is not required for all WordPress JavaScript development, it’s essential when working with modern JavaScript tools and developing for the Block Editor.

Node.js and its accompanying development tools allow you to:

- Install and run WordPress packages needed for Block Editor development, such as `wp-scripts`
- Set up local WordPress environments with `wp-env` and `@wp-playground/cli`
- Use the latest ECMAScript features and write code in ESNext
- Lint, format, and test JavaScript code
- Scaffold custom blocks with the `create-block` package

The list goes on. While modern JavaScript development can be challenging, WordPress provides several tools, like [`wp-scripts`](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-scripts/) and [`create-block`](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/), that streamline the process and are made possible by Node.js development tools.

**The recommended Node.js version for block development is [Active LTS](https://nodejs.org/en/about/previous-releases) (Long Term Support)**. However, there are times when you need to use different versions. A Node.js version manager tool like `nvm` is strongly recommended and allows you to change your `node` version when required. You will also need Node Package Manager ( `npm`) and the Node Package eXecute ( `npx`) to work with some WordPress packages. Both are installed automatically with Node.js.

To be able to use the Node.js tools and [packages provided by WordPress](https://github.com/WordPress/gutenberg/tree/trunk/packages) for block development, you’ll need to set a proper Node.js runtime environment on your machine. To learn more about how to do this, refer to the links below.

- [Install Node.js for Mac and Linux](https://developer.wordpress.org/block-editor/getting-started/devenv/nodejs-development-environment/#node-js-installation-on-mac-and-linux-with-nvm)
- [Install Node.js for Windows](https://developer.wordpress.org/block-editor/getting-started/devenv/nodejs-development-environment/#node-js-installation-on-windows-and-others)

## [Local WordPress environment](https://developer.wordpress.org/block-editor/getting-started/devenv/\#local-wordpress-environment)

A local WordPress environment (site) provides a controlled, efficient, and secure space for development, allowing you to build and test your code before deploying it to a production site. The same [requirements](https://en-gb.wordpress.org/about/requirements/) for WordPress apply to local sites.

In the broader WordPress community, many tools are available for setting up a local WordPress environment on your computer. The Block Editor Handbook covers `wp-env`, which is open-source and maintained by the WordPress project itself. It’s also the recommended tool for Gutenberg development.

Refer to the [Get started with `wp-env`](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/) guide for setup instructions.

Throughout the Handbook, you may also see references to `[@wp-playground/cli](https://github.com/WordPress/wordpress-playground/tree/trunk/packages/playground/cli)`. This is a lightweight tool powered by [WordPress Playground](https://developer.wordpress.org/playground/) that streamlines setting up a simple local WordPress environment. While still experimental, this tool is great for quickly testing WordPress releases, plugins, and themes.

This list is not exhaustive, but here are several additional options to choose from if you prefer not to use `wp-env`:

- [WordPress Studio](https://developer.wordpress.com/studio/)
- [Local](https://localwp.com/)
- [XAMPP](https://www.apachefriends.org/)
- [MAMP](https://www.mamp.info/en/mamp/mac/)
- [Varying Vagrant Vagrants](https://varyingvagrantvagrants.org/) (VVV)

First published

March 9, 2021

Last updated

August 6, 2025

Edit article

[Improve it on GitHub: Block Development Environment](https://github.com/WordPress/gutenberg/edit/trunk/docs/getting-started/devenv/README.md)

[PreviousGetting StartedPrevious: Getting Started](https://developer.wordpress.org/block-editor/getting-started/)

[NextNode.js development environmentNext: Node.js development environment](https://developer.wordpress.org/block-editor/getting-started/devenv/nodejs-development-environment/)

Notifications