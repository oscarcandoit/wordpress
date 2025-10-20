---
url: https://www.advancedcustomfields.com/resources/local-json
scraped_at: 2025-10-20T02:26:57.678Z
---

# Local JSON

Last updated Sep 28, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/local-json/#overview)

## Overview

Link copied

Local JSON is a helpful feature which saves field groups, post types, taxonomies, and option pages as JSON files within your theme. The idea is similar to caching, and both dramatically speeds up ACF and allows for version control over your field settings!

[Link to heading#](https://www.advancedcustomfields.com/resources/local-json/#getting-started)

## Getting Started

Link copied

To start using the local JSON feature, create a new folder in your theme and name it `acf-json`. This new folder must be writable by the server (in most cases, `755` permissions will work well).

After creating that folder and saving a field group, post type, taxonomy, or options page in the ACF admin, ACF will also save that item to a JSON file in that folder.

Once the JSON file has been created, ACF will load the relevant settings from the file – reducing the number of database calls on page load and improving performance.

[Link to heading#](https://www.advancedcustomfields.com/resources/local-json/#saving-explained)

## Saving Explained

Link copied

Each time you save a field group, post type, taxonomy, or options page, a JSON file will be created (or updated) with the settings for the item being saved. By default, the JSON file will be named using the unique key for that item.

There are several filters that can be used to customize the JSON save path(s). To set a universal save path for all JSON files, use the `acf/settings/save_json` filter:

```php
<?php

function my_acf_json_save_point( $path ) {
    return get_stylesheet_directory() . '/my-custom-folder';
}
add_filter( 'acf/settings/save_json', 'my_acf_json_save_point' );
```

As of ACF 6.2, there are also several modifiers for the `acf/settings/save_json` filter that can be used to specify different paths for different files:

- `acf/settings/save_json/key={$key}` The field group, post type, taxonomy, or UI options page key.
- `acf/settings/save_json/name={$name}` The name of a field group, post type, taxonomy, or UI options page.
- `acf/settings/save_json/type={$post_type}` Can be one of `acf-field-group`, `acf-post-type`, `acf-taxonomy`, or `acf-ui-options-page`.

These filters give you granular control over where a JSON file is saved based on the name, key, or the post type of the item being saved. If multiple paths are a match for the same file, the most specific path will be chosen – i.e., the `acf/settings/save_json/key={$key}` filter will override the `acf/settings/save_json/name={$name}` filter and so on.

For example, you can set all ACF custom post types to save into a specific folder using the following filter:

```php
<?php

function my_acf_cpt_save_folder( $path ) {
    return get_stylesheet_directory() . '/acf-json/post-types';
}
add_filter( 'acf/settings/save_json/type=acf-post-type', 'my_acf_cpt_save_folder' );
```

ACF 6.2 also introduced a new `acf/json/save_paths` filter with two parameters. The first parameter is an array of all the possible save paths for the file being saved, and the second parameter is an array containing all of the settings for the field group, post type, taxonomy, or options page. This allows you to use one function for multiple items and conditionally change the path based on things like the item name:

```php
<?php

function custom_acf_json_save_paths( $paths, $post ) {
    if ( $post['title'] === 'Theme Settings' ) {
        $paths = array( get_stylesheet_directory() . '/options-pages' );
    }

    if ( $post['title'] === 'Theme Settings Fields' ) {
        $paths = array( get_stylesheet_directory() . '/field-groups' );
    }

    return $paths;
}
add_filter( 'acf/json/save_paths', 'custom_acf_json_save_paths', 10, 2 );
```

If you use a custom save path and want ACF to also load files from that path, make sure that you add that path to the `acf/settings/load_json` filter as shown [below](https://www.advancedcustomfields.com/resources/local-json/#loading-explained).

To customize the filename, you can use the new `acf/json/save_file_name` filter. Here’s a quick example of how you can change the filename to match that of the field group, post type, or taxonomy:

```php
<?php

function custom_acf_json_filename( $filename, $post, $load_path ) {
    $filename = str_replace(
        array(
            ' ',
            '_',
        ),
        array(
            '-',
            '-'
        ),
        $post['title']
    );

    $filename = strtolower( $filename ) . '.json';

    return $filename;
}
add_filter( 'acf/json/save_file_name', 'custom_acf_json_filename', 10, 3 );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/local-json/#loading-explained)

## Loading Explained

Link copied

All `.json` files within the `acf-json` folder are loaded during ACF’s initialization procedure. By default, ACF looks for a folder within your theme called `acf-json`. However, this is just one of the load points which can be added.

To add a new load point (folder) for ACF to look in, please add the following code to your theme or plugin.

```php
<?php

function my_acf_json_load_point( $paths ) {
    // Remove the original path (optional).
    unset($paths[0]);

    // Append the new path and return it.
    $paths[] = get_stylesheet_directory() . '/my-custom-folder';

    return $paths;
}
add_filter( 'acf/settings/load_json', 'my_acf_json_load_point' );
```

This filter will allow plugin and theme developers to easily register field groups, post types, taxonomies, or options pages which cannot be edited by clients.

[Link to heading#](https://www.advancedcustomfields.com/resources/local-json/#syncing-changes)

## Syncing Changes

Link copied

The real power of ACF’s local JSON feature is the ability to sync changes. This allows multiple devs to work on a project, use git to push/pull files, and keep all databases synchronized with the latest field groups, post types, taxonomies, and options pages.

Items stored in JSON will be available for sync when either the items do not exist in the database, or when the JSON version contains a higher “modified” value (within the JSON array) than the post modified date recorded in the database.

When items are detected for synchronization, you will see a new tab above the list table where you can select the items to be imported.

[![acf-pro-sync-available](https://www.advancedcustomfields.com/wp-content/uploads/2014/12/acf-pro-sync-available.png)](https://www.advancedcustomfields.com/wp-content/uploads/2014/12/acf-pro-sync-available.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/local-json/#security)

## Security

Link copied

If you wish to hide your JSON files from the public, simply add an empty `index.php` file to your `acf-json` folder to prevent directory listing. WordPress uses the same method to hide the wp-content/themes folder. They like to add a message too 👍.

[Link to heading#](https://www.advancedcustomfields.com/resources/local-json/#indexphp)

#### index.php

Link copied

```php
<?php // Silence is golden.
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

[Link to heading#](https://www.advancedcustomfields.com/resources/local-json/#related)

## Related

Link copied

- Filters: [acf/json/save\_file\_name](https://www.advancedcustomfields.com/resources/acf-json-save_file_name/)
- Guides: [Improving ACF Performance](https://www.advancedcustomfields.com/resources/improving-acf-performance/)
- Guides: [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)
- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Features: [WP REST API Integration](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/)

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

[Got it](https://www.advancedcustomfields.com/resources/local-json/#)