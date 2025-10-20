---
url: https://www.advancedcustomfields.com/resources/get_sub_field
scraped_at: 2025-10-20T02:28:44.995Z
---

# get\_sub\_field()

Last updated Feb 6, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field/#description)

## Description

Link copied

Returns the value of a specific sub field value from a Repeater or Flexible Content field loop.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field/#parameters)

## Parameters

Link copied

```php
get_sub_field($selector, [$format_value = true], [$escape_html = false]);
```

- `$selector` _(string)_ _(Required)_ The sub field name or field key.
- `$format_value` _(bool)_ _(Optional)_ Whether to apply formatting logic. Defaults to true.
- `$escape_html` _(bool)_ _(Optional)_ Since 6.2.6 – return an escaped HTML safe version of the field value. Requires $format\_value to be true. Defaults to false.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field/#return)

## Return

Link copied

_(mixed)_ The sub field value.

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field/#examples)

## Examples

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field/#get-a-value-from-within-a-repeater-field)

### Get a value from within a Repeater field.

Link copied

This example shows how to loop through a Repeater field and load a sub field value.

```php
if( have_rows('parent_field') ):
    while ( have_rows('parent_field') ) : the_row();
        $sub_value = get_sub_field('sub_field');
        // Do something...
    endwhile;
else :
    // no rows found
endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field/#get-a-value-from-within-a-flexible-content-field)

### Get a value from within a Flexible Content field.

Link copied

This example shows how to loop through a Flexible Content field and load a sub field value.

```php
if( have_rows('parent_field') ):
    while( have_rows('parent_field') ): the_row();

        // Layout 1.
        if( get_row_layout() == 'layout_1' ):

            // Layout 1 value.
            $value = get_sub_field('sub_field_1');

        // Layout 2.
        elseif( get_row_layout() == 'layout_2' ):

            // Layout 2 value.
            $value = get_sub_field('sub_field_2');

        endif;

    endwhile;
endif;
```

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field/#nested-loops)

### Nested loops

Link copied

This example shows how to loop through a nested Repeater field and load a sub field value.

```php
/**
 * Field Structure:
 *
 * - parent_repeater (Repeater)
 *   - parent_title (Text)
 *   - child_repeater (Repeater)
 *     - child_title (Text)
 */
if( have_rows('parent_repeater') ):
    while( have_rows('parent_repeater') ) : the_row();

        // Get parent value.
        $parent_title = get_sub_field('parent_title');

        // Loop over sub repeater rows.
        if( have_rows('child_repeater') ):
            while( have_rows('child_repeater') ) : the_row();

                // Get sub value.
                $child_title = get_sub_field('child_title');

            endwhile;
        endif;
    endwhile;
endif;
```

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

[Link to heading#](https://www.advancedcustomfields.com/resources/get_sub_field/#related)

## Related

Link copied

- Functions: [the\_sub\_field()](https://www.advancedcustomfields.com/resources/the_sub_field/)
- Functions: [get\_sub\_field\_object()](https://www.advancedcustomfields.com/resources/get_sub_field_object/)
- Functions: [have\_rows()](https://www.advancedcustomfields.com/resources/have_rows/)
- Deprecated: [has\_sub\_field()](https://www.advancedcustomfields.com/resources/has_sub_field/)
- Basic: [get\_field\_object()](https://www.advancedcustomfields.com/resources/get_field_object/)

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

[Got it](https://www.advancedcustomfields.com/resources/get_sub_field/#)