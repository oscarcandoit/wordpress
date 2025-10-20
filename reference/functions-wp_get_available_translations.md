---
url: https://developer.wordpress.org/reference/functions/wp_get_available_translations
scraped_at: 2025-10-20T03:25:22.184Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_get\_available\_translations()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)wp\_get\_available\_translations()

Search

# wp\_get\_available\_translations(): array

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#description)
  - [See also](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#see-also)
- [Return](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#return)
- [Source](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#source)
- [Related](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#wp--skip-link--target)

Get available translations from the WordPress.org API.

## [Description](https://developer.wordpress.org/reference/functions/wp_get_available_translations/\#description)

### [See also](https://developer.wordpress.org/reference/functions/wp_get_available_translations/\#see-also)

- [translations\_api()](https://developer.wordpress.org/reference/functions/translations_api)

## [Return](https://developer.wordpress.org/reference/functions/wp_get_available_translations/\#return)

array Array of translations keyed by the language code, each an associative array of data.

If the API response results in an error, an empty array will be returned.

- `...$0` array


- `language` string
Language code.

- `version` string
WordPress version.

- `updated` string
Date the translation was last updated, in MySQL datetime format.

- `english_name` string
English name of the language.

- `native_name` string
Native name of the language.

- `package` string
URL to download the translation package.

- `iso` string\[\]
Array of ISO language codes.

- `strings` array
Array of translated strings used in the installation process.


## [Source](https://developer.wordpress.org/reference/functions/wp_get_available_translations/\#source)

`wp-admin/includes/translation-install.php`
[Expand code](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#)

[Copy](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#)

```php
function wp_get_available_translations() {
	if ( ! wp_installing() ) {
		$translations = get_site_transient( 'available_translations' );
		if ( false !== $translations ) {
			return $translations;
		}
	}

	$api = translations_api( 'core', array( 'version' => wp_get_wp_version() ) );

	if ( is_wp_error( $api ) || empty( $api['translations'] ) ) {
		return array();
	}

	$translations = array();
	// Key the array with the language code.
	foreach ( $api['translations'] as $translation ) {
		$translations[ $translation['language'] ] = $translation;
	}

	if ( ! defined( 'WP_INSTALLING' ) ) {
		set_site_transient( 'available_translations', $translations, 3 * HOUR_IN_SECONDS );
	}

	return $translations;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/translation-install.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/translation-install.php#L167) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/translation-install.php#L167-L192)

## [Related](https://developer.wordpress.org/reference/functions/wp_get_available_translations/\#related)

| Uses | Description |
| --- | --- |
| [wp\_get\_wp\_version()](https://developer.wordpress.org/reference/functions/wp_get_wp_version/) `wp-includes/functions.php` | Returns the current WordPress version. |
| [wp\_installing()](https://developer.wordpress.org/reference/functions/wp_installing/) `wp-includes/load.php` | Checks or sets whether WordPress is in “installation” mode. |
| [translations\_api()](https://developer.wordpress.org/reference/functions/translations_api/) `wp-admin/includes/translation-install.php` | Retrieve translations from WordPress Translation API. |
| [set\_site\_transient()](https://developer.wordpress.org/reference/functions/set_site_transient/) `wp-includes/option.php` | Sets/updates the value of a site transient. |
| [get\_site\_transient()](https://developer.wordpress.org/reference/functions/get_site_transient/) `wp-includes/option.php` | Retrieves the value of a site transient. |
| [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) `wp-includes/load.php` | Checks whether the given variable is a WordPress Error. |

[Show 1 more](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#) [Show less](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#)

| Used by | Description |
| --- | --- |
| [wp\_download\_language\_pack()](https://developer.wordpress.org/reference/functions/wp_download_language_pack/) `wp-admin/includes/translation-install.php` | Download a language pack. |

## [Changelog](https://developer.wordpress.org/reference/functions/wp_get_available_translations/\#changelog)

| Version | Description |
| --- | --- |
| [4.0.0](https://developer.wordpress.org/reference/since/4.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/wp_get_available_translations/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#comment-content-1567)



Before calling `wp_get_available_translations` you should include `translation-install.php` like in the following example:





`wp-admin/includes/translation-install.php`
[Copy](https://developer.wordpress.org/reference/functions/wp_get_available_translations/#)




```php
require_once( ABSPATH . 'wp-admin/includes/translation-install.php' );
$language_list = wp_get_available_translations();
```





Otherwise you might get this fatal error if that file was not included before:

`Fatal error: Call to undefined function wp_get_available_translations()`





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_available_translations%2F%3Freplytocom%3D1567%23feedback-editor-1567)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fwp_get_available_translations%2F) before being able to contribute a note or feedback.

Notifications