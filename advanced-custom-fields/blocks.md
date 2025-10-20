---
url: https://www.advancedcustomfields.com/resources/blocks
scraped_at: 2025-10-20T02:31:31.605Z
---

# ACF Blocks

Last updated Jul 30, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#introduction)

## Introduction

Link copied

ACF Blocks are customizable, dynamic, and integrate deeply with custom fields. A premium feature found in [ACF PRO](https://www.advancedcustomfields.com/pro), ACF Blocks uses a powerful PHP-based framework to develop custom block types without the thorough knowledge of JavaScript or React required to create WordPress blocks.

The PHP-based nature of ACF Blocks means PHP developers can easily create bespoke solutions in line with modern WordPress theme development. ACF Blocks maintain compatibility with WordPress core, providing access to many of the same features as native blocks.

![A testimonial block created with ACF Blocks.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/overview-testimonial-block.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#simplify-your-workflow)

## Simplify Your Workflow

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#php-environment)

### PHP Environment

Link copied

ACF Blocks is a PHP framework and does not require any JavaScript. This differentiates itself from the WordPress block API which relies heavily on modern JavaScript techniques, syntax and build tools.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#simple-templating)

### Simple Templating

Link copied

Similar to WordPress theme development, ACF Blocks are rendered using a PHP template file or callback function, allowing full control over the HTML output.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#custom-fields-compatible)

### Custom Fields Compatible

Link copied

ACF Blocks offer full compatibility with all field types including both the Repeater and Clone fields! Build your field group and attach it to your newly-registered block using ACF’s familiar Location rules.

![ACF Location rules configured to show this field group if the Block is equal to Testimonial. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/ACF-Blocks-Location-Settings.png)

It’s a similar story for template functions. Whether you are loading a field value via `get_field()`, or looping over a Repeater field using `have_rows()`, the experience remains familiar and consistent with regular theme development.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#live-previews)

### Live Previews

Link copied

Content changes, and so do block previews! When editing an ACF Block, the HTML will update in the backend giving you a real-time preview of your content. If you use an ACF Block in a Query Loop block or in a Full Site Editing Block Theme, your block preview will automatically update as your query changes.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#total-wordpress-compatibility)

## Total WordPress Compatibility

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#native-compatibility)

### Native Compatibility

Link copied

ACF Blocks maintain native compatibility with WordPress core. This allows features such as “alignment”, “anchor” and even [Reusable Blocks](https://wordpress.org/documentation/article/reusable-blocks/) to work!

ACF Blocks are not compatible with the standalone [Gutenberg](https://wordpress.org/plugins/gutenberg/) plugin, as the plugin forces on new, experimental features and API versions which are not yet supported by ACF.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#anywhere-everywhere)

### Anywhere and Everywhere

Link copied

ACF Blocks are not tied to metadata, meaning they can be used anywhere in WordPress, and multiple times per post.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#block-asset-loading)

### Block Asset Loading

Link copied

ACF Blocks supported enqueueing block-specific assets before WordPress did! WordPress now supports this, requiring assets be loaded using specific WordPress asset configuration keys. Blocks created with earlier versions of ACF Blocks should be migrated to use the WordPress provided methods.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#block-json-support)

### block.json Support

Link copied

ACF Blocks are registered with the standard WordPress function, `register_block_type()`, which loads a `block.json` file containing your configuration.

```php php
add_action( 'init', 'register_acf_blocks' );
function register_acf_blocks() {
    register_block_type( __DIR__ . '/blocks/your-example-block' );
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#flexible-design-development)

## Flexible Design & Development

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#block-versioning)

### Block Versioning

Link copied

Introduced in ACF 6.0, block versioning allows you to opt in to enable new features, or opt out to ensure blocks you’ve already created maintain backwards compatibility.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#blocks-without-fields)

### Blocks Without Fields

Link copied

ACF Blocks can be created without fields, useful in cases where you want to show post templating elements such as titles or post content, or when you want to display fields which are added on the post being displayed, rather than from the block.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#innerblock-support)

### InnerBlock Support

Link copied

ACF Blocks include full support for InnerBlocks, allowing you to nest blocks inside one another. This can be achieved by adding `<InnerBlocks />` to your PHP template file for the block.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#block-context-changes)

### Block Context Changes

Link copied

ACF Blocks support block context. This means you can configure your blocks to pass data to their InnerBlocks, including data from the ACF fields on the parent block. When anything about this block context changes, it will automatically reload the template of the child blocks, while your template handles any changes the parent block’s field values may cause.

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#next-steps)

## Next Steps

Link copied

ACF Blocks give you the functionality of native WordPress blocks, in a familiar PHP environment. This feature of [ACF PRO](https://www.advancedcustomfields.com/pro/) lets you give your clients perfectly tailored solutions that combine the power of Advanced Custom Fields with the ease of content editing and layout offered by the modern WordPress Site Editor.

Next, we’ll look at some of the key concepts used in WordPress blocks, and how they apply when creating ACF Blocks.

* * *

**[Next: Key Concepts](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/)**

Questions about ACF Blocks? Check out our [FAQ](https://www.advancedcustomfields.com/resources/acf-blocks-faq/).

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

[Link to heading#](https://www.advancedcustomfields.com/resources/blocks/#related)

## Related

Link copied

- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)
- ACF Blocks: [What’s New With ACF Blocks in ACF 6](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/)
- ACF Blocks: [ACF Blocks V3](https://www.advancedcustomfields.com/resources/acf-blocks-v3/)

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

[Got it](https://www.advancedcustomfields.com/resources/blocks/#)