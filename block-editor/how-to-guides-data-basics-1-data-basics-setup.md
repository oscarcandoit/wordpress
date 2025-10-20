---
url: https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup
scraped_at: 2025-10-20T03:12:51.260Z
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Setup


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)[Create your First App with Gutenberg Data](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/)Setup

Search

# Setup

## In this article

Table of Contents

- [Creating a plugin](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/#creating-a-plugin)
- [Setting up the build pipeline](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/#setting-up-the-build-pipeline)
- [Testing if it worked](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/#testing-if-it-worked)
- [What’s next?](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/#whats-next)

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/#wp--skip-link--target)

We will build the application as a WordPress plugin, which means you need to have WordPress itself installed. One way to do this is by following the instructions on the [Getting Started](https://developer.wordpress.org/block-editor/contributors/code/getting-started-with-code-contribution/) page. Once your setup is complete, you can follow along with the rest of this tutorial.

Also, this tutorial will lean heavily on Redux concepts such as state, actions, and selectors. If you are not familiar with them, you may want to start by reviewing [Getting Started With Redux](https://redux.js.org/introduction/getting-started).

## [Creating a plugin](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/\#creating-a-plugin)

We’ll do all the development inside of a WordPress plugin. Let’s start by creating a `wp-content/plugins/my-first-gutenberg-app` directory in your local WordPress environment. We will need to create four files inside that directory:

- my-first-gutenberg-app.php – to create a new admin page
- src/index.js – for our JavaScript application
- src/style.css – for the minimal stylesheet
- package.json – for the build process

Go ahead and create these files using the following snippets:

**src/index.js:**

```js
import { createRoot } from 'react-dom';
import './style.css';

function MyFirstApp() {
    return <span>Hello from JavaScript!</span>;
}

const root = createRoot( document.getElementById( 'my-first-gutenberg-app' ) );
window.addEventListener(
    'load',
    function () {
        root.render(
            <MyFirstApp />,
        );
    },
    false
);

```

**src/style.css:**

```css
.toplevel_page_my-first-gutenberg-app #wpcontent {
    background: #fff;
    height: 1000px;
}
button .components-spinner {
    width: 15px;
    height: 15px;
    margin-top: 0;
    margin-bottom: 0;
    margin-left: 0;
}
.form-buttons {
    display: flex;
}
.my-gutenberg-form .form-buttons {
    margin-top: 20px;
    margin-left: 1px;
}
.form-error {
    color: #cc1818;
}
.form-buttons button {
    margin-right: 4px;
}
.form-buttons .components-spinner {
    margin-top: 0;
}
#my-first-gutenberg-app {
    max-width: 500px;
}
#my-first-gutenberg-app ul,
#my-first-gutenberg-app ul li {
    list-style-type: disc;
}
#my-first-gutenberg-app ul {
    padding-left: 20px;
}
#my-first-gutenberg-app .components-search-control__input {
    height: 36px;
    margin-left: 0;
}

#my-first-gutenberg-app .list-controls {
    display: flex;
    width: 100%;
}

#my-first-gutenberg-app .list-controls .components-search-control {
    flex-grow: 1;
    margin-right: 8px;
}

```

**my-first-gutenberg-app.php:**

```php
<?php
/**
 * Plugin Name: My first Gutenberg App
 *
 */

function my_admin_menu() {
    // Create a new admin page for our app.
    add_menu_page(
        __( 'My first Gutenberg app', 'gutenberg' ),
        __( 'My first Gutenberg app', 'gutenberg' ),
        'manage_options',
        'my-first-gutenberg-app',
        function () {
            echo '
            <h2>Pages</h2>
            <div id="my-first-gutenberg-app"></div>
        ';
        },
        'dashicons-schedule',
        3
    );
}

add_action( 'admin_menu', 'my_admin_menu' );

function load_custom_wp_admin_scripts( $hook ) {
    // Load only on ?page=my-first-gutenberg-app.
    if ( 'toplevel_page_my-first-gutenberg-app' !== $hook ) {
        return;
    }

    // Load the required WordPress packages.

    // Automatically load imported dependencies and assets version.
    $asset_file = include plugin_dir_path( __FILE__ ) . 'build/index.asset.php';

    // Enqueue CSS dependencies.
    foreach ( $asset_file['dependencies'] as $style ) {
        wp_enqueue_style( $style );
    }

    // Load our app.js.
    wp_register_script(
        'my-first-gutenberg-app',
        plugins_url( 'build/index.js', __FILE__ ),
        $asset_file['dependencies'],
        $asset_file['version']
    );
    wp_enqueue_script( 'my-first-gutenberg-app' );

    // Load our style.css.
    wp_register_style(
        'my-first-gutenberg-app',
        plugins_url( 'build/style-index.css', __FILE__ ),
        array(),
        $asset_file['version']
    );
    wp_enqueue_style( 'my-first-gutenberg-app' );
}

add_action( 'admin_enqueue_scripts', 'load_custom_wp_admin_scripts' );

```

**package.json:**

```json
{
  "name": "09-code-data-basics-esnext",
  "version": "1.1.0",
  "private": true,
  "description": "My first Gutenberg App",
  "author": "The WordPress Contributors",
  "license": "GPL-2.0-or-later",
  "keywords": [\
    "WordPress",\
    "block"\
  ],
  "homepage": "https://github.com/WordPress/gutenberg-examples/",
  "repository": "git+https://github.com/WordPress/gutenberg-examples.git",
  "bugs": {
    "url": "https://github.com/WordPress/gutenberg-examples/issues"
  },
  "main": "build/index.js",
  "devDependencies": {
    "@wordpress/scripts": "^24.0.0"
  },
  "scripts": {
    "build": "wp-scripts build",
    "format": "wp-scripts format",
    "lint:js": "wp-scripts lint-js",
    "packages-update": "wp-scripts packages-update",
    "start": "wp-scripts start"
  }
}

```

## [Setting up the build pipeline](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/\#setting-up-the-build-pipeline)

This tutorial will proceed assuming the reader is familiar with ESNext syntax and the concept of build tools (like webpack). If that sounds confusing, you may want to review the [Getting started with JavaScript Build Setup](https://developer.wordpress.org/block-editor/how-to-guides/javascript/js-build-setup/) first.

To install the build tool, navigate to the plugin directory using your terminal and run `npm install`.

Once all the dependencies are in place, all that’s left is to run `npm start` and voila! A watcher will run in the terminal. You can then edit away in your text editor; after each save, it will automatically build.

## [Testing if it worked](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/\#testing-if-it-worked)

If you now go to the Plugins page, you should see a plugin called **My first Gutenberg App**. Go ahead and activate it. A new menu item labeled _My first Gutenberg app_ should show up. Once you click it, you will see a page that says _Hello from JavaScript!_:

![](https://i0.wp.com/raw.githubusercontent.com/WordPress/gutenberg/HEAD/docs/how-to-guides/data-basics/media/setup/hello-from-js.jpg?ssl=1)

Congratulations! You are now ready to start building the app!

## [What’s next?](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/1-data-basics-setup/\#whats-next)

- Previous part: [Introduction](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/)
- Next part: [Building a basic list of pages](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/2-building-a-list-of-pages/)
- (optional) Review the [finished app](https://github.com/WordPress/block-development-examples/tree/trunk/plugins/data-basics-59c8f8) in the block-development-examples repository

First published

February 9, 2022

Last updated

April 17, 2025

Edit article

[Improve it on GitHub: Setup](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/data-basics/1-data-basics-setup.md)

[PreviousCreate your First App with Gutenberg DataPrevious: Create your First App with Gutenberg Data](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/)

[NextBuilding a list of pagesNext: Building a list of pages](https://developer.wordpress.org/block-editor/how-to-guides/data-basics/2-building-a-list-of-pages/)

Notifications