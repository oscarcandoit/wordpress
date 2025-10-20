---
url: https://developer.wordpress.org/block-editor/reference-guides/filters/global-styles-filters
scraped_at: 2025-10-20T03:15:06.698Z
---

[Skip to content](https://developer.wordpress.org/block-editor/reference-guides/filters/global-styles-filters/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Global Styles Filters


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Reference Guides](https://developer.wordpress.org/block-editor/reference-guides/)[Hooks Reference](https://developer.wordpress.org/block-editor/reference-guides/filters/)Global Styles Filters

Search

# Global Styles Filters

[↑ Back to top](https://developer.wordpress.org/block-editor/reference-guides/filters/global-styles-filters/#wp--skip-link--target)

WordPress 6.1 has introduced some server-side filters to hook into the `theme.json` data provided at the different data layers:

- `wp_theme_json_data_default`: hooks into the default data provided by WordPress
- `wp_theme_json_data_blocks`: hooks into the data provided by the blocks
- `wp_theme_json_data_theme`: hooks into the data provided by the theme
- `wp_theme_json_data_user`: hooks into the data provided by the user

Each filter receives an instance of the `WP_Theme_JSON_Data` class with the data for the respective layer. To provide new data, the filter callback needs to use the `update_with( $new_data )` method, where `$new_data` is a valid `theme.json`-like structure. As with any `theme.json`, the new data needs to declare which `version` of the `theme.json` is using, so it can correctly be migrated to the runtime one, should it be different.

_Example:_

This is how to pass a new color palette for the theme and disable the text color UI:

```php
function wpdocs_filter_theme_json_theme( $theme_json ){
    $new_data = array(
        'version'  => 2,
        'settings' => array(
            'color' => array(
                'text'       => false,
                'palette'    => array( /* New palette */
                    array(
                        'slug'  => 'foreground',
                        'color' => 'black',
                        'name'  => __( 'Foreground', 'theme-domain' ),
                    ),
                    array(
                        'slug'  => 'background',
                        'color' => 'white',
                        'name'  => __( 'Background', 'theme-domain' ),
                    ),
                ),
            ),
        ),
    );

    return $theme_json->update_with( $new_data );
}
add_filter( 'wp_theme_json_data_theme', 'wpdocs_filter_theme_json_theme' );

```

First published

September 13, 2022

Last updated

October 30, 2024

Edit article

[Improve it on GitHub: Global Styles Filters](https://github.com/WordPress/gutenberg/edit/trunk/docs/reference-guides/filters/global-styles-filters.md)

[PreviousAutocompletePrevious: Autocomplete](https://developer.wordpress.org/block-editor/reference-guides/filters/autocomplete-filters/)

[NextInteractivity API ReferenceNext: Interactivity API Reference](https://developer.wordpress.org/block-editor/reference-guides/interactivity-api/)

Notifications