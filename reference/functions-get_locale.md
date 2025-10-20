---
url: https://developer.wordpress.org/reference/functions/get_locale
scraped_at: 2025-10-20T03:13:06.150Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_locale/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_locale()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_locale()

Search

# get\_locale(): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_locale/#description)
- [Return](https://developer.wordpress.org/reference/functions/get_locale/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_locale/#source)
- [Changelog](https://developer.wordpress.org/reference/functions/get_locale/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_locale/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_locale/#wp--skip-link--target)

Retrieves the current locale.

## [Description](https://developer.wordpress.org/reference/functions/get_locale/\#description)

If the locale is set, then it will filter the locale in the [‘locale’](https://developer.wordpress.org/reference/hooks/locale/) filter hook and return the value.

If the locale is not set already, then the WPLANG constant is used if it is defined. Then it is filtered through the [‘locale’](https://developer.wordpress.org/reference/hooks/locale/) filter hook and the value for the locale global set and the locale is returned.

The process to get the locale should only be done once, but the locale will always be filtered using the [‘locale’](https://developer.wordpress.org/reference/hooks/locale/) hook.

## [Return](https://developer.wordpress.org/reference/functions/get_locale/\#return)

string The locale of the blog or from the ['locale'](https://developer.wordpress.org/reference/hooks/locale/) hook.

## [Source](https://developer.wordpress.org/reference/functions/get_locale/\#source)

`wp-includes/l10n.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_locale/#)

[Copy](https://developer.wordpress.org/reference/functions/get_locale/#)

```php
function get_locale() {
	global $locale, $wp_local_package;

	if ( isset( $locale ) ) {
		/** This filter is documented in wp-includes/l10n.php */
		return apply_filters( 'locale', $locale );
	}

	if ( isset( $wp_local_package ) ) {
		$locale = $wp_local_package;
	}

	// WPLANG was defined in wp-config.
	if ( defined( 'WPLANG' ) ) {
		$locale = WPLANG;
	}

	// If multisite, check options.
	if ( is_multisite() ) {
		// Don't check blog option when installing.
		if ( wp_installing() ) {
			$ms_locale = get_site_option( 'WPLANG' );
		} else {
			$ms_locale = get_option( 'WPLANG' );
			if ( false === $ms_locale ) {
				$ms_locale = get_site_option( 'WPLANG' );
			}
		}

		if ( false !== $ms_locale ) {
			$locale = $ms_locale;
		}
	} else {
		$db_locale = get_option( 'WPLANG' );
		if ( false !== $db_locale ) {
			$locale = $db_locale;
		}
	}

	if ( empty( $locale ) ) {
		$locale = 'en_US';
	}

	/**
	 * Filters the locale ID of the WordPress installation.
	 *
	 * @since 1.5.0
	 *
	 * @param string $locale The locale ID.
	 */
	return apply_filters( 'locale', $locale );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/l10n.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/l10n.php#L30) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/l10n.php#L30-L81)

## [Changelog](https://developer.wordpress.org/reference/functions/get_locale/\#changelog)

| Version | Description |
| --- | --- |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_locale/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/get_locale/#comment-content-647)



This sets the monetary locale and if empty, sets as `en_US`





`wp-includes/l10n.php`
[Copy](https://developer.wordpress.org/reference/functions/get_locale/#)




```php
setlocale( LC_MONETARY, get_locale() );
$my_local_settings = localeconv();
if ( $my_local_settings['int_curr_symbol'] == "" ) {
   	setlocale( LC_MONETARY, 'en_US' );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_locale%2F%3Freplytocom%3D647%23feedback-editor-647)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_locale%2F) before being able to contribute a note or feedback.

Notifications