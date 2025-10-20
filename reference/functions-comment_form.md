---
url: https://developer.wordpress.org/reference/functions/comment_form
scraped_at: 2025-10-20T03:26:56.471Z
---

[Skip to content](https://developer.wordpress.org/reference/functions/comment_form/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

comment\_form()


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Functions](https://developer.wordpress.org/reference/functions/)comment\_form()

Search

# comment\_form( array$args = array(), int\|WP\_Post$post = null )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/functions/comment_form/#description)
- [Parameters](https://developer.wordpress.org/reference/functions/comment_form/#parameters)
- [Source](https://developer.wordpress.org/reference/functions/comment_form/#source)
- [Hooks](https://developer.wordpress.org/reference/functions/comment_form/#hooks)
- [Related](https://developer.wordpress.org/reference/functions/comment_form/#related)
- [Changelog](https://developer.wordpress.org/reference/functions/comment_form/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/functions/comment_form/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/functions/comment_form/#wp--skip-link--target)

Outputs a complete commenting form for use within a template.

## [Description](https://developer.wordpress.org/reference/functions/comment_form/\#description)

Most strings and form fields may be controlled through the `$args` array passed into the function, while you may also choose to use the [‘comment\_form\_default\_fields’](https://developer.wordpress.org/reference/hooks/comment_form_default_fields/) filter to modify the array of default fields if you’d just like to add a new one or remove a single field. All fields are also individually passed through a filter of the [‘comment\_form\_field\_$name’](https://developer.wordpress.org/reference/hooks/comment_form_field_name/) where `$name` is the key used in the array of fields.

## [Parameters](https://developer.wordpress.org/reference/functions/comment_form/\#parameters)

`$args` arrayoptional

Default arguments and form fields to override.

- `fields` array
Default comment fields, filterable by default via the ['comment\_form\_default\_fields'](https://developer.wordpress.org/reference/hooks/comment_form_default_fields/) hook.

- `author` string
Comment author field HTML.

- `email` string
Comment author email field HTML.

- `url` string
Comment author URL field HTML.

- `cookies` string
Comment cookie opt-in field HTML.


- `comment_field` string
The comment textarea field HTML.

- `must_log_in` string
HTML element for a ‘must be logged in to comment’ message.

- `logged_in_as` string
The HTML for the ‘logged in as \[user\]’ message, the Edit profile link, and the Log out link.

- `comment_notes_before` string
HTML element for a message displayed before the comment fields if the user is not logged in.


Default ‘Your email address will not be published.’.

- `comment_notes_after` string
HTML element for a message displayed after the textarea field.

- `action` string
The comment form element action attribute. Default `'/wp-comments-post.php'`.

- `id_form` string
The comment form element id attribute. Default `'commentform'`.

- `id_submit` string
The comment submit element id attribute. Default `'submit'`.

- `class_container` string
The comment form container class attribute. Default `'comment-respond'`.

- `class_form` string
The comment form element class attribute. Default `'comment-form'`.

- `class_submit` string
The comment submit element class attribute. Default `'submit'`.

- `name_submit` string
The comment submit element name attribute. Default `'submit'`.

- `title_reply` string
The translatable `'reply'` button label. Default ‘Leave a Reply’.

- `title_reply_to` string
The translatable `'reply-to'` button label. Default ‘Leave a Reply to %s’, where %s is the author of the comment being replied to.

- `title_reply_before` string
HTML displayed before the comment form title.


Default: `<h3 id="reply-title" class="comment-reply-title">`.

- `title_reply_after` string
HTML displayed after the comment form title.


Default: `</h3>`.

- `cancel_reply_before` string
HTML displayed before the cancel reply link.

- `cancel_reply_after` string
HTML displayed after the cancel reply link.

- `cancel_reply_link` string
The translatable ‘cancel reply’ button label. Default ‘Cancel reply’.

- `label_submit` string
The translatable `'submit'` button label. Default ‘Post a comment’.

- `submit_button` string
HTML format for the Submit button.


Default: `<input name="%1$s" type="submit" id="%2$s" class="%3$s" value="%4$s" />`.

- `submit_field` string
HTML format for the markup surrounding the Submit button and comment hidden fields. Default: `<p class="form-submit">%1$s %2$s</p>`, where %1$s is the submit button markup and %2$s is the comment hidden fields.

- `format` string
The comment form format. Default `'xhtml'`. Accepts `'xhtml'`, `'html5'`.


Default: `array()`

`$post` int\|[WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/)optional

Post ID or [WP\_Post](https://developer.wordpress.org/reference/classes/wp_post/) object to generate the form for. Default current post.

Default: `null`

## [Source](https://developer.wordpress.org/reference/functions/comment_form/\#source)

`wp-includes/comment-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/comment_form/#)

[Copy](https://developer.wordpress.org/reference/functions/comment_form/#)

```php
function comment_form( $args = array(), $post = null ) {
	$post = get_post( $post );

	// Exit the function if the post is invalid or comments are closed.
	if ( ! $post || ! comments_open( $post ) ) {
		/**
		 * Fires after the comment form if comments are closed.
		 *
		 * For backward compatibility, this action also fires if comment_form()
		 * is called with an invalid post object or ID.
		 *
		 * @since 3.0.0
		 */
		do_action( 'comment_form_comments_closed' );

		return;
	}

	$post_id       = $post->ID;
	$commenter     = wp_get_current_commenter();
	$user          = wp_get_current_user();
	$user_identity = $user->exists() ? $user->display_name : '';

	$args = wp_parse_args( $args );
	if ( ! isset( $args['format'] ) ) {
		$args['format'] = current_theme_supports( 'html5', 'comment-form' ) ? 'html5' : 'xhtml';
	}

	$req   = get_option( 'require_name_email' );
	$html5 = 'html5' === $args['format'];

	// Define attributes in HTML5 or XHTML syntax.
	$required_attribute = ( $html5 ? ' required' : ' required="required"' );
	$checked_attribute  = ( $html5 ? ' checked' : ' checked="checked"' );

	// Identify required fields visually and create a message about the indicator.
	$required_indicator = ' ' . wp_required_field_indicator();
	$required_text      = ' ' . wp_required_field_message();

	$fields = array(
		'author' => sprintf(
			'<p class="comment-form-author">%s %s</p>',
			sprintf(
				'<label for="author">%s%s</label>',
				__( 'Name' ),
				( $req ? $required_indicator : '' )
			),
			sprintf(
				'<input id="author" name="author" type="text" value="%s" size="30" maxlength="245" autocomplete="name"%s />',
				esc_attr( $commenter['comment_author'] ),
				( $req ? $required_attribute : '' )
			)
		),
		'email'  => sprintf(
			'<p class="comment-form-email">%s %s</p>',
			sprintf(
				'<label for="email">%s%s</label>',
				__( 'Email' ),
				( $req ? $required_indicator : '' )
			),
			sprintf(
				'<input id="email" name="email" %s value="%s" size="30" maxlength="100" aria-describedby="email-notes" autocomplete="email"%s />',
				( $html5 ? 'type="email"' : 'type="text"' ),
				esc_attr( $commenter['comment_author_email'] ),
				( $req ? $required_attribute : '' )
			)
		),
		'url'    => sprintf(
			'<p class="comment-form-url">%s %s</p>',
			sprintf(
				'<label for="url">%s</label>',
				__( 'Website' )
			),
			sprintf(
				'<input id="url" name="url" %s value="%s" size="30" maxlength="200" autocomplete="url" />',
				( $html5 ? 'type="url"' : 'type="text"' ),
				esc_attr( $commenter['comment_author_url'] )
			)
		),
	);

	if ( has_action( 'set_comment_cookies', 'wp_set_comment_cookies' ) && get_option( 'show_comments_cookies_opt_in' ) ) {
		$consent = empty( $commenter['comment_author_email'] ) ? '' : $checked_attribute;

		$fields['cookies'] = sprintf(
			'<p class="comment-form-cookies-consent">%s %s</p>',
			sprintf(
				'<input id="wp-comment-cookies-consent" name="wp-comment-cookies-consent" type="checkbox" value="yes"%s />',
				$consent
			),
			sprintf(
				'<label for="wp-comment-cookies-consent">%s</label>',
				__( 'Save my name, email, and website in this browser for the next time I comment.' )
			)
		);

		// Ensure that the passed fields include cookies consent.
		if ( isset( $args['fields'] ) && ! isset( $args['fields']['cookies'] ) ) {
			$args['fields']['cookies'] = $fields['cookies'];
		}
	}

	/**
	 * Filters the default comment form fields.
	 *
	 * @since 3.0.0
	 *
	 * @param string[] $fields Array of the default comment fields.
	 */
	$fields = apply_filters( 'comment_form_default_fields', $fields );

	$defaults = array(
		'fields'               => $fields,
		'comment_field'        => sprintf(
			'<p class="comment-form-comment">%s %s</p>',
			sprintf(
				'<label for="comment">%s%s</label>',
				_x( 'Comment', 'noun' ),
				$required_indicator
			),
			'<textarea id="comment" name="comment" cols="45" rows="8" maxlength="65525"' . $required_attribute . '></textarea>'
		),
		'must_log_in'          => sprintf(
			'<p class="must-log-in">%s</p>',
			sprintf(
				/* translators: %s: Login URL. */
				__( 'You must be <a href="%s">logged in</a> to post a comment.' ),
				/** This filter is documented in wp-includes/link-template.php */
				wp_login_url( apply_filters( 'the_permalink', get_permalink( $post_id ), $post_id ) )
			)
		),
		'logged_in_as'         => sprintf(
			'<p class="logged-in-as">%s%s</p>',
			sprintf(
				/* translators: 1: User name, 2: Edit user link, 3: Logout URL. */
				__( 'Logged in as %1$s. <a href="%2$s">Edit your profile</a>. <a href="%3$s">Log out?</a>' ),
				$user_identity,
				get_edit_user_link(),
				/** This filter is documented in wp-includes/link-template.php */
				wp_logout_url( apply_filters( 'the_permalink', get_permalink( $post_id ), $post_id ) )
			),
			$required_text
		),
		'comment_notes_before' => sprintf(
			'<p class="comment-notes">%s%s</p>',
			sprintf(
				'<span id="email-notes">%s</span>',
				__( 'Your email address will not be published.' )
			),
			$required_text
		),
		'comment_notes_after'  => '',
		'action'               => site_url( '/wp-comments-post.php' ),
		'id_form'              => 'commentform',
		'id_submit'            => 'submit',
		'class_container'      => 'comment-respond',
		'class_form'           => 'comment-form',
		'class_submit'         => 'submit',
		'name_submit'          => 'submit',
		'title_reply'          => __( 'Leave a Reply' ),
		/* translators: %s: Author of the comment being replied to. */
		'title_reply_to'       => __( 'Leave a Reply to %s' ),
		'title_reply_before'   => '<h3 id="reply-title" class="comment-reply-title">',
		'title_reply_after'    => '</h3>',
		'cancel_reply_before'  => ' <small>',
		'cancel_reply_after'   => '</small>',
		'cancel_reply_link'    => __( 'Cancel reply' ),
		'label_submit'         => __( 'Post Comment' ),
		'submit_button'        => '<input name="%1$s" type="submit" id="%2$s" class="%3$s" value="%4$s" />',
		'submit_field'         => '<p class="form-submit">%1$s %2$s</p>',
		'format'               => 'xhtml',
	);

	/**
	 * Filters the comment form default arguments.
	 *
	 * Use 'comment_form_default_fields' to filter the comment fields.
	 *
	 * @since 3.0.0
	 *
	 * @param array $defaults The default comment form arguments.
	 */
	$args = wp_parse_args( $args, apply_filters( 'comment_form_defaults', $defaults ) );

	// Ensure that the filtered arguments contain all required default values.
	$args = array_merge( $defaults, $args );

	// Remove `aria-describedby` from the email field if there's no associated description.
	if ( isset( $args['fields']['email'] ) && ! str_contains( $args['comment_notes_before'], 'id="email-notes"' ) ) {
		$args['fields']['email'] = str_replace(
			' aria-describedby="email-notes"',
			'',
			$args['fields']['email']
		);
	}

	/**
	 * Fires before the comment form.
	 *
	 * @since 3.0.0
	 */
	do_action( 'comment_form_before' );
	?>
	<div id="respond" class="<?php echo esc_attr( $args['class_container'] ); ?>">
		<?php
		echo $args['title_reply_before'];

		comment_form_title( $args['title_reply'], $args['title_reply_to'], true, $post_id );

		if ( get_option( 'thread_comments' ) ) {
			echo $args['cancel_reply_before'];

			cancel_comment_reply_link( $args['cancel_reply_link'] );

			echo $args['cancel_reply_after'];
		}

		echo $args['title_reply_after'];

		if ( get_option( 'comment_registration' ) && ! is_user_logged_in() ) :

			echo $args['must_log_in'];
			/**
			 * Fires after the HTML-formatted 'must log in after' message in the comment form.
			 *
			 * @since 3.0.0
			 */
			do_action( 'comment_form_must_log_in_after' );

		else :

			printf(
				'<form action="%s" method="post" id="%s" class="%s"%s>',
				esc_url( $args['action'] ),
				esc_attr( $args['id_form'] ),
				esc_attr( $args['class_form'] ),
				( $html5 ? ' novalidate' : '' )
			);

			/**
			 * Fires at the top of the comment form, inside the form tag.
			 *
			 * @since 3.0.0
			 */
			do_action( 'comment_form_top' );

			if ( is_user_logged_in() ) :

				/**
				 * Filters the 'logged in' message for the comment form for display.
				 *
				 * @since 3.0.0
				 *
				 * @param string $args_logged_in The HTML for the 'logged in as [user]' message,
				 *                               the Edit profile link, and the Log out link.
				 * @param array  $commenter      An array containing the comment author's
				 *                               username, email, and URL.
				 * @param string $user_identity  If the commenter is a registered user,
				 *                               the display name, blank otherwise.
				 */
				echo apply_filters( 'comment_form_logged_in', $args['logged_in_as'], $commenter, $user_identity );

				/**
				 * Fires after the is_user_logged_in() check in the comment form.
				 *
				 * @since 3.0.0
				 *
				 * @param array  $commenter     An array containing the comment author's
				 *                              username, email, and URL.
				 * @param string $user_identity If the commenter is a registered user,
				 *                              the display name, blank otherwise.
				 */
				do_action( 'comment_form_logged_in_after', $commenter, $user_identity );

			else :

				echo $args['comment_notes_before'];

			endif;

			// Prepare an array of all fields, including the textarea.
			$comment_fields = array( 'comment' => $args['comment_field'] ) + (array) $args['fields'];

			/**
			 * Filters the comment form fields, including the textarea.
			 *
			 * @since 4.4.0
			 *
			 * @param array $comment_fields The comment fields.
			 */
			$comment_fields = apply_filters( 'comment_form_fields', $comment_fields );

			// Get an array of field names, excluding the textarea.
			$comment_field_keys = array_diff( array_keys( $comment_fields ), array( 'comment' ) );

			// Get the first and the last field name, excluding the textarea.
			$first_field = reset( $comment_field_keys );
			$last_field  = end( $comment_field_keys );

			foreach ( $comment_fields as $name => $field ) {

				if ( 'comment' === $name ) {

					/**
					 * Filters the content of the comment textarea field for display.
					 *
					 * @since 3.0.0
					 *
					 * @param string $args_comment_field The content of the comment textarea field.
					 */
					echo apply_filters( 'comment_form_field_comment', $field );

					echo $args['comment_notes_after'];

				} elseif ( ! is_user_logged_in() ) {

					if ( $first_field === $name ) {
						/**
						 * Fires before the comment fields in the comment form, excluding the textarea.
						 *
						 * @since 3.0.0
						 */
						do_action( 'comment_form_before_fields' );
					}

					/**
					 * Filters a comment form field for display.
					 *
					 * The dynamic portion of the hook name, `$name`, refers to the name
					 * of the comment form field.
					 *
					 * Possible hook names include:
					 *
					 *  - `comment_form_field_comment`
					 *  - `comment_form_field_author`
					 *  - `comment_form_field_email`
					 *  - `comment_form_field_url`
					 *  - `comment_form_field_cookies`
					 *
					 * @since 3.0.0
					 *
					 * @param string $field The HTML-formatted output of the comment form field.
					 */
					echo apply_filters( "comment_form_field_{$name}", $field ) . "\n";

					if ( $last_field === $name ) {
						/**
						 * Fires after the comment fields in the comment form, excluding the textarea.
						 *
						 * @since 3.0.0
						 */
						do_action( 'comment_form_after_fields' );
					}
				}
			}

			$submit_button = sprintf(
				$args['submit_button'],
				esc_attr( $args['name_submit'] ),
				esc_attr( $args['id_submit'] ),
				esc_attr( $args['class_submit'] ),
				esc_attr( $args['label_submit'] )
			);

			/**
			 * Filters the submit button for the comment form to display.
			 *
			 * @since 4.2.0
			 *
			 * @param string $submit_button HTML markup for the submit button.
			 * @param array  $args          Arguments passed to comment_form().
			 */
			$submit_button = apply_filters( 'comment_form_submit_button', $submit_button, $args );

			$submit_field = sprintf(
				$args['submit_field'],
				$submit_button,
				get_comment_id_fields( $post_id )
			);

			/**
			 * Filters the submit field for the comment form to display.
			 *
			 * The submit field includes the submit button, hidden fields for the
			 * comment form, and any wrapper markup.
			 *
			 * @since 4.2.0
			 *
			 * @param string $submit_field HTML markup for the submit field.
			 * @param array  $args         Arguments passed to comment_form().
			 */
			echo apply_filters( 'comment_form_submit_field', $submit_field, $args );

			/**
			 * Fires at the bottom of the comment form, inside the closing form tag.
			 *
			 * @since 1.5.0
			 *
			 * @param int $post_id The post ID.
			 */
			do_action( 'comment_form', $post_id );

			echo '</form>';

		endif;
		?>
	</div><!-- #respond -->
	<?php

	/**
	 * Fires after the comment form.
	 *
	 * @since 3.0.0
	 */
	do_action( 'comment_form_after' );
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/comment-template.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/comment-template.php#L2496) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/comment-template.php#L2496-L2911)

## [Hooks](https://developer.wordpress.org/reference/functions/comment_form/\#hooks)

[do\_action( ‘comment\_form’, int$post\_id )](https://developer.wordpress.org/reference/hooks/comment_form/)

Fires at the bottom of the comment form, inside the closing form tag.

[do\_action( ‘comment\_form\_after’ )](https://developer.wordpress.org/reference/hooks/comment_form_after/)

Fires after the comment form.

[do\_action( ‘comment\_form\_after\_fields’ )](https://developer.wordpress.org/reference/hooks/comment_form_after_fields/)

Fires after the comment fields in the comment form, excluding the textarea.

[do\_action( ‘comment\_form\_before’ )](https://developer.wordpress.org/reference/hooks/comment_form_before/)

Fires before the comment form.

[do\_action( ‘comment\_form\_before\_fields’ )](https://developer.wordpress.org/reference/hooks/comment_form_before_fields/)

Fires before the comment fields in the comment form, excluding the textarea.

[do\_action( ‘comment\_form\_comments\_closed’ )](https://developer.wordpress.org/reference/hooks/comment_form_comments_closed/)

Fires after the comment form if comments are closed.

[apply\_filters( ‘comment\_form\_defaults’, array$defaults )](https://developer.wordpress.org/reference/hooks/comment_form_defaults/)

Filters the comment form default arguments.

[apply\_filters( ‘comment\_form\_default\_fields’, string\[\]$fields )](https://developer.wordpress.org/reference/hooks/comment_form_default_fields/)

Filters the default comment form fields.

[apply\_filters( ‘comment\_form\_fields’, array$comment\_fields )](https://developer.wordpress.org/reference/hooks/comment_form_fields/)

Filters the comment form fields, including the textarea.

[apply\_filters( ‘comment\_form\_field\_comment’, string$args\_comment\_field )](https://developer.wordpress.org/reference/hooks/comment_form_field_comment/)

Filters the content of the comment textarea field for display.

[apply\_filters( “comment\_form\_field\_{$name}”, string$field )](https://developer.wordpress.org/reference/hooks/comment_form_field_name/)

Filters a comment form field for display.

[apply\_filters( ‘comment\_form\_logged\_in’, string$args\_logged\_in, array$commenter, string$user\_identity )](https://developer.wordpress.org/reference/hooks/comment_form_logged_in/)

Filters the ‘logged in’ message for the comment form for display.

[do\_action( ‘comment\_form\_logged\_in\_after’, array$commenter, string$user\_identity )](https://developer.wordpress.org/reference/hooks/comment_form_logged_in_after/)

Fires after the [is\_user\_logged\_in()](https://developer.wordpress.org/reference/functions/is_user_logged_in/) check in the comment form.

[do\_action( ‘comment\_form\_must\_log\_in\_after’ )](https://developer.wordpress.org/reference/hooks/comment_form_must_log_in_after/)

Fires after the HTML-formatted ‘must log in after’ message in the comment form.

[apply\_filters( ‘comment\_form\_submit\_button’, string$submit\_button, array$args )](https://developer.wordpress.org/reference/hooks/comment_form_submit_button/)

Filters the submit button for the comment form to display.

[apply\_filters( ‘comment\_form\_submit\_field’, string$submit\_field, array$args )](https://developer.wordpress.org/reference/hooks/comment_form_submit_field/)

Filters the submit field for the comment form to display.

[do\_action( ‘comment\_form\_top’ )](https://developer.wordpress.org/reference/hooks/comment_form_top/)

Fires at the top of the comment form, inside the form tag.

[apply\_filters( ‘the\_permalink’, string$permalink, int\|WP\_Post$post )](https://developer.wordpress.org/reference/hooks/the_permalink/)

Filters the display of the permalink for the current post.

## [Related](https://developer.wordpress.org/reference/functions/comment_form/\#related)

| Uses | Description |
| --- | --- |
| [wp\_required\_field\_message()](https://developer.wordpress.org/reference/functions/wp_required_field_message/) `wp-includes/general-template.php` | Creates a message to explain required form fields. |
| [wp\_required\_field\_indicator()](https://developer.wordpress.org/reference/functions/wp_required_field_indicator/) `wp-includes/general-template.php` | Assigns a visual indicator for required form fields. |
| [is\_user\_logged\_in()](https://developer.wordpress.org/reference/functions/is_user_logged_in/) `wp-includes/pluggable.php` | Determines whether the current visitor is a logged in user. |
| [wp\_get\_current\_user()](https://developer.wordpress.org/reference/functions/wp_get_current_user/) `wp-includes/pluggable.php` | Retrieves the current user object. |
| [wp\_login\_url()](https://developer.wordpress.org/reference/functions/wp_login_url/) `wp-includes/general-template.php` | Retrieves the login URL. |
| [wp\_logout\_url()](https://developer.wordpress.org/reference/functions/wp_logout_url/) `wp-includes/general-template.php` | Retrieves the logout URL. |
| [site\_url()](https://developer.wordpress.org/reference/functions/site_url/) `wp-includes/link-template.php` | Retrieves the URL for the current site where WordPress application files (e.g. wp-blog-header.php or the wp-admin/ folder) are accessible. |
| [get\_edit\_user\_link()](https://developer.wordpress.org/reference/functions/get_edit_user_link/) `wp-includes/link-template.php` | Retrieves the edit user link. |
| [has\_action()](https://developer.wordpress.org/reference/functions/has_action/) `wp-includes/plugin.php` | Checks if any action has been registered for a hook. |
| [comment\_form\_title()](https://developer.wordpress.org/reference/functions/comment_form_title/) `wp-includes/comment-template.php` | Displays text based on comment reply status. |
| [cancel\_comment\_reply\_link()](https://developer.wordpress.org/reference/functions/cancel_comment_reply_link/) `wp-includes/comment-template.php` | Displays HTML content for cancel comment reply link. |
| [get\_comment\_id\_fields()](https://developer.wordpress.org/reference/functions/get_comment_id_fields/) `wp-includes/comment-template.php` | Retrieves hidden input HTML for replying to comments. |
| [comments\_open()](https://developer.wordpress.org/reference/functions/comments_open/) `wp-includes/comment-template.php` | Determines whether the current post is open for comments. |
| [wp\_get\_current\_commenter()](https://developer.wordpress.org/reference/functions/wp_get_current_commenter/) `wp-includes/comment.php` | Gets current commenter’s name, email, and URL. |
| [current\_theme\_supports()](https://developer.wordpress.org/reference/functions/current_theme_supports/) `wp-includes/theme.php` | Checks a theme’s support for a given feature. |
| [esc\_attr()](https://developer.wordpress.org/reference/functions/esc_attr/) `wp-includes/formatting.php` | Escaping for HTML attributes. |
| [esc\_url()](https://developer.wordpress.org/reference/functions/esc_url/) `wp-includes/formatting.php` | Checks and cleans a URL. |
| [wp\_parse\_args()](https://developer.wordpress.org/reference/functions/wp_parse_args/) `wp-includes/functions.php` | Merges user defined arguments into defaults array. |
| [get\_permalink()](https://developer.wordpress.org/reference/functions/get_permalink/) `wp-includes/link-template.php` | Retrieves the full permalink for the current post or post ID. |
| [do\_action()](https://developer.wordpress.org/reference/functions/do_action/) `wp-includes/plugin.php` | Calls the callback functions that have been added to an action hook. |
| [apply\_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) `wp-includes/plugin.php` | Calls the callback functions that have been added to a filter hook. |
| [get\_option()](https://developer.wordpress.org/reference/functions/get_option/) `wp-includes/option.php` | Retrieves an option value based on an option name. |
| [get\_post()](https://developer.wordpress.org/reference/functions/get_post/) `wp-includes/post.php` | Retrieves post data given a post ID or post object. |

[Show 18 more](https://developer.wordpress.org/reference/functions/comment_form/#) [Show less](https://developer.wordpress.org/reference/functions/comment_form/#)

## [Changelog](https://developer.wordpress.org/reference/functions/comment_form/\#changelog)

| Version | Description |
| --- | --- |
| [5.5.0](https://developer.wordpress.org/reference/since/5.5.0/) | Introduced the `'class_container'` argument. |
| [4.9.6](https://developer.wordpress.org/reference/since/4.9.6/) | Introduced the `'cookies'` default comment field. |
| [4.6.0](https://developer.wordpress.org/reference/since/4.6.0/) | Introduced the `'action'` argument. |
| [4.5.0](https://developer.wordpress.org/reference/since/4.5.0/) | The `'author'`, `'email'`, and `'url'` form fields are limited to 245, 100, and 200 characters, respectively. |
| [4.4.0](https://developer.wordpress.org/reference/since/4.4.0/) | Introduced the `'class_form'`, `'title_reply_before'`, `'title_reply_after'`, `'cancel_reply_before'`, and `'cancel_reply_after'` arguments. |
| [4.2.0](https://developer.wordpress.org/reference/since/4.2.0/) | Introduced the `'submit_button'` and `'submit_fields'` arguments. |
| [4.1.0](https://developer.wordpress.org/reference/since/4.1.0/) | Introduced the `'class_submit'` argument. |
| [3.0.0](https://developer.wordpress.org/reference/since/3.0.0/) | Introduced. |

[Show 3 more](https://developer.wordpress.org/reference/functions/comment_form/#) [Show less](https://developer.wordpress.org/reference/functions/comment_form/#)

## [User Contributed Notes](https://developer.wordpress.org/reference/functions/comment_form/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/functions/comment_form/#comment-content-439)



**Simple example how to change some comment form fields:**





`wp-includes/comment-template.php`
[Copy](https://developer.wordpress.org/reference/functions/comment_form/#)




```php
$comments_args = array(
           // Change the title of send button
           'label_submit' => __( 'Send', 'textdomain' ),
           // Change the title of the reply section
           'title_reply' => __( 'Write a Reply or Comment', 'textdomain' ),
           // Remove "Text or HTML to be displayed after the set of comment fields".
           'comment_notes_after' => '',
           // Redefine your own textarea (the comment body).
           'comment_field' => '<p class="comment-form-comment"><label for="comment">' . _x( 'Comment', 'noun' ) . '</label><br /><textarea id="comment" name="comment" aria-required="true"></textarea></p>',
);
comment_form( $comments_args );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcomment_form%2F%3Freplytocom%3D439%23feedback-editor-439)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/functions/comment_form/#comment-content-3615)



Order of the Comment Fields > **Functions.php**





`wp-includes/comment-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/comment_form/#)

[Copy](https://developer.wordpress.org/reference/functions/comment_form/#)




```php
//Comment Field Order
add_filter( 'comment_form_fields', 'mo_comment_fields_custom_order' );
function mo_comment_fields_custom_order( $fields ) {
       $comment_field = $fields['comment'];
       $author_field = $fields['author'];
       $email_field = $fields['email'];
       $url_field = $fields['url'];
       $cookies_field = $fields['cookies'];
       unset( $fields['comment'] );
       unset( $fields['author'] );
       unset( $fields['email'] );
       unset( $fields['url'] );
       unset( $fields['cookies'] );
       // the order of fields is the order below, change it as needed:
       $fields['author'] = $author_field;
       $fields['email'] = $email_field;
       $fields['url'] = $url_field;
       $fields['comment'] = $comment_field;
       $fields['cookies'] = $cookies_field;
       // done ordering, now return the fields:
       return $fields;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcomment_form%2F%3Freplytocom%3D3615%23feedback-editor-3615)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/functions/comment_form/#comment-content-3614)



Expanded list of Translate Friendly options -> comments.php





`wp-includes/comment-template.php`
[Expand code](https://developer.wordpress.org/reference/functions/comment_form/#)

[Copy](https://developer.wordpress.org/reference/functions/comment_form/#)




```php
//Declare Vars
$comment_send = 'Send';
$comment_reply = 'Leave a Message';
$comment_reply_to = 'Reply';

$comment_author = 'Name';
$comment_email = 'E-Mail';
$comment_body = 'Comment';
$comment_url = 'Website';
$comment_cookies_1 = ' By commenting you accept the';
$comment_cookies_2 = ' Privacy Policy';

$comment_before = 'Registration isn\'t required.';

$comment_cancel = 'Cancel Reply';

//Array
$comments_args = array(
       //Define Fields
       'fields' => array(
           //Author field
           'author' => '<p class="comment-form-author"><br /><input id="author" name="author" aria-required="true" placeholder="' . $comment_author .'"></input></p>',
           //Email Field
           'email' => '<p class="comment-form-email"><br /><input id="email" name="email" placeholder="' . $comment_email .'"></input></p>',
           //URL Field
           'url' => '<p class="comment-form-url"><br /><input id="url" name="url" placeholder="' . $comment_url .'"></input></p>',
           //Cookies
           'cookies' => '<input type="checkbox" required>' . $comment_cookies_1 . '<a href="' . get_privacy_policy_url() . '">' . $comment_cookies_2 . '</a>',
       ),
       // Change the title of send button
       'label_submit' => __( $comment_send ),
       // Change the title of the reply section
       'title_reply' => __( $comment_reply ),
       // Change the title of the reply section
       'title_reply_to' => __( $comment_reply_to ),
       //Cancel Reply Text
       'cancel_reply_link' => __( $comment_cancel ),
       // Redefine your own textarea (the comment body).
       'comment_field' => '<p class="comment-form-comment"><br /><textarea id="comment" name="comment" aria-required="true" placeholder="' . $comment_body .'"></textarea></p>',
       //Message Before Comment
       'comment_notes_before' => __( $comment_before),
       // Remove "Text or HTML to be displayed after the set of comment fields".
       'comment_notes_after' => '',
       //Submit Button ID
       'id_submit' => __( 'comment-submit' ),
);
comment_form( $comments_args );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcomment_form%2F%3Freplytocom%3D3614%23feedback-editor-3614)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Ffunctions%2Fcomment_form%2F) before being able to contribute a note or feedback.

Notifications