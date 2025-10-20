---
url: https://www.advancedcustomfields.com/resources/page-link
scraped_at: 2025-10-20T02:24:09.950Z
---

# Page Link

Last updated Mar 6, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/page-link/#description)

## Description

Link copied

The Page Link field creates an interactive drop-down to select one or more posts, pages, custom post type items or archive URLs. This field type uses the Select2 library to enable search and AJAX functionality.

[Link to heading#](https://www.advancedcustomfields.com/resources/page-link/#screenshots)

## Screenshots

Link copied

[![A Page Link field that allows you to choose an existing post, page,CPT or archive URL from a list](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-page-link-field-interface.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-page-link-field-interface.png) The Page Link field interface[![List of field settings shown when setting up a Page Link field](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-page-link-field-settings.png)](https://www.advancedcustomfields.com/wp-content/uploads/2013/02/acf-page-link-field-settings.png) The Page Link field settings

[Link to heading#](https://www.advancedcustomfields.com/resources/page-link/#changelog)

## Changelog

Link copied

- Added `Allow Archives` in version 5.4.0.
- Added Select2 UI in version 5.0.0.

[Link to heading#](https://www.advancedcustomfields.com/resources/page-link/#settings)

## Settings

Link copied

- **Filter by Post Type**


Filters the selectable results via one or more post type. When left empty, all post types will be shown. As results are grouped by their post type, the selected post types here may be positioned into a specific order.

- **Filter by Taxonomy**


Filters the selectable results via one or more taxonomy term.

- **Allow Null**


Allows the current selection to be cleared and an empty value to be saved.

- **Allow Archives URLs**


Includes post type archive URLs within the select list of options.

- **Multiple**


Allows you to select more than one choice. When enabled, you may also drag/drop to reorder the selected choices.


[Link to heading#](https://www.advancedcustomfields.com/resources/page-link/#template-usage)

## Template usage

Link copied

The Page Link field will return either a single URL or array of URLs. To get more data from a selected post, please use the [post object](https://www.advancedcustomfields.com/resources/post-object/) field instead.

[Link to heading#](https://www.advancedcustomfields.com/resources/page-link/#display-single-value)

### Display single value

Link copied

This example demonstrates how to display a selected page link value.

```php
<a href="<?php the_field('page_link'); ?>">Continue reading</a>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/page-link/#display-multiple-values)

### Display multiple values

Link copied

This example demonstrates how to load and display multiple selected page link values.

```php
<?php
$urls = get_field('urls');
if( $urls ): ?>
    <h3>Further reading</h3>
    <ul>
        <?php foreach( $urls as $url ): ?>
        <li>
            <a href="<?php echo esc_url( $url ); ?>"><?php echo esc_html( $url ); ?></a>
        </li>
        <?php endforeach; ?>
    </ul>
<?php endif; ?>
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

[Link to heading#](https://www.advancedcustomfields.com/resources/page-link/#related)

## Related

Link copied

- Field Types: [Post Object](https://www.advancedcustomfields.com/resources/post-object/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
- Field Types: [Link](https://www.advancedcustomfields.com/resources/link/)
- Content: [File](https://www.advancedcustomfields.com/resources/file/)
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

[Got it](https://www.advancedcustomfields.com/resources/page-link/#)