---
url: https://www.advancedcustomfields.com/resources/acf-fields-google_map-api
scraped_at: 2025-10-20T02:24:37.294Z
---

# acf/fields/google\_map/api

Last updated Mar 31, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/#description)

## Description

Link copied

Used to modify the url parameters used to load the Google Maps JS API.

Primarily, this filter exists to set a Google API key, however, it may also be used to customize `other_params` used in the `google.load` function.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/#changelog)

## Changelog

Link copied

- Added in version 5.3.10

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/#parameters)

## Parameters

Link copied

```php
apply_filters( 'acf/fields/google_map/api', $args );
```

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/#args)

### $args

Link copied

_(array)_ Array of url parameters.
– **libraries**

(string) A comma separated list of [libraries](https://developers.google.com/maps/documentation/javascript/libraries) to load. Defaults to “places”.
~~~
‘libraries’ => ‘places’,
~~~

- **key**


(string) A Google Maps [API key](https://developers.google.com/maps/documentation/javascript/get-api-key). Defaults to an empty string.


```php
'key' => '',
```

- **client**


(string) Optional. A Google API client ID. Defaults to an empty string.


```php
'client' => '',
```

- **callback**


(string) Optional. A global JavaScript function to call when the API has loaded. Defaults to `Function.prototype` (a no-op).


```php
'callback' => 'Function.prototype',
```


[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/#example)

## Example

Link copied

This example demonstrates how to register a [Google API key](https://developers.google.com/maps/documentation/javascript/get-api-key) to be used when loading the Google Maps JS library.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/#functionsphp)

#### functions.php

Link copied

```php
<?php
add_filter('acf/fields/google_map/api', 'my_acf_google_map_api');
function my_acf_google_map_api( $args ) {
    $args['key'] = 'xxx';
    return $args;
}
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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/#related)

## Related

Link copied

- Filters: [acf/load\_field](https://www.advancedcustomfields.com/resources/acf-load_field/)
- Filters: [acf/load\_value](https://www.advancedcustomfields.com/resources/acf-load_value/)
- Filters: [acf/prepare\_field](https://www.advancedcustomfields.com/resources/acf-prepare_field/)
- Filters: [acf/update\_value](https://www.advancedcustomfields.com/resources/acf-update_value/)
- Filters: [acf/format\_value](https://www.advancedcustomfields.com/resources/acf-format_value/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-fields-google_map-api/#)