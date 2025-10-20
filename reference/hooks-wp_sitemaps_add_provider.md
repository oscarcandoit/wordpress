---
url: https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider
scraped_at: 2025-10-20T03:20:21.556Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_sitemaps\_add\_provider


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_Sitemaps\_Registry::add\_provider](https://developer.wordpress.org/reference/classes/wp_sitemaps_registry/add_provider/)wp\_sitemaps\_add\_provider

Search

# apply\_filters( ‘wp\_sitemaps\_add\_provider’, WP\_Sitemaps\_Provider$provider, string$name )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#source)
- [Related](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#wp--skip-link--target)

Filters the sitemap provider before it is added.

## [Parameters](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/\#parameters)

`$provider` [WP\_Sitemaps\_Provider](https://developer.wordpress.org/reference/classes/wp_sitemaps_provider/)

Instance of a [WP\_Sitemaps\_Provider](https://developer.wordpress.org/reference/classes/wp_sitemaps_provider/).

`$name` string

Name of the sitemap provider.

## [Source](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/\#source)

`wp-includes/sitemaps/class-wp-sitemaps-registry.php`
[Copy](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#)

```php
$provider = apply_filters( 'wp_sitemaps_add_provider', $provider, $name );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/sitemaps/class-wp-sitemaps-registry.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/sitemaps/class-wp-sitemaps-registry.php#L50) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/sitemaps/class-wp-sitemaps-registry.php#L50-L50)

## [Related](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/\#related)

| Used by | Description |
| --- | --- |
| [WP\_Sitemaps\_Registry::add\_provider()](https://developer.wordpress.org/reference/classes/wp_sitemaps_registry/add_provider/) `wp-includes/sitemaps/class-wp-sitemaps-registry.php` | Adds a new sitemap provider. |

## [Changelog](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/\#changelog)

| Version | Description |
| --- | --- |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#comment-content-6322)





`wp-includes/sitemaps/class-wp-sitemaps-registry.php`
[Expand code](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#)

[Copy](https://developer.wordpress.org/reference/hooks/wp_sitemaps_add_provider/#)




```php
// wp-sitemaps users disable
add_filter( 'wp_sitemaps_add_provider', function ( $provider, $name ) {
       if ( 'users' === $name ) {
           return false;
       }

       return $provider;
}, 10, 2 );

add_filter( 'wp_sitemaps_register_providers', function ( $providers ) {
       unset( $providers['users'] );
       return $providers;
} );

// wp-sitemaps tags disable
add_filter( 'wp_sitemaps_taxonomies', function ( $taxonomies ) {
       unset( $taxonomies['post_tag'] );
       return $taxonomies;
} );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_sitemaps_add_provider%2F%3Freplytocom%3D6322%23feedback-editor-6322)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_sitemaps_add_provider%2F) before being able to contribute a note or feedback.

Notifications