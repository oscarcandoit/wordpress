---
url: https://developer.wordpress.org/reference/functions/validate_file
scraped_at: 2025-10-20T03:25:50.937Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/validate_file/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

validate\_file()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)validate\_file()

Search

# validate\_file( string$file, string\[\]$allowed\_files = array() ): int

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/validate_file/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/validate_file/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/validate_file/#return)
- [Source](https://developer.wordpress.org/reference/functions/validate_file/#source)
- [Related](https://developer.wordpress.org/reference/functions/validate_file/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/validate_file/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/validate_file/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/validate_file/#wp--skip-link--target)

Validates a file name and path against an allowed set of rules.

## [Description](https://developer.wordpress.org/reference/functions/validate_file/\#description)

A return value of `1` means the file path contains directory traversal.

A return value of `2` means the file path contains a Windows drive path.

A return value of `3` means the file is not in the allowed files list.

## [Parameters](https://developer.wordpress.org/reference/functions/validate_file/\#parameters)

`$file` stringrequired

File path.

`$allowed_files` string\[\]optional

Array of allowed files.

Default: `array()`

## [Return](https://developer.wordpress.org/reference/functions/validate_file/\#return)

int 0 means nothing is wrong, greater than 0 means something was wrong.

## [Source](https://developer.wordpress.org/reference/functions/validate_file/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/validate_file/#)

[Copy](https://developer.wordpress.org/reference/functions/validate_file/#)

```php
function validate_file( $file, $allowed_files = array() ) {
	if ( ! is_scalar( $file ) || '' === $file ) {
		return 0;
	}

	// Normalize path for Windows servers.
	$file = wp_normalize_path( $file );
	// Normalize path for $allowed_files as well so it's an apples to apples comparison.
	$allowed_files = array_map( 'wp_normalize_path', $allowed_files );

	// `../` on its own is not allowed:
	if ( '../' === $file ) {
		return 1;
	}

	// More than one occurrence of `../` is not allowed:
	if ( preg_match_all( '#\.\./#', $file, $matches, PREG_SET_ORDER ) && ( count( $matches ) > 1 ) ) {
		return 1;
	}

	// `../` which does not occur at the end of the path is not allowed:
	if ( str_contains( $file, '../' ) && '../' !== mb_substr( $file, -3, 3 ) ) {
		return 1;
	}

	// Files not in the allowed file list are not allowed:
	if ( ! empty( $allowed_files ) && ! in_array( $file, $allowed_files, true ) ) {
		return 3;
	}

	// Absolute Windows drive paths are not allowed:
	if ( ':' === substr( $file, 1, 1 ) ) {
		return 2;
	}

	return 0;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L6233) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L6233-L6269)

## [Related](https://developer.wordpress.org/reference/functions/validate_file/\#related)

| Uses | Description |
| --- | --- |
| [wp\_normalize\_path()](https://developer.wordpress.org/reference/functions/wp_normalize_path/) `wp-includes/functions.php` | Normalizes a filesystem path. |

| Used by | Description |
| --- | --- |
| [WP\_REST\_Plugins\_Controller::validate\_plugin\_param()](https://developer.wordpress.org/reference/classes/wp_rest_plugins_controller/validate_plugin_param/) `wp-includes/rest-api/endpoints/class-wp-rest-plugins-controller.php` | Checks that the “plugin” parameter is a valid path. |
| [wp\_edit\_theme\_plugin\_file()](https://developer.wordpress.org/reference/functions/wp_edit_theme_plugin_file/) `wp-admin/includes/file.php` | Attempts to edit a file for a theme or plugin. |
| [wp\_ajax\_delete\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_delete_plugin/) `wp-admin/includes/ajax-actions.php` | Handles deleting a plugin via AJAX. |
| [wp\_ajax\_update\_plugin()](https://developer.wordpress.org/reference/functions/wp_ajax_update_plugin/) `wp-admin/includes/ajax-actions.php` | Handles updating a plugin via AJAX. |
| [validate\_plugin()](https://developer.wordpress.org/reference/functions/validate_plugin/) `wp-admin/includes/plugin.php` | Validates the plugin path. |
| [validate\_file\_to\_edit()](https://developer.wordpress.org/reference/functions/validate_file_to_edit/) `wp-admin/includes/file.php` | Makes sure that the file that was requested to be edited is allowed to be edited. |
| [download\_url()](https://developer.wordpress.org/reference/functions/download_url/) `wp-admin/includes/file.php` | Downloads a URL to a local temporary file using the WordPress HTTP API. |
| [\_unzip\_file\_ziparchive()](https://developer.wordpress.org/reference/functions/_unzip_file_ziparchive/) `wp-admin/includes/file.php` | Attempts to unzip an archive using the ZipArchive class. |
| [\_unzip\_file\_pclzip()](https://developer.wordpress.org/reference/functions/_unzip_file_pclzip/) `wp-admin/includes/file.php` | Attempts to unzip an archive using the PclZip library. |
| [WP\_Customize\_Manager::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_manager/__construct/) `wp-includes/class-wp-customize-manager.php` | Constructor. |
| [wp\_get\_active\_and\_valid\_plugins()](https://developer.wordpress.org/reference/functions/wp_get_active_and_valid_plugins/) `wp-includes/load.php` | Retrieves an array of active and valid plugin files. |
| [get\_single\_template()](https://developer.wordpress.org/reference/functions/get_single_template/) `wp-includes/template.php` | Retrieves path of single template in current or parent template. Applies to single Posts, single Attachments, and single custom post types. |
| [get\_page\_template()](https://developer.wordpress.org/reference/functions/get_page_template/) `wp-includes/template.php` | Retrieves path of page template in current or parent template. |
| [wp\_get\_active\_network\_plugins()](https://developer.wordpress.org/reference/functions/wp_get_active_network_plugins/) `wp-includes/ms-load.php` | Returns array of network plugin files to be included in global scope. |

[Show 9 more](https://developer.wordpress.org/reference/functions/validate_file/#) [Show less](https://developer.wordpress.org/reference/functions/validate_file/#)

## [Changelog](https://developer.wordpress.org/reference/functions/validate_file/\#changelog)

| Version | Description |
| --- | --- |
| [1.2.0](https://developer.wordpress.org/reference/since/1.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/validate_file/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/validate_file/#comment-content-1494)



**Valid file path**





`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/validate_file/#)




```php
$path = 'uploads/2012/12/my_image.jpg';
return validate_file( $path ); // Returns 0 (valid path).
```





**Invalid file path**





`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/validate_file/#)




```php
$path = '../../wp-content/uploads/2012/12/my_image.jpg';
return validate_file( $path ); // Returns 1 (invalid path).
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fvalidate_file%2F%3Freplytocom%3D1494%23feedback-editor-1494)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fvalidate_file%2F) before being able to contribute a note or feedback.

Notifications