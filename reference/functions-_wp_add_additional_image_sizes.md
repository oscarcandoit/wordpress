---
url: https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes
scraped_at: 2025-10-20T03:18:44.296Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

\_wp\_add\_additional\_image\_sizes()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)\_wp\_add\_additional\_image\_sizes()

Search

# \_wp\_add\_additional\_image\_sizes()

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#description)
- [Source](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#source)
- [Changelog](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#wp--skip-link--target)

This function’s access is marked private. This means it is not intended for use by plugin or theme developers, only in other core functions. It is listed here for completeness.

Adds additional default image sub-sizes.

## [Description](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/\#description)

These sizes are meant to enhance the way WordPress displays images on the front-end on larger, high-density devices. They make it possible to generate more suitable `srcset` and `sizes` attributes when the users upload large images.

The sizes can be changed or removed by themes and plugins but that is not recommended.

The size "names" reflect the image dimensions, so changing the sizes would be quite misleading.

## [Source](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/\#source)

`wp-includes/media.php`
[Copy](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#)

```php
}

/**
 * Tries to convert an attachment URL into a post ID.
 *
 * @since 4.0.0

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/media.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/media.php#L5471) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/media.php#L5471-L5476)

## [Changelog](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/\#changelog)

| Version | Description |
| --- | --- |
| [5.3.0](https://developer.wordpress.org/reference/since/5.3.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#comment-content-6722)



To remove those two image sizes you can use the code below:





`wp-includes/media.php`
[Copy](https://developer.wordpress.org/reference/functions/_wp_add_additional_image_sizes/#)




```php
add_action( 'init', 'wpdocs_remove_default_additional_image_sizes' );
function wpdocs_remove_default_additional_image_sizes() {
       remove_image_size( '1536x1536' );
       remove_image_size( '2048x2048' );
}
```





Code can be added to `functions.php` file of the theme.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2F_wp_add_additional_image_sizes%2F%3Freplytocom%3D6722%23feedback-editor-6722)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2F_wp_add_additional_image_sizes%2F) before being able to contribute a note or feedback.

Notifications