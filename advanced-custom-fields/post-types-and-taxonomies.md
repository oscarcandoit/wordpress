---
url: https://www.advancedcustomfields.com/resources/post-types-and-taxonomies
scraped_at: 2025-10-20T02:25:35.970Z
---

# Post Types and Taxonomies

Last updated Jun 5, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#overview)

## Overview

Link copied

![ACF 6.1 CPTs and Taxonomies promo image.](https://www.advancedcustomfields.com/wp-content/uploads/2023/03/ACF-6.1-BETA-PROMO-1.jpg)

As of ACF 6.1 you can now register [custom post types](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/) and [custom taxonomies](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/), along with [custom fields](https://www.advancedcustomfields.com/resources/creating-a-field-group/), turning WordPress into a fully fledged content management system.

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#registering-custom-post-types)

## Registering Custom Post Types

Link copied

Post types are great for storing data objects other than posts and pages, where WordPress provides an admin UI for managing your data and a URL structure for viewing them on the frontend of the site.

[Learn how to register a custom post type with ACF](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/).

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#registering-custom-taxonomies)

## Registering Custom Taxonomies

Link copied

Taxonomies are used to classify and categorize individual posts for a post type. WordPress provides an admin UI for managing terms in a taxonomy and categorizing posts with terms.

[Learn how to register a custom taxonomy with ACF](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/).

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#export--import)

## Export & Import

Link copied

It’s important that post type and taxonomy definitions are as portable and reusable as possible, so we have applied the same functionality to post types and taxonomies as custom fields. There is support for [PHP export](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#php-export), exporting and importing JSON, [local JSON](https://www.advancedcustomfields.com/resources/local-json/) and [synchronized JSON](https://www.advancedcustomfields.com/resources/synchronized-json/) as well as [importing post types and taxonomies created with the Custom Post Type UI plugin (CPTUI)](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#importing-from-cptui).

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#php-export)

### PHP Export

Link copied

When you select post types or taxonomies in the “Export” meta box of the “Tools” page, and click **Generate PHP**, the PHP that is generated is the native WordPress registration function. This makes it easy to use ACF to generate post types and taxonomies, and then just grab the code to use on your sites:

![Exporting PHP code for custom post types.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-export-php-cpt.png)

Once you have exported a custom post type or taxonomy to PHP and included it in your theme or plugin, it is no longer manageable in ACF’s admin pages and you can safely delete it from ACF.

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#importing-from-custom-post-type-ui)

### Importing from Custom Post Type UI

Link copied

We recognize many users have both the Custom Post Type UI (CPTUI) plugin alongside ACF and may want to consolidate post types, taxonomies, and fields into ACF going forward. To help with that, we have developed a dedicated import tool to migrate post types and taxonomies created with CPTUI to ACF.

When the CPTUI plugin is active and there are post types and taxonomies created with it, ACF will display a notice in the ACF plugin admin alerting you that ACF can now manage them, with a link to the “Tools” page to perform the import. There is a new section in the “Import” meta box of the “Tools” page to where you can choose to import the post types, taxonomies, or both from CPTUI.

![Importing post types and taxonomies created with CPTUI plugin.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-cptui-import.png)

Click the **Import from Custom Post Type UI** button to start the process. Once successfully imported you can safely deactivate the CPTUI plugin. The import does _not_ delete any CPTUI plugin data. We recommend deactivating the CPTUI plugin after the import to ensure there are no duplicate post types and taxonomies registered.

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#advanced)

## Advanced

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#disabling-cpts-and-taxonomies)

### Disabling CPTs and Taxonomies

Link copied

Not all ACF users will need this part of the plugin and will prefer to stick with their existing process to register post types and taxonomies. It is possible to [disable post types and taxonomies](https://www.advancedcustomfields.com/resources/acf-settings-enable_post_types/) and remove the feature from the plugin admin.

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#adding-custom-settings-and-tabs)

### Adding Custom Settings and Tabs

Link copied

It is possible for third-party developers to customize the post type and taxonomy edit screens to add custom settings to the UI using the following filters:

- `acf/post_type/render_settings_tab/$tab-key`
- `acf/taxonomy/render_settings_tab/$tab-key`

Use the `acf_render_field_wrap()` function to add settings to post types and taxonomies, as opposed to the `acf_render_field_setting()` function normally used to add settings to fields.

The `acf_render_field_setting()` function assumes the first parameter you supply is an ACF field, which may cause errors. The `acf_render_field_wrap()` function instead creates an input based on a “pseudo-field” array you provide:

```php
add_action('acf/post_type/render_settings_tab/graphql-settings', function ($acf_post_type) {
    acf_render_field_wrap(
        array(
            'label'        => 'Admin Only',
            'instructions' => '',
            'name'         => 'admin_only',
            'prefix'       => 'acf_post_type',
            'value'        => isset( $acf_post_type['admin_only'] ) ? $acf_post_type['admin_only'] : false,
            'type'         => 'true_false',
            'ui'           => 1,
        )
    );
});
```

If you need to also pass the setting to the WordPress core `register_post_type()` function, make sure to use the `acf/post_type/registration_args filter` as well:

```php
add_filter( 'acf/post_type/registration_args', function( $args, $post_type ) {
    if ( isset( $post_type['admin_only'] ) ) {
        $args['admin_only'] = (bool) $post_type['admin_only'];
    }

    return $args;
}, 10, 2 );
```

It is also possible to add custom tabs to the “Advanced Settings” meta box, using the following filters:

- `acf/post_type/additional_settings_tabs`
- `acf/taxonomy/additional_settings_tabs`

For example, to add a new tab called “My Settings” to the post type screen, you’d use:

```php
add_filter( 'acf/post_type/additional_settings_tabs', function ( $tabs ) {
    $tabs['my-settings'] = 'My Settings';

    return $tabs;
} );
```

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

[Link to heading#](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#related)

## Related

Link copied

- Tutorials: [Registering a Custom Post Type](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/)
- Guides: [Registering a Custom Taxonomy](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/)
- Features: [WP REST API Integration](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/)
- Videos: [Creating a Custom Taxonomy with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/)
- : [Frequently Asked Questions](https://www.advancedcustomfields.com/resources/frequently-asked-questions/)

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

[Got it](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/#)