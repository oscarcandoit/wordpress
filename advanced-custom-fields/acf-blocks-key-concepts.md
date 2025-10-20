---
url: https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts
scraped_at: 2025-10-20T02:31:12.980Z
---

# Key Concepts

Last updated Jul 8, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#overview)

## Overview

Link copied

ACF Blocks allows you to build on top of the WordPress blocks system introduced in [WordPress 5.0 “Bebo”](https://wordpress.org/news/2018/12/bebo/), giving you access to many of the same features available to core blocks, but with the output rendered from a PHP template. ACF Blocks are highly flexible, allowing you to define [attributes](https://developer.wordpress.org/block-editor/explanations/architecture/key-concepts/#data-attributes), [block styles](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-styles/), and [block variations](https://developer.wordpress.org/block-editor/explanations/architecture/key-concepts/#block-variations). You can then compose your ACF Blocks into [patterns](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-patterns/), [templates](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-templates/) and template parts, save them as [synced patterns](https://wordpress.org/news/2023/07/synced-patterns-the-evolution-of-reusable-blocks/), and extend them to incorporate WordPress [styles](https://developer.wordpress.org/block-editor/explanations/architecture/key-concepts/#styles).

A thorough understanding of the [Block Editor Handbook](https://developer.wordpress.org/block-editor/) will greatly expand what you can build with ACF Blocks, but you don’t have to read the whole thing to get started. Below we highlight some of the key points to remember when working with blocks.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#key-terminology)

## Key Terminology

Link copied

Here are some common terms we’ll use to help distinguish between WordPress core block APIs and ACF Blocks APIs when necessary:

- **ACF Block(s):** Represents the ACF product’s API extensions, which mostly leverage and are scaffolded on top of WordPress core block’s APIs.
- **WordPress core block(s):** Refers to WordPress’s native and core APIs for blocks, which most of ACF Blocks is built upon. WordPress core blocks are mostly written in [React](https://react.dev/learn).
- **Block(s) or block(s):** When used without the prefix “ACF” or “WordPress core”, this refers to the general concept and lower-level APIs used by both WordPress core blocks _and_ ACF Blocks, as well as the end output from the block.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#points-to-remember)

## Points to Remember

Link copied

- Block data is saved within the `post_content` database table as [serialized HTML](https://developer.wordpress.org/block-editor/explanations/architecture/data-flow/#the-anatomy-of-a-serialized-block). This makes them unique to meta boxes that save data to the `postmeta` table.
- Every block in WordPress requires a [`block.json`](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-metadata/) file to register its properties. This is the entry point for every new block type.
- Native WordPress blocks can be static or dynamic. ACF Blocks are a custom type of dynamic block, rendered by ACF on the server and allowing for PHP logic.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#elements-of-acf-blocks)

## Elements of ACF Blocks

Link copied

There are three essential elements when it comes to ACF Blocks: a `block.json` file, a PHP file, and a CSS file. In fact, the CSS file is optional as your block may inherit styles from your theme, but you’ll need it to incorporate any unique styling. Most ACF Blocks also have an ACF field group associated with them, allowing the ACF Block to pull data from the fields. However, this is not actually essential to creating an ACF Block.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#acf-blocks-and-blockjson)

### ACF Blocks and block.json

Link copied

Both WordPress core blocks and ACF Blocks register their properties in a file called `block.json` to define their settings, styles, and metadata. The process is very similar to the one used for WordPress core blocks, but with the addition of [the `acf` configuration key](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/).

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#block-variables-or-parameters-for-callbacks-in-php)

## Block Variables (or Parameters for Callbacks) in PHP

Link copied

You have access to data about your block by default when creating an ACF Block, either by variables made available in your template or passed into your callback as parameters. New parameters are defined in exactly the same way as any other PHP template file.

- `$block` (array) The block settings and attributes.
- `$content` (string) The block inner HTML (empty).
- `$is_preview` (boolean) True during backend preview render, i.e., when rendering inside the block editor’s content, or rendered inside the block editor when adding a new block, showing a preview when hovering over the new block. This variable is only set to true when [is\_admin()](https://developer.wordpress.org/reference/functions/is_admin/) and current screen [is\_block\_editor()](https://developer.wordpress.org/reference/classes/wp_screen/is_block_editor/) both return true.
- `$post_id` (integer) The Post ID of the current context. This will be the page/post a block is saved against, or if the block is used in a template, synced pattern or query loop block, it will be the post\_id of the currently displayed item.
- `$context` (array) The context provided to the block by the post or its parent block.

For render callbacks, the parameters are provided in the following order:

```php
callback_function( $block, $content, $is_preview, $post_id, $wp_block, $context );
```

* * *

**[Next: Create Your First ACF Block](https://www.advancedcustomfields.com/resources/create-your-first-acf-block/)**

* * *

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#related)

## Related

Link copied

- ACF Blocks: [Create Your First ACF Block](https://www.advancedcustomfields.com/resources/create-your-first-acf-block/)
- ACF Blocks: [How To Upgrade a Legacy Block to block.json With ACF 6](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/)
- ACF Blocks: [ACF Blocks](https://www.advancedcustomfields.com/resources/blocks/)
- ACF Blocks: [Extending ACF Blocks With Block Supports](https://www.advancedcustomfields.com/resources/extending-acf-blocks-with-block-supports/)
- ACF Blocks: [ACF Blocks FAQ](https://www.advancedcustomfields.com/resources/acf-blocks-faq/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/#)