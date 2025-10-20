---
url: https://developer.wordpress.org/apis/transients
scraped_at: 2025-10-20T04:07:19.155Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/transients/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Transients


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Transients

Search

# Transients

## In this article

Table of Contents

- [Overview](https://developer.wordpress.org/apis/transients/#overview)
- [Function Reference](https://developer.wordpress.org/apis/transients/#function-reference)
- [Using Transients](https://developer.wordpress.org/apis/transients/#using-transients)
  - [Saving Transients](https://developer.wordpress.org/apis/transients/#saving-transients)
  - [Fetching Transients](https://developer.wordpress.org/apis/transients/#fetching-transients)
  - [Removing Saved Transients](https://developer.wordpress.org/apis/transients/#removing-saved-transients)
- [Complete Example](https://developer.wordpress.org/apis/transients/#complete-example)

[↑ Back to top](https://developer.wordpress.org/apis/transients/#wp--skip-link--target)

## [Overview](https://developer.wordpress.org/apis/transients/\#overview)

This page contains the technical documentation of **WordPress Transients API**, which offers a simple and standardized way of storing cached data in the database temporarily by giving it a custom name and a timeframe after which it will expire and be deleted.

The Transients API is very similar to the [Options API](https://developer.wordpress.org/plugins/settings/options-api/) but with the added feature of an expiration time, which simplifies the process of using the `wp_options` database table to temporarily store cached information.

Note that the “site\_” functions are essentially the same as their counterparts, but work network wide when using WordPress [Multisite](https://codex.wordpress.org/Glossary#Multisite).

Also of note is that Transients are inherently sped up by caching plugins, where normal Options are not. A _memcached_ plugin, for example, would make WordPress store transient values in fast memory instead of in the database. For this reason, transients should be used to store any data that is expected to expire, or which can expire at any time. Transients should also never be assumed to be in the database, since they may not be stored there at all.

Furthermore, it is possible for the transient to not be available before the expiration time. Much like what is done with caching, your code should have a fall back method to re-generate the data if the transient is not available.

Ryan McCue explained it this way on a [ticket](https://core.trac.wordpress.org/ticket/20316#comment:47):

> Everyone seems to misunderstand how transient expiration works, so the long and short of it is: transient expiration times are a maximum time. There is no minimum age. Transients might disappear one second after you set them, or 24 hours, but they will never be around after the expiration time.

The intended audience for this article includes WordPress theme authors, plugin authors and anyone who needs to cache specific data but wants it to be refreshed within a given timeframe. This document assumes a basic understanding of PHP scripting.

## [Function Reference](https://developer.wordpress.org/apis/transients/\#function-reference)

**Set/Get Transient:**

- [set\_transient()](https://developer.wordpress.org/reference/functions/set_transient/)
- [get\_transient()](https://developer.wordpress.org/reference/functions/get_transient/)
- [set\_site\_transient()](https://developer.wordpress.org/reference/functions/set_site_transient/)
- [get\_site\_transient()](https://developer.wordpress.org/reference/functions/get_site_transient/)

**Delete Transient:**

- [delete\_transient()](https://developer.wordpress.org/reference/functions/delete_transient/)
- [delete\_site\_transient()](https://developer.wordpress.org/reference/functions/delete_site_transient/)

## [Using Transients](https://developer.wordpress.org/apis/transients/\#using-transients)

### [Saving Transients](https://developer.wordpress.org/apis/transients/\#saving-transients)

To save a transient you use [set\_transient()](https://developer.wordpress.org/reference/functions/set_transient/):

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
set_transient( $transient, $value, $expiration );
```

- `$transient` (string): Transient name.

Expected to not be SQL-escaped. Must be 172 characters or fewer in length.
- `$value` (array\|object): Data to save, either a regular variable or an array/object.

The API will handle serialization of complex data for you.
- `$expiration` (integer): The maximum of seconds to keep the data before refreshing.

Transients may expire before the `$expiration` (Due to External Object Caches, or database upgrades) but will never return their value past $expiration.

So for example to save the `$special_query_results` object for 12 hours you would do:

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
set_transient( 'special_query_results', $special_query_results, 60*60*12 );
```

#### [Using Time Constants](https://developer.wordpress.org/apis/transients/\#using-time-constants)

In [WordPress 3.5](https://codex.wordpress.org/Version_3.5), several constants were introduced to easily express time:

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
MINUTE_IN_SECONDS  = 60 (seconds)
HOUR_IN_SECONDS    = 60 * MINUTE_IN_SECONDS
DAY_IN_SECONDS     = 24 * HOUR_IN_SECONDS
WEEK_IN_SECONDS    = 7 * DAY_IN_SECONDS
MONTH_IN_SECONDS   = 30 * DAY_IN_SECONDS
YEAR_IN_SECONDS    = 365 * DAY_IN_SECONDS
```

So for example, the code sample from above can be simplified to:

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
set_transient( 'special_query_results', $special_query_results, 12 * HOUR_IN_SECONDS );
```

### [Fetching Transients](https://developer.wordpress.org/apis/transients/\#fetching-transients)

To get a saved transient you use [get\_transient()](https://developer.wordpress.org/reference/functions/get_transient/):

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
get_transient( $transient );
```

`$transient`: the unique slug used while saving the transient with `set_transient()`.

In our case we could fetch our special query results with:

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
get_transient( 'special_query_results' );
```

If the transient does not exist, or has expired, then `get_transient()` will return `false`. This should be checked using the identity operator `===` instead of the normal equality operator `==`, because an integer value of zero (or other “empty”/”falsey” data) could be the data you’re wanting to store. Because of this “false” value, transients should not be used to hold plain boolean values (true/false). Put them into an array or convert them to integers instead.

Example usage:

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
if ( false === ( $value = get_transient( 'value' ) ) ) {
	// this code runs when there is no valid transient set
}
```

The above code will get the transient and put it into `$value`. The code inside the if block only runs when there’s not a valid transient for it to get. This is typically a method to re-generate the transient value through other means. Keep in mind that it’s possible for a transient to not be available before it’s normal expiration time.

### [Removing Saved Transients](https://developer.wordpress.org/apis/transients/\#removing-saved-transients)

Our transient will die naturally of old age once $expiration seconds have passed since we last ran [set\_transient()](https://developer.wordpress.org/reference/functions/set_transient/), but we can force the transient to die early by manually deleting it. This is useful for times when a given activity (saving a post, adding a category etc.) will make the cached data inherently stale and in need of updating.

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
delete_transient( $transient );
```

`$transient`: the unique name used when saving with `set_transient()`.

In our case, obviously, this would be:

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
delete_transient( 'special_query_results' );
```

WordPress infrequently cleans out expired transients. To prevent expired transients from building up in the database, it’s a good practice to always remove your transient once you are done with it and no longer need it.

## [Complete Example](https://developer.wordpress.org/apis/transients/\#complete-example)

Putting it all together here is an example of how to use transients in your code.

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
<?php
// Get any existing copy of our transient data
if ( false === ( $special_query_results = get_transient( 'special_query_results' ) ) ) {
	// It wasn't there, so regenerate the data and save the transient
	$special_query_results = new WP_Query( 'cat=5&order=random&tag=tech&post_meta_key=thumbnail' );
	set_transient( 'special_query_results', $special_query_results, 12 * HOUR_IN_SECONDS );
}
// Use the data like you would have normally...
?>
```

And an example of using [delete\_transient()](https://developer.wordpress.org/reference/functions/delete_transient/). In this case we’ll add a function to the `edit_term` action, which will run every time a category or tag is edited (i.e. we’re assuming that the editing of a term invalidates our data and we want to remove the cached version).

``
[Copy](https://developer.wordpress.org/apis/transients/#)

```php
<?php
// Create a simple function to delete our transient
function edit_term_delete_transient() {
	delete_transient( 'special_query_results' );
}
// Add the function to the edit_term hook so it runs when categories/tags are edited
add_action( 'edit_term', 'edit_term_delete_transient' );
?>
```

Use transients with [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) to retrieve “featured posts”:

``
[Expand code](https://developer.wordpress.org/apis/transients/#)

[Copy](https://developer.wordpress.org/apis/transients/#)

```php
<?php
// Check for transient. If none, then execute WP_Query
if ( false === ( $featured = get_transient( 'foo_featured_posts' ) ) ) {
	$featured = new WP_Query(
		array(
			'category' => 'featured',
			'posts_per_page' => 5
		)
	);

	// Put the results in a transient. Expire after 12 hours.
	set_transient( 'foo_featured_posts', $featured, 12 * HOUR_IN_SECONDS );
}
?>

// Run the loop as normal

<?php if ( $featured->have_posts() ) : ?>

	<?php while ( $featured->have_posts() ) : $featured->the_post(); ?>
		// featured posts found, do stuff
	<?php endwhile; ?>

<?php else: ?>
	// no featured posts found
<?php endif; ?>

<?php wp_reset_postdata(); ?>

```

Using transients in your plugins and themes is simple and only adds a few extra lines of code, but if used in the right situations (long/expensive database queries or complex processed data) it can save seconds off the load times on your site.

First published

August 12, 2019

Last updated

November 21, 2022

[PreviousThemePrevious: Theme](https://developer.wordpress.org/apis/theme/)

[NextXML-RPCNext: XML-RPC](https://developer.wordpress.org/apis/xml-rpc/)

Notifications