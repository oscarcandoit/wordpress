---
url: https://www.advancedcustomfields.com/resources/acf-field-functions
scraped_at: 2025-10-20T02:23:28.159Z
---

# Updates to ACF Field Functions in 5.11

Last updated Mar 23, 2022

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field-functions/#updates-to-acf-field-functions-in-511)

## Updates to ACF Field Functions in 5.11

Link copied

In versions of ACF prior to 5.11, the ACF shortcode `[acf field="field_name"]`, along with the `get_field()` and `the_field()` functions, could also be used to retrieve WordPress options or post, user or term meta values which weren’t ACF fields. Depending how these functions were used, it could have security implications as site options could inadvertently be exposed to the frontend or to users who do not have admin permissions. In addition, these functions could retrieve values of fields that are no longer registered with ACF, as their meta values remain in the database.

Aside from being a security risk, we don’t recommend using functions like `get_field()` to get anything other than an ACF field. These functions run additional logic and database queries to find a valid field and format it correctly. As a result it would be less performant to use `get_field` instead of the relevant WordPress core functions.

With ACF 5.11.2 and above, the ACF shortcode will only retrieve values for registered ACF fields, whilst `get_field()` and `the_field()` will prevent access to site options which are not registered ACF fields. While this should be fine for most sites, there are a few scenarios that might require special attention. This doc will go over some of those scenarios and offer some solutions.

For ACF 5.11 and 5.11.1, the data access changes for the ACF shortcode were also applied to `get_field()` and `the_field()`.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field-functions/#non-acf-data)

## Using ACF Functions to Retrieve Data From Outside ACF

Link copied

The update to ACF version 5.11.2 means that calling the ACF shortcode on non-ACF options or post, user or term meta will return null, whereas before it might have returned the value.

Calls to get\_field() or the\_field() on non-ACF WordPress options will also return null. However, using those functions to retrieve any post, user or term meta will return the value, regardless of if the meta is an ACF field.

To avoid this, we recommend using WordPress core functions to retrieve non-ACF field data. Developers should use the `get_option()` [function](https://developer.wordpress.org/reference/functions/get_option/) to retrieve data in the `wp_options` table, or the `get_post_meta()` [function](https://developer.wordpress.org/reference/functions/get_post_meta/) to retrieve meta from the `wp_postmeta` table.

In ACF 5.12.1, these restrictions now also correctly apply when using a field key to access an option value, the same as using the field name.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field-functions/#registering-fields-via-php)

## Registering Fields via PHP

Link copied

Any fields registered using the [acf\_add\_local\_field\_group() and acf\_add\_local\_field()](https://www.advancedcustomfields.com/resources/register-fields-via-php/) PHP functions **should** be registered **before** `get_field()` is used. We recommend registering any local fields on the [acf/init](https://www.advancedcustomfields.com/resources/acf-init/) action hook or directly in your theme’s `functions.php` file.

It’s important to note that calling `get_field()` or `the_field()` will initialize ACF if it hasn’t done so already. This means that if you call those functions before your local field groups are registered, ACF won’t be able to find those fields.

Starting with 5.11.1, ACF will detect if this has happened, and output a [`_doing_it_wrong`](https://developer.wordpress.org/reference/functions/_doing_it_wrong/) notice to your PHP error log. From 5.11.2, we will still return data along side this warning to avoid site errors while you modify your code to be compatible.

To correct this, make sure that:

1. Field groups registered via PHP are registered after ACF has initialized, preferably on the `acf/init` hook.
2. Calls to `get_field()` or `the_field()` happen inside an action hook/filter which fires after your fields have been registered, or inside your theme’s template files.

Below is an example of how to correctly register fields using the `acf/init` hook.

```php
add_action( 'acf/init', 'my_acf_add_local_field_groups' );

function my_acf_add_local_field_groups() {
    acf_add_local_field_group(array(
        'key' => 'group_1',
        'title' => 'Page Hero',
        'fields' => array (
            array (
                'key' => 'field_1',
                'label' => 'Hero Title',
                'name' => hero_title,
                'type' => 'text',
            )
        ),
        'location' => array (
            array (
                array (
                    'param' => 'post_type',
                    'operator' => '==',
                    'value' => page,
                ),
            ),
        ),
    ));
}
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field-functions/#registering-fields-inside-conditional-logic)

### Registering Fields Inside Conditional Logic

Link copied

Care should be taken when registering local fields/field groups inside conditional logic, as `get_field()` and related functions may not work as intended.

For example, the following code registers a field in PHP, but only in the WordPress admin due to the `is_admin()` check. Any calls to `get_field()` in frontend theme code wouldn’t be able to retrieve the value for that field:

```php
if ( is_admin() ) {
    add_action( 'acf/init', 'my_acf_add_local_field_groups' );
}

function my_acf_add_local_field_groups() {
    acf_add_local_field_group(array(
        'key' => 'group_1',
        'title' => 'Page Hero',
        'fields' => array (
            array (
                'key' => 'field_1',
                'label' => 'Hero Title',
                'name' => hero_title,
                'type' => 'text',
            )
        ),
        'location' => array (
            array (
                array (
                    'param' => 'post_type',
                    'operator' => '==',
                    'value' => page,
                ),
            ),
        ),
    ));
}
```

The conditional logic needs to be removed so that the ‘acf/init’ action is called on both the admin and frontend of the site:

```php
add_action( 'acf/init', 'my_acf_add_local_field_groups' );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field-functions/#multisite-installs-using-the-same-field-across-multiple-subsites)

## Multisite Installs Using the Same Field Across Multiple Subsites

Link copied

ACF fields are only available to the subsite that registered them. If you want to use the same ACF field on multiple subsites, you should create the field on any subsites that will use the field.

Alternatively, you could export the field groups that you want to re-use as PHP (via **Custom Fields -> Tools -> Generate PHP**), and include that PHP in the `functions.php` file of any themes used by the subsites. This will [register the fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/), and make sure they are available across the multisite network.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-field-functions/#related)

## Related

Link copied

- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Functions: [Shortcode](https://www.advancedcustomfields.com/resources/shortcode/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Functions: [update\_field()](https://www.advancedcustomfields.com/resources/update_field/)
- Guides: [ACF Security Principles](https://www.advancedcustomfields.com/resources/acf-security-principles/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-field-functions/#)