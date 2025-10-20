---
url: https://www.advancedcustomfields.com/resources/get_field
scraped_at: 2025-10-20T02:28:27.103Z
---

# get\_field()

Last updated Feb 6, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#description)

## Description

Link copied

Returns the value of a specific field.

Intuitive and powerful (much like ACF itself ?), this function can be used to load the value of any field from any location. Please note that each field type returns different forms of data (string, int, array, etc).

Any returned values should be escaped using an [appropriate escaping function](https://developer.wordpress.org/apis/security/escaping/) before they are output.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#parameters)

## Parameters

Link copied

```php
get_field($selector, [$post_id = false], [$format_value = true], [$escape_html = false]);
```

- `$selector` _(string)_ _(Required)_ The field name or field key.
- `$post_id` _(mixed)_ _(Optional)_ The post ID where the value is saved. Defaults to false, which will use the current post.
- `$format_value` _(bool)_ _(Optional)_ Whether to apply formatting logic. Defaults to true.
- `$escape_html` _(bool)_ _(Optional)_ Since 6.2.6 – return an escaped HTML safe version of the field value. Requires $format\_value to be true. Defaults to false.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#return)

## Return

Link copied

_(mixed)_ The field value.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#get-a-value-from-the-current-post)

### Get a value from the current post

Link copied

This example shows how to load the value of field ‘text\_field’ from the current post.

```php
$value = get_field( "text_field" );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#get-a-value-from-a-specific-post)

### Get a value from a specific post

Link copied

This example shows how to load the value of field ‘text\_field’ from the post with ID = 123.

```php
$value = get_field( "text_field", 123 );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#check-if-value-exists)

### Check if value exists

Link copied

This example shows how to check if a value exists for a field.

```php
$value = get_field( "text_field" );

if( $value ) {
    echo wp_kses_post( $value );
} else {
    echo 'empty';
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#get-a-value-from-different-objects)

### Get a value from different objects

Link copied

This example shows a variety of **$post\_id** values to get a value from a post, user, term and option.

```php
$post_id = false; // current post
$post_id = 1; // post ID = 1
$post_id = "user_2"; // user ID = 2
$post_id = "category_3"; // category term ID = 3
$post_id = "event_4"; // event (custom taxonomy) term ID = 4
$post_id = "option"; // options page
$post_id = "options"; // same as above

$value = get_field( 'my_field', $post_id );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#get-a-value-without-formatting)

### Get a value without formatting

Link copied

In this example, the field “image” is an image field which would normally return an Image object.
However, by passing false as a 3rd parameter to the get\_field function, the value is never formatted and returned as is from the Database.

Please note the second parameter is set to **false** to target the current post.

```php
$image = get_field('image', false, false);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#get-an-escaped-html-safe-field-value-since-acf-626)

### Get an escaped (HTML safe) field value (since ACF 6.2.6)

Link copied

In this example, the field “wysiwyg” is a wysiwyg field which returns a string containing the contents of the WYSIWYG field.
However, by passing true as the fourth parameter, we’ll ask the field to make sure it’s escaped. In the case of the WYSIWYG field, this escaping happens before filters are run on the field, so shortcodes will still work, but any `<script>` or `<iframe>` s saved in the field will be removed.

Please note the second parameter is set to **false** to target the current post, and the third parameter is set to **true** which is required when getting an escaped value, otherwise a `_doing_it_wrong` will be thrown.

```php
$escaped_wysiwyg = get_field('wysiwyg', false, true, true);
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#escaping-the-value)

### Escaping the value

Link copied

Before you output any value provided by `get_field`, you should escape it using one of the [WordPress escaping functions](https://developer.wordpress.org/apis/security/escaping/) to ensure your field values aren’t able to be used for malicious purposes. For example using [`wp_kses_post`](https://developer.wordpress.org/reference/functions/wp_kses_post/)

```php
$value = get_field( "text_field" );

if( $value ) {
    echo wp_kses_post( $value );
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#notes)

## Notes

Link copied

Prior to ACF 5.11, `get_field()` could be used to retrieve the values of options or meta for items not associated with ACF fields. This had security implications as site options could be exposed. `get_field()` also could retrieve values of fields that are no longer registered with ACF.

This was updated in ACF 5.11, see the [Updates to ACF Field Functions in 5.11](https://www.advancedcustomfields.com/resources/acf-field-functions/) resource for more info.

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/get_field/#related)

## Related

Link copied

- Basic: [the\_field()](https://www.advancedcustomfields.com/resources/the_field/)
- Basic: [get\_fields()](https://www.advancedcustomfields.com/resources/get_fields/)
- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)
- Functions: [update\_field()](https://www.advancedcustomfields.com/resources/update_field/)
- Functions: [get\_sub\_field\_object()](https://www.advancedcustomfields.com/resources/get_sub_field_object/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/get_field/#)