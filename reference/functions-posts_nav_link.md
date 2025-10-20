---
url: https://developer.wordpress.org/reference/functions/posts_nav_link
scraped_at: 2025-10-20T03:12:54.521Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/posts_nav_link/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

posts\_nav\_link()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)posts\_nav\_link()

Search

# posts\_nav\_link( string$sep = '', string$prelabel = '', string$nxtlabel = '' )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/posts_nav_link/#parameters)
- [More Information](https://developer.wordpress.org/reference/functions/posts_nav_link/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/posts_nav_link/#source)
- [Related](https://developer.wordpress.org/reference/functions/posts_nav_link/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/posts_nav_link/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/posts_nav_link/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/posts_nav_link/#wp--skip-link--target)

Displays the post pages link navigation for previous and next pages.

## [Parameters](https://developer.wordpress.org/reference/functions/posts_nav_link/\#parameters)

`$sep` stringoptional

Separator for posts navigation links.

Default: `''`

`$prelabel` stringoptional

Label for previous pages.

Default: `''`

`$nxtlabel` stringoptional

Optional Label for next pages.

Default: `''`

## [More Information](https://developer.wordpress.org/reference/functions/posts_nav_link/\#more-information)

For displaying next and previous pages of posts see [next\_posts\_link()](https://developer.wordpress.org/reference/functions/next_posts_link/ "Function Reference/next posts link") and [previous\_posts\_link()](https://codex.wordpress.org/Function_Reference/previous_posts_link "Function Reference/previous posts link").

For displaying next and previous post navigation on individual posts, see [next\_post\_link()](https://developer.wordpress.org/reference/functions/next_post_link/ "Template Tags/next post link") and [previous\_post\_link()](https://developer.wordpress.org/reference/functions/previous_post_link/ "Template Tags/previous post link").

Note: since weblog posts are traditionally listed in reverse chronological order (with most recent posts at the top), there is some ambiguity in the definition of “next page”. WordPress defines “next page” as the “next page _toward the past_“.

## [Source](https://developer.wordpress.org/reference/functions/posts_nav_link/\#source)

`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/posts_nav_link/#)

```php
function posts_nav_link( $sep = '', $prelabel = '', $nxtlabel = '' ) {
	$args = array_filter( compact( 'sep', 'prelabel', 'nxtlabel' ) );
	echo get_posts_nav_link( $args );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L2756) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L2756-L2759)

## [Related](https://developer.wordpress.org/reference/functions/posts_nav_link/\#related)

| Uses | Description |
| --- | --- |
| [get\_posts\_nav\_link()](https://developer.wordpress.org/reference/functions/get_posts_nav_link/) `wp-includes/link-template.php` | Retrieves the post pages link navigation for previous and next pages. |

## [Changelog](https://developer.wordpress.org/reference/functions/posts_nav_link/\#changelog)

| Version | Description |
| --- | --- |
| [0.71](https://developer.wordpress.org/reference/since/0.71/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/posts_nav_link/\#user-contributed-notes)

1. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/posts_nav_link/#comment-content-1177)



**Using Images**





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/posts_nav_link/#)




```php
<?php posts_nav_link( ' ', '<img src="' . esc_attr( get_bloginfo( 'stylesheet_directory' ) . '/images/prev.jpg . ')'" />', '<img src="' . esc_attr( get_bloginfo( 'stylesheet_directory' ) . '/images/next.jpg . ')'" />' ); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fposts_nav_link%2F%3Freplytocom%3D1177%23feedback-editor-1177)

2. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/posts_nav_link/#comment-content-1175)



**Default Usage**



By default, the [posts\_nav\_link()](https://developer.wordpress.org/reference/functions/posts_nav_link/) look like this:



« Previous Page — Next Page »





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/posts_nav_link/#)




```php
<?php posts_nav_link(); ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fposts_nav_link%2F%3Freplytocom%3D1175%23feedback-editor-1175)

3. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/posts_nav_link/#comment-content-1176)



**In Centered DIV**



Displays previous and next page links (“previous page · next page”) centered on the page.





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/posts_nav_link/#)




```php
<div style="text-align:center;">
   	<?php posts_nav_link( ' · ', 'previous page', 'next page' ); ?>
</div>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fposts_nav_link%2F%3Freplytocom%3D1176%23feedback-editor-1176)

4. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/posts_nav_link/#comment-content-1178)



**Kubrick Theme Format**



The Kubrick theme format for posts navigation, could be formatted this way. However, using [posts\_nav\_link()](https://developer.wordpress.org/reference/functions/posts_nav_link/) in this way will result in unintended behavior, such as double stacked next and previous links that link to the incorrect sections.



The Kubrick Theme actually uses [next\_posts\_link()](https://developer.wordpress.org/reference/functions/next_posts_link/) and [previous\_posts\_link()](https://developer.wordpress.org/reference/functions/previous_posts_link/) .



This is poor code and should not be used:





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/posts_nav_link/#)




```php
<div class="navigation">
<div class="alignleft"><?php posts_nav_link( '', '', '&laquo; Previous Entries' ); ?></div>
<div class="alignright"><?php posts_nav_link( '', 'Next Entries &raquo;', '' ); ?></div>
</div>
```





This is better code:





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/posts_nav_link/#)




```php
<div class="navigation">
<div class="alignleft"><?php previous_posts_link( '&laquo; Previous Entries' ); ?></div>
<div class="alignright"><?php next_posts_link( 'Next Entries &raquo;', '' ); ?></div>
</div>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fposts_nav_link%2F%3Freplytocom%3D1178%23feedback-editor-1178)

5. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/posts_nav_link/#comment-content-1179)



You can change the text in each of the links and in the text in between the links.



`You can go back to the previous page or you can go forward to the next page.`





`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/posts_nav_link/#)




```php
<p><?php posts_nav_link( ' or ', 'You can go back to the previous page', 'you can go forward to the next page' ); ?>.</p>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fposts_nav_link%2F%3Freplytocom%3D1179%23feedback-editor-1179)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fposts_nav_link%2F) before being able to contribute a note or feedback.

Notifications