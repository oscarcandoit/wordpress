---
url: https://developer.wordpress.org/reference/hooks/login_redirect
scraped_at: 2025-10-20T03:24:26.649Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/login_redirect/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

login\_redirect


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)login\_redirect

Search

# apply\_filters( ‘login\_redirect’, string$redirect\_to, string$requested\_redirect\_to, WP\_User\|WP\_Error$user )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/login_redirect/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/login_redirect/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/login_redirect/#source)
- [Changelog](https://developer.wordpress.org/reference/hooks/login_redirect/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/login_redirect/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/login_redirect/#wp--skip-link--target)

Filters the login redirect URL.

## [Parameters](https://developer.wordpress.org/reference/hooks/login_redirect/\#parameters)

`$redirect_to` string

The redirect destination URL.

`$requested_redirect_to` string

The requested redirect destination URL passed as a parameter.

`$user` [WP\_User](https://developer.wordpress.org/reference/classes/wp_user/)\|[WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)

[WP\_User](https://developer.wordpress.org/reference/classes/wp_user/) object if login was successful, [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) object otherwise.

## [More Information](https://developer.wordpress.org/reference/hooks/login_redirect/\#more-information)

The `$current_user` global may not be available at the time this filter is run. So you should use the `$user` parameter passed to this filter.

## [Source](https://developer.wordpress.org/reference/hooks/login_redirect/\#source)

`wp-login.php`
[Copy](https://developer.wordpress.org/reference/hooks/login_redirect/#)

```php
$redirect_to = apply_filters( 'login_redirect', $redirect_to, $requested_redirect_to, $user );

```

[View all references](https://developer.wordpress.org/reference/files/wp-login.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-login.php#L1360) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-login.php#L1360-L1360)

## [Changelog](https://developer.wordpress.org/reference/hooks/login_redirect/\#changelog)

| Version | Description |
| --- | --- |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/login_redirect/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/hooks/login_redirect/#comment-content-2074)



Examples



This example redirects admins to the dashboard and other users to the homepage. Make sure you use add\_filter outside of [is\_admin()](https://developer.wordpress.org/reference/functions/is_admin/) , since that function is not available when the filter is called.





`wp-login.php`
[Expand code](https://developer.wordpress.org/reference/hooks/login_redirect/#)

[Copy](https://developer.wordpress.org/reference/hooks/login_redirect/#)




```php
/**
    * Redirect user after successful login.
    *
    * @param string $redirect_to URL to redirect to.
    * @param string $request URL the user is coming from.
    * @param object $user Logged user's data.
    * @return string
    */
function my_login_redirect( $redirect_to, $request, $user ) {
   	//is there a user to check?
   	if ( isset( $user->roles ) && is_array( $user->roles ) ) {
   		//check for admins
   		if ( in_array( 'administrator', $user->roles ) ) {
   			// redirect them to the default place
   			return $redirect_to;
   		} else {
   			return home_url();
   		}
   	} else {
   		return $redirect_to;
   	}
}

add_filter( 'login_redirect', 'my_login_redirect', 10, 3 );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flogin_redirect%2F%3Freplytocom%3D2074%23feedback-editor-2074)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/hooks/login_redirect/#comment-content-2075)



Notes



You can register the login\_redirect filter to use all 3 parameters like this:





`wp-login.php`
[Copy](https://developer.wordpress.org/reference/hooks/login_redirect/#)




```php
<?php add_filter( 'login_redirect', 'filter_function_name', 10, 3 ); ?>
```





In the example, ‘filter\_function\_name’ is the function WordPress should call during the login process. Note that filter\_function\_name should be unique function name. It cannot match any other function name already declared.



The $current\_user global may not be available at the time this filter is run. So you should use the $user global or the $user parameter passed to this filter.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flogin_redirect%2F%3Freplytocom%3D2075%23feedback-editor-2075)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/hooks/login_redirect/#comment-content-4854)



Example Migrated from Codex:



Redirect all logins to the homepage with an anonymous function (php 5.3+).





`wp-login.php`
[Copy](https://developer.wordpress.org/reference/hooks/login_redirect/#)




```php
add_filter( 'login_redirect', function( $url, $query, $user ) {
   	return home_url();
}, 10, 3 );
```







[Show feedback (1)](https://developer.wordpress.org/reference/hooks/login_redirect/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flogin_redirect%2F%3Freplytocom%3D4854%23feedback-editor-4854)



- Super useful, thank you!



[MetalMusicMan](https://profiles.wordpress.org/metalmusicman/) [4 years ago](https://developer.wordpress.org/reference/hooks/login_redirect/#comment-5719)


4. [Skip to note 8 content](https://developer.wordpress.org/reference/hooks/login_redirect/#comment-content-3848)





`wp-login.php`
[Expand code](https://developer.wordpress.org/reference/hooks/login_redirect/#)

[Copy](https://developer.wordpress.org/reference/hooks/login_redirect/#)




```php
<?php

/**
    * WordPress function for redirecting users on login based on user role
    */
function wpdocs_my_login_redirect( $url, $request, $user ) {
       if ( $user && is_object( $user ) && is_a( $user, 'WP_User' ) ) {
           if ( $user->has_cap( 'administrator' ) ) {
               $url = admin_url();
           } else {
               $url = home_url( '/members-only/' );
           }
       }
       return $url;
}

add_filter( 'login_redirect', 'wpdocs_my_login_redirect', 10, 3 );
```





Thanks WP Scholar : [https://wpscholar.com/blog/wordpress-user-login-redirect/](https://wpscholar.com/blog/wordpress-user-login-redirect/) :D





[Show feedback (1)](https://developer.wordpress.org/reference/hooks/login_redirect/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flogin_redirect%2F%3Freplytocom%3D3848%23feedback-editor-3848)



- `$user->has_cap()` to check a role is discouraged as it may produce unreliable results.



[Chad Butler](https://profiles.wordpress.org/cbutlerjr/) [5 years ago](https://developer.wordpress.org/reference/hooks/login_redirect/#comment-4693)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Flogin_redirect%2F) before being able to contribute a note or feedback.

Notifications