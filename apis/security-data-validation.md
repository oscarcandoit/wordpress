---
url: https://developer.wordpress.org/apis/security/data-validation
scraped_at: 2025-10-20T04:10:00.351Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/security/data-validation/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Validating Data


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)[Security](https://developer.wordpress.org/apis/security/)Validating Data

Search

# Validating Data

## In this article

Table of Contents

- [Validation Philosophies](https://developer.wordpress.org/apis/security/data-validation/#validation-philosophies)
  - [Safelist](https://developer.wordpress.org/apis/security/data-validation/#safelist)
- [Example One](https://developer.wordpress.org/apis/security/data-validation/#example-one)
- [Example Two](https://developer.wordpress.org/apis/security/data-validation/#example-two)
- [Validation Functions](https://developer.wordpress.org/apis/security/data-validation/#validation-functions)

[↑ Back to top](https://developer.wordpress.org/apis/security/data-validation/#wp--skip-link--target)

Untrusted data comes from many sources (users, third party sites, even your own database!) and all of it needs to be checked before it’s used.

Remember: Even admins are users, and users will enter incorrect data, either on purpose or accidentally. It’s your job to protect them from themselves.

_Validating_ input is the process of testing data against a predefined pattern (or patterns) with a definitive result: valid or invalid. Validation is a more specific approach when compared to sanitization, but both have their roles.

Simple validation examples:

- Check that required fields have not been left blank
- Check that an entered phone number only contains numbers and punctuation
- Check that an requested string is one of five valid options
- Check that a quantity field is greater than 0

**Data validation should be performed as early as possible.** That means validating the data before performing any actions.

## [Validation Philosophies](https://developer.wordpress.org/apis/security/data-validation/\#validation-philosophies)

There are several different philosophies about how validation should be done. Each is appropriate for different scenarios.

### [Safelist](https://developer.wordpress.org/apis/security/data-validation/\#safelist)

Accept data only from a finite list of known and trusted values.

When comparing untrusted data against the safelist, it’s important to make sure that strict type checking is used. Otherwise an attacker could craft input in a way that will pass the safelist but still have a malicious effect.

#### [Comparison Operator](https://developer.wordpress.org/apis/security/data-validation/\#comparison-operator)

``
[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
$untrusted_input = '1 malicious string';  // will evaluate to integer 1 during loose comparisons

if ( 1 === $untrusted_input ) {  // == would have evaluated to true, but === evaluates to false
    echo '<p>Valid data';
} else {
    wp_die( 'Invalid data' );
}
```

#### [in\_array()](https://developer.wordpress.org/apis/security/data-validation/\#in_array)

``
[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
$untrusted_input = '1 malicious string';  // will evaluate to integer 1 during loose comparisons
$safe_values     = array( 1, 5, 7 );

if ( in_array( $untrusted_input, $safe_values, true ) ) {  // `true` enables strict type checking
    echo '<p>Valid data';
} else {
    wp_die( 'Invalid data' );
}
```

#### [switch()](https://developer.wordpress.org/apis/security/data-validation/\#switch)

``
[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
$untrusted_input = '1 malicious string';  // will evaluate to integer 1 during loose comparisons

switch ( true ) {
    case 1 === $untrusted_input:  // do your own strict comparison instead of relying on switch()'s loose comparison
        echo '<p>Valid data';
        break;

    default:
        wp_die( 'Invalid data' );
}
```

#### [Blocklist](https://developer.wordpress.org/apis/security/data-validation/\#blocklist)

Reject data from finite list of known untrusted values. This is very rarely a good idea.

#### [Format Detection](https://developer.wordpress.org/apis/security/data-validation/\#format-detection)

Test to see if the data is of the correct format. Only accept it if it is.

``
[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
if ( ! ctype_alnum( $data ) ) {
  wp_die( "Invalid format" );
}

if ( preg_match( "/[^0-9.-]/", $data ) ) {
  wp_die( "Invalid format" );
}
```

#### [Format Correction](https://developer.wordpress.org/apis/security/data-validation/\#format-correction)

Accept most any data, but remove or alter the dangerous pieces.

``
[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
$trusted_integer = (int) $untrusted_integer;
$trusted_alpha = preg_replace( '/[^a-z]/i', "", $untrusted_alpha );
$trusted_slug = sanitize_title( $untrusted_slug );
```

## [Example One](https://developer.wordpress.org/apis/security/data-validation/\#example-one)

Let’s say we have an input field designed to accept a US zipcode:

``
[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
<input type="text" id="wporg_zip_code" name="my-zipcode" maxlength="10" />
```

Here we’ve told the browser to only allow up to ten characters of input…but there’s no limitation on _which_ characters they can input. They could enter `11221` or `eval()`.

This is where validation comes in. When processing the form, we write code to check each field for its proper data type, and discard it if it’s incorrect.

For example: to check the `my-zipcode` field, we might do something like this:

``
[Expand code](https://developer.wordpress.org/apis/security/data-validation/#)

[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
/**
 * Validate a US zip code.
 *
 * @param string $zip_code   RAW zip code to check.
 *
 * @return bool              true if valid, false otherwise.
 */
function wporg_is_valid_us_zip_code( string $zip_code ):bool {
    // Scenario 1: empty.
    if ( empty( $zip_code ) ) {
        return false;
    }

    // Scenario 2: more than 10 characters.
    // The `maxlength` attribute is only enforced by
    // the browser, so we still need to validate the
    // length of the input on the server to protect
    // against a manual submission.
    if ( 10 < strlen( trim( $zip_code ) ) ) {
        return false;
    }

    // Scenario 3: incorrect format.
    if ( ! preg_match( '/^d{5}(-?d{4})?$/', $zip_code ) ) {
        return false;
    }

    // Passed successfully.
    return true;
}
```

Then, when processing the form, your code should check the `wporg_zip_code` field and perform the action based on the result:

``
[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
if ( isset( $_POST['wporg_zip_code'] ) && wporg_is_valid_us_zip_code( $_POST['wporg_zip_code'] ) ) {
    // $_POST['wporg_zip_code'] is valid; carry on
}
```

Note that this specific example is checking that the supplied data is in the correct format; it is not checking that the supplied and correctly formatted data is a valid zipcode. For that, you’d need a second function to compare against a list of valid zipcodes.

## [Example Two](https://developer.wordpress.org/apis/security/data-validation/\#example-two)

Say your code will query the database for posts, and you want to allow the user to sort the query results.

``
[Copy](https://developer.wordpress.org/apis/security/data-validation/#)

```php
$allowed_keys = array( 'author', 'post_author', 'date', 'post_date' );
$orderby      = sanitize_key( $_POST['orderby'] );
if ( in_array( $orderby, $allowed_keys, true ) ) {
    // $orderby is valid; carry on
}
```

This example code checks an incoming sort key (stored in the `orderby` input parameter) for validity by comparing it against an array of allowed sort keys. This prevents the user from passing in arbitrary and potentially malicious data.

Before checking the incoming sort key against the array, the key is passed into the built-in WordPress function `sanitize_key()`. This function ensures (among other things) that the key is in lowercase, which we want because `in_array()` performs a case-sensitive search.

Passing `true` into the third parameter of `in_array()` enables strict type checking, which tells the function to not only compare values but value types as well. This allows the code to be certain that the incoming sort key is a string and not some other data type.

## [Validation Functions](https://developer.wordpress.org/apis/security/data-validation/\#validation-functions)

Most validation is done as part of custom code, but there are some helper functions too. These are in addition to the ones listed on the Sanitization page.

- `balanceTags( $html )` or `force_balance_tags( $html )` – Tries to make sure HTML tags are balanced so that valid XML is output.
- `[count()](https://php.net/count)` for checking how many items are in an array
- `[in\_array()](https://php.net/in_array)` for checking whether something exists in an array
- `[is\_email()](https://developer.wordpress.org/reference/functions/is_email/)` will validate whether an email address is valid.
- [`is_array()`](https://www.php.net/is_array) for checking whether something is an array
- `[mb\_strlen()](https://php.net/mb_strlen)` or `[strlen()](https://php.net/strlen)` for checking that a string has the expected number of characters
- `[preg\_match()](https://php.net/preg_match)`, `[strpos()](https://php.net/strpos)` for checking for occurrences of certain strings in other strings
- `sanitize_html_class( $class, $fallback )` – Sanitizes a html classname to ensure it only contains valid characters. Strips the string down to A-Z,a-z,0-9,’-‘ and if this results in an empty string then it will return the alternate value supplied.
- `tag_escape( $html_tag_name )` – Sanitizes an HTML tag name (does not escape anything, despite the name of the function).
- `[term\_exists()](https://developer.wordpress.org/reference/functions/term_exists/)` checks whether a tag, category, or other taxonomy term exists.
- `[username\_exists()](https://developer.wordpress.org/reference/functions/username_exists/)` checks if username exists.
- `[validate\_file()](https://developer.wordpress.org/reference/functions/validate_file/)` will validate that an entered file path is a real path (but not whether the file exists).

Check the [WordPress code reference](https://developer.wordpress.org/reference/) for more functions like these. Search for functions with names like these: `*_exists()`, `*_validate()`, and `is_*()`. Not all of these are validation functions, but many are helpful.

First published

November 20, 2022

Last updated

November 15, 2023

[PreviousSanitizing DataPrevious: Sanitizing Data](https://developer.wordpress.org/apis/security/sanitizing/)

[NextEscaping DataNext: Escaping Data](https://developer.wordpress.org/apis/security/escaping/)

Notifications