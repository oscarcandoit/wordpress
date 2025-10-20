---
url: https://developer.wordpress.org/reference/functions/wp_login_url
scraped_at: 2025-10-20T03:27:15.931Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_login_url/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_login\_url()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_login\_url()

Search

# wp\_login\_url( string$redirect = '', bool$force\_reauth = false ): string

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/wp_login_url/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_login_url/#return)
- [More Information](https://developer.wordpress.org/reference/functions/wp_login_url/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/wp_login_url/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_login_url/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_login_url/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_login_url/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_login_url/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_login_url/#wp--skip-link--target)

Retrieves the login URL.

## [Parameters](https://developer.wordpress.org/reference/functions/wp_login_url/\#parameters)

`$redirect` stringoptional

Path to redirect to on log in.

Default: `''`

`$force_reauth` booloptional

Whether to force reauthorization, even if a cookie is present.

Default: `false`

## [Return](https://developer.wordpress.org/reference/functions/wp_login_url/\#return)

string The login URL. Not HTML-encoded.

## [More Information](https://developer.wordpress.org/reference/functions/wp_login_url/\#more-information)

$redirect argument **must** be absolute, such as [http://example.com/mypage/](http://example.com/mypage/). For best results, use site\_url( ‘/mypage/ ‘ ).

## [Source](https://developer.wordpress.org/reference/functions/wp_login_url/\#source)

`wp-includes/general-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_login_url/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_login_url/#)

```php
function wp_login_url( $redirect = '', $force_reauth = false ) {
	$login_url = site_url( 'wp-login.php', 'login' );

	if ( ! empty( $redirect ) ) {
		$login_url = add_query_arg( 'redirect_to', urlencode( $redirect ), $login_url );
	}

	if ( $force_reauth ) {
		$login_url = add_query_arg( 'reauth', '1', $login_url );
	}

	/**
	 * Filters the login URL.
	 *
	 * @since 2.8.0
	 * @since 4.2.0 The `$force_reauth` parameter was added.
	 *
	 * @param string $login_url    The login URL. Not HTML-encoded.
	 * @param string $redirect     The path to redirect to on login, if supplied.
	 * @param bool   $force_reauth Whether to force reauthorization, even if a cookie is present.
	 */
	return apply_filters( 'login_url', $login_url, $redirect, $force_reauth );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/general-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/general-template.php#L446) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/general-template.php#L446-L468)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_login_url/\#hooks)

[apply\_filters( ‘login\_url’, string$login\_url, string$redirect, bool$force\_reauth )](https://developer.wordpress.org/reference/hooks/login_url/)

Filters the login URL.

## [Related](https://developer.wordpress.org/reference/functions/wp_login_url/\#related)

| Uses | Description |
| --- | --- |
| [site\_url()](https://developer.wordpress.org/reference/functions/site_url/) `wp-includes/link-template.php` | Retrieves the URL for the current site where WordPress application files (e.g. wp-blog-header.php or the wp-admin/ folder) are accessible. |
| [add\_query\_arg()](https://developer.wordpress.org/reference/functions/add_query_arg/) `wp-includes/functions.php` | Retrieves a modified URL query string. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

[Show 1 more](https://developer.wordpress.org/reference/functions/wp_login_url/#) [Show less](https://developer.wordpress.org/reference/functions/wp_login_url/#)

| Used by | Description |
| --- | --- |
| [is\_login()](https://developer.wordpress.org/reference/functions/is_login/) `wp-includes/load.php` | Determines whether the current request is for the login screen. |
| [WP\_Recovery\_Mode\_Link\_Service::handle\_begin\_link()](https://developer.wordpress.org/reference/classes/wp_recovery_mode_link_service/handle_begin_link/) `wp-includes/class-wp-recovery-mode-link-service.php` | Enters recovery mode when the user hits wp-login.php with a valid recovery mode link. |
| [WP\_Recovery\_Mode\_Link\_Service::get\_recovery\_mode\_begin\_url()](https://developer.wordpress.org/reference/classes/wp_recovery_mode_link_service/get_recovery_mode_begin_url/) `wp-includes/class-wp-recovery-mode-link-service.php` | Gets a URL to begin recovery mode. |
| [wp\_admin\_bar\_recovery\_mode\_menu()](https://developer.wordpress.org/reference/functions/wp_admin_bar_recovery_mode_menu/) `wp-includes/admin-bar.php` | Adds a link to exit recovery mode when Recovery Mode is active. |
| [wp\_recovery\_mode\_nag()](https://developer.wordpress.org/reference/functions/wp_recovery_mode_nag/) `wp-admin/includes/update.php` | Displays a notice when the user is in recovery mode. |
| [wp\_send\_user\_request()](https://developer.wordpress.org/reference/functions/wp_send_user_request/) `wp-includes/user.php` | Send a confirmation request email to confirm an action. |
| [WP\_Customize\_Manager::customize\_pane\_settings()](https://developer.wordpress.org/reference/classes/wp_customize_manager/customize_pane_settings/) `wp-includes/class-wp-customize-manager.php` | Prints JavaScript settings for parent window. |
| [confirm\_another\_blog\_signup()](https://developer.wordpress.org/reference/functions/confirm_another_blog_signup/) `wp-signup.php` | Shows a message confirming that the new site has been created. |
| [network\_step2()](https://developer.wordpress.org/reference/functions/network_step2/) `wp-admin/includes/network.php` | Prints step 2 for Network installation process. |
| [wp\_new\_blog\_notification()](https://developer.wordpress.org/reference/functions/wp_new_blog_notification/) `wp-admin/includes/upgrade.php` | Notifies the site admin that the installation of WordPress is complete. |
| [wp\_new\_user\_notification()](https://developer.wordpress.org/reference/functions/wp_new_user_notification/) `wp-includes/pluggable.php` | Emails login credentials to a newly-registered user. |
| [auth\_redirect()](https://developer.wordpress.org/reference/functions/auth_redirect/) `wp-includes/pluggable.php` | Checks if a user is logged in, if not it redirects them to the login page. |
| [wp\_loginout()](https://developer.wordpress.org/reference/functions/wp_loginout/) `wp-includes/general-template.php` | Displays the Log In/Out link. |
| [wp\_auth\_check\_html()](https://developer.wordpress.org/reference/functions/wp_auth_check_html/) `wp-includes/functions.php` | Outputs the HTML that shows the wp-login dialog when the user is no longer logged in. |
| [register\_new\_user()](https://developer.wordpress.org/reference/functions/register_new_user/) `wp-includes/user.php` | Handles registering a new user. |
| [wp\_redirect\_admin\_locations()](https://developer.wordpress.org/reference/functions/wp_redirect_admin_locations/) `wp-includes/canonical.php` | Redirects a variety of shorthand URLs to the admin. |
| [wpmu\_welcome\_user\_notification()](https://developer.wordpress.org/reference/functions/wpmu_welcome_user_notification/) `wp-includes/ms-functions.php` | Notifies a user that their account activation has been successful. |
| [wpmu\_validate\_user\_signup()](https://developer.wordpress.org/reference/functions/wpmu_validate_user_signup/) `wp-includes/ms-functions.php` | Sanitizes and validates data required for a user sign-up. |
| [wp\_xmlrpc\_server::initialise\_blog\_option\_info()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/initialise_blog_option_info/) `wp-includes/class-wp-xmlrpc-server.php` | Sets up blog options property. |
| [get\_post\_reply\_link()](https://developer.wordpress.org/reference/functions/get_post_reply_link/) `wp-includes/comment-template.php` | Retrieves HTML content for reply to post link. |
| [comment\_form()](https://developer.wordpress.org/reference/functions/comment_form/) `wp-includes/comment-template.php` | Outputs a complete commenting form for use within a template. |
| [get\_comment\_reply\_link()](https://developer.wordpress.org/reference/functions/get_comment_reply_link/) `wp-includes/comment-template.php` | Retrieves HTML content for reply to comment link. |

[Show 17 more](https://developer.wordpress.org/reference/functions/wp_login_url/#) [Show less](https://developer.wordpress.org/reference/functions/wp_login_url/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_login_url/\#changelog)

| Version | Description |
| --- | --- |
| [2.7.0](https://developer.wordpress.org/reference/since/2.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_login_url/\#user-contributed-notes)

1. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/wp_login_url/#comment-content-1185)



**Login and Redirect to Current Page**





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_login_url/#)




```php
<a href="<?php echo esc_url( wp_login_url( get_permalink() ) ); ?>" alt="<?php esc_attr_e( 'Login', 'textdomain' ); ?>">
   	<?php _e( 'Login', 'textdomain' ); ?>
</a>
```







[Show feedback (1)](https://developer.wordpress.org/reference/functions/wp_login_url/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_login_url%2F%3Freplytocom%3D1185%23feedback-editor-1185)



- Thanks for the snippets , I think a tag does’nt have alt attribute , you can use title instead.



[dwyall](https://profiles.wordpress.org/dwyall/) [1 year ago](https://developer.wordpress.org/reference/functions/wp_login_url/#comment-7168)


2. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/wp_login_url/#comment-content-3577)



For the [redirect example to the current URL via `get_permalink()`](https://developer.wordpress.org/reference/functions/wp_login_url/#comment-1185) above, note that if the request is a 404, `get_permalink()` will return `false`, so you may want to grab the actual URL instead.



A scenario where it could be useful to still redirect to your current URL even if it was a 404, would be if the current URL was a private post, and your user was not yet logged-in – hence ended up on a 404.



In that case, if you show them a login link, they should be redirected back to the current URL (i.e. the private post), so that they finally can access it.





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_login_url/#)




```php
<?php $current_url = home_url( add_query_arg( [], $GLOBALS['wp']->request ) ); ?>
<a href="<?php echo esc_url( wp_login_url( $current_url )  ); ?>"><?php _e( 'Log in' ) ?></a>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_login_url%2F%3Freplytocom%3D3577%23feedback-editor-3577)

3. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/wp_login_url/#comment-content-1184)



**Basic Example**





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_login_url/#)




```php
<a href="<?php echo esc_url( wp_login_url() ); ?>" alt="<?php esc_attr_e( 'Login', 'textdomain' ); ?>">
   	<?php _e( 'Login', 'textdomain' );
</a>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_login_url%2F%3Freplytocom%3D1184%23feedback-editor-1184)

4. [Skip to note 9 content](https://developer.wordpress.org/reference/functions/wp_login_url/#comment-content-6454)



To check with WP CLI: `wp eval "echo wp_login_url();"`





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_login_url%2F%3Freplytocom%3D6454%23feedback-editor-6454)

5. [Skip to note 10 content](https://developer.wordpress.org/reference/functions/wp_login_url/#comment-content-1186)



**Login and Redirect to Homepage**





`wp-includes/general-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_login_url/#)




```php
<a href="<?php echo esc_url( wp_login_url( home_url() ) ); ?>" alt="<?php esc_attr_e( 'Login', 'textdomain' ); ?>">
   	<?php _e( 'Login', 'textdomain' ); ?>
</a>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_login_url%2F%3Freplytocom%3D1186%23feedback-editor-1186)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_login_url%2F) before being able to contribute a note or feedback.

Notifications