---
url: https://developer.wordpress.org/plugins/hooks/filters
scraped_at: 2025-10-20T03:34:03.416Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/hooks/filters/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Filters


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Hooks](https://developer.wordpress.org/plugins/hooks/)Filters

Search

# Filters

## In this article

Table of Contents

- [Add Filter](https://developer.wordpress.org/plugins/hooks/filters/#add-filter)
  - [Additional Parameters](https://developer.wordpress.org/plugins/hooks/filters/#additional-parameters)
  - [Example](https://developer.wordpress.org/plugins/hooks/filters/#example)

[↑ Back to top](https://developer.wordpress.org/plugins/hooks/filters/#wp--skip-link--target)

**Filters** are one of the two types of [Hooks](https://developer.wordpress.org/plugins/hooks/).

They provide a way for functions to modify data during the execution of WordPress Core, plugins, and themes. They are the counterpart to [Actions](https://developer.wordpress.org/plugins/hooks/actions/).

Unlike [Actions](https://developer.wordpress.org/plugins/hooks/actions/), filters are meant to work in an isolated manner, and should never have [side effects](https://en.wikipedia.org/wiki/Side_effect_(computer_science)) such as affecting global variables and output. Filters expect to have something returned back to them.

## [Add Filter](https://developer.wordpress.org/plugins/hooks/filters/\#add-filter)

The process of adding a filter includes two steps.

First, you need to create a Callback function which will be called when the filter is run. Second, you need to add your Callback function to a hook which will perform the calling of the function.

You will use the [add\_filter()](https://developer.wordpress.org/reference/functions/add_filter/) function, passing at least two parameters:

1. `string $hook_name` which is the name of the filter you’re hooking to, and
2. `callable $callback` the name of your callback function.

The example below will run when the `the_title` filter is executed.

``
[Copy](https://developer.wordpress.org/plugins/hooks/filters/#)

```php
function wporg_filter_title( $title ) {
	return 'The ' . $title . ' was filtered';
}
add_filter( 'the_title', 'wporg_filter_title' );
```

Lets say we have a post title, “Learning WordPress”, the above example will modify it to be “The Learning WordPress was filtered”.

You can refer to the [Hooks](https://developer.wordpress.org/plugins/hooks/) chapter for a list of available hooks.

As you gain more experience, looking through WordPress Core source code will allow you to find the most appropriate hook.

### [Additional Parameters](https://developer.wordpress.org/plugins/hooks/filters/\#additional-parameters)

[add\_filter()](https://developer.wordpress.org/reference/functions/add_filter/) can accept two additional parameters, `int $priority` for the priority given to the callback function, and `int $accepted_args` for the number of arguments that will be passed to the callback function.

For detailed explanation of these parameters please read the article on [Actions](https://developer.wordpress.org/plugins/hooks/actions/).

### [Example](https://developer.wordpress.org/plugins/hooks/filters/\#example)

To add a CSS class to the `<body>` tag when a certain condition is met:

``
[Copy](https://developer.wordpress.org/plugins/hooks/filters/#)

```php
function wporg_css_body_class( $classes ) {
	if ( ! is_admin() ) {
		$classes[] = 'wporg-is-awesome';
	}
	return $classes;
}
add_filter( 'body_class', 'wporg_css_body_class' );
```

First published

September 16, 2014

Last updated

November 17, 2022

[PreviousActionsPrevious: Actions](https://developer.wordpress.org/plugins/hooks/actions/)

[NextCustom HooksNext: Custom Hooks](https://developer.wordpress.org/plugins/hooks/custom-hooks/)

Notifications