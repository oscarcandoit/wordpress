---
url: https://www.advancedcustomfields.com/resources/taxonomy
scraped_at: 2025-10-20T02:26:10.621Z
---

# Taxonomy

Last updated Aug 9, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#description)

## Description

Link copied

The Taxonomy field allows the selection of one or more taxonomy terms.

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#screenshots)

## Screenshots

Link copied

![Creating a Taxonomy field in an ACF field group. The tab shown depicts General settings for the field: Field Type, Field Label, Field Name, Taxonomy, Create Terms, Save Terms, Load Terms, Return Value, and Appearance. The other tabs are Validation, Presentation, Conditional Logic, and Advanced.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Taxonomy-Field-General-Settings-1.png)

Creating a Taxonomy field in an ACF field group.

![The Taxonomy field UI as it might appear to content editors, in this case showing parent and child categories. ](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Taxonomy-Field-UI-1.png)

The Taxonomy field UI as it might appear to content editors, in this case showing parent and child categories.

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#changelog)

## Changelog

Link copied

- Split setting `load_save_terms` into `load_terms` and `save_terms` in version 5.2.7.
- `Create Terms` added in version 5.2.3

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#settings)

## Settings

Link copied

- **Taxonomy**


Selects the taxonomy you wish to select term(s) from.

- **Create Terms**


Allows new terms to be created while editing. Defaults to on.

- **Save Terms**


Connects selected terms to the post. Defaults to off.

- **Load Terms**


Loads values from the post terms. Defaults to off.

- **Return Value**


Specifies the format of the returned data. Choose from Term Object ( `WP_Term`) or Term ID (int).

- **Appearance**


Selects the type of interface displayed (Checkbox, Multi Select, Radio Buttons, or Select).

- **Required**


Enabling this prevents the field from accepting empty values. Defaults to off.

- **Instructions**


Shows instructions when submitting data.

- **Conditional Logic**


Enabling this setting allows you to customize the logic which determines if the current field should be visible. Groups of conditional logic rules can be created to allow for multiple and/or statements.

- **Bidirectional**


Found on the Advanced tab, enabling this setting allows you to update a value in the target fields for each value selected for this field, adding or removing the Post ID, Taxonomy ID, or User ID of the item being updated. Please see [Bidirectional Relationships](https://www.advancedcustomfields.com/resources/bidirectional-relationships/) for more information on using this setting to create bidirectional relationships directly in ACF’s UI.


[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#template-usage)

## Template usage

Link copied

The Taxonomy field will return one or more values (objects or IDs) depending on the Return Value setting. Below are some examples of how you can use this data.

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#display-single-value)

### Display single value

Link copied

This example demonstrates how to get and display a single term object. This would imply that your Appearance setting is Radio Buttons or Select.

```php
<?php
$term = get_field('taxonomy_field_name');
if( $term ): ?>
    <h2><?php echo esc_html( $term->name ); ?></h2>
    <p><?php echo esc_html( $term->description ); ?></p>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#display-multiple-values)

### Display multiple values

Link copied

This example demonstrates how to get and loop over multiple selected term objects. This implies that your Appearance setting is Checkbox or Multi Select.

```php
<?php
$terms = get_field('taxonomy_field_name');
if( $terms ): ?>
    <ul>
    <?php foreach( $terms as $term ): ?>
        <li>
            <h2><?php echo esc_html( $term->name ); ?></h2>
            <p><?php echo esc_html( $term->description ); ?></p>
            <a href="<?php echo esc_url( get_term_link( $term ) ); ?>">View all '<?php echo esc_html( $term->name ); ?>' posts</a>
        </li>
    <?php endforeach; ?>
    </ul>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#display-values-from-a-selected-term)

### Display values from a selected term

Link copied

The Advanced Custom Fields plugin can be used to [add custom fields to taxonomy terms](https://www.advancedcustomfields.com/resources/adding-fields-taxonomy-term/).
Building on this, the following examples demonstrate how to load a custom field value from a selected term value.

```php
<?php
$term = get_field('taxonomy_field_name');
if( $term ): ?>
    <h2>Term name: <?php echo esc_html( $term->name ); ?></h2>
    <p>Term color: <?php the_field('color', $term); ?></p>
<?php endif; ?>
```

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#notes)

## Notes

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#customizing-query-args)

### Customizing query args

Link copied

The query arguments used to find and display taxonomy terms can be customized via one of the following filters depending on the Appearance setting of your Taxonomy field.

- For Select and Multi Select, use the [acf/fields/taxonomy/query](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-query/) filter.

- For Checkbox and Radio, use the [acf/fields/taxonomy/wp\_list\_categories](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-wp_list_categories/) filter.


[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#customization-of-text)

### Customization of Text

Link copied

The text displayed for each taxonomy term can be customized via the [acf/fields/taxonomy/result](https://www.advancedcustomfields.com/resources/acf-fields-taxonomy-result/) filter.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/taxonomy/#related)

## Related

Link copied

- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Field Types: [Post Object](https://www.advancedcustomfields.com/resources/post-object/)
- Choice: [Radio Button](https://www.advancedcustomfields.com/resources/radio-button/)
- Choice: [Button Group](https://www.advancedcustomfields.com/resources/button-group/)
- Field Types: [Relationship](https://www.advancedcustomfields.com/resources/relationship/)

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

[Got it](https://www.advancedcustomfields.com/resources/taxonomy/#)