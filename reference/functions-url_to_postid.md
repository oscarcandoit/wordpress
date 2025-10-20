---
url: https://developer.wordpress.org/reference/functions/url_to_postid
scraped_at: 2025-10-20T03:21:36.058Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/url_to_postid/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

url\_to\_postid()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)url\_to\_postid()

Search

# url\_to\_postid( string$url ): int

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/url_to_postid/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/url_to_postid/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/url_to_postid/#return)
- [Source](https://developer.wordpress.org/reference/functions/url_to_postid/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/url_to_postid/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/url_to_postid/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/url_to_postid/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/url_to_postid/#wp--skip-link--target)

Examines a URL and try to determine the post ID it represents.

## [Description](https://developer.wordpress.org/reference/functions/url_to_postid/\#description)

Checks are supposedly from the hosted site blog.

## [Parameters](https://developer.wordpress.org/reference/functions/url_to_postid/\#parameters)

`$url` stringrequired

Permalink to check.

## [Return](https://developer.wordpress.org/reference/functions/url_to_postid/\#return)

int Post ID, or 0 on failure.

## [Source](https://developer.wordpress.org/reference/functions/url_to_postid/\#source)

`wp-includes/rewrite.php`
[Expand code](https://developer.wordpress.org/reference/functions/url_to_postid/#)

[Copy](https://developer.wordpress.org/reference/functions/url_to_postid/#)

```php
function url_to_postid( $url ) {
	global $wp_rewrite;

	/**
	 * Filters the URL to derive the post ID from.
	 *
	 * @since 2.2.0
	 *
	 * @param string $url The URL to derive the post ID from.
	 */
	$url = apply_filters( 'url_to_postid', $url );

	$url_host = parse_url( $url, PHP_URL_HOST );

	if ( is_string( $url_host ) ) {
		$url_host = str_replace( 'www.', '', $url_host );
	} else {
		$url_host = '';
	}

	$home_url_host = parse_url( home_url(), PHP_URL_HOST );

	if ( is_string( $home_url_host ) ) {
		$home_url_host = str_replace( 'www.', '', $home_url_host );
	} else {
		$home_url_host = '';
	}

	// Bail early if the URL does not belong to this site.
	if ( $url_host && $url_host !== $home_url_host ) {
		return 0;
	}

	// First, check to see if there is a 'p=N' or 'page_id=N' to match against.
	if ( preg_match( '#[?&](p|page_id|attachment_id)=(\d+)#', $url, $values ) ) {
		$id = absint( $values[2] );
		if ( $id ) {
			return $id;
		}
	}

	// Get rid of the #anchor.
	$url_split = explode( '#', $url );
	$url       = $url_split[0];

	// Get rid of URL ?query=string.
	$url_split = explode( '?', $url );
	$url       = $url_split[0];

	// Set the correct URL scheme.
	$scheme = parse_url( home_url(), PHP_URL_SCHEME );
	$url    = set_url_scheme( $url, $scheme );

	// Add 'www.' if it is absent and should be there.
	if ( str_contains( home_url(), '://www.' ) && ! str_contains( $url, '://www.' ) ) {
		$url = str_replace( '://', '://www.', $url );
	}

	// Strip 'www.' if it is present and shouldn't be.
	if ( ! str_contains( home_url(), '://www.' ) ) {
		$url = str_replace( '://www.', '://', $url );
	}

	if ( trim( $url, '/' ) === home_url() && 'page' === get_option( 'show_on_front' ) ) {
		$page_on_front = get_option( 'page_on_front' );

		if ( $page_on_front && get_post( $page_on_front ) instanceof WP_Post ) {
			return (int) $page_on_front;
		}
	}

	// Check to see if we are using rewrite rules.
	$rewrite = $wp_rewrite->wp_rewrite_rules();

	// Not using rewrite rules, and 'p=N' and 'page_id=N' methods failed, so we're out of options.
	if ( empty( $rewrite ) ) {
		return 0;
	}

	// Strip 'index.php/' if we're not using path info permalinks.
	if ( ! $wp_rewrite->using_index_permalinks() ) {
		$url = str_replace( $wp_rewrite->index . '/', '', $url );
	}

	if ( str_contains( trailingslashit( $url ), home_url( '/' ) ) ) {
		// Chop off http://domain.com/[path].
		$url = str_replace( home_url(), '', $url );
	} else {
		// Chop off /path/to/blog.
		$home_path = parse_url( home_url( '/' ) );
		$home_path = isset( $home_path['path'] ) ? $home_path['path'] : '';
		$url       = preg_replace( sprintf( '#^%s#', preg_quote( $home_path ) ), '', trailingslashit( $url ) );
	}

	// Trim leading and lagging slashes.
	$url = trim( $url, '/' );

	$request              = $url;
	$post_type_query_vars = array();

	foreach ( get_post_types( array(), 'objects' ) as $post_type => $t ) {
		if ( ! empty( $t->query_var ) ) {
			$post_type_query_vars[ $t->query_var ] = $post_type;
		}
	}

	// Look for matches.
	$request_match = $request;
	foreach ( (array) $rewrite as $match => $query ) {

		/*
		 * If the requesting file is the anchor of the match,
		 * prepend it to the path info.
		 */
		if ( ! empty( $url ) && ( $url !== $request ) && str_starts_with( $match, $url ) ) {
			$request_match = $url . '/' . $request;
		}

		if ( preg_match( "#^$match#", $request_match, $matches ) ) {

			if ( $wp_rewrite->use_verbose_page_rules && preg_match( '/pagename=\$matches\[([0-9]+)\]/', $query, $varmatch ) ) {
				// This is a verbose page match, let's check to be sure about it.
				$page = get_page_by_path( $matches[ $varmatch[1] ] );
				if ( ! $page ) {
					continue;
				}

				$post_status_obj = get_post_status_object( $page->post_status );
				if ( ! $post_status_obj->public && ! $post_status_obj->protected
					&& ! $post_status_obj->private && $post_status_obj->exclude_from_search ) {
					continue;
				}
			}

			/*
			 * Got a match.
			 * Trim the query of everything up to the '?'.
			 */
			$query = preg_replace( '!^.+\?!', '', $query );

			// Substitute the substring matches into the query.
			$query = addslashes( WP_MatchesMapRegex::apply( $query, $matches ) );

			// Filter out non-public query vars.
			global $wp;
			parse_str( $query, $query_vars );
			$query = array();
			foreach ( (array) $query_vars as $key => $value ) {
				if ( in_array( (string) $key, $wp->public_query_vars, true ) ) {
					$query[ $key ] = $value;
					if ( isset( $post_type_query_vars[ $key ] ) ) {
						$query['post_type'] = $post_type_query_vars[ $key ];
						$query['name']      = $value;
					}
				}
			}

			// Resolve conflicts between posts with numeric slugs and date archive queries.
			$query = wp_resolve_numeric_slug_conflicts( $query );

			// Do the query.
			$query = new WP_Query( $query );
			if ( ! empty( $query->posts ) && $query->is_singular ) {
				return $query->post->ID;
			} else {
				return 0;
			}
		}
	}
	return 0;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/rewrite.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/rewrite.php#L492) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/rewrite.php#L492-L662)

## [Hooks](https://developer.wordpress.org/reference/functions/url_to_postid/\#hooks)

[apply\_filters( ‘url\_to\_postid’, string$url )](https://developer.wordpress.org/reference/hooks/url_to_postid/)

Filters the URL to derive the post ID from.

## [Related](https://developer.wordpress.org/reference/functions/url_to_postid/\#related)

| Uses | Description |
| --- | --- |
| [wp\_resolve\_numeric\_slug\_conflicts()](https://developer.wordpress.org/reference/functions/wp_resolve_numeric_slug_conflicts/) `wp-includes/rewrite.php` | Resolves numeric slugs that collide with date permalinks. |
| [WP\_MatchesMapRegex::apply()](https://developer.wordpress.org/reference/classes/wp_matchesmapregex/apply/) `wp-includes/class-wp-matchesmapregex.php` | Substitute substring matches in subject. |
| [WP\_Query::\_\_construct()](https://developer.wordpress.org/reference/classes/wp_query/__construct/) `wp-includes/class-wp-query.php` | Constructor. |
| [set\_url\_scheme()](https://developer.wordpress.org/reference/functions/set_url_scheme/) `wp-includes/link-template.php` | Sets the scheme for a URL. |
| [get\_page\_by\_path()](https://developer.wordpress.org/reference/functions/get_page_by_path/) `wp-includes/post.php` | Retrieves a page given its path. |
| [get\_post\_status\_object()](https://developer.wordpress.org/reference/functions/get_post_status_object/) `wp-includes/post.php` | Retrieves a post status object by name. |
| [WP\_Rewrite::wp\_rewrite\_rules()](https://developer.wordpress.org/reference/classes/wp_rewrite/wp_rewrite_rules/) `wp-includes/class-wp-rewrite.php` | Retrieves the rewrite rules. |
| [WP\_Rewrite::using\_index\_permalinks()](https://developer.wordpress.org/reference/classes/wp_rewrite/using_index_permalinks/) `wp-includes/class-wp-rewrite.php` | Determines whether permalinks are being used and rewrite module is not enabled. |
| [trailingslashit()](https://developer.wordpress.org/reference/functions/trailingslashit/) `wp-includes/formatting.php` | Appends a trailing slash. |
| [absint()](https://developer.wordpress.org/reference/functions/absint/) `wp-includes/load.php` | Converts a value to non-negative integer. |
| [home\_url()](https://developer.wordpress.org/reference/functions/home_url/) `wp-includes/link-template.php` | Retrieves the URL for the current site where the front end is accessible. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |
| [get\_post\_types()](https://developer.wordpress.org/reference/functions/get_post_types/) `wp-includes/post.php` | Gets a list of all registered post type objects. |

[Show 10 more](https://developer.wordpress.org/reference/functions/url_to_postid/#) [Show less](https://developer.wordpress.org/reference/functions/url_to_postid/#)

| Used by | Description |
| --- | --- |
| [get\_oembed\_response\_data\_for\_url()](https://developer.wordpress.org/reference/functions/get_oembed_response_data_for_url/) `wp-includes/embed.php` | Retrieves the oEmbed response data for a given URL. |
| [WP\_oEmbed\_Controller::get\_item()](https://developer.wordpress.org/reference/classes/wp_oembed_controller/get_item/) `wp-includes/class-wp-oembed-controller.php` | Callback for the embed API endpoint. |
| [is\_local\_attachment()](https://developer.wordpress.org/reference/functions/is_local_attachment/) `wp-includes/post.php` | Determines whether an attachment URI is local and really an attachment. |
| [wp\_xmlrpc\_server::pingback\_ping()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/pingback_ping/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves a pingback and registers it. |
| [wp\_xmlrpc\_server::pingback\_extensions\_getPingbacks()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/pingback_extensions_getpingbacks/) `wp-includes/class-wp-xmlrpc-server.php` | Retrieves an array of URLs that pingbacked the given URL. |
| [wp\_xmlrpc\_server::wp\_newComment()](https://developer.wordpress.org/reference/classes/wp_xmlrpc_server/wp_newcomment/) `wp-includes/class-wp-xmlrpc-server.php` | Creates a new comment. |
| [pingback()](https://developer.wordpress.org/reference/functions/pingback/) `wp-includes/comment.php` | Pings back the links found in a post. |

[Show 2 more](https://developer.wordpress.org/reference/functions/url_to_postid/#) [Show less](https://developer.wordpress.org/reference/functions/url_to_postid/#)

## [Changelog](https://developer.wordpress.org/reference/functions/url_to_postid/\#changelog)

| Version | Description |
| --- | --- |
| [1.0.0](https://developer.wordpress.org/reference/since/1.0.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Furl_to_postid%2F) before being able to contribute a note or feedback.

Notifications