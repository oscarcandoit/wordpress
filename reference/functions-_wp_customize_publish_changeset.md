---
url: https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset
scraped_at: 2025-10-20T03:20:40.954Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

\_wp\_customize\_publish\_changeset()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)\_wp\_customize\_publish\_changeset()

Search

# \_wp\_customize\_publish\_changeset( string$new\_status, string$old\_status, WP\_Post$changeset\_post )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#wp--skip-link--target)

This function’s access is marked private. This means it is not intended for use by plugin or theme developers, only in other core functions. It is listed here for completeness.

Publishes a snapshot’s changes.

## [Parameters](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/\#parameters)

`$new_status` stringrequired

New post status.

`$old_status` stringrequired

Old post status.

`$changeset_post` [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)required

Changeset post object.

## [Source](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/\#source)

`wp-includes/theme.php`
[Expand code](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#)

[Copy](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#)

```php
function _wp_customize_publish_changeset( $new_status, $old_status, $changeset_post ) {
	global $wp_customize;

	$is_publishing_changeset = (
		'customize_changeset' === $changeset_post->post_type
		&&
		'publish' === $new_status
		&&
		'publish' !== $old_status
	);
	if ( ! $is_publishing_changeset ) {
		return;
	}

	if ( empty( $wp_customize ) ) {
		require_once ABSPATH . WPINC . '/class-wp-customize-manager.php';
		$wp_customize = new WP_Customize_Manager(
			array(
				'changeset_uuid'     => $changeset_post->post_name,
				'settings_previewed' => false,
			)
		);
	}

	if ( ! did_action( 'customize_register' ) ) {
		/*
		 * When running from CLI or Cron, the customize_register action will need
		 * to be triggered in order for core, themes, and plugins to register their
		 * settings. Normally core will add_action( 'customize_register' ) at
		 * priority 10 to register the core settings, and if any themes/plugins
		 * also add_action( 'customize_register' ) at the same priority, they
		 * will have a $wp_customize with those settings registered since they
		 * call add_action() afterward, normally. However, when manually doing
		 * the customize_register action after the setup_theme, then the order
		 * will be reversed for two actions added at priority 10, resulting in
		 * the core settings no longer being available as expected to themes/plugins.
		 * So the following manually calls the method that registers the core
		 * settings up front before doing the action.
		 */
		remove_action( 'customize_register', array( $wp_customize, 'register_controls' ) );
		$wp_customize->register_controls();

		/** This filter is documented in wp-includes/class-wp-customize-manager.php */
		do_action( 'customize_register', $wp_customize );
	}
	$wp_customize->_publish_changeset_values( $changeset_post->ID );

	/*
	 * Trash the changeset post if revisions are not enabled. Unpublished
	 * changesets by default get garbage collected due to the auto-draft status.
	 * When a changeset post is published, however, it would no longer get cleaned
	 * out. This is a problem when the changeset posts are never displayed anywhere,
	 * since they would just be endlessly piling up. So here we use the revisions
	 * feature to indicate whether or not a published changeset should get trashed
	 * and thus garbage collected.
	 */
	if ( ! wp_revisions_enabled( $changeset_post ) ) {
		$wp_customize->trash_changeset_post( $changeset_post->ID );
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/theme.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/theme.php#L3640) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/theme.php#L3640-L3699)

## [Hooks](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/\#hooks)

[do\_action( ‘customize\_register’, WP\_Customize\_Manager$manager )](https://developer.wordpress.org/reference/hooks/customize_register/)

Fires once WordPress has loaded, allowing scripts and styles to be initialized.

## [Related](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/\#related)

| Uses | Description |
| --- | --- |
| [WP\_Customize\_Manager::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_customize_manager/__construct/) `wp-includes/class-wp-customize-manager.php` | Constructor. |
| [remove\_action()](https://developer.wordpress.org/reference/functions/remove_action/) `wp-includes/plugin.php` | Removes a callback function from an action hook. |
| [did\_action()](https://developer.wordpress.org/reference/functions/did_action/) `wp-includes/plugin.php` | Retrieves the number of times an action has been fired during the current request. |
| [wp\_revisions\_enabled()](https://developer.wordpress.org/reference/functions/wp_revisions_enabled/) `wp-includes/revision.php` | Determines whether revisions are enabled for a given post. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |

[Show 1 more](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#) [Show less](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/#)

## [Changelog](https://developer.wordpress.org/reference/functions/_wp_customize_publish_changeset/\#changelog)

| Version | Description |
| --- | --- |
| [4.7.0](https://developer.wordpress.org/reference/since/4.7.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2F_wp_customize_publish_changeset%2F) before being able to contribute a note or feedback.

Notifications