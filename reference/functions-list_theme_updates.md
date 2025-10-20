---
url: https://developer.wordpress.org/reference/functions/list_theme_updates
scraped_at: 2025-10-20T03:16:19.534Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/list_theme_updates/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

list\_theme\_updates()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)list\_theme\_updates()

Search

# list\_theme\_updates()

## In this article

Table of Contents

- [Source](https://developer.wordpress.org/reference/functions/list_theme_updates/#source)
- [Related](https://developer.wordpress.org/reference/functions/list_theme_updates/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/list_theme_updates/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/list_theme_updates/#wp--skip-link--target)

Display the upgrade themes form.

## [Source](https://developer.wordpress.org/reference/functions/list_theme_updates/\#source)

`wp-admin/update-core.php`
[Expand code](https://developer.wordpress.org/reference/functions/list_theme_updates/#)

[Copy](https://developer.wordpress.org/reference/functions/list_theme_updates/#)

```php
function list_theme_updates() {
	$themes = get_theme_updates();
	if ( empty( $themes ) ) {
		echo '<h2>' . __( 'Themes' ) . '</h2>';
		echo '<p>' . __( 'Your themes are all up to date.' ) . '</p>';
		return;
	}

	$form_action = 'update-core.php?action=do-theme-upgrade';

	$themes_count = count( $themes );
	?>
<h2>
	<?php
	printf(
		'%s <span class="count">(%d)</span>',
		__( 'Themes' ),
		number_format_i18n( $themes_count )
	);
	?>
</h2>
<p><?php _e( 'The following themes have new versions available. Check the ones you want to update and then click &#8220;Update Themes&#8221;.' ); ?></p>
<p>
	<?php
	printf(
		/* translators: %s: Link to documentation on child themes. */
		__( '<strong>Please Note:</strong> Any customizations you have made to theme files will be lost. Please consider using <a href="%s">child themes</a> for modifications.' ),
		__( 'https://developer.wordpress.org/themes/advanced-topics/child-themes/' )
	);
	?>
</p>
<form method="post" action="<?php echo esc_url( $form_action ); ?>" name="upgrade-themes" class="upgrade">
	<?php wp_nonce_field( 'upgrade-core' ); ?>
<p><input id="upgrade-themes" class="button" type="submit" value="<?php esc_attr_e( 'Update Themes' ); ?>" name="upgrade" /></p>
<table class="widefat updates-table" id="update-themes-table">
	<thead>
	<tr>
		<td class="manage-column check-column"><input type="checkbox" id="themes-select-all" /></td>
		<td class="manage-column"><label for="themes-select-all"><?php _e( 'Select All' ); ?></label></td>
	</tr>
	</thead>

	<tbody class="plugins">
	<?php
	$auto_updates = array();
	if ( wp_is_auto_update_enabled_for_type( 'theme' ) ) {
		$auto_updates       = (array) get_site_option( 'auto_update_themes', array() );
		$auto_update_notice = ' | ' . wp_get_auto_update_message();
	}

	foreach ( $themes as $stylesheet => $theme ) {
		$requires_wp  = isset( $theme->update['requires'] ) ? $theme->update['requires'] : null;
		$requires_php = isset( $theme->update['requires_php'] ) ? $theme->update['requires_php'] : null;

		$compatible_wp  = is_wp_version_compatible( $requires_wp );
		$compatible_php = is_php_version_compatible( $requires_php );

		$compat = '';

		if ( ! $compatible_wp && ! $compatible_php ) {
			$compat .= '<br />' . __( 'This update does not work with your versions of WordPress and PHP.' ) . '&nbsp;';
			if ( current_user_can( 'update_core' ) && current_user_can( 'update_php' ) ) {
				$compat .= sprintf(
					/* translators: 1: URL to WordPress Updates screen, 2: URL to Update PHP page. */
					__( '<a href="%1$s">Please update WordPress</a>, and then <a href="%2$s">learn more about updating PHP</a>.' ),
					esc_url( self_admin_url( 'update-core.php' ) ),
					esc_url( wp_get_update_php_url() )
				);

				$annotation = wp_get_update_php_annotation();

				if ( $annotation ) {
					$compat .= '</p><p><em>' . $annotation . '</em>';
				}
			} elseif ( current_user_can( 'update_core' ) ) {
				$compat .= sprintf(
					/* translators: %s: URL to WordPress Updates screen. */
					__( '<a href="%s">Please update WordPress</a>.' ),
					esc_url( self_admin_url( 'update-core.php' ) )
				);
			} elseif ( current_user_can( 'update_php' ) ) {
				$compat .= sprintf(
					/* translators: %s: URL to Update PHP page. */
					__( '<a href="%s">Learn more about updating PHP</a>.' ),
					esc_url( wp_get_update_php_url() )
				);

				$annotation = wp_get_update_php_annotation();

				if ( $annotation ) {
					$compat .= '</p><p><em>' . $annotation . '</em>';
				}
			}
		} elseif ( ! $compatible_wp ) {
			$compat .= '<br />' . __( 'This update does not work with your version of WordPress.' ) . '&nbsp;';
			if ( current_user_can( 'update_core' ) ) {
				$compat .= sprintf(
					/* translators: %s: URL to WordPress Updates screen. */
					__( '<a href="%s">Please update WordPress</a>.' ),
					esc_url( self_admin_url( 'update-core.php' ) )
				);
			}
		} elseif ( ! $compatible_php ) {
			$compat .= '<br />' . __( 'This update does not work with your version of PHP.' ) . '&nbsp;';
			if ( current_user_can( 'update_php' ) ) {
				$compat .= sprintf(
					/* translators: %s: URL to Update PHP page. */
					__( '<a href="%s">Learn more about updating PHP</a>.' ),
					esc_url( wp_get_update_php_url() )
				);

				$annotation = wp_get_update_php_annotation();

				if ( $annotation ) {
					$compat .= '</p><p><em>' . $annotation . '</em>';
				}
			}
		}

		$checkbox_id = 'checkbox_' . md5( $theme->get( 'Name' ) );
		?>
	<tr>
		<td class="check-column">
			<?php if ( $compatible_wp && $compatible_php ) : ?>
				<input type="checkbox" name="checked[]" id="<?php echo $checkbox_id; ?>" value="<?php echo esc_attr( $stylesheet ); ?>" />
				<label for="<?php echo $checkbox_id; ?>">
					<span class="screen-reader-text">
					<?php
					/* translators: Hidden accessibility text. %s: Theme name. */
					printf( __( 'Select %s' ), $theme->display( 'Name' ) );
					?>
					</span>
				</label>
			<?php endif; ?>
		</td>
		<td class="plugin-title"><p>
			<img src="<?php echo esc_url( $theme->get_screenshot() . '?ver=' . $theme->version ); ?>" width="85" height="64" class="updates-table-screenshot" alt="" />
			<strong><?php echo $theme->display( 'Name' ); ?></strong>
			<?php
			printf(
				/* translators: 1: Theme version, 2: New version. */
				__( 'You have version %1$s installed. Update to %2$s.' ),
				$theme->display( 'Version' ),
				$theme->update['new_version']
			);

			echo ' ' . $compat;

			if ( in_array( $stylesheet, $auto_updates, true ) ) {
				echo $auto_update_notice;
			}
			?>
		</p></td>
	</tr>
			<?php
	}
	?>
	</tbody>

	<tfoot>
	<tr>
		<td class="manage-column check-column"><input type="checkbox" id="themes-select-all-2" /></td>
		<td class="manage-column"><label for="themes-select-all-2"><?php _e( 'Select All' ); ?></label></td>
	</tr>
	</tfoot>
</table>
<p><input id="upgrade-themes-2" class="button" type="submit" value="<?php esc_attr_e( 'Update Themes' ); ?>" name="upgrade" /></p>
</form>
	<?php
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/update-core.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/update-core.php#L639) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/update-core.php#L639-L808)

## [Related](https://developer.wordpress.org/reference/functions/list_theme_updates/\#related)

| Uses | Description |
| --- | --- |
| [wp\_is\_auto\_update\_enabled\_for\_type()](https://developer.wordpress.org/reference/functions/wp_is_auto_update_enabled_for_type/) `wp-admin/includes/update.php` | Checks whether auto-updates are enabled. |
| [wp\_get\_auto\_update\_message()](https://developer.wordpress.org/reference/functions/wp_get_auto_update_message/) `wp-admin/includes/update.php` | Determines the appropriate auto-update message to be displayed. |
| [is\_wp\_version\_compatible()](https://developer.wordpress.org/reference/functions/is_wp_version_compatible/) `wp-includes/functions.php` | Checks compatibility with the current WordPress version. |
| [is\_php\_version\_compatible()](https://developer.wordpress.org/reference/functions/is_php_version_compatible/) `wp-includes/functions.php` | Checks compatibility with the current PHP version. |
| [wp\_get\_update\_php\_annotation()](https://developer.wordpress.org/reference/functions/wp_get_update_php_annotation/) `wp-includes/functions.php` | Returns the default annotation for the web hosting altering the “Update PHP” page URL. |
| [wp\_get\_update\_php\_url()](https://developer.wordpress.org/reference/functions/wp_get_update_php_url/) `wp-includes/functions.php` | Gets the URL to learn more about updating the PHP version the site is running on. |
| [get\_theme\_updates()](https://developer.wordpress.org/reference/functions/get_theme_updates/) `wp-admin/includes/update.php` | Retrieves themes with updates available. |
| [wp\_nonce\_field()](https://developer.wordpress.org/reference/functions/wp_nonce_field/) `wp-includes/functions.php` | Retrieves or display nonce hidden field for forms. |
| [self\_admin\_url()](https://developer.wordpress.org/reference/functions/self_admin_url/) `wp-includes/link-template.php` | Retrieves the URL to the admin area for either the current site or the network depending on context. |
| [current\_user\_can()](https://developer.wordpress.org/reference/functions/current_user_can/) `wp-includes/capabilities.php` | Returns whether the current user has the specified capability. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [esc\_attr()](https://developer.wordpress.org/reference/functions/esc_attr/) `wp-includes/formatting.php` | Escaping for HTML attributes. |
| [number\_format\_i18n()](https://developer.wordpress.org/reference/functions/number_format_i18n/) `wp-includes/functions.php` | Converts float number to format based on the locale. |
| [get\_site\_option()](https://developer.wordpress.org/reference/functions/get_site_option/) `wp-includes/option.php` | Retrieve an option value for the current network based on name of option. |

[Show 9 more](https://developer.wordpress.org/reference/functions/list_theme_updates/#) [Show less](https://developer.wordpress.org/reference/functions/list_theme_updates/#)

## [Changelog](https://developer.wordpress.org/reference/functions/list_theme_updates/\#changelog)

| Version | Description |
| --- | --- |
| [2.9.0](https://developer.wordpress.org/reference/since/2.9.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Flist_theme_updates%2F) before being able to contribute a note or feedback.

Notifications