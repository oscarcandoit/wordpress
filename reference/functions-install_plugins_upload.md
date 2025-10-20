---
url: https://developer.wordpress.org/reference/functions/install_plugins_upload
scraped_at: 2025-10-20T03:26:10.139Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/install_plugins_upload/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

install\_plugins\_upload()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)install\_plugins\_upload()

Search

# install\_plugins\_upload()

## In this article

Table of Contents

- [Source](https://developer.wordpress.org/reference/functions/install_plugins_upload/#source)
- [Related](https://developer.wordpress.org/reference/functions/install_plugins_upload/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/install_plugins_upload/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/install_plugins_upload/#wp--skip-link--target)

Displays a form to upload plugins from zip files.

## [Source](https://developer.wordpress.org/reference/functions/install_plugins_upload/\#source)

`wp-admin/includes/plugin-install.php`
[Expand code](https://developer.wordpress.org/reference/functions/install_plugins_upload/#)

[Copy](https://developer.wordpress.org/reference/functions/install_plugins_upload/#)

```php
function install_plugins_upload() {
	?>
<div class="upload-plugin">
	<p class="install-help"><?php _e( 'If you have a plugin in a .zip format, you may install or update it by uploading it here.' ); ?></p>
	<form method="post" enctype="multipart/form-data" class="wp-upload-form" action="<?php echo esc_url( self_admin_url( 'update.php?action=upload-plugin' ) ); ?>">
		<?php wp_nonce_field( 'plugin-upload' ); ?>
		<label class="screen-reader-text" for="pluginzip">
			<?php
			/* translators: Hidden accessibility text. */
			_e( 'Plugin zip file' );
			?>
		</label>
		<input type="file" id="pluginzip" name="pluginzip" accept=".zip" />
		<?php submit_button( _x( 'Install Now', 'plugin' ), '', 'install-plugin-submit', false ); ?>
	</form>
</div>
	<?php
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/plugin-install.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/plugin-install.php#L342) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/plugin-install.php#L342-L359)

## [Related](https://developer.wordpress.org/reference/functions/install_plugins_upload/\#related)

| Uses | Description |
| --- | --- |
| [submit\_button()](https://developer.wordpress.org/reference/functions/submit_button/) `wp-admin/includes/template.php` | Echoes a submit button, with provided text and appropriate class(es). |
| [wp\_nonce\_field()](https://developer.wordpress.org/reference/functions/wp_nonce_field/) `wp-includes/functions.php` | Retrieves or display nonce hidden field for forms. |
| [self\_admin\_url()](https://developer.wordpress.org/reference/functions/self_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for either the current site or the network depending on context. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |

[Show 1 more](https://developer.wordpress.org/reference/functions/install_plugins_upload/#) [Show less](https://developer.wordpress.org/reference/functions/install_plugins_upload/#)

## [Changelog](https://developer.wordpress.org/reference/functions/install_plugins_upload/\#changelog)

| Version | Description |
| --- | --- |
| [2.8.0](https://developer.wordpress.org/reference/since/2.8.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Finstall_plugins_upload%2F) before being able to contribute a note or feedback.

Notifications