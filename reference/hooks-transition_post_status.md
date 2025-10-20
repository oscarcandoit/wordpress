---
url: https://developer.wordpress.org/reference/hooks/transition_post_status
scraped_at: 2025-10-20T03:20:13.523Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/transition_post_status/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

transition\_post\_status


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)transition\_post\_status

Search

# do\_action( ‘transition\_post\_status’, string$new\_status, string$old\_status, WP\_Post$post )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/transition_post_status/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/transition_post_status/#source)
- [Related](https://developer.wordpress.org/reference/hooks/transition_post_status/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/transition_post_status/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/transition_post_status/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/transition_post_status/#wp--skip-link--target)

Fires when a post is transitioned from one status to another.

## [Parameters](https://developer.wordpress.org/reference/hooks/transition_post_status/\#parameters)

`$new_status` string

New post status.

`$old_status` string

Old post status.

`$post` [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)

Post object.

## [Source](https://developer.wordpress.org/reference/hooks/transition_post_status/\#source)

`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/hooks/transition_post_status/#)

```php
do_action( 'transition_post_status', $new_status, $old_status, $post );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/post.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/post.php#L5740) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/post.php#L5740-L5740)

## [Related](https://developer.wordpress.org/reference/hooks/transition_post_status/\#related)

| Used by | Description |
| --- | --- |
| [wp\_transition\_post\_status()](https://developer.wordpress.org/reference/functions/wp_transition_post_status/) `wp-includes/post.php` | Fires actions related to the transitioning of a post’s status. |

## [Changelog](https://developer.wordpress.org/reference/hooks/transition_post_status/\#changelog)

| Version | Description |
| --- | --- |
| [2.3.0](https://developer.wordpress.org/reference/since/2.3.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/transition_post_status/\#user-contributed-notes)

1. [Skip to note 6 content](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-content-2977)



Please note that the name transition\_post\_status is misleading. The hook does not only fire on a post status _transition_ but also when a post is updated while the status is not changed from one to another at all.



So if you wish to really only do stuff on **status transition** and not on regular post updates, you will need to (at least) start with a basic bailout like this:





`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/hooks/transition_post_status/#)

[Copy](https://developer.wordpress.org/reference/hooks/transition_post_status/#)




```php
/**
    * Do stuff only when posts are actually transitioned from one status to another.
    *
    * @param string  $new_status New post status.
    * @param string  $old_status Old post status.
    * @param WP_Post $post       Post object.
    */
function wpdocs_run_on_transition_only( $new_status, $old_status, $post ) {
       if ( $old_status == $new_status )
   		return;

   	// do stuff
}
add_action( 'transition_post_status', 'wpdocs_run_on_transition_only', 10, 3 );
```





For doing stuff when moving **in and out (!) of published status** only, use





`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/hooks/transition_post_status/#)




```php
if ( $old_status == $new_status || $old_status != 'publish' && $new_status != 'publish' )
   	return;

// do stuff
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Ftransition_post_status%2F%3Freplytocom%3D2977%23feedback-editor-2977)

2. [Skip to note 7 content](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-content-244)



Sometimes you only want to fire a callback when a post status is _transitioned_ to ‘publish’, i.e. coming from some other status other than publish (published posts retain the publish status even when updating).



**Only fire a callback when a post status is transitioned to publish**





`wp-includes/post.php`
[Expand code](https://developer.wordpress.org/reference/hooks/transition_post_status/#)

[Copy](https://developer.wordpress.org/reference/hooks/transition_post_status/#)




```php
/**
    * Fire a callback only when my-custom-post-type posts are transitioned to 'publish'.
    *
    * @param string  $new_status New post status.
    * @param string  $old_status Old post status.
    * @param WP_Post $post       Post object.
    */
function wpdocs_run_on_publish_only( $new_status, $old_status, $post ) {
   	if ( ( 'publish' === $new_status && 'publish' !== $old_status )
   		&& 'my-custom-post-type' === $post->post_type
   	) {
   			// do stuff
   	}
}
add_action( 'transition_post_status', 'wpdocs_run_on_publish_only', 10, 3 );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Ftransition_post_status%2F%3Freplytocom%3D244%23feedback-editor-244)

3. [Skip to note 8 content](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-content-1753)



**Example: Check if someone published a custom post type first time.**





`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/hooks/transition_post_status/#)




```php
// Check to see if user posted first time.
add_action( 'transition_post_status', 'some_function', 10, 3 );
function some_function( $new, $old, $post ) {
       if ( ( $new == 'publish' ) && ( $old != 'publish' ) && ( $post->post_type == 'your_post_type' ) ) {
   		// do stuff
   	} else {
   		return;
   	}
}
```







[Show feedback (1)](https://developer.wordpress.org/reference/hooks/transition_post_status/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Ftransition_post_status%2F%3Freplytocom%3D1753%23feedback-editor-1753)



- This does not guarantee that it is the _first_ time the post was published: it will fire if the post was published, changed to a different status, and then published again.



[crstauf](https://profiles.wordpress.org/crstauf/) [5 years ago](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-3824)


4. [Skip to note 9 content](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-content-3712)



If you are looking to hook something on a specific post status change you can also use this hook





`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/hooks/transition_post_status/#)




```php
do_action( "{$old_status}_to_{$new_status}", $post );
```





This could be used for two specific post status. For example if you are looking to hook something when a draft post is published you can use this hook like this,





`wp-includes/post.php`
[Copy](https://developer.wordpress.org/reference/hooks/transition_post_status/#)




```php
    add_action( "draft_to_publish", function( $post ) { //do something here } );
```





Of course this opens up a possibility for so many things and you don’t have to keep relying on ` transition_post_status` which runs even when post status are not changed.





[Show feedback (1)](https://developer.wordpress.org/reference/hooks/transition_post_status/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Ftransition_post_status%2F%3Freplytocom%3D3712%23feedback-editor-3712)



- It’s important to note that using anonymous functions in [add\_action()](https://developer.wordpress.org/reference/functions/add_action/) or [add\_filter()](https://developer.wordpress.org/reference/functions/add_filter/) is in most cases an incredibly bad idea. This would make the code in the functions really hard to get rid of from another plugin or theme. In cases when your code is to be used in other people’s projects, anonymous functions are almost “immune” to being removed through remove\_function() or [remove\_filter()](https://developer.wordpress.org/reference/functions/remove_filter/) and it’s rarely the case that one would look after this effect.



[Vladimir Vassilev](https://profiles.wordpress.org/vloo/) [4 years ago](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-5727)


5. [Skip to note 10 content](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-content-3821)



Status can be one of: publish, future, draft, pending, private





[Show feedback (2)](https://developer.wordpress.org/reference/hooks/transition_post_status/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Ftransition_post_status%2F%3Freplytocom%3D3821%23feedback-editor-3821)



- If there are plugins that introduce new status types, they may also be (untested) run through this hook.



[crstauf](https://profiles.wordpress.org/crstauf/) [5 years ago](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-3825)

- This seems to be incomplete. List from old codex [https://codex.wordpress.org/Post\_Status\_Transitions](https://codex.wordpress.org/Post_Status_Transitions), section with title “The available post statuses are:”



[te-online](https://profiles.wordpress.org/thomasebert/) [3 years ago](https://developer.wordpress.org/reference/hooks/transition_post_status/#comment-5858)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Ftransition_post_status%2F) before being able to contribute a note or feedback.

Notifications