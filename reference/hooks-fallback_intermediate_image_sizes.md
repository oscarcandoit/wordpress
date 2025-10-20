---
url: https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes
scraped_at: 2025-10-20T03:25:17.239Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

fallback\_intermediate\_image\_sizes


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)fallback\_intermediate\_image\_sizes

Search

# apply\_filters( ‘fallback\_intermediate\_image\_sizes’, string\[\]$fallback\_sizes, array$metadata )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#source)
- [Related](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#wp--skip-link--target)

Filters the image sizes generated for non-image mime types.

## [Parameters](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/\#parameters)

`$fallback_sizes` string\[\]

An array of image size names.

`$metadata` array

Current attachment metadata.

## [Source](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/\#source)

`wp-admin/includes/image.php`
[Copy](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#)

```php
$fallback_sizes = apply_filters( 'fallback_intermediate_image_sizes', $fallback_sizes, $metadata );

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/image.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/image.php#L686) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/image.php#L686-L686)

## [Related](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/\#related)

| Used by | Description |
| --- | --- |
| [wp\_generate\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_generate_attachment_metadata/) `wp-admin/includes/image.php` | Generates attachment meta data and create image sub-sizes for images. |

## [Changelog](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/\#changelog)

| Version | Description |
| --- | --- |
| [4.7.0](https://developer.wordpress.org/reference/since/4.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#comment-content-4651)



By default, when you upload an image such as a png or jpeg to the media library, WordPress generates all the standard image sizes that may be used by a theme, such as ‘thumbnail’ and ‘post-thumbnail’. Including any custom sizes you may have added to your theme using `add_theme_support( 'post-thumbnails' )`, `set_post_thumbnail_size( 250, 250, true );`, `add_image_size( 'small', 500, 500 );`, etc.



But when you upload an image in pdf format, by default WordPress **only** generates the ‘thumbnail’, ‘medium’ and ‘large’ sizes — **not** all the other sizes your theme may use. Here’s a quick fix for that you can put into your theme’s `functions.php`:





`wp-admin/includes/image.php`
[Copy](https://developer.wordpress.org/reference/hooks/fallback_intermediate_image_sizes/#)




```php
// Note for PHP 7 or higher, uses return type declaration
add_filter(
     'fallback_intermediate_image_sizes',
     function ( array $fallback_sizes, array $metadata ) : array {
       return array_merge( $fallback_sizes, array_keys( wp_get_registered_image_subsizes() ) );
     },
10, 2 );
```





WordPress also has hardcoded behavior in `wp-admin/includes/image.php` to override whatever you have set the ‘crop’ parameter to for ‘thumbnail’ to `false`. This is a bug in my opinion because if your theme depends on images being cropped to specific dimensions or aspect ratio, this overrides it for no good reason I can think of. I don’t know of any workaround for this.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Ffallback_intermediate_image_sizes%2F%3Freplytocom%3D4651%23feedback-editor-4651)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Ffallback_intermediate_image_sizes%2F) before being able to contribute a note or feedback.

Notifications