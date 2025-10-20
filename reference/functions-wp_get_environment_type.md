---
url: https://developer.wordpress.org/reference/functions/wp_get_environment_type
scraped_at: 2025-10-20T03:18:54.676Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_environment\_type()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_environment\_type()

Search

# wp\_get\_environment\_type(): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#description)
- [Return](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#return)
- [More Information](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#wp--skip-link--target)

Retrieves the current environment type.

## [Description](https://developer.wordpress.org/reference/functions/wp_get_environment_type/\#description)

The type can be set via the `WP_ENVIRONMENT_TYPE` global system variable, or a constant of the same name.

Possible values are ‘local’, ‘development’, ‘staging’, and ‘production’.

If not set, the type defaults to ‘production’.

## [Return](https://developer.wordpress.org/reference/functions/wp_get_environment_type/\#return)

string The current environment type.

## [More Information](https://developer.wordpress.org/reference/functions/wp_get_environment_type/\#more-information)

- This function allows plugin and theme authors to more easily differentiate how they handle specific functionality between production and development sites in a standardized way.
- When `development` is returned by [wp\_get\_environment\_type()](https://developer.wordpress.org/reference/functions/wp_get_environment_type/) , `WP_DEBUG` will be set to `true` if it is not defined in the `wp-config.php` file of the site.
- All hosts that support setting up staging environments are requested to set this feature to `staging` on those staging environments. Similarly, all developers with development environments shall set this value to `development` appropriately.

Example Usage:

`wp-includes/load.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#)

```php
switch ( wp_get_environment_type() ) {
case 'local':
case 'development':
do_nothing();
break;

case 'staging':
do_staging_thing();
break;

case 'production':
default:
do_production_thing();
break;
}
```

## [Source](https://developer.wordpress.org/reference/functions/wp_get_environment_type/\#source)

`wp-includes/load.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#)

```php
function wp_get_environment_type() {
	static $current_env = '';

	if ( ! defined( 'WP_RUN_CORE_TESTS' ) && $current_env ) {
		return $current_env;
	}

	$wp_environments = array(
		'local',
		'development',
		'staging',
		'production',
	);

	// Add a note about the deprecated WP_ENVIRONMENT_TYPES constant.
	if ( defined( 'WP_ENVIRONMENT_TYPES' ) && function_exists( '_deprecated_argument' ) ) {
		if ( function_exists( '__' ) ) {
			/* translators: %s: WP_ENVIRONMENT_TYPES */
			$message = sprintf( __( 'The %s constant is no longer supported.' ), 'WP_ENVIRONMENT_TYPES' );
		} else {
			$message = sprintf( 'The %s constant is no longer supported.', 'WP_ENVIRONMENT_TYPES' );
		}

		_deprecated_argument(
			'define()',
			'5.5.1',
			$message
		);
	}

	// Check if the environment variable has been set, if `getenv` is available on the system.
	if ( function_exists( 'getenv' ) ) {
		$has_env = getenv( 'WP_ENVIRONMENT_TYPE' );
		if ( false !== $has_env ) {
			$current_env = $has_env;
		}
	}

	// Fetch the environment from a constant, this overrides the global system variable.
	if ( defined( 'WP_ENVIRONMENT_TYPE' ) && WP_ENVIRONMENT_TYPE ) {
		$current_env = WP_ENVIRONMENT_TYPE;
	}

	// Make sure the environment is an allowed one, and not accidentally set to an invalid value.
	if ( ! in_array( $current_env, $wp_environments, true ) ) {
		$current_env = 'production';
	}

	return $current_env;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/load.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/load.php#L247) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/load.php#L247-L296)

## [Related](https://developer.wordpress.org/reference/functions/wp_get_environment_type/\#related)

| Uses | Description |
| --- | --- |
| [\_deprecated\_argument()](https://developer.wordpress.org/reference/functions/_deprecated_argument/) `wp-includes/functions.php` | Marks a function argument as deprecated and inform when it has been used. |

| Used by | Description |
| --- | --- |
| [wp\_is\_authorize\_application\_redirect\_url\_valid()](https://developer.wordpress.org/reference/functions/wp_is_authorize_application_redirect_url_valid/) `wp-admin/includes/user.php` | Validates the redirect URL protocol scheme. The protocol can be anything except `http` and `javascript`. |
| [wp\_is\_application\_passwords\_supported()](https://developer.wordpress.org/reference/functions/wp_is_application_passwords_supported/) `wp-includes/user.php` | Checks if Application Passwords is supported. |
| [WP\_Site\_Health::is\_development\_environment()](https://developer.wordpress.org/reference/classes/wp_site_health/is_development_environment/) `wp-admin/includes/class-wp-site-health.php` | Checks if the current environment type is set to ‘development’ or ‘local’. |
| [WP\_Site\_Health::get\_tests()](https://developer.wordpress.org/reference/classes/wp_site_health/get_tests/) `wp-admin/includes/class-wp-site-health.php` | Returns a set of tests that belong to the site status page. |
| [wp\_initial\_constants()](https://developer.wordpress.org/reference/functions/wp_initial_constants/) `wp-includes/default-constants.php` | Defines initial WordPress constants. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_environment_type/\#changelog)

| Version | Description |
| --- | --- |
| [5.5.1](https://developer.wordpress.org/reference/since/5.5.1/) | Removed the ability to alter the list of types. |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_environment_type/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#comment-content-4923)



See case from rtCamp. They placed in `mu-plugins/non-production.php`.





`wp-includes/load.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#)




```php
<?php
/**
    *  Non-production environment functionality.
    */

if ( 'production' !== wp_get_environment_type() ) {

   	// Block crawling.
   	add_filter( 'robots_txt', 'wpdocs_name_block_crawling', 999 );

   	// Enable "Discourage search engines from indexing this site" option.
   	add_filter( 'pre_option_blog_public', '__return_zero', 999 );

}

/**
    * Filters the robots.txt output to block crawling on non-production environment.
    *
    * @param string $output The robots.txt output.
    */
function wpdocs_name_block_crawling( $output ) {

   	$output = '# Crawling is blocked for non-production environment' . PHP_EOL;
   	$output .= 'User-agent: *' . PHP_EOL;
   	$output .= 'Disallow: /';

   	return $output;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_environment_type%2F%3Freplytocom%3D4923%23feedback-editor-4923)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#comment-content-5819)



Setting the environment type by _.htaccess_ or Apache configuration



`# Rules to set WP_ENVIRONMENT_TYPE based on hostname
RewriteCond %{HTTP_HOST} [.]?localhost$
RewriteRule .? - [E=WP_ENVIRONMENT_TYPE:local]
RewriteCond %{HTTP_HOST} ^staging.domain.com$
RewriteRule .? - [E=WP_ENVIRONMENT_TYPE:staging]
RewriteCond %{HTTP_HOST} ^www.domain.com$
RewriteRule .? - [E=WP_ENVIRONMENT_TYPE:production]`



Setting the environment type by Nginx configuration (best inside the php location)

`fastcgi_param WP_ENVIRONMENT_TYPE staging;`





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_environment_type%2F%3Freplytocom%3D5819%23feedback-editor-5819)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#comment-content-6360)



You can turn this into various functions to use specifically in certain environments:





`wp-includes/load.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#)




```php
function is_local_environment() {
      $env = wp_get_environment_type();
      return (defined('WP_ENVIRONMENT_TYPE') && $env === 'local');
}
```





And then use that in your code. Example:





`wp-includes/load.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#)




```php
if ( is_local_environment() ) {
     // do something only in local environment
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_environment_type%2F%3Freplytocom%3D6360%23feedback-editor-6360)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/functions/wp_get_environment_type/#comment-content-6540)



The return value is cached via a `static` variable, so the `WP_ENVIRONMENT_TYPE` global system variable or constant must be set before the first call to `wp_get_environment_type()`. Otherwise, the defined environment type is not honored.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_environment_type%2F%3Freplytocom%3D6540%23feedback-editor-6540)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_environment_type%2F) before being able to contribute a note or feedback.

Notifications