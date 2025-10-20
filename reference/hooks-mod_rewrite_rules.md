---
url: https://developer.wordpress.org/reference/hooks/mod_rewrite_rules
scraped_at: 2025-10-20T03:27:08.187Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

mod\_rewrite\_rules


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_Rewrite::mod\_rewrite\_rules](https://developer.wordpress.org/reference/classes/wp_rewrite/mod_rewrite_rules/)mod\_rewrite\_rules

Search

# apply\_filters( ‘mod\_rewrite\_rules’, string$rules )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#source)
- [Related](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#wp--skip-link--target)

Filters the list of rewrite rules formatted for output to an .htaccess file.

## [Parameters](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/\#parameters)

`$rules` string

mod\_rewrite Rewrite rules formatted for .htaccess.

## [Source](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/\#source)

`wp-includes/class-wp-rewrite.php`
[Copy](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#)

```php
$rules = apply_filters( 'mod_rewrite_rules', $rules );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-rewrite.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-rewrite.php#L1605) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-rewrite.php#L1605-L1605)

## [Related](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/\#related)

| Used by | Description |
| --- | --- |
| [WP\_Rewrite::mod\_rewrite\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/mod_rewrite_rules/) `wp-includes/class-wp-rewrite.php` | Retrieves mod\_rewrite-formatted rewrite rules to write to .htaccess. |

## [Changelog](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/\#changelog)

| Version | Description |
| --- | --- |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#comment-content-5568)





`wp-includes/class-wp-rewrite.php`
[Copy](https://developer.wordpress.org/reference/hooks/mod_rewrite_rules/#)




```php
// Setting the X-Content-Type-Options Header
function add_headers_htaccess( $rules ) {
     $new_rule = <<<EOD
     <IfModule mod_headers.c>
     Header always set X-Content-Type-Options "nosniff"
     </IfModule>
     EOD;

     return $new_rule . $rules;
}
add_filter('mod_rewrite_rules', 'add_headers_htaccess');
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fmod_rewrite_rules%2F%3Freplytocom%3D5568%23feedback-editor-5568)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fmod_rewrite_rules%2F) before being able to contribute a note or feedback.

Notifications