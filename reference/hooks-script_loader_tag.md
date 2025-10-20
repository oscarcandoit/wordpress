---
url: https://developer.wordpress.org/reference/hooks/script_loader_tag
scraped_at: 2025-10-20T03:19:15.870Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/script_loader_tag/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

script\_loader\_tag


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_Scripts::do\_item](https://developer.wordpress.org/reference/classes/wp_scripts/do_item/)script\_loader\_tag

Search

# apply\_filters( ‘script\_loader\_tag’, string$tag, string$handle, string$src )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/script_loader_tag/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/script_loader_tag/#source)
- [Related](https://developer.wordpress.org/reference/hooks/script_loader_tag/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/script_loader_tag/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/script_loader_tag/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/script_loader_tag/#wp--skip-link--target)

Filters the HTML script tag of an enqueued script.

## [Parameters](https://developer.wordpress.org/reference/hooks/script_loader_tag/\#parameters)

`$tag` string

The `<script>` tag for the enqueued script.

`$handle` string

The script’s registered handle.

`$src` string

The script’s source URL.

## [Source](https://developer.wordpress.org/reference/hooks/script_loader_tag/\#source)

`wp-includes/class-wp-scripts.php`
[Copy](https://developer.wordpress.org/reference/hooks/script_loader_tag/#)

```php
$tag = apply_filters( 'script_loader_tag', $tag, $handle, $src );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes_class-wp-scripts-php-2/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-scripts.php#L441) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-scripts.php#L441-L441)

## [Related](https://developer.wordpress.org/reference/hooks/script_loader_tag/\#related)

| Used by | Description |
| --- | --- |
| [WP\_Scripts::do\_item()](https://developer.wordpress.org/reference/classes/wp_scripts/do_item/) `wp-includes/class-wp-scripts.php` | Processes a script dependency. |

## [Changelog](https://developer.wordpress.org/reference/hooks/script_loader_tag/\#changelog)

| Version | Description |
| --- | --- |
| [4.1.0](https://developer.wordpress.org/reference/since/4.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/script_loader_tag/\#user-contributed-notes)

1. [Skip to note 3 content](https://developer.wordpress.org/reference/hooks/script_loader_tag/#comment-content-1902)



Useful when a script excecution depends on “ attributes, eg:





`wp-includes/class-wp-scripts.php`
[Copy](https://developer.wordpress.org/reference/hooks/script_loader_tag/#)




```php
add_filter( 'script_loader_tag', 'add_id_to_script', 10, 3 );

function add_id_to_script( $tag, $handle, $src ) {
       if ( 'dropbox.js' === $handle ) {
           $tag = '<script type="text/javascript" src="' . esc_url( $src ) . '" id="dropboxjs" data-app-key="MY_APP_KEY"></script>';
       }

       return $tag;
}
```







[Show feedback (3)](https://developer.wordpress.org/reference/hooks/script_loader_tag/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fscript_loader_tag%2F%3Freplytocom%3D1902%23feedback-editor-1902)



- Missing { on line 4.



[Sam Kent](https://profiles.wordpress.org/oxocube/) [7 years ago](https://developer.wordpress.org/reference/hooks/script_loader_tag/#comment-2797)

- Is it possible to do with Array? I have several Scripts that I want to do this, can I just replicate this code by changing the scripts? An Array would be better, right?



[ofmarconi](https://profiles.wordpress.org/ofmarconi/) [3 years ago](https://developer.wordpress.org/reference/hooks/script_loader_tag/#comment-5867)

- When I check this with PHPCS against the WordPress coding standard, it returns and error `Scripts must be registered/enqueued via wp_enqueue_script()`



[Peter Hebert](https://profiles.wordpress.org/peterhebert/) [2 years ago](https://developer.wordpress.org/reference/hooks/script_loader_tag/#comment-6883)


2. [Skip to note 4 content](https://developer.wordpress.org/reference/hooks/script_loader_tag/#comment-content-5507)



It can be used to defer or async all JS scripts :





`wp-includes/class-wp-scripts.php`
[Copy](https://developer.wordpress.org/reference/hooks/script_loader_tag/#)




```php
function prefix_defer_js( $html ) {
       if ( ! is_admin() ) {
           $html = str_replace( '></script>', ' defer></script>', $html );
       }
       return $html;
}
add_filter( 'script_loader_tag', 'prefix_defer_js' );
```





You can also use the `$handle` argument to filter scripts.





[Show feedback (1)](https://developer.wordpress.org/reference/hooks/script_loader_tag/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fscript_loader_tag%2F%3Freplytocom%3D5507%23feedback-editor-5507)



- To expand on Geoffrey Brossard’s note, you might run into issues deferring all, the example below you can exclude the handles you might need from this filter like so:







`wp-includes/class-wp-scripts.php`
[Copy](https://developer.wordpress.org/reference/hooks/script_loader_tag/#)




```php
     function prefix_defer_js($tag, $handle) {  	if (is_admin()) return $tag;  	 	$exclude_handles = [  	 		'heartbeat',  	 		'wp-hooks',  	 		'wp-auth-check',  	 		'jquery',  	 		'jquery-core',   			'jquery-ui-core',  	 		'wp-i18n'  	 	];  	 	if (in_array($handle, $exclude_handles)) {  	 		$tag = $tag;  	 	} else {  	 		$tag = str_replace('>', ' defer>', $tag);  	 	}   		return $tag;  	 }  	 add_filter('script_loader_tag', 'prefix_defer_js', 10, 2);
```







[studiolxv](https://profiles.wordpress.org/studiolxv/) [3 years ago](https://developer.wordpress.org/reference/hooks/script_loader_tag/#comment-6257)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fscript_loader_tag%2F) before being able to contribute a note or feedback.

Notifications