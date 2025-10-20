---
url: https://developer.wordpress.org/reference/functions/wp_robots_no_robots
scraped_at: 2025-10-20T03:12:58.907Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_robots\_no\_robots()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_robots\_no\_robots()

Search

# wp\_robots\_no\_robots( array$robots ): array

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#wp--skip-link--target)

Adds `noindex` to the robots meta tag.

## [Description](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/\#description)

This directive tells web robots not to index the page content.

Typical usage is as a [‘wp\_robots’](https://developer.wordpress.org/reference/hooks/wp_robots/) callback:

`wp-includes/robots-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#)

```php
add_filter( 'wp_robots', 'wp_robots_no_robots' );
```

## [Parameters](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/\#parameters)

`$robots` arrayrequired

Associative array of robots directives.

## [Return](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/\#return)

array Filtered robots directives.

## [Source](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/\#source)

`wp-includes/robots-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#)

```php
function wp_robots_no_robots( array $robots ) {
	$robots['noindex'] = true;

	if ( get_option( 'blog_public' ) ) {
		$robots['follow'] = true;
	} else {
		$robots['nofollow'] = true;
	}

	return $robots;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/robots-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/robots-template.php#L140) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/robots-template.php#L140-L150)

## [Related](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/\#related)

| Uses | Description |
| --- | --- |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |

| Used by | Description |
| --- | --- |
| [wp\_robots\_noindex()](https://developer.wordpress.org/reference/functions/wp_robots_noindex/) `wp-includes/robots-template.php` | Adds `noindex` to the robots meta tag if required by the site configuration. |
| [wp\_robots\_noindex\_embeds()](https://developer.wordpress.org/reference/functions/wp_robots_noindex_embeds/) `wp-includes/robots-template.php` | Adds `noindex` to the robots meta tag for embeds. |
| [wp\_robots\_noindex\_search()](https://developer.wordpress.org/reference/functions/wp_robots_noindex_search/) `wp-includes/robots-template.php` | Adds `noindex` to the robots meta tag if a search is being performed. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/\#changelog)

| Version | Description |
| --- | --- |
| [5.7.0](https://developer.wordpress.org/reference/since/5.7.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#comment-content-7265)



Two examples, both adding noindex to all Post Format archives:





`wp-includes/robots-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#)




```php
add_action(
       'wp_head',
       function() {
           is_tax( 'post_format' ) && add_filter( 'wp_robots', 'wp_robots_no_robots' );
       },
       0
);
```





(Note: a priority of 0 otherwise the action runs too late.)





`wp-includes/robots-template.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_robots_no_robots/#)




```php
add_filter(
       'wp_robots',
       function ( array $robots ) {
           if ( is_tax( 'post_format' ) ) {
               return wp_robots_no_robots( $robots );
           }
           return $robots;
       }
);
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_robots_no_robots%2F%3Freplytocom%3D7265%23feedback-editor-7265)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_robots_no_robots%2F) before being able to contribute a note or feedback.

Notifications