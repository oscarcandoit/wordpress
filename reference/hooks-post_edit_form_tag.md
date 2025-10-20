---
url: https://developer.wordpress.org/reference/hooks/post_edit_form_tag
scraped_at: 2025-10-20T03:26:50.639Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

post\_edit\_form\_tag


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)post\_edit\_form\_tag

Search

# do\_action( ‘post\_edit\_form\_tag’, WP\_Post$post )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#source)
- [Changelog](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#wp--skip-link--target)

Fires inside the post editor form tag.

## [Parameters](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/\#parameters)

`$post` [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)

Post object.

## [More Information](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/\#more-information)

Applies to the tag for the default post edit page (which is used for pages and custom post types). It is at the end of the form start tag and before the closing bracket.

`wp-admin/edit-form-advanced.php`
[Copy](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#)

```php
<form name="post" action="post.php" method="post" id="post"<?php do_action('post_edit_form_tag'); ?>>
```

## [Source](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/\#source)

`wp-admin/edit-form-advanced.php`
[Copy](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#)

```php
do_action( 'post_edit_form_tag', $post );

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/edit-form-advanced.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/edit-form-advanced.php#L482) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/edit-form-advanced.php#L482-L482)

## [Changelog](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/\#changelog)

| Version | Description |
| --- | --- |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#comment-content-4633)



Example migrated from Codex:





`wp-admin/edit-form-advanced.php`
[Copy](https://developer.wordpress.org/reference/hooks/post_edit_form_tag/#)




```php
add_action( 'post_edit_form_tag' , 'post_edit_form_tag' );

function post_edit_form_tag( ) {
       echo ' enctype="multipart/form-data"';
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpost_edit_form_tag%2F%3Freplytocom%3D4633%23feedback-editor-4633)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpost_edit_form_tag%2F) before being able to contribute a note or feedback.

Notifications