---
url: https://developer.wordpress.org/reference/functions/get_page_template
scraped_at: 2025-10-20T03:17:11.179Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/get_page_template/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

get\_page\_template()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)get\_page\_template()

Search

# get\_page\_template(): string

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/get_page_template/#description)
  - [See also](https://developer.wordpress.org/reference/functions/get_page_template/#see-also)
- [Return](https://developer.wordpress.org/reference/functions/get_page_template/#return)
- [Source](https://developer.wordpress.org/reference/functions/get_page_template/#source)
- [Related](https://developer.wordpress.org/reference/functions/get_page_template/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/get_page_template/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_page_template/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/get_page_template/#wp--skip-link--target)

Retrieves path of page template in current or parent template.

## [Description](https://developer.wordpress.org/reference/functions/get_page_template/\#description)

Note: For block themes, use [locate\_block\_template()](https://developer.wordpress.org/reference/functions/locate_block_template/) function instead.

The hierarchy for this template looks like:

1. {Page Template}.php
2. page-{page\_name}.php
3. page-{id}.php
4. page.php

An example of this is:

1. page-templates/full-width.php
2. page-about.php
3. page-4.php
4. page.php

The template hierarchy and template path are filterable via the [‘$type\_template\_hierarchy’](https://developer.wordpress.org/reference/hooks/type_template_hierarchy/) and [‘$type\_template’](https://developer.wordpress.org/reference/hooks/type_template/) dynamic hooks, where `$type` is ‘page’.

### [See also](https://developer.wordpress.org/reference/functions/get_page_template/\#see-also)

- [get\_query\_template()](https://developer.wordpress.org/reference/functions/get_query_template)

## [Return](https://developer.wordpress.org/reference/functions/get_page_template/\#return)

string Full path to page template file.

## [Source](https://developer.wordpress.org/reference/functions/get_page_template/\#source)

`wp-includes/template.php`
[Expand code](https://developer.wordpress.org/reference/functions/get_page_template/#)

[Copy](https://developer.wordpress.org/reference/functions/get_page_template/#)

```php
function get_page_template() {
	$id       = get_queried_object_id();
	$template = get_page_template_slug();
	$pagename = get_query_var( 'pagename' );

	if ( ! $pagename && $id ) {
		/*
		 * If a static page is set as the front page, $pagename will not be set.
		 * Retrieve it from the queried object.
		 */
		$post = get_queried_object();
		if ( $post ) {
			$pagename = $post->post_name;
		}
	}

	$templates = array();
	if ( $template && 0 === validate_file( $template ) ) {
		$templates[] = $template;
	}
	if ( $pagename ) {
		$pagename_decoded = urldecode( $pagename );
		if ( $pagename_decoded !== $pagename ) {
			$templates[] = "page-{$pagename_decoded}.php";
		}
		$templates[] = "page-{$pagename}.php";
	}
	if ( $id ) {
		$templates[] = "page-{$id}.php";
	}
	$templates[] = 'page.php';

	return get_query_template( 'page', $templates );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/template.php#L467) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/template.php#L467-L500)

## [Related](https://developer.wordpress.org/reference/functions/get_page_template/\#related)

| Uses | Description |
| --- | --- |
| [get\_queried\_object\_id()](https://developer.wordpress.org/reference/functions/get_queried_object_id/) `wp-includes/query.php` | Retrieves the ID of the currently queried object. |
| [get\_query\_var()](https://developer.wordpress.org/reference/functions/get_query_var/) `wp-includes/query.php` | Retrieves the value of a query variable in the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) class. |
| [get\_queried\_object()](https://developer.wordpress.org/reference/functions/get_queried_object/) `wp-includes/query.php` | Retrieves the currently queried object. |
| [validate\_file()](https://developer.wordpress.org/reference/functions/validate_file/) `wp-includes/functions.php` | Validates a file name and path against an allowed set of rules. |
| [get\_query\_template()](https://developer.wordpress.org/reference/functions/get_query_template/) `wp-includes/template.php` | Retrieves path to a template. |
| [get\_page\_template\_slug()](https://developer.wordpress.org/reference/functions/get_page_template_slug/) `wp-includes/post-template.php` | Gets the specific template filename for a given post. |

[Show 1 more](https://developer.wordpress.org/reference/functions/get_page_template/#) [Show less](https://developer.wordpress.org/reference/functions/get_page_template/#)

## [Changelog](https://developer.wordpress.org/reference/functions/get_page_template/\#changelog)

| Version | Description |
| --- | --- |
| [4.7.0](https://developer.wordpress.org/reference/since/4.7.0/) | The decoded form of `page-{page_name}.php` was added to the top of the template hierarchy when the page name contains multibyte characters. |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/get_page_template/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/get_page_template/#comment-content-523)



Display the filename of the page template used to render a page (printed within an HTML comment, in this example) :





`wp-includes/template.php`
[Copy](https://developer.wordpress.org/reference/functions/get_page_template/#)




```php
<?php echo '<!-- ' . basename( get_page_template() ) . ' -->'; ?>
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_page_template%2F%3Freplytocom%3D523%23feedback-editor-523)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/get_page_template/#comment-content-868)



The link for $type\_template is not found on this page. It needs updating.





[Show feedback (1)](https://developer.wordpress.org/reference/functions/get_page_template/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_page_template%2F%3Freplytocom%3D868%23feedback-editor-868)



- Yes, here’s the missing link: [{$type}\_template](https://developer.wordpress.org/reference/hooks/type_template/)



[David Brumbaugh](https://profiles.wordpress.org/dbrumbaugh10up/) [10 years ago](https://developer.wordpress.org/reference/functions/get_page_template/#comment-875)


3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/get_page_template/#comment-content-5978)



this function is probably useless / not working as intended with Gutenberg Full Site Edit, as it returns /wp-includes/template-canvas.php





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_page_template%2F%3Freplytocom%3D5978%23feedback-editor-5978)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fget_page_template%2F) before being able to contribute a note or feedback.

Notifications