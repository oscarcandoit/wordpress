---
url: https://developer.wordpress.org/reference/functions/get_avatar_url
scraped_at: 2025-10-20T03:24:17.340Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_avatar_url/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_avatar\_url()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_avatar\_url()

Search

# get\_avatar\_url( mixed$id\_or\_email, array$args = null ): string\|false

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/get_avatar_url/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/get_avatar_url/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_avatar_url/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_avatar_url/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_avatar_url/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_avatar_url/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_avatar_url/#wp--skip-link--target)

Retrieves the avatar URL.

## [Parameters](https://developer.wordpress.org/reference/functions/get_avatar_url/\#parameters)

`$id_or_email` mixedrequired

The avatar to retrieve a URL for. Accepts a user ID, Gravatar SHA-256 or MD5 hash, user email, [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/) object, [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) object, or [WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/) object.

`$args` arrayoptional

Arguments to use instead of the default arguments.

- `size` int
Height and width of the avatar in pixels. Default 96.

- `default` string
URL for the default image or a default type. Accepts:



- `'404'` (return a 404 instead of a default image)
- `'retro'` (a 8-bit arcade-style pixelated face)
- `'robohash'` (a robot)
- `'monsterid'` (a monster)
- `'wavatar'` (a cartoon face)
- `'identicon'` (the "quilt", a geometric pattern)
- `'mystery'`, `'mm'`, or `'mysteryman'` (The Oyster Man)
- `'blank'` (transparent GIF)
- `'gravatar_default'` (the Gravatar logo) Default is the value of the `'avatar_default'` option, with a fallback of `'mystery'`.

- `force_default` bool
Whether to always show the default image, never the Gravatar.


Default false.

- `rating` string
What rating to display avatars up to. Accepts:



- `'G'` (suitable for all audiences)
- `'PG'` (possibly offensive, usually for audiences 13 and above)
- `'R'` (intended for adult audiences above 17)
- `'X'` (even more mature than above) Default is the value of the `'avatar_rating'` option.

- `scheme` string
URL scheme to use. See [set\_url\_scheme()](https://developer.wordpress.org/reference/functions/set_url_scheme/) for accepted values.

- `processed_args` array
When the function returns, the value will be the processed/sanitized $args plus a "found\_avatar" guess. Pass as a reference.


Default: `null`

## [Return](https://developer.wordpress.org/reference/functions/get_avatar_url/\#return)

string\|false The URL of the avatar on success, false on failure.

## [Source](https://developer.wordpress.org/reference/functions/get_avatar_url/\#source)

`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_avatar_url/#)

```php
function get_avatar_url( $id_or_email, $args = null ) {
	$args = get_avatar_data( $id_or_email, $args );
	return $args['url'];
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L4321) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L4321-L4324)

## [Related](https://developer.wordpress.org/reference/functions/get_avatar_url/\#related)

| Uses | Description |
| --- | --- |
| [get\_avatar\_data()](https://developer.wordpress.org/reference/functions/get_avatar_data/) `wp-includes/link-template.php` | Retrieves default data about the avatar. |

| Used by | Description |
| --- | --- |
| [get\_block\_editor\_settings()](https://developer.wordpress.org/reference/functions/get_block_editor_settings/) `wp-includes/block-editor.php` | Returns the contextualized block editor settings for a selected editor context. |
| [WP\_Customize\_Manager::get\_lock\_user\_data()](https://developer.wordpress.org/reference/classes/wp_customize_manager/get_lock_user_data/) `wp-includes/class-wp-customize-manager.php` | Gets lock user data. |
| [rest\_get\_avatar\_urls()](https://developer.wordpress.org/reference/functions/rest_get_avatar_urls/) `wp-includes/rest-api.php` | Retrieves the avatar URLs in various sizes. |
| [wp\_check\_locked\_posts()](https://developer.wordpress.org/reference/functions/wp_check_locked_posts/) `wp-admin/includes/misc.php` | Checks lock status for posts displayed on the Posts screen. |
| [wp\_refresh\_post\_lock()](https://developer.wordpress.org/reference/functions/wp_refresh_post_lock/) `wp-admin/includes/misc.php` | Checks lock status on the New/Edit Post screen and refresh the lock. |
| [get\_avatar()](https://developer.wordpress.org/reference/functions/get_avatar/) `wp-includes/pluggable.php` | Retrieves the avatar `<img>` tag for a user, email address, MD5 hash, comment, or post. |

[Show 1 more](https://developer.wordpress.org/reference/functions/get_avatar_url/#) [Show less](https://developer.wordpress.org/reference/functions/get_avatar_url/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_avatar_url/\#changelog)

| Version | Description |
| --- | --- |
| [4.2.0](https://developer.wordpress.org/reference/since/4.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_avatar_url/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/get_avatar_url/#comment-content-2250)



Insert this code to call the avatar of current user.





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_avatar_url/#)




```php
<?php
$user = wp_get_current_user();

if ( $user ) :
   	?>
   	<img src="<?php echo esc_url( get_avatar_url( $user->ID ) ); ?>" />
<?php endif; ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_avatar_url%2F%3Freplytocom%3D2250%23feedback-editor-2250)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/get_avatar_url/#comment-content-3121)



`size` takes only one integer as this function is meant to always return a square image.





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_avatar_url/#)




```php
get_avatar_url($user->ID, ['size' => '51']);
```





Example to build a responsive user image:





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_avatar_url/#)




```php
<picture>
     <source srcset="<?php print get_avatar_url($user->ID, ['size' => '51']); ?>" media="(min-width: 992px)"/>
     <img src="<?php print get_avatar_url($user->ID, ['size' => '40']); ?>"/>
</picture>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_avatar_url%2F%3Freplytocom%3D3121%23feedback-editor-3121)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/get_avatar_url/#comment-content-2102)



You can use get\_avatar\_url to create a dynamic favicon from the user’s avatar, this useful when creating a custom user profile,





`wp-includes/link-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_avatar_url/#)

[Copy](https://developer.wordpress.org/reference/functions/get_avatar_url/#)




```php
&lt;link rel="shortcut icon" href="&lt;?php echo get_avatar_url($user-&gt;ID,array('width'=&gt;'16','height'=&gt;'16')); ?&gt;" /&gt;
</code>

If the profile page uses the user's login, then you can obtain the user ID, where the user's login name is the last item in the request uri,

<code>
&lt;?php
$permalink = $_SERVER['REQUEST_URI'];

$username = explode("/",$permalink)[count(explode("/",$permalink))-1];

$user = get_user_by('login',$username);
?&gt;
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_avatar_url%2F%3Freplytocom%3D2102%23feedback-editor-2102)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_avatar_url%2F) before being able to contribute a note or feedback.

Notifications