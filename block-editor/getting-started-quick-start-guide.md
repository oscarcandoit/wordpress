---
url: https://developer.wordpress.org/block-editor/getting-started/quick-start-guide
scraped_at: 2025-10-20T03:45:56.720Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Quick Start Guide


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Getting Started](https://developer.wordpress.org/block-editor/getting-started/)Quick Start Guide

Search

# Quick Start Guide

## In this article

Table of Contents

- [Scaffold the block plugin](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/#scaffold-the-block-plugin)
- [Basic usage](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/#basic-usage)
- [View the block in action](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/#view-the-block-in-action)
- [Additional resources](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/#additional-resources)

[↑ Back to top](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/#wp--skip-link--target)

This guide is designed to demonstrate the basic principles of block development in WordPress using a hands-on approach. Following the steps below, you will create a custom block plugin that uses modern JavaScript (ESNext and JSX) in a matter of minutes. The example block displays the copyright symbol (©) and the current year, the perfect addition to any website’s footer. You can see these steps in action through this short video demonstration.

WordPress Block Development: Quick Start Guide - YouTube

[Photo image of WordPress](https://www.youtube.com/channel/UCpJf6LGZ0a4n9Lj4aVt9spg?embeds_referring_euri=https%3A%2F%2Fdeveloper.wordpress.org%2F)

WordPress

113K subscribers

[WordPress Block Development: Quick Start Guide](https://www.youtube.com/watch?v=nrut8SfXA44)

WordPress

Search

Watch later

Share

Copy link

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

More videos

## More videos

You're signed out

Videos you watch may be added to the TV's watch history and influence TV recommendations. To avoid this, cancel and sign in to YouTube on your computer.

CancelConfirm

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

[Watch on](https://www.youtube.com/watch?v=nrut8SfXA44&embeds_referring_euri=https%3A%2F%2Fdeveloper.wordpress.org%2F)

0:00

0:00 / 2:32
•Live

•

## [Scaffold the block plugin](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/\#scaffold-the-block-plugin)

Start by ensuring you have Node.js and `npm` installed on your computer. Review the [Node.js development environment](https://developer.wordpress.org/block-editor/getting-started/devenv/nodejs-development-environment/) guide if not.

Next, use the [`@wordpress/create-block`](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-create-block/) package and the [`@wordpress/create-block-tutorial-template`](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-create-block-tutorial-template/) template to scaffold the complete “Copyright Date Block” plugin.

You can use `create-block` to scaffold a block just about anywhere and then use [`wp-env`](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/) inside the generated plugin folder. This will create a local WordPress development environment with your new block plugin installed and activated.

If you already have your own [local WordPress development environment](https://developer.wordpress.org/block-editor/getting-started/devenv/#local-wordpress-environment), navigate to the `plugins/` folder using the terminal.

Choose the folder where you want to create the plugin, and then execute the following command in the terminal from within that folder:

```sh
npx @wordpress/create-block copyright-date-block --template @wordpress/create-block-tutorial-template

```

The `slug` provided ( `copyright-date-block`) defines the folder name for the scaffolded plugin and the internal block name.

Navigate to the Plugins page of your local WordPress installation and activate the “Copyright Date Block” plugin. The example block will then be available in the Editor.

## [Basic usage](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/\#basic-usage)

With the plugin activated, you can explore how the block works. Use the following command to move into the newly created plugin folder and start the development process.

```sh
cd copyright-date-block && npm start

```

When `create-block` scaffolds the block, it installs `wp-scripts` and adds the most common scripts to the block’s `package.json` file. Refer to the [Get started with wp-scripts](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-scripts/) article for an introduction to this package.

The `npm start` command will start a development server and watch for changes in the block’s code, rebuilding the block whenever modifications are made.

When you are finished making changes, run the `npm run build` command. This optimizes the block code and makes it production-ready.

## [View the block in action](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/\#view-the-block-in-action)

You can use any local WordPress development environment to test your new block, but the scaffolded plugin includes configuration for `wp-env`. You must have [Docker](https://www.docker.com/products/docker-desktop) already installed and running on your machine, but if you do, run the `npx wp-env start` command.

Once the script finishes running, you can access the local environment at: `http://localhost:8888`. Log into the WordPress dashboard using username `admin` and password `password`. The plugin will already be installed and activated. Open the Editor or Site Editor, and insert the Copyright Date Block as you would any other block.

Visit the [Getting started](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/) guide to learn more about `wp-env`.

## [Additional resources](https://developer.wordpress.org/block-editor/getting-started/quick-start-guide/\#additional-resources)

- [Get started with create-block](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/)
- [Get started with wp-scripts](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-scripts/)
- [Get started with wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/)

First published

November 13, 2023

Last updated

April 29, 2024

Edit article

[Improve it on GitHub: Quick Start Guide](https://github.com/WordPress/gutenberg/edit/trunk/docs/getting-started/quick-start-guide.md)

[PreviousGet started with wp-scriptsPrevious: Get started with wp-scripts](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-scripts/)

[NextTutorial: Build your first blockNext: Tutorial: Build your first block](https://developer.wordpress.org/block-editor/getting-started/tutorial/)

Notifications