---
url: https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head
scraped_at: 2025-10-20T03:18:14.738Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

adjacent\_posts\_rel\_link\_wp\_head()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)adjacent\_posts\_rel\_link\_wp\_head()

Search

# adjacent\_posts\_rel\_link\_wp\_head()

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/#description)
  - [See also](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/#see-also)
- [Source](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/#source)
- [Related](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/#wp--skip-link--target)

Displays relational links for the posts adjacent to the current post for single post pages.

## [Description](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/\#description)

This is meant to be attached to actions like ‘wp\_head’. Do not call this directly in plugins or theme templates.

### [See also](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/\#see-also)

- [adjacent\_posts\_rel\_link()](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link)

## [Source](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/\#source)

`wp-includes/link-template.php`
[Copy](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/#)

```php
function adjacent_posts_rel_link_wp_head() {
	if ( ! is_single() || is_attachment() ) {
		return;
	}
	adjacent_posts_rel_link();
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/link-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/link-template.php#L2133) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/link-template.php#L2133-L2138)

## [Related](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/\#related)

| Uses | Description |
| --- | --- |
| [is\_single()](https://developer.wordpress.org/reference/functions/is_single/) `wp-includes/query.php` | Determines whether the query is for an existing single post. |
| [is\_attachment()](https://developer.wordpress.org/reference/functions/is_attachment/) `wp-includes/query.php` | Determines whether the query is for an existing attachment page. |
| [adjacent\_posts\_rel\_link()](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link/) `wp-includes/link-template.php` | Displays the relational links for the posts adjacent to the current post. |

## [Changelog](https://developer.wordpress.org/reference/functions/adjacent_posts_rel_link_wp_head/\#changelog)

| Version | Description |
| --- | --- |
| [5.6.0](https://developer.wordpress.org/reference/since/5.6.0/) | No longer used in core. |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fadjacent_posts_rel_link_wp_head%2F) before being able to contribute a note or feedback.

Notifications