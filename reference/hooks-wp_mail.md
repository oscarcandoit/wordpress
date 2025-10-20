---
url: https://developer.wordpress.org/reference/hooks/wp_mail
scraped_at: 2025-10-20T03:41:52.492Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/hooks/wp_mail/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp\_mail


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)wp\_mail

Search

# apply\_filters( ‘wp\_mail’, array$args )

## In this article

Table of Contents

- [Parameters](https://developer.wordpress.org/reference/hooks/wp_mail/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/wp_mail/#more-information)
- [Source](https://developer.wordpress.org/reference/hooks/wp_mail/#source)
- [Related](https://developer.wordpress.org/reference/hooks/wp_mail/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/wp_mail/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/wp_mail/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/wp_mail/#wp--skip-link--target)

Filters the [wp\_mail()](https://developer.wordpress.org/reference/functions/wp_mail/) arguments.

## [Parameters](https://developer.wordpress.org/reference/hooks/wp_mail/\#parameters)

`$args` array

Array of the `wp_mail()` arguments.

- `to` string\|string\[\]
Array or comma-separated list of email addresses to send message.

- `subject` string
Email subject.

- `message` string
Message contents.

- `headers` string\|string\[\]
Additional headers.

- `attachments` string\|string\[\]
Paths to files to attach.


## [More Information](https://developer.wordpress.org/reference/hooks/wp_mail/\#more-information)

- The wp\_mail filter hook allows you to filter the arguments that are passed to the [wp\_mail()](https://developer.wordpress.org/reference/functions/wp_mail/) function. The arguments for [wp\_mail()](https://developer.wordpress.org/reference/functions/wp_mail/) are passed through the filter as an array.
- $attachments should be an array. If it is not, it will be converted to one by the wp\_mail function after the filter.

## [Source](https://developer.wordpress.org/reference/hooks/wp_mail/\#source)

`wp-includes/pluggable.php`
[Copy](https://developer.wordpress.org/reference/hooks/wp_mail/#)

```php
$atts = apply_filters( 'wp_mail', compact( 'to', 'subject', 'message', 'headers', 'attachments' ) );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/pluggable.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/pluggable.php#L192) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/pluggable.php#L192-L192)

## [Related](https://developer.wordpress.org/reference/hooks/wp_mail/\#related)

| Used by | Description |
| --- | --- |
| [wp\_mail()](https://developer.wordpress.org/reference/functions/wp_mail/) `wp-includes/pluggable.php` | Sends an email, similar to PHP’s mail function. |

## [Changelog](https://developer.wordpress.org/reference/hooks/wp_mail/\#changelog)

| Version | Description |
| --- | --- |
| [2.2.0](https://developer.wordpress.org/reference/since/2.2.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/wp_mail/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/wp_mail/#comment-content-2118)



modify the recipient of the email





`wp-includes/pluggable.php`
[Expand code](https://developer.wordpress.org/reference/hooks/wp_mail/#)

[Copy](https://developer.wordpress.org/reference/hooks/wp_mail/#)




```php
add_filter('wp_mail','redirect_mails', 10,1);
function redirect_mails($args){
       $to = $args['to'];
       //$args['subject']
       //$args['message']
       //$args['headers']
       //$args['attachments']
       $user = get_user_by( 'email', $to);
       $_role = get_user_meta($user->ID, 'my_custom_role', true);
       if ($role == 'opportunity-owner') {
         $test_mentor_email = get_option('test_mentor_email');
         if ($test_mentor_email != '') {
           $to = $test_mentor_email;
         }
       }
       $args['to']=$to;
       return $args;
     }
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_mail%2F%3Freplytocom%3D2118%23feedback-editor-2118)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fwp_mail%2F) before being able to contribute a note or feedback.

Notifications