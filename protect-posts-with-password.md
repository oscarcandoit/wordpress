---
url: https://wordpress.org/documentation/article/protect-posts-with-password
scraped_at: 2025-10-20T02:04:41.316Z
---

[Skip to content](https://wordpress.org/documentation/article/protect-posts-with-password/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Protect posts with password

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Publishing](https://wordpress.org/documentation/category/publishing/)Protect posts with password

Search documentation

# Protect posts with password

## In this article

Table of Contents

- [Post Visibility Settings](https://wordpress.org/documentation/article/protect-posts-with-password/#post-visibility-settings)
- [Finding or Changing a Password](https://wordpress.org/documentation/article/protect-posts-with-password/#finding-or-changing-a-password)
- [Password Protected Posts](https://wordpress.org/documentation/article/protect-posts-with-password/#password-protected-posts)
  - [Password Protecting Many Posts and Pages](https://wordpress.org/documentation/article/protect-posts-with-password/#password-protecting-many-posts-and-pages)
- [Protect Custom Fields](https://wordpress.org/documentation/article/protect-posts-with-password/#protect-custom-fields)
- [Customize the Protected Text](https://wordpress.org/documentation/article/protect-posts-with-password/#customize-the-protected-text)
  - [Password Form Text](https://wordpress.org/documentation/article/protect-posts-with-password/#password-form-text)
  - [Protected Excerpt Text](https://wordpress.org/documentation/article/protect-posts-with-password/#protected-excerpt-text)
  - [Add the Password Form to the Excerpt](https://wordpress.org/documentation/article/protect-posts-with-password/#add-the-password-form-to-the-excerpt)
- [Hiding Password Protected Posts](https://wordpress.org/documentation/article/protect-posts-with-password/#hiding-password-protected-posts)
- [Changing the cookie lifetime](https://wordpress.org/documentation/article/protect-posts-with-password/#changing-the-cookie-lifetime)

[↑ Back to top](https://wordpress.org/documentation/article/protect-posts-with-password/#wp--skip-link--target)

## [Post Visibility Settings](https://wordpress.org/documentation/article/protect-posts-with-password/\#post-visibility-settings)

Once you publish a WordPress post (or Page), it is visible to the public (by default). In WordPress terms, this means a post with a _Published_ status has a default visibility of _Public_, based on the settings in the [Publish box](https://wordpress.org/support/article/writing-posts/#post-field-descriptions) of a [Edit Post Screen](https://wordpress.org/support/article/administration-screens/#posts-make-some-content).

WordPress also offers two less public options for your post’s [Content Visibility](https://codex.wordpress.org/Content_Visibility). Clicking the “Edit” link next to **Visibility: Public** reveals three radio buttons:

- _Public_ is selected by default.
- Checking _Password protected_ reveals a text field for entering a password, that will be required to view that post. **The password is limited to 20 characters.**
- Checking _Private_ makes your post visible only to your site’s Users with the role of [Administrator or Editor](https://wordpress.org/support/article/roles-and-capabilities/).Visibility Settings

![](https://wordpress.org/documentation/files/2019/02/protected_edit.png)

When you’re done editing the post’s visibility, click the “OK” button. You should now see your post’s new setting, e.g., **Visibility: Password Protected.** Remember: a setting change does not take effect until you click the “Publish” button (or “Update” if the post is already published.)

## [Finding or Changing a Password](https://wordpress.org/documentation/article/protect-posts-with-password/\#finding-or-changing-a-password)

Only an Administrator, Editor, or the post’s Author can change a post’s password or visibility setting. To do so, use the “Visibility: Edit” link again. These settings are also available using the post’s Quick Edit link in the All Posts Screen.

The **Visibility** “Edit” link (or “Quick Edit”) is also a good way to reveal a forgotten post password.

## [Password Protected Posts](https://wordpress.org/documentation/article/protect-posts-with-password/\#password-protected-posts)

[![](https://wordpress.org/documentation/files/2019/02/protected_password.png)](https://codex.wordpress.org/File:protected_password.png)

WordPress displays a password-protected post differently. It makes these changes to the post’s:

- **Title–** Adds the text “Protected: ” before the post Title.
- **Excerpt–** Instead of the post Excerpt, prints this text: “There is no excerpt because this is a protected post.”
- **Content–** Instead of the post Content, prints a password form with this text: “This post is password protected. To view it please enter your password below:”

[![](https://wordpress.org/documentation/files/2019/02/protected_content.png)](https://codex.wordpress.org/File:protected_content.png)

So, a password-protected post with a title of “My Post” would display like this:

### [Password Protecting Many Posts and Pages](https://wordpress.org/documentation/article/protect-posts-with-password/\#password-protecting-many-posts-and-pages)

WordPress stores this password in a browser cookie so readers don’t have to re-enter passwords if they visit the same page multiple times. Furthermore, if multiple posts use the same password, the reader will only have to enter the password once to access every post (see caveat below).

WordPress will only track one password at a time. Therefore, if two posts use two different passwords, entering the password for post A, then entering the password for post B means that revisiting post A (or any post which shares its password) will require the user to re-enter the password for post A.

## [Protect Custom Fields](https://wordpress.org/documentation/article/protect-posts-with-password/\#protect-custom-fields)

WordPress does not print a password-protected post’s Content or Excerpt until the correct password is entered. But a post’s [Custom Field(s)](https://wordpress.org/support/article/custom-fields/) data is not protected, and can still show. To stop CFs from printing, wrap your [get\_post\_meta](https://codex.wordpress.org/Function_Reference/get_post_meta) calls (e.g., in single.php or page.php) with a conditional statement using: [post\_password\_required](https://codex.wordpress.org/Function_Reference/post_password_required). This one WordPress function checks both whether your post requires a password and whether the correct password has been provided:

```
<?php
if ( ! post_password_required() ) {
    // Code to fetch and print CFs, such as:
    $key_1_value_1 = get_post_meta( $post->ID, 'key_1', true );
        echo $key_1_value_1;
}
?>

```

The post\_password\_required function within in an if statement is also handy for other customizations, such as preventing password-protected posts from displaying in a list.

## [Customize the Protected Text](https://wordpress.org/documentation/article/protect-posts-with-password/\#customize-the-protected-text)

With [WordPress Filters](https://codex.wordpress.org/Plugin_API/Filter_Reference) you can: change the default text in the password form, change the default text for the password-protected post Excerpt, and insert the password form into the post Excerpt. To do so, add the following code to your custom plugin file.

### [Password Form Text](https://wordpress.org/documentation/article/protect-posts-with-password/\#password-form-text)

The password form displays this default message: “This post is password protected. To view it please enter your password below:” The following code will return the form with different text and different html structure — in this example the custom message is: “To view this protected post, enter the password below:”

```
<?php
function my_password_form() {
    global $post;
    $label = 'pwbox-'.( empty( $post->ID ) ? rand() : $post->ID );
    $o = '<form action="' . esc_url( site_url( 'wp-login.php?action=postpass', 'login_post' ) ) . '" method="post">
    ' . __( "To view this protected post, enter the password below:" ) . '
    <label for="' . $label . '">' . __( "Password:" ) . ' </label><input name="post_password" id="' . $label . '" type="password" size="20" maxlength="20" /><input type="submit" name="Submit" value="' . esc_attr__( "Submit" ) . '" />
    </form>
    ';
    return $o;
}
add_filter( 'the_password_form', 'my_password_form' );
?>

```

Please note: the my\_password\_form function must return a value: don’t use print or echo.

#### [Password Size Limitation](https://wordpress.org/documentation/article/protect-posts-with-password/\#password-size-limitation)

Make sure to set the maxlength parameter to a value of 20 when replacing the password protection form as WordPress will only save the first 20 characters due to database constraints.

### [Protected Excerpt Text](https://wordpress.org/documentation/article/protect-posts-with-password/\#protected-excerpt-text)

The default Excerpt of a password-protected post is: “There is no excerpt because this is a protected post.” This code will replace that text with your own — HTML allowed:

```
<?php
function my_excerpt_protected( $excerpt ) {
    if ( post_password_required() )
        $excerpt = '<em>[This is password-protected.]</em>';
    return $excerpt;
}
add_filter( 'the_excerpt', 'my_excerpt_protected' );
?>

```

Replace “<em>\[This is password-protected.\]</em>” with your custom password-protected Excerpt message.

### [Add the Password Form to the Excerpt](https://wordpress.org/documentation/article/protect-posts-with-password/\#add-the-password-form-to-the-excerpt)

Another option for your protected Excerpts is to print out the password form instead of the Excerpt message. That way people enter the password right from an index or archive page. Then, when they click the Title link, they’ll see the Content. With the get\_the\_password\_form function, you can make the password form be the Excerpt for a password-protected post:

```
<?php
function my_excerpt_password_form( $excerpt ) {
    if ( post_password_required() )
        $excerpt = get_the_password_form();
    return $excerpt;
}
add_filter( 'the_excerpt', 'my_excerpt_password_form' );
?>

```

This will get the default WordPress password form and text or [any customizations](https://wordpress.org/documentation/article/protect-posts-with-password/#password-form-text) you’ve made. For a better understanding of how post\_password\_required() and get\_the\_password\_form() work, read their function definitions in `[wp-includes/post-template.php](https://core.trac.wordpress.org/browser/tags/5.1.0/src/wp-includes/post-template.php#L0)`.

In this same WordPress core file you’ll also find the the\_excerpt and the\_password\_form filters, and the functions [get\_the\_excerpt()](https://codex.wordpress.org/Function_Reference/get_the_excerpt), [get\_the\_title()](https://codex.wordpress.org/Function_Reference/get_the_title), and [get\_the\_content()](https://codex.wordpress.org/Function_Reference/get_the_content). These functions control how a post’s title, excerpt and content display, depending on its visibility setting.

## [Hiding Password Protected Posts](https://wordpress.org/documentation/article/protect-posts-with-password/\#hiding-password-protected-posts)

Sometimes, you don’t want your password protected posts to show up on other places around your site, like on the home page or archive pages. To effectively hide them from these pages without affecting your pagination, place the following code in your custom plugin file:

```
<?php

// Filter to hide protected posts
function exclude_protected($where) {
	global $wpdb;
	return $where .= " AND {$wpdb->posts}.post_password = '' ";
}

// Decide where to display them
function exclude_protected_action($query) {
	if( !is_single() && !is_page() && !is_admin() ) {
		add_filter( 'posts_where', 'exclude_protected' );
	}
}

// Action to queue the filter at the right time
add_action('pre_get_posts', 'exclude_protected_action');

?>

```

This code works in two parts: the first part effectively removes any password protected posts directly from any SQL query that WordPress is running, using the [posts\_where filter](https://codex.wordpress.org/Plugin_API/Filter_Reference/posts_where). The second part adds this filter to all pages except single posts, pages, and admin pages.

For more information on why pre\_get\_posts is the right action for this function, see the [pre\_get\_posts action reference](https://codex.wordpress.org/Plugin_API/Action_Reference/pre_get_posts).

## [Changing the cookie lifetime](https://wordpress.org/documentation/article/protect-posts-with-password/\#changing-the-cookie-lifetime)

See [https://developer.wordpress.org/reference/hooks/post\_password\_expires/](https://developer.wordpress.org/reference/hooks/post_password_expires/)

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/protect-posts-with-password/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fprotect-posts-with-password%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

February 28, 2019

Last updated

January 16, 2023

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.