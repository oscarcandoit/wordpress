---
url: https://www.advancedcustomfields.com/resources/acf-blocks-v3
scraped_at: 2025-10-20T02:34:06.069Z
---

# ACF Blocks V3

Last updated Oct 7, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-v3/#acf-blocks-v3)

## ACF Blocks V3

Link copied

ACF Blocks Version 3 brings your ACF Blocks improved usability, new functionality, and fixes some issues as well:

- New: ACF Blocks v3 is compatible with WordPress/Gutenberg blocks v3 (iframe)
- New: ACF Blocks Edit Mode has been removed and replaced with a slide-out sidebar/modal. The preview area is always the preview area, and fields can be edited either in the sidebar, or in the larger slide-out/modal sidebar
- Fixed: You can now edit ACF blocks in Edit mode inside WP Core’s pattern editor
- Fixed/Changed: Validation errors now first appear after you click “Save/publish”, as opposed to immediately, while you are typing into a field for the first time
- Fixed/Changed: After fixing a field validation error it shows as fixed immediately as opposed to needing to click out of the block and back into it
- Fixed: Blocks with radio buttons no longer affect each other’s field values
- Fixed: Blocks with required radio buttons now validate correctly
- Fixed: ACF field validation now works in the Site Editor
- Fixed: WYSIWYG fields are no longer affected by typing into other blocks

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-v3/#upgrading-to-v3)

## Upgrading to v3

Link copied

To upgrade your blocks to version 3, you have a few options depending on your needs.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-v3/#if-using-blockjson)

### If using block.json

Link copied

If you are using block.json to register your blocks, you can add a `blockVersion` key to the `acf` object, and set its value to `3`. For example:

```php
{
"name": "acf/my-block",
"title": "My Block",
"acf": {
   "blockVersion": 3,
   "renderTemplate": "render-template.php"
 },
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-v3/#if-using-acfregisterblocktype)

### If using acf\_register\_block\_type

Link copied

If you are using the `acf_register_block_type` PHP function to register your blocks, add the acf\_block\_version to it. For example:

```php
function my_acf_blocks_init() {
    acf_register_block_type(
        array(
            'name' => 'testimonial',
            'title' => 'Testimonial',
            'render_template' => 'blocks/testimonial-block.php'
            'api_version' => 3,
            'acf_block_version' => 3,
        )
    );
}
add_action('acf/init', 'my_acf_blocks_init');
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-v3/#if-you-want-to-opt-in-all-of-your-blocks-in-a-single-line)

### If you want to opt-in all of your blocks in a single line

Link copied

If you want to opt all of your blocks into version 3 you can use the `acf/blocks/default_block_version` PHP filter, which will make any blocks without a specific version defined use version 3. For example:

```php
function my_custom_function_to_bump_the_block_version( $version, $block ) {
     return 3;
}
add_filter( 'acf/blocks/default_block_version', 'my_custom_function_to_bump_the_block_version', 10, 2 );
```

Note that if you have defined the blockVersion specifically in your block.json file, the `acf/blocks/default_block_version` filter will not override that.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-v3/#notable-changes-from-v2)

## Notable changes from V2

Link copied

In ACF Blocks Version 2, you could have your fields show up in the preview area by using “Edit” mode, or you could have them show up in the block editor sidebar if your block is in “Preview” mode. You could also toggle between the two by clicking the pencil icon in the block’s toolbar.

But in ACF Blocks Version 3, the concept of modes no longer exists. Rather, your block will always be in “preview”, always showing what’s in your PHP render template in the block preview area.

The block’s ACF fields show up in the sidebar, and also in a pop-out sidebar that has more space.

The pencil icon button in the block toolbar remains, and when clicked it will open the fields in the larger pop-out sidebar, allowing you to have more space for editing your fields.

ACF Blocks Version 3 is available from ACF PRO version 6.6 or later.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-v3/#related)

## Related

Link copied

- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [How To Upgrade a Legacy Block to block.json With ACF 6](https://www.advancedcustomfields.com/resources/how-to-upgrade-a-legacy-block-to-block-json-with-acf-6/)
- ACF Blocks: [ACF Blocks Configuration via block.json](https://www.advancedcustomfields.com/resources/acf-block-configuration-via-block-json/)
- ACF Blocks: [What’s New With ACF Blocks in ACF 6](https://www.advancedcustomfields.com/resources/whats-new-with-acf-blocks-in-acf-6/)
- ACF Blocks: [ACF Blocks](https://www.advancedcustomfields.com/resources/blocks/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-blocks-v3/#)