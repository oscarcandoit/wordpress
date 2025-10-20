---
url: https://www.advancedcustomfields.com/resources/html-escaping
scraped_at: 2025-10-20T02:33:03.845Z
---

# HTML Escaping

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/html-escaping/#introduction)

## Introduction

Link copied

ACF 5.10 introduced an important security feature, HTML escaping. First introduced as an experimental feature in [ACF 5.9.6](https://www.advancedcustomfields.com/blog/acf-5-9-6-release/), it ensures that all HTML content rendered by ACF is passed through the WordPress `wp_kses()` [function](https://developer.wordpress.org/reference/functions/wp_kses/).

By running all HTML content through this WordPress core function, ACF ensures that any HTML it renders is not vulnerable to [Cross Site Scripting](https://www.softwaretestinghelp.com/cross-site-scripting-xss-attack-test/) attacks.

It’s important to note that this only affects HTML content rendered by ACF in your WordPress dashboard or any [front-end forms](https://www.advancedcustomfields.com/blog/wordpress-frontend-form/) rendered through `acf_form()`. This will not affect field values loaded through API functions such as `get_field()`. We don’t make any assumptions about where you are using your field values within your theme and do not escape to them as a result.

From ACF 6.2.5, HTML escaping also applies to the values output by the [ACF Shortcode](https://www.advancedcustomfields.com/resources/shortcode/) and from ACF 6.2.7, it applies to [`the_field` and `the_sub_field`](https://www.advancedcustomfields.com/blog/acf-6-2-5-security-release/)

[Link to heading#](https://www.advancedcustomfields.com/resources/html-escaping/#implementation)

## Implementation

Link copied

This new ACF HTML escaping system introduces a new escaping function, `acf_esc_html()`, which is now used throughout the plugin wherever HTML is rendered by ACF. This function takes the content to be rendered and passes it to the `wp_kses()` function, returning the result. It also passes a context string of `acf`.

```php php
/**
 * Sanitizes text content and strips out disallowed HTML.
 *
 * This function emulates wp_kses_post() with a context of "acf" for extensibility.
 *
 * @date    16/4/21
 * @since   5.9.6
 *
 * @param   string $string
 * @return  string
 */
function acf_esc_html( $string = '' ) {
    return wp_kses( (string) $string, 'acf' );
}
```

By passing the ACF content through `wp_kses()`, WordPress will strip out any disallowed HTML tags or tag attributes. The list of allowed tags is managed by the WordPress `wp_kses_allowed_html()` [function](https://developer.wordpress.org/reference/functions/wp_kses_allowed_html/). By default, WordPress ships with a bunch of predefined allowed tags and their allowed attributes. Below is an example of the allowed `button` tag, as well as its allowed attributes.

```php php
[button] => Array
    (
        [disabled] => true
        [name] => true
        [type] => true
        [value] => true
        [aria-describedby] => true
        [aria-details] => true
        [aria-label] => true
        [aria-labelledby] => true
        [aria-hidden] => true
        [class] => true
        [id] => true
        [style] => true
        [title] => true
        [role] => true
        [data-*] => true
    )
```

If an HTML element appears in the content passed to `wp_kses()` that is not in the list of allowed tags, or an attribute on a tag not in the allowed list, it will be stripped from the content.

[Link to heading#](https://www.advancedcustomfields.com/resources/html-escaping/#customization)

## Customization

Link copied

Passing the custom context of `acf` to `wp_kses()` allows for 3rd party customization of the allowed HTML tags and attributes. If you have a specific HTML tag or tag attribute that you want to allow, you can add it to the list of allowed tags, using the `wp_kses_allowed_html` [filter hook](https://developer.wordpress.org/reference/hooks/wp_kses_allowed_html/) in PHP.

For example, you can use this filter in your theme functions.php or a custom plugin, to enable an `iframe` tag:

```php php
add_filter( 'wp_kses_allowed_html', 'acf_add_allowed_iframe_tag', 10, 2 );
function acf_add_allowed_iframe_tag( $tags, $context ) {
    if ( $context === 'acf' ) {
        $tags['iframe'] = array(
            'src'             => true,
            'height'          => true,
            'width'           => true,
            'frameborder'     => true,
            'allowfullscreen' => true,
        );
    }

    return $tags;
}
```

Here is another example, explicitly allowed the `svg` and `path` tags:

```php php
add_filter( 'wp_kses_allowed_html', 'acf_add_allowed_svg_tag', 10, 2 );
function acf_add_allowed_svg_tag( $tags, $context ) {
    if ( $context === 'acf' ) {
        $tags['svg']  = array(
            'xmlns'       => true,
            'fill'        => true,
            'viewbox'     => true,
            'role'        => true,
            'aria-hidden' => true,
            'focusable'   => true,
        );
        $tags['path'] = array(
            'd'    => true,
            'fill' => true,
        );
    }

    return $tags;
}
```

It is important to remember that any allowed tags you add could have security implications, so be sure only to allow tags that are considered safe. An example of a possible unsafe tag is the `script` tag.

The WordPress functionality that strips HTML tags and tag properties it deems unsafe, also strips out CSS properties that are considered unsafe, like the `display` CSS property. In some cases, you may find the need to define and enqueue an inline style in the WordPress dashboard, to apply such a property to your ACF instruction messages.

```html php
<div style="display: flex">
```

Because `display` is stripped, this property would be stripped from the div tag.

Similarly to how you can allow specific HTML tags, you can also allow specific CSS properties, using the `safe_style_css` filter:

```php
add_filter( 'safe_style_css', 'add_display_to_safe_css', 10, 1 );
function add_display_to_safe_css( $css_attributes ) {
    $css_attributes[] = 'display';

    return $css_attributes;
}
```

Please note that while it is possible to do this, we don’t recommend it, as it could expose your site to security vulnerabilities.

[Link to heading#](https://www.advancedcustomfields.com/resources/html-escaping/#html-escaping-blocks)

## HTML Escaping in ACF Blocks

Link copied

In Advanced Custom Fields PRO version 5.12 and above, WordPress will run it’s default `wp_kses_post()` sanitization on ACF blocks for admin users without the `unfiltered_html` capability. In some circumstances, this can result in HTML being removed from the block content — and therefore not rendered on the frontend — that wouldn’t have been removed in versions previous to 5.12.

If a user that doesn’t have the `unfiltered_html` capability needed to insert HTML into ACF blocks that is being removed by `wp_kses_post()`, you can add support for specific HTML tags by using the same `wp_kses_allowed_html` filter as shown above, except with the “post” context:

```php
add_filter( 'wp_kses_allowed_html', 'acf_add_allowed_iframe_tag', 10, 2 );
function acf_add_allowed_iframe_tag( $tags, $context ) {
    if ( $context === 'post' ) {
     $tags['iframe'] = array(
         'src'          => true,
         'height'       => true,
         'width'        => true,
         'frameborder'  => true,
         'allowfullscreen' => true,
     );
    }

    return $tags;
}
```

Alternatively, you could manually grant the user the `unfiltered_html` capability.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/html-escaping/#related)

## Related

Link copied

- Basic: [get\_field()](https://www.advancedcustomfields.com/resources/get_field/)
- Features: [Updates to ACF Field Functions in 5.11](https://www.advancedcustomfields.com/resources/acf-field-functions/)
- Guides: [Adding custom javascript to fields](https://www.advancedcustomfields.com/resources/adding-custom-javascript-fields/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)

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

[Got it](https://www.advancedcustomfields.com/resources/html-escaping/#)