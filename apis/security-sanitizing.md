---
url: https://developer.wordpress.org/apis/security/sanitizing
scraped_at: 2025-10-20T04:09:36.210Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/security/sanitizing/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Sanitizing Data


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)[Security](https://developer.wordpress.org/apis/security/)Sanitizing Data

Search

# Sanitizing Data

## In this article

Table of Contents

- [Example](https://developer.wordpress.org/apis/security/sanitizing/#example)
- [Sanitization functions](https://developer.wordpress.org/apis/security/sanitizing/#sanitization-functions)

[↑ Back to top](https://developer.wordpress.org/apis/security/sanitizing/#wp--skip-link--target)

Untrusted data comes from many sources (users, third party sites, even your own database!) and all of it needs to be checked before it’s used.

Remember: Even admins are users, and users will enter incorrect data, either on purpose or accidentally. It’s your job to protect them from themselves.

_Sanitizing_ input is the process of securing/cleaning/filtering input data. Validation is preferred over sanitization because validation is more specific. But when “more specific” isn’t possible, sanitization is the next best thing.

## [Example](https://developer.wordpress.org/apis/security/sanitizing/\#example)

Let’s say we have an input field named `title`:

``
[Copy](https://developer.wordpress.org/apis/security/sanitizing/#)

```markup
<input id="title" type="text" name="title">
```

We can’t use Validation here because the text field is too general: it can be anything at all. So we sanitize the input data with the `sanitize_text_field()` function:

``
[Copy](https://developer.wordpress.org/apis/security/sanitizing/#)

```php
$title = sanitize_text_field( $_POST['title'] );
update_post_meta( $post->ID, 'title', $title );
```

Behind the scenes, `sanitize_text_field()` does the following:

1. Checks for invalid UTF-8
2. Converts single less-than characters (<) to entity
3. Strips all tags
4. Removes line breaks, tabs and extra white space
5. Strips octets

## [Sanitization functions](https://developer.wordpress.org/apis/security/sanitizing/\#sanitization-functions)

There are many functions that will help you sanitize your data.

- `[sanitize\_email()](https://developer.wordpress.org/reference/functions/sanitize_email/)`
- `[sanitize\_file\_name()](https://developer.wordpress.org/reference/functions/sanitize_file_name/)`
- `[sanitize\_hex\_color()](https://developer.wordpress.org/reference/functions/sanitize_hex_color/)`
- `[sanitize\_hex\_color\_no\_hash()](https://developer.wordpress.org/reference/functions/sanitize_hex_color_no_hash/)`
- `[sanitize\_html\_class()](https://developer.wordpress.org/reference/functions/sanitize_html_class/)`
- `[sanitize\_key()](https://developer.wordpress.org/reference/functions/sanitize_key/)`
- `[sanitize\_meta()](https://developer.wordpress.org/reference/functions/sanitize_meta/)`
- `[sanitize\_mime\_type()](https://developer.wordpress.org/reference/functions/sanitize_mime_type/)`
- `[sanitize\_option()](https://developer.wordpress.org/reference/functions/sanitize_option/)`
- `[sanitize\_sql\_orderby()](https://developer.wordpress.org/reference/functions/sanitize_sql_orderby/)`
- `[sanitize\_term()](https://developer.wordpress.org/reference/functions/sanitize_term/)`
- `[sanitize\_term\_field()](https://developer.wordpress.org/reference/functions/sanitize_term_field/)`
- `[sanitize\_text\_field()](https://developer.wordpress.org/reference/functions/sanitize_text_field/)`
- `[sanitize\_textarea\_field()](https://developer.wordpress.org/reference/functions/sanitize_textarea_field/)`
- `[sanitize\_title()](https://developer.wordpress.org/reference/functions/sanitize_title/)`
- `[sanitize\_title\_for\_query()](https://developer.wordpress.org/reference/functions/sanitize_title_for_query/)`
- `[sanitize\_title\_with\_dashes()](https://developer.wordpress.org/reference/functions/sanitize_title_with_dashes/)`
- `[sanitize\_user()](https://developer.wordpress.org/reference/functions/sanitize_user/)`
- `[sanitize\_url()](https://developer.wordpress.org/reference/functions/sanitize_url/)`
- `[wp\_kses()](https://developer.wordpress.org/reference/functions/wp_kses/)`
- `[wp\_kses\_post()](https://developer.wordpress.org/reference/functions/wp_kses_post/)`

First published

November 20, 2022

Last updated

May 31, 2023

[PreviousSecurityPrevious: Security](https://developer.wordpress.org/apis/security/)

[NextValidating DataNext: Validating Data](https://developer.wordpress.org/apis/security/data-validation/)

Notifications