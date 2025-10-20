---
url: https://developer.wordpress.org/reference/functions/add_feed
scraped_at: 2025-10-20T03:21:50.272Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/add_feed/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

add\_feed()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)add\_feed()

Search

# add\_feed( string$feedname, callable$callback ): string

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/add_feed/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/add_feed/#return)
- [More Information](https://developer.wordpress.org/reference/functions/add_feed/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/add_feed/#source)
- [Related](https://developer.wordpress.org/reference/functions/add_feed/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/add_feed/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/add_feed/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/add_feed/#wp--skip-link--target)

Adds a new feed type like /atom1/.

## [Parameters](https://developer.wordpress.org/reference/functions/add_feed/\#parameters)

`$feedname` stringrequired

Feed name. Should not start with `'_'`.

`$callback` callablerequired

Callback to run on feed display.

## [Return](https://developer.wordpress.org/reference/functions/add_feed/\#return)

string Feed action name.

## [More Information](https://developer.wordpress.org/reference/functions/add_feed/\#more-information)

Requires one-time use of [flush\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/flush_rules/ "Rewrite API/flush rules") to take effect.

`$feedname` parameter should not start with ‘ `_`‘. Please refer [#59945](https://core.trac.wordpress.org/ticket/59945).

## [Source](https://developer.wordpress.org/reference/functions/add_feed/\#source)

`wp-includes/rewrite.php`
[Expand code](https://developer.wordpress.org/reference/functions/add_feed/#)

[Copy](https://developer.wordpress.org/reference/functions/add_feed/#)

```php
function add_feed( $feedname, $callback ) {
	global $wp_rewrite;

	if ( ! in_array( $feedname, $wp_rewrite->feeds, true ) ) {
		$wp_rewrite->feeds[] = $feedname;
	}

	$hook = 'do_feed_' . $feedname;

	// Remove default function hook.
	remove_action( $hook, $hook );

	add_action( $hook, $callback, 10, 2 );

	return $hook;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/rewrite.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/rewrite.php#L251) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/rewrite.php#L251-L266)

## [Related](https://developer.wordpress.org/reference/functions/add_feed/\#related)

| Uses | Description |
| --- | --- |
| [remove\_action()](https://developer.wordpress.org/reference/functions/remove_action/) `wp-includes/plugin.php` | Removes a callback function from an action hook. |
| [add\_action()](https://developer.wordpress.org/reference/functions/add_action/) `wp-includes/plugin.php` | Adds a callback function to an action hook. |

## [Changelog](https://developer.wordpress.org/reference/functions/add_feed/\#changelog)

| Version | Description |
| --- | --- |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/add_feed/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/add_feed/#comment-content-2086)



When a new custom feed is added, the endpoint will render using a \`Content-Type: application/octet-stream; charset=UTF-8\` by default. It would be useful to document working with content types in combination with [add\_feed()](https://developer.wordpress.org/reference/functions/add_feed/) .



For example either:





`wp-includes/rewrite.php`
[Copy](https://developer.wordpress.org/reference/functions/add_feed/#)




```php
function add_custom_feed() {
   	add_feed( 'custom', 'render_custom_feed' );
}
add_action( 'init', 'add_custom_feed' );

function render_custom_feed() {
   	header( 'Content-Type: application/rss+xml' );
   	echo 'aye!';
}
```





or:





`wp-includes/rewrite.php`
[Expand code](https://developer.wordpress.org/reference/functions/add_feed/#)

[Copy](https://developer.wordpress.org/reference/functions/add_feed/#)




```php
function add_custom_feed() {
   	add_feed( 'custom', 'render_custom_feed' );
}
add_action( 'init', 'add_custom_feed' );


function custom_feed_content_type( $content_type, $type ) {
   	if( 'custom' == $type ) {
   		$content_type = 'application/rss+xml';
   	}
   	return $content_type;
}
add_filter( 'feed_content_type', 'custom_feed_content_type', 10, 2 );

function render_custom_feed() {
   	echo 'aye!';
}
```





will work.



See: [https://core.trac.wordpress.org/ticket/36334](https://core.trac.wordpress.org/ticket/36334)





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_feed%2F%3Freplytocom%3D2086%23feedback-editor-2086)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/add_feed/#comment-content-3905)



**Usage of [add\_feed()](https://developer.wordpress.org/reference/functions/add_feed/)**





`wp-includes/rewrite.php`
[Copy](https://developer.wordpress.org/reference/functions/add_feed/#)




```php
function wpdocs_add_mwb_feed() {
       add_feed( 'mwbfeed', 'wpdocs_makewebbetter_feed' );
}
add_action( 'init', 'wpdocs_add_mwb_feed' );

function wpdocs_makewebbetter_feed() {
       add_filter( 'pre_option_rss_use_excerpt', '__return_zero' );
       load_template( PATHTEMPLATEFILE . '/feeds/a-feed-template.php' );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_feed%2F%3Freplytocom%3D3905%23feedback-editor-3905)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/add_feed/#comment-content-4237)



**RSS Feed based on custom WP Query with parameters**





`wp-includes/rewrite.php`
[Expand code](https://developer.wordpress.org/reference/functions/add_feed/#)

[Copy](https://developer.wordpress.org/reference/functions/add_feed/#)




```php
add_action( 'init', 'wpdocs_custom_feed_rss2' );
function wpdocs_custom_feed_rss2() {

       // Create your feed name like this : https://yoursite.com/wpdocs_custom?tag=test
       add_feed( 'wpdocs_custom', 'wpdocs_change_main_query' );
       function wpdocs_change_main_query() {

           // Set right headers for RSS Feed
           header( 'Content-Type: application/rss+xml' );

           // Get main WP Query
           global $wp_query;

           // Get parameters in url
           if ( ! empty( $_GET['tag'] ) ) :
               $tag = $_GET['tag'];
           endif;

           // Overwrite main WP Query with yours
           $wp_query = new WP_Query(
               array(
                   'post_type' => 'any',
                   'fields'    => 'ids',
                   'tag'       => $tag,
               )
           );

           // Use the basic template to load your custom RSS Feed
           get_template_part( 'feed', 'rss2' );
       }
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_feed%2F%3Freplytocom%3D4237%23feedback-editor-4237)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/add_feed/#comment-content-7071)



The **Feed name Parameters $feedname**(required) should not start with **\`\_\`** if it start with this then we will recieve the **wp\_die** error message.





`wp-includes/rewrite.php`
[Copy](https://developer.wordpress.org/reference/functions/add_feed/#)




```php
function feed2_callback( $is_comment_feed, $feed ) {
   	header( 'Content-Type: application/xml; charset=UTF-8', true );
   	echo '';
?>

   	Test

<?php
}

add_feed( '_feed2', 'feed2_callback' );
```





Next, update the rewrite rule and access [http://localhost/\_feed2](http://localhost/_feed2), which will return **wp\_die** with **404** status.



This is not a problem with the code I tried, but because the “\_” at the beginning of the feed name is removed in the do\_feed function.





`wp-includes/rewrite.php`
[Copy](https://developer.wordpress.org/reference/functions/add_feed/#)




```php
function do_feed() {
   	global $wp_query;

   	$feed = get_query_var( 'feed' );

   	// Remove the pad, if present.
   	$feed = preg_replace( '/^_+/', '', $feed );
```





This process results in an action name of `'do_feed_' . 'feed2'` when `$feed` is `'_feed2'`.



Since this is not done in the `add_feed` function and the action name specified in the `add_action` function is `'do_feed_' . '_feed2'`, since the two action names do not match, which resulting in the error indicated in the response.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_feed%2F%3Freplytocom%3D7071%23feedback-editor-7071)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadd_feed%2F) before being able to contribute a note or feedback.

Notifications