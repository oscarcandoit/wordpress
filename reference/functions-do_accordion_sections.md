---
url: https://developer.wordpress.org/reference/functions/do_accordion_sections
scraped_at: 2025-10-20T03:20:10.004Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/do_accordion_sections/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

do\_accordion\_sections()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)do\_accordion\_sections()

Search

# do\_accordion\_sections( string\|object$screen, string$context, mixed$data\_object ): int

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/do_accordion_sections/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/do_accordion_sections/#parameters)
- [Return](https://developer.wordpress.org/reference/functions/do_accordion_sections/#return)
- [Source](https://developer.wordpress.org/reference/functions/do_accordion_sections/#source)
- [Related](https://developer.wordpress.org/reference/functions/do_accordion_sections/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/do_accordion_sections/#changelog)

[↑ Back to top](https://developer.wordpress.org/reference/functions/do_accordion_sections/#wp--skip-link--target)

Meta Box Accordion Template Function.

## [Description](https://developer.wordpress.org/reference/functions/do_accordion_sections/\#description)

Largely made up of abstracted code from [do\_meta\_boxes()](https://developer.wordpress.org/reference/functions/do_meta_boxes/) , this function serves to build meta boxes as list items for display as a collapsible accordion.

## [Parameters](https://developer.wordpress.org/reference/functions/do_accordion_sections/\#parameters)

`$screen` string\|objectrequired

The screen identifier.

`$context` stringrequired

The screen context for which to display accordion sections.

`$data_object` mixedrequired

Gets passed to the section callback function as the first parameter.

## [Return](https://developer.wordpress.org/reference/functions/do_accordion_sections/\#return)

int Number of meta boxes as accordion sections.

## [Source](https://developer.wordpress.org/reference/functions/do_accordion_sections/\#source)

`wp-admin/includes/template.php`
[Expand code](https://developer.wordpress.org/reference/functions/do_accordion_sections/#)

[Copy](https://developer.wordpress.org/reference/functions/do_accordion_sections/#)

```php
function do_accordion_sections( $screen, $context, $data_object ) {
	global $wp_meta_boxes;

	wp_enqueue_script( 'accordion' );

	if ( empty( $screen ) ) {
		$screen = get_current_screen();
	} elseif ( is_string( $screen ) ) {
		$screen = convert_to_screen( $screen );
	}

	$page = $screen->id;

	$hidden = get_hidden_meta_boxes( $screen );
	?>
	<div id="side-sortables" class="accordion-container">
		<ul class="outer-border">
	<?php
	$i          = 0;
	$first_open = false;

	if ( isset( $wp_meta_boxes[ $page ][ $context ] ) ) {
		foreach ( array( 'high', 'core', 'default', 'low' ) as $priority ) {
			if ( isset( $wp_meta_boxes[ $page ][ $context ][ $priority ] ) ) {
				foreach ( $wp_meta_boxes[ $page ][ $context ][ $priority ] as $box ) {
					if ( false === $box || ! $box['title'] ) {
						continue;
					}

					++$i;
					$hidden_class = in_array( $box['id'], $hidden, true ) ? 'hide-if-js' : '';

					$open_class    = '';
					$aria_expanded = 'false';
					if ( ! $first_open && empty( $hidden_class ) ) {
						$first_open    = true;
						$open_class    = 'open';
						$aria_expanded = 'true';
					}
					?>
					<li class="control-section accordion-section <?php echo $hidden_class; ?> <?php echo $open_class; ?> <?php echo esc_attr( $box['id'] ); ?>" id="<?php echo esc_attr( $box['id'] ); ?>">
						<h3 class="accordion-section-title hndle">
							<button type="button" class="accordion-trigger" aria-expanded="<?php echo $aria_expanded; ?>" aria-controls="<?php echo esc_attr( $box['id'] ); ?>-content">
								<span class="accordion-title">
									<?php echo esc_html( $box['title'] ); ?>
									<span class="dashicons dashicons-arrow-down" aria-hidden="true"></span>
								</span>
							</button>
						</h3>
						<div class="accordion-section-content <?php postbox_classes( $box['id'], $page ); ?>" id="<?php echo esc_attr( $box['id'] ); ?>-content">
							<div class="inside">
								<?php call_user_func( $box['callback'], $data_object, $box ); ?>
							</div><!-- .inside -->
						</div><!-- .accordion-section-content -->
					</li><!-- .accordion-section -->
					<?php
				}
			}
		}
	}
	?>
		</ul><!-- .outer-border -->
	</div><!-- .accordion-container -->
	<?php
	return $i;
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/template.php#L1537) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/template.php#L1537-L1602)

## [Related](https://developer.wordpress.org/reference/functions/do_accordion_sections/\#related)

| Uses | Description |
| --- | --- |
| [get\_current\_screen()](https://developer.wordpress.org/reference/functions/get_current_screen/) `wp-admin/includes/screen.php` | Get the current screen object |
| [get\_hidden\_meta\_boxes()](https://developer.wordpress.org/reference/functions/get_hidden_meta_boxes/) `wp-admin/includes/screen.php` | Gets an array of IDs of hidden meta boxes. |
| [convert\_to\_screen()](https://developer.wordpress.org/reference/functions/convert_to_screen/) `wp-admin/includes/template.php` | Converts a screen string to a screen object. |
| [postbox\_classes()](https://developer.wordpress.org/reference/functions/postbox_classes/) `wp-admin/includes/post.php` | Returns the list of classes to be used by a meta box. |
| [wp\_enqueue\_script()](https://developer.wordpress.org/reference/functions/wp_enqueue_script/) `wp-includes/functions.wp-scripts.php` | Enqueues a script. |
| [esc\_attr()](https://developer.wordpress.org/reference/functions/esc_attr/) `wp-includes/formatting.php` | Escaping for HTML attributes. |
| [esc\_html()](https://developer.wordpress.org/reference/functions/esc_html/) `wp-includes/formatting.php` | Escaping for HTML blocks. |

[Show 2 more](https://developer.wordpress.org/reference/functions/do_accordion_sections/#) [Show less](https://developer.wordpress.org/reference/functions/do_accordion_sections/#)

## [Changelog](https://developer.wordpress.org/reference/functions/do_accordion_sections/\#changelog)

| Version | Description |
| --- | --- |
| [3.6.0](https://developer.wordpress.org/reference/since/3.6.0/) | Introduced. |

## User Contributed Notes

You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fdo_accordion_sections%2F) before being able to contribute a note or feedback.

Notifications