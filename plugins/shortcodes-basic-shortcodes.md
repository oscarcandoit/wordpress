---
url: https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes
scraped_at: 2025-10-20T03:38:09.464Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Basic Shortcodes


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Shortcodes](https://developer.wordpress.org/plugins/shortcodes/)Basic Shortcodes

Search

# Basic Shortcodes

## In this article

Table of Contents

- [Add a Shortcode](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/#add-a-shortcode)
- [Remove a Shortcode](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/#remove-a-shortcode)
- [Check if a Shortcode Exists](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/#check-if-a-shortcode-exists)

[↑ Back to top](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/#wp--skip-link--target)

## [Add a Shortcode](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/\#add-a-shortcode)

It is possible to add your own shortcodes by using the Shortcode API. The process involves registering a callback `$func` to a shortcode `$tag` using `add_shortcode()`.

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/#)

```php
add_shortcode(
    string $tag,
    callable $func
);
```

`[wporg]` is your new shortcode. The use of the shortcode will trigger the `wporg_shortcode` callback function.

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/#)

```php
add_shortcode('wporg', 'wporg_shortcode');
function wporg_shortcode( $atts = [], $content = null) {
    // do something to $content
    // always return
    return $content;
}
```

## [Remove a Shortcode](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/\#remove-a-shortcode)

It is possible to remove shortcodes by using the Shortcode API. The process involves removing a registered `$tag` using [remove\_shortcode()](https://developer.wordpress.org/reference/functions/remove_shortcode/) .

``
[Copy](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/#)

```php
remove_shortcode(
    string $tag
);
```

Make sure that the shortcode have been registered before attempting to remove. Specify a higher priority number for [add\_action()](https://developer.wordpress.org/reference/functions/add_action/) or hook into an action hook that is run later.

## [Check if a Shortcode Exists](https://developer.wordpress.org/plugins/shortcodes/basic-shortcodes/\#check-if-a-shortcode-exists)

To check whether a shortcode has been registered use `shortcode_exists()`.

First published

September 18, 2014

Last updated

November 17, 2022

[PreviousShortcodesPrevious: Shortcodes](https://developer.wordpress.org/plugins/shortcodes/)

[NextEnclosing ShortcodesNext: Enclosing Shortcodes](https://developer.wordpress.org/plugins/shortcodes/enclosing-shortcodes/)

Notifications