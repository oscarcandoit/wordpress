---
url: https://developer.wordpress.org/reference/hooks/jpeg_quality
scraped_at: 2025-10-20T03:26:34.152Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/jpeg_quality/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

jpeg\_quality


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_Image\_Editor::set\_quality](https://developer.wordpress.org/reference/classes/wp_image_editor/set_quality/)jpeg\_quality

Search

# apply\_filters( ‘jpeg\_quality’, int$quality, string$context )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/jpeg_quality/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/jpeg_quality/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/jpeg_quality/#source)
- [Related](https://developer.wordpress.org/reference/hooks/jpeg_quality/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/jpeg_quality/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/jpeg_quality/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/jpeg_quality/#wp--skip-link--target)

Filters the JPEG compression quality for backward-compatibility.

## [Description](https://developer.wordpress.org/reference/hooks/jpeg_quality/\#description)

Applies only during initial editor instantiation, or when set\_quality() is run manually without the `$quality` argument.

The [WP\_Image\_Editor::set\_quality()](https://developer.wordpress.org/reference/classes/wp_image_editor/set_quality/) method has priority over the filter.

The filter is evaluated under two contexts: ‘image\_resize’, and ‘edit\_image’, (when a JPEG image is saved to file).

## [Parameters](https://developer.wordpress.org/reference/hooks/jpeg_quality/\#parameters)

`$quality` int

Quality level between 0 (low) and 100 (high) of the JPEG.

`$context` string

Context of the filter.

## [Source](https://developer.wordpress.org/reference/hooks/jpeg_quality/\#source)

`wp-includes/class-wp-image-editor.php`
[Copy](https://developer.wordpress.org/reference/hooks/jpeg_quality/#)

```php
$quality = apply_filters( 'jpeg_quality', $quality, 'image_resize' );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-image-editor.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-image-editor.php#L296) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-image-editor.php#L296-L296)

## [Related](https://developer.wordpress.org/reference/hooks/jpeg_quality/\#related)

| Used by | Description |
| --- | --- |
| [wp\_save\_image\_file()](https://developer.wordpress.org/reference/functions/wp_save_image_file/) `wp-admin/includes/image-edit.php` | Saves image to file. |
| [WP\_Image\_Editor::set\_quality()](https://developer.wordpress.org/reference/classes/wp_image_editor/set_quality/) `wp-includes/class-wp-image-editor.php` | Sets Image Compression quality on a 1-100% scale. |

## [Changelog](https://developer.wordpress.org/reference/hooks/jpeg_quality/\#changelog)

| Version | Description |
| --- | --- |
| [2.5.0](https://developer.wordpress.org/reference/since/2.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/jpeg_quality/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/hooks/jpeg_quality/#comment-content-1935)



To change JPEG Compression, temporarily add the below code to functions.php then refresh the site to re-compress all thumbnails on the site.





`wp-includes/class-wp-image-editor.php`
[Copy](https://developer.wordpress.org/reference/hooks/jpeg_quality/#)




```php
function my_prefix_regenerate_thumbnail_quality() {
   	return 80;

}

add_filter( 'jpeg_quality', 'my_prefix_regenerate_thumbnail_quality');
```







[Show feedback (1)](https://developer.wordpress.org/reference/hooks/jpeg_quality/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fjpeg_quality%2F%3Freplytocom%3D1935%23feedback-editor-1935)



- “Refresh(ing) the site” is not going to recompress the images. For this you’ll need to regenerate all thumbnails and derived sizes using a plugin for this purpose.



[theMikeD](https://profiles.wordpress.org/themiked/) [3 years ago](https://developer.wordpress.org/reference/hooks/jpeg_quality/#comment-6022)


2. [Skip to note 5 content](https://developer.wordpress.org/reference/hooks/jpeg_quality/#comment-content-1916)



Snippets should be included here, not hosted elsewhere.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fjpeg_quality%2F%3Freplytocom%3D1916%23feedback-editor-1916)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/hooks/jpeg_quality/#comment-content-1576)



Changing the JPEG compression quality:



[https://generatewp.com/snippet/xNM817E/](https://generatewp.com/snippet/xNM817E/)





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fjpeg_quality%2F%3Freplytocom%3D1576%23feedback-editor-1576)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fjpeg_quality%2F) before being able to contribute a note or feedback.

Notifications