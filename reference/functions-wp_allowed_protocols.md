---
url: https://developer.wordpress.org/reference/functions/wp_allowed_protocols
scraped_at: 2025-10-20T03:13:14.857Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_allowed\_protocols()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_allowed\_protocols()

Search

# wp\_allowed\_protocols(): string\[\]

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#description)
  - [See also](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#see-also)
- [Return](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#wp--skip-link--target)

Retrieves a list of protocols to allow in HTML attributes.

## [Description](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/\#description)

### [See also](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/\#see-also)

- [wp\_kses()](https://developer.wordpress.org/reference/functions/wp_kses)
- [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url)

## [Return](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/\#return)

string\[\] Array of allowed protocols. Defaults to an array containing `'http'`, `'https'`, `'ftp'`, `'ftps'`, `'mailto'`, `'news'`, `'irc'`, `'irc6'`, `'ircs'`, `'gopher'`, `'nntp'`, `'feed'`, `'telnet'`, `'mms'`, `'rtsp'`, `'sms'`, `'svn'`, `'tel'`, `'fax'`, `'xmpp'`, `'webcal'`, and `'urn'`.

This covers all common link protocols, except for `'javascript'` which should not be allowed for untrusted users.

## [Source](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#)

```php
function wp_allowed_protocols() {
	static $protocols = array();

	if ( empty( $protocols ) ) {
		$protocols = array( 'http', 'https', 'ftp', 'ftps', 'mailto', 'news', 'irc', 'irc6', 'ircs', 'gopher', 'nntp', 'feed', 'telnet', 'mms', 'rtsp', 'sms', 'svn', 'tel', 'fax', 'xmpp', 'webcal', 'urn' );
	}

	if ( ! did_action( 'wp_loaded' ) ) {
		/**
		 * Filters the list of protocols allowed in HTML attributes.
		 *
		 * @since 3.0.0
		 *
		 * @param string[] $protocols Array of allowed protocols e.g. 'http', 'ftp', 'tel', and more.
		 */
		$protocols = array_unique( (array) apply_filters( 'kses_allowed_protocols', $protocols ) );
	}

	return $protocols;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L7189) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L7189-L7208)

## [Hooks](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/\#hooks)

[apply\_filters( ‘kses\_allowed\_protocols’, string\[\]$protocols )](https://developer.wordpress.org/reference/hooks/kses_allowed_protocols/)

Filters the list of protocols allowed in HTML attributes.

## [Related](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/\#related)

| Uses | Description |
| --- | --- |
| [did\_action()](https://developer.wordpress.org/reference/functions/did_action/) `wp-includes/plugin.php` | Retrieves the number of times an action has been fired during the current request. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |

| Used by | Description |
| --- | --- |
| [\_make\_clickable\_rel\_attr()](https://developer.wordpress.org/reference/functions/_make_clickable_rel_attr/) `wp-includes/formatting.php` | Helper function used to build the “rel” attribute for a URL when creating an anchor using [make\_clickable()](https://developer.wordpress.org/reference/functions/make_clickable/) . |
| [wp\_is\_internal\_link()](https://developer.wordpress.org/reference/functions/wp_is_internal_link/) `wp-includes/link-template.php` | Determines whether or not the specified URL is of a host included in the internal hosts list. |
| [wp\_rel\_callback()](https://developer.wordpress.org/reference/functions/wp_rel_callback/) `wp-includes/formatting.php` | Callback to add a rel attribute to HTML A element. |
| [wp\_filter\_oembed\_iframe\_title\_attribute()](https://developer.wordpress.org/reference/functions/wp_filter_oembed_iframe_title_attribute/) `wp-includes/embed.php` | Filters the given oEmbed HTML to make sure iframes have a title attribute. |
| [wp\_targeted\_link\_rel\_callback()](https://developer.wordpress.org/reference/functions/wp_targeted_link_rel_callback/) `wp-includes/formatting.php` | Callback to add `rel="noopener"` string to HTML A element. |
| [wp\_kses\_one\_attr()](https://developer.wordpress.org/reference/functions/wp_kses_one_attr/) `wp-includes/kses.php` | Filters one HTML attribute and ensures its value is allowed. |
| [edit\_user()](https://developer.wordpress.org/reference/functions/edit_user/) `wp-admin/includes/user.php` | Edit user settings based on contents of $\_POST |
| [\_links\_add\_base()](https://developer.wordpress.org/reference/functions/_links_add_base/) `wp-includes/formatting.php` | Callback to add a base URL to relative links in passed content. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [safecss\_filter\_attr()](https://developer.wordpress.org/reference/functions/safecss_filter_attr/) `wp-includes/kses.php` | Filters an inline style attribute and removes disallowed rules. |
| [wp\_kses()](https://developer.wordpress.org/reference/functions/wp_kses/) `wp-includes/kses.php` | Filters text content and strips out disallowed HTML. |

[Show 6 more](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#) [Show less](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/#)

## [Changelog](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/\#changelog)

| Version | Description |
| --- | --- |
| [5.6.0](https://developer.wordpress.org/reference/since/5.6.0/) | Added `'irc6'` and `'ircs'` to the protocols array. |
| [5.3.0](https://developer.wordpress.org/reference/since/5.3.0/) | Added `'sms'` to the protocols array. |
| [4.7.0](https://developer.wordpress.org/reference/since/4.7.0/) | Added `'urn'` to the protocols array. |
| [4.3.0](https://developer.wordpress.org/reference/since/4.3.0/) | Added `'webcal'` to the protocols array. |
| [3.3.0](https://developer.wordpress.org/reference/since/3.3.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_allowed_protocols%2F) before being able to contribute a note or feedback.

Notifications