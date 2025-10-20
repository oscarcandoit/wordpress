---
url: https://developer.wordpress.org/reference/functions/is_main_site
scraped_at: 2025-10-20T03:20:45.444Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/is_main_site/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

is\_main\_site()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)is\_main\_site()

Search

# is\_main\_site( int$site\_id = null, int$network\_id = null ): bool

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/functions/is_main_site/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/is_main_site/#return)
- [More Information](https://developer.wordpress.org/reference/functions/is_main_site/#more-information)
- [Source](https://developer.wordpress.org/reference/functions/is_main_site/#source)
- [Related](https://developer.wordpress.org/reference/functions/is_main_site/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/is_main_site/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/is_main_site/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/is_main_site/#wp--skip-link--target)

Determines whether a site is the main site of the current network.

## [Parameters](https://developer.wordpress.org/reference/functions/is_main_site/\#parameters)

`$site_id` intoptional

Site ID to test. Defaults to current site.

Default: `null`

`$network_id` intoptional

Network ID of the network to check for.

Defaults to current network.

Default: `null`

## [Return](https://developer.wordpress.org/reference/functions/is_main_site/\#return)

bool True if $site\_id is the main site of the network, or if not running Multisite.

## [More Information](https://developer.wordpress.org/reference/functions/is_main_site/\#more-information)

Replaces function `is_main_blog()`, deprecated since 3.0.0. (wp-includes/ms-deprecated.php)

## [Source](https://developer.wordpress.org/reference/functions/is_main_site/\#source)

`wp-includes/functions.php`
[Expand code](https://developer.wordpress.org/reference/functions/is_main_site/#)

[Copy](https://developer.wordpress.org/reference/functions/is_main_site/#)

```php
function is_main_site( $site_id = null, $network_id = null ) {
	if ( ! is_multisite() ) {
		return true;
	}

	if ( ! $site_id ) {
		$site_id = get_current_blog_id();
	}

	$site_id = (int) $site_id;

	return get_main_site_id( $network_id ) === $site_id;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/functions.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/functions.php#L6400) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/functions.php#L6400-L6412)

## [Related](https://developer.wordpress.org/reference/functions/is_main_site/\#related)

| Uses | Description |
| --- | --- |
| [get\_main\_site\_id()](https://developer.wordpress.org/reference/functions/get_main_site_id/) `wp-includes/functions.php` | Gets the main site ID. |
| [is\_multisite()](https://developer.wordpress.org/reference/functions/is_multisite/) `wp-includes/load.php` | Determines whether Multisite is enabled. |
| [get\_current\_blog\_id()](https://developer.wordpress.org/reference/functions/get_current_blog_id/) `wp-includes/load.php` | Retrieves the current site ID. |

[Show 1 more](https://developer.wordpress.org/reference/functions/is_main_site/#) [Show less](https://developer.wordpress.org/reference/functions/is_main_site/#)

| Used by | Description |
| --- | --- |
| [wp\_schedule\_update\_user\_counts()](https://developer.wordpress.org/reference/functions/wp_schedule_update_user_counts/) `wp-includes/user.php` | Schedules a recurring recalculation of the total count of users. |
| [WP\_MS\_Sites\_List\_Table::site\_states()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/site_states/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Determines whether to output comma-separated site states. |
| [WP\_Site\_Health\_Auto\_Updates::test\_wp\_version\_check\_attached()](https://developer.wordpress.org/reference/classes/wp_site_health_auto_updates/test_wp_version_check_attached/) `wp-admin/includes/class-wp-site-health-auto-updates.php` | Checks if updates are intercepted by a filter. |
| [delete\_expired\_transients()](https://developer.wordpress.org/reference/functions/delete_expired_transients/) `wp-includes/option.php` | Deletes all expired transients. |
| [wp\_load\_press\_this()](https://developer.wordpress.org/reference/functions/wp_load_press_this/) `wp-admin/press-this.php` |  |
| [\_wp\_upload\_dir()](https://developer.wordpress.org/reference/functions/_wp_upload_dir/) `wp-includes/functions.php` | A non-filtered, non-cached version of [wp\_upload\_dir()](https://developer.wordpress.org/reference/functions/wp_upload_dir/) that doesn’t check the path. |
| [WP\_MS\_Sites\_List\_Table::handle\_row\_actions()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/handle_row_actions/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Generates and displays row action links. |
| [WP\_MS\_Sites\_List\_Table::column\_cb()](https://developer.wordpress.org/reference/classes/wp_ms_sites_list_table/column_cb/) `wp-admin/includes/class-wp-ms-sites-list-table.php` | Handles the checkbox column output. |
| [wp\_should\_upgrade\_global\_tables()](https://developer.wordpress.org/reference/functions/wp_should_upgrade_global_tables/) `wp-admin/includes/upgrade.php` | Determine if global tables should be upgraded. |
| [WP\_Automatic\_Updater::run()](https://developer.wordpress.org/reference/classes/wp_automatic_updater/run/) `wp-admin/includes/class-wp-automatic-updater.php` | Kicks off the background update process, looping through all pending updates. |
| [avoid\_blog\_page\_permalink\_collision()](https://developer.wordpress.org/reference/functions/avoid_blog_page_permalink_collision/) `wp-admin/includes/ms.php` | Avoids a collision between a site slug and a permalink slug. |
| [wpmu\_delete\_blog()](https://developer.wordpress.org/reference/functions/wpmu_delete_blog/) `wp-admin/includes/ms.php` | Deletes a site. |
| [wp\_upgrade()](https://developer.wordpress.org/reference/functions/wp_upgrade/) `wp-admin/includes/upgrade.php` | Runs WordPress Upgrade functions. |
| [WP\_Rewrite::rewrite\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/rewrite_rules/) `wp-includes/class-wp-rewrite.php` | Constructs rewrite matches and queries from permalink structure. |
| [wp\_schedule\_update\_network\_counts()](https://developer.wordpress.org/reference/functions/wp_schedule_update_network_counts/) `wp-includes/ms-functions.php` | Schedules update of the network-wide counts for the current network. |
| [get\_dirsize()](https://developer.wordpress.org/reference/functions/get_dirsize/) `wp-includes/functions.php` | Gets the size of a directory. |
| [maybe\_redirect\_404()](https://developer.wordpress.org/reference/functions/maybe_redirect_404/) `wp-includes/ms-functions.php` | Corrects 404 redirects when NOBLOGREDIRECT is defined. |
| [is\_main\_blog()](https://developer.wordpress.org/reference/functions/is_main_blog/) `wp-includes/ms-deprecated.php` | Deprecated functionality to determine if the current site is the main site. |

[Show 13 more](https://developer.wordpress.org/reference/functions/is_main_site/#) [Show less](https://developer.wordpress.org/reference/functions/is_main_site/#)

## [Changelog](https://developer.wordpress.org/reference/functions/is_main_site/\#changelog)

| Version | Description |
| --- | --- |
| [4.9.0](https://developer.wordpress.org/reference/since/4.9.0/) | The `$network_id` parameter was added. |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/is_main_site/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/functions/is_main_site/#comment-content-1398)



**Example**





`wp-includes/functions.php`
[Copy](https://developer.wordpress.org/reference/functions/is_main_site/#)




```php
if ( is_main_site( $blog_id ) ) {
     // display something special for the main site.
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_main_site%2F%3Freplytocom%3D1398%23feedback-editor-1398)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fis_main_site%2F) before being able to contribute a note or feedback.

Notifications