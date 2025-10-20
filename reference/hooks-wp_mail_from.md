---
url: https://developer.wordpress.org/reference/hooks/wp_mail_from
scraped_at: 2025-10-20T03:14:55.058Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/wp_mail_from/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_mail\_from


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)wp\_mail\_from

Search

# apply\_filters( ‘wp\_mail\_from’, string$from\_email )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/wp_mail_from/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/wp_mail_from/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/wp_mail_from/#source)
- [Related](https://developer.wordpress.org/reference/hooks/wp_mail_from/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/wp_mail_from/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/wp_mail_from/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/wp_mail_from/#wp--skip-link--target)

Filters the email address to send from.

## [Parameters](https://developer.wordpress.org/reference/hooks/wp_mail_from/\#parameters)

`$from_email` string

Email address to send from.

## [More Information](https://developer.wordpress.org/reference/hooks/wp_mail_from/\#more-information)

- The `wp_mail_from` filter modifies the “from email address” used in an email sent using the [wp\_mail()](https://developer.wordpress.org/reference/functions/wp_mail/) function. When used together with the ‘ [wp\_mail\_from\_name](https://developer.wordpress.org/reference/hooks/wp_mail_from_name/)‘ filter, it creates a from address like “Name”. The filter should return an email address.
- To avoid your email being marked as spam, it is highly recommended that your “from” domain match your website.
- Some hosts may require that your “from” address be a legitimate address.
- If you apply your filter using an anonymous function, you cannot remove it using [remove\_filter()](https://developer.wordpress.org/reference/functions/remove_filter/) .

## [Source](https://developer.wordpress.org/reference/hooks/wp_mail_from/\#source)

`wp-includes/pluggable.php`
[Copy](https://developer.wordpress.org/reference/hooks/wp_mail_from/#)

```php
$from_email = apply_filters( 'wp_mail_from', $from_email );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/pluggable.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/pluggable.php#L397) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/pluggable.php#L397-L397)

## [Related](https://developer.wordpress.org/reference/hooks/wp_mail_from/\#related)

| Used by | Description |
| --- | --- |
| [wp\_mail()](https://developer.wordpress.org/reference/functions/wp_mail/) `wp-includes/pluggable.php` | Sends an email, similar to PHP’s mail function. |

## [Changelog](https://developer.wordpress.org/reference/hooks/wp_mail_from/\#changelog)

| Version | Description |
| --- | --- |
| [2.2.0](https://developer.wordpress.org/reference/since/2.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/wp_mail_from/\#user-contributed-notes)

1. [Skip to note 5 content](https://developer.wordpress.org/reference/hooks/wp_mail_from/#comment-content-2485)



The default “from” value is wordpress@ **thesitedomainname**. Where **thesitedomainname** is the domain name of your web site (e.g. xxxyyyzz.com).





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_mail_from%2F%3Freplytocom%3D2485%23feedback-editor-2485)

2. [Skip to note 6 content](https://developer.wordpress.org/reference/hooks/wp_mail_from/#comment-content-4552)



Examples migrated from Codex:





`wp-includes/pluggable.php`
[Copy](https://developer.wordpress.org/reference/hooks/wp_mail_from/#)




```php
add_filter( 'wp_mail_from', 'custom_wp_mail_from' );
function custom_wp_mail_from( $original_email_address ) {
   	//Make sure the email is from the same domain
   	//as your website to avoid being marked as spam.
   	return 'webmaster@mydomainname.com';
}
```





Using anonymous functions (PHP 5.3.0+) for callback:





`wp-includes/pluggable.php`
[Copy](https://developer.wordpress.org/reference/hooks/wp_mail_from/#)




```php
add_filter( 'wp_mail_from', function( $email ) {
   	return 'webmaster@mydomainname.com';
} );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_mail_from%2F%3Freplytocom%3D4552%23feedback-editor-4552)

3. [Skip to note 7 content](https://developer.wordpress.org/reference/hooks/wp_mail_from/#comment-content-3815)



Example of how to use this filter to update the user portion of the email address to send from.





`wp-includes/pluggable.php`
[Expand code](https://developer.wordpress.org/reference/hooks/wp_mail_from/#)

[Copy](https://developer.wordpress.org/reference/hooks/wp_mail_from/#)




```php
<?php
/**
    * Filter the email address to send from and replace the user.
    *
    * @param string $from_email Email address to send from.
    *
    * @return string The new email address.
    */
function wporg_replace_user_mail_from( $from_email ) {
   	// This will give us and array with the email user and the domain
   	// like this [ 'wordpress', 'example.tld' ]
   	$parts = explode( '@', $from_email );

   	// Add our new email user, add @ again, and append the domain
   	// This will be hello@example.tld
   	return 'hello@' . $parts[1];
}

add_filter( 'wp_mail_from', 'wporg_replace_user_mail_from' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_mail_from%2F%3Freplytocom%3D3815%23feedback-editor-3815)

4. [Skip to note 8 content](https://developer.wordpress.org/reference/hooks/wp_mail_from/#comment-content-4068)



Simple way to filter the email address using str\_replace() function.





`wp-includes/pluggable.php`
[Copy](https://developer.wordpress.org/reference/hooks/wp_mail_from/#)




```php
<?php
/**
    * Filter the email address using str_replace() function.
    */
function wpdocs_custom_wp_mail_from( $original_email_address ) {
   	// The $original_email_address value is wordpress@yourdomain.tld
   	// So we just change 'wordpress@' to something else like 'noreply@' or etc
   	return str_replace( 'wordpress@', 'noreply@', $original_email_address );
}
add_filter( 'wp_mail_from', 'wpdocs_custom_wp_mail_from' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_mail_from%2F%3Freplytocom%3D4068%23feedback-editor-4068)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_mail_from%2F) before being able to contribute a note or feedback.

Notifications