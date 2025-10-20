---
url: https://developer.wordpress.org/reference/functions/esc_html_e
scraped_at: 2025-10-20T03:24:21.030Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/esc_html_e/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

esc\_html\_e()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)esc\_html\_e()

Search

# esc\_html\_e( string$text, string$domain = 'default' )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/esc_html_e/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/esc_html_e/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/esc_html_e/#source)
- [Changelog](https://developer.wordpress.org/reference/functions/esc_html_e/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/esc_html_e/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/esc_html_e/#wp--skip-link--target)

Displays translated text that has been escaped for safe use in HTML output.

## [Description](https://developer.wordpress.org/reference/functions/esc_html_e/\#description)

If there is no translation, or the text domain isn’t loaded, the original text is escaped and displayed.

If you need the value for use in PHP, use [esc\_html\_\_()](https://developer.wordpress.org/reference/functions/esc_html__/) .

## [Parameters](https://developer.wordpress.org/reference/functions/esc_html_e/\#parameters)

`$text` stringrequired

Text to translate.

`$domain` stringoptional

Text domain. Unique identifier for retrieving translated strings.

Default `'default'`.

Default: `'default'`

## [Source](https://developer.wordpress.org/reference/functions/esc_html_e/\#source)

`wp-includes/l10n.php`
[Copy](https://developer.wordpress.org/reference/functions/esc_html_e/#)

```php
 */
function esc_html_e( $text, $domain = 'default' ) {
	echo esc_html( translate( $text, $domain ) );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/l10n.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/l10n.php#L387) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/l10n.php#L387-L389)

## [Changelog](https://developer.wordpress.org/reference/functions/esc_html_e/\#changelog)

| Version | Description |
| --- | --- |
| [2.8.0](https://developer.wordpress.org/reference/since/2.8.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/esc_html_e/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/functions/esc_html_e/#comment-content-2413)



Escape & Echo (Display) the translated text.





`wp-includes/l10n.php`
[Copy](https://developer.wordpress.org/reference/functions/esc_html_e/#)




```php
<h1><?php esc_html_e( 'Title', 'text-domain' )?></h1>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fesc_html_e%2F%3Freplytocom%3D2413%23feedback-editor-2413)

2. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/esc_html_e/#comment-content-7289)



**[esc\_html()](https://developer.wordpress.org/reference/functions/esc_html/)** is for escaping.

**[esc\_html\_\_()](https://developer.wordpress.org/reference/functions/esc_html__/)** is for translating and escaping.

**[esc\_html\_e()](https://developer.wordpress.org/reference/functions/esc_html_e/)** is for translating, escaping and directly echoing





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fesc_html_e%2F%3Freplytocom%3D7289%23feedback-editor-7289)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fesc_html_e%2F) before being able to contribute a note or feedback.

Notifications