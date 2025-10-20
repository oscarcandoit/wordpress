---
url: https://developer.wordpress.org/plugins/hooks/custom-hooks
scraped_at: 2025-10-20T04:48:13.627Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/hooks/custom-hooks/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Custom Hooks


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Hooks](https://developer.wordpress.org/plugins/hooks/)Custom Hooks

Search

# Custom Hooks

## In this article

Table of Contents

- [Create a Hook](https://developer.wordpress.org/plugins/hooks/custom-hooks/#create-a-hook)
- [Add a Callback to the Hook](https://developer.wordpress.org/plugins/hooks/custom-hooks/#add-a-callback-to-the-hook)
- [Naming Conflicts](https://developer.wordpress.org/plugins/hooks/custom-hooks/#naming-conflicts)
- [Examples](https://developer.wordpress.org/plugins/hooks/custom-hooks/#examples)
  - [Extensible Action: Settings Form](https://developer.wordpress.org/plugins/hooks/custom-hooks/#extensible-action-settings-form)
  - [Extensible Filter: Custom Post Type](https://developer.wordpress.org/plugins/hooks/custom-hooks/#extensible-filter-custom-post-type)

[↑ Back to top](https://developer.wordpress.org/plugins/hooks/custom-hooks/#wp--skip-link--target)

An important, but often overlooked practice is using custom hooks in your plugin so that other developers can extend and modify it.

Custom hooks are created and called in the same way that WordPress Core hooks are.

## [Create a Hook](https://developer.wordpress.org/plugins/hooks/custom-hooks/\#create-a-hook)

To create a custom hook, use `[do\_action()](https://developer.wordpress.org/reference/functions/do_action/)` for [Actions](https://developer.wordpress.org/plugins/hooks/actions/) and `[apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/)` for [Filters](https://developer.wordpress.org/plugins/hooks/filters/).

We recommend using \` [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) \` on any text that is output to the browser. Particularly on the frontend.

This makes it easier for plugins to be modified according to the user’s needs.

## [Add a Callback to the Hook](https://developer.wordpress.org/plugins/hooks/custom-hooks/\#add-a-callback-to-the-hook)

To add a callback function to a custom hook, use `[add\_action()](https://developer.wordpress.org/reference/functions/add_action/)` for [Actions](https://developer.wordpress.org/plugins/hooks/actions/) and `[add\_filter()](https://developer.wordpress.org/reference/functions/add_filter/)` for [Filters](https://developer.wordpress.org/plugins/hooks/filters/).

## [Naming Conflicts](https://developer.wordpress.org/plugins/hooks/custom-hooks/\#naming-conflicts)

Naming conflicts (“collisions”) occur when two developers use the same hook name for completely different purposes. This leads to difficult to find bugs. So it’s important to prefix your hook names with a unique string to avoid hook name collisions.collisions with other plugins.

For example, a filter named `email_body` is generic enough that two or more developers could use this hook in different plugins for different purposes. So to avoid this, a prefix is added. For example, functions used as examples in this handbook use `wporg_` as the prefix.

When you choose your prefix, you can use your company name, your wp handle, the plugin name, anything you like really. The goal is to make it unique so choose wisely.

## [Examples](https://developer.wordpress.org/plugins/hooks/custom-hooks/\#examples)

### [Extensible Action: Settings Form](https://developer.wordpress.org/plugins/hooks/custom-hooks/\#extensible-action-settings-form)

If your plugin adds a settings form to the Administrative Panels, you can use Actions to allow other plugins to add their own settings to it.

``
[Copy](https://developer.wordpress.org/plugins/hooks/custom-hooks/#)

```php
    do_action( 'wporg_after_settings_page_html' );
```

Now another plugin can register a callback function for the `wporg_after_settings_page_html` hook and inject new settings:

``
[Copy](https://developer.wordpress.org/plugins/hooks/custom-hooks/#)

```php
add_action( 'wporg_after_settings_page_html', 'myprefix_add_settings' );
```

Note that because this is an action, no value is returned. Also note that since no priority is given, it will run at default priority 10.

### [Extensible Filter: Custom Post Type](https://developer.wordpress.org/plugins/hooks/custom-hooks/\#extensible-filter-custom-post-type)

In this example, when the new post type is registered, the parameters that define it are passed through a filter, so another plugin can change them before the post type is created.

``
[Copy](https://developer.wordpress.org/plugins/hooks/custom-hooks/#)

```php
function wporg_create_post_type() {
    $post_type_params = [/* ... */];

    register_post_type(
        'post_type_slug',
        apply_filters( 'wporg_post_type_params', $post_type_params )
    );
}
```

Now another plugin can register a callback function for the `wporg_post_type_params` hook and change post type parameters:

``
[Copy](https://developer.wordpress.org/plugins/hooks/custom-hooks/#)

```php
function myprefix_change_post_type_params( $post_type_params ) {
	$post_type_params['hierarchical'] = true;
	return $post_type_params;
}
add_filter( 'wporg_post_type_params', 'myprefix_change_post_type_params' );
```

Note that filters filters take data, modify it, and return it. So the code called ( `myprefix_change_post_type_params` ) doesn’t output anything using echo or html, or anything else directly to the screen. Also note that the retuned value is used directly by `register_post_type` without being assigned to a variable first. This is simple to skip that extra (an unnecessary) step.

Also note that since no priority is given, it will run at default priority 10. And since there is no value for the number of parameters expected, the default of one is assumed.

First published

September 16, 2014

Last updated

March 20, 2025

[PreviousFiltersPrevious: Filters](https://developer.wordpress.org/plugins/hooks/filters/)

[NextAdvanced TopicsNext: Advanced Topics](https://developer.wordpress.org/plugins/hooks/advanced-topics/)

Notifications