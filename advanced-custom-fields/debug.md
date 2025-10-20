---
url: https://www.advancedcustomfields.com/resources/debug
scraped_at: 2025-10-20T02:16:52.412Z
---

# Debug, diagnose and solve

Last updated Jan 9, 2017

[Link to heading#](https://www.advancedcustomfields.com/resources/debug/#overview)

## Overview

Link copied

When customizing your theme with ACF functionality, you may experience some issues. These issues may resemble a blank page, a broken page, a value not being loaded or a visible error report. Although frustrating at first, these issues are in fact good feedback, and can be solved quickly. The process of solving these issues, of removing the bugs is known as **debugging**.

[Link to heading#](https://www.advancedcustomfields.com/resources/debug/#exposing-errors)

## Exposing errors

Link copied

Our first step to diagnosing any code related issue is to turn on error reporting. This will prevent the all too common “I’m getting no error message”  issue.

To enable error reporting, simply edit your `wp-config.php` file and look for the following:

[Link to heading#](https://www.advancedcustomfields.com/resources/debug/#wp-configphp)

#### wp-config.php

Link copied

```php
/**
 * For developers: WordPress debugging mode.
 *
 * Change this to true to enable the display of notices during development.
 * It is strongly recommended that plugin and theme developers use WP_DEBUG
 * in their development environments.
 */
define('WP_DEBUG', false);
```

By default, the `WP_DEBUG` setting is disabled, but to expose any potential PHP errors, you will need to enable it. You can do this by setting the value to `true` like so:

```php
define('WP_DEBUG', true);
```

With error reporting now enabled, please refresh the page which contained the issue and look for any PHP errors. Each PHP error will contain the type of error, the file which caused the error and the line number that the error occurred on. If you see any PHP errors, please use this information to resolve the error.

You may find that the error is pointing to a line of code in your template or perhaps you have a section of code which is simply not performing the task you intended such as displaying an image. With an idea of where the issue is coming from, it’s time to debug the data!

[Link to heading#](https://www.advancedcustomfields.com/resources/debug/#debugging-data)

## Debugging data

Link copied

It is likely that the issue your are experiencing is coming from a line of code which interacts with some ACF data. In this case, it is important to confirm that the data you are interacting with is as expected. This is possible by using the `var_dump()` function.

`var_dump()` is a native PHP function which displays structured, humanly readable information about one (or more) variables. This is particularly useful when dealing with arrays and objects as `var_dump()` displays their structure recursively giving you the best possible picture of what’s going on. Here’s an example of how to use `var_dump()` in context:

```php
<?php

$image = get_field('image');

echo '<pre>';
    var_dump( $image );
echo '</pre>';

?>
```

Please note that the above code also makes use of the `pre` tag to correctly render the line breaks and display an array or object in a more humanly readable format.

Now that you can see the data that your theme is interacting with, you may be able to spot where the problem lies. Perhaps you expected the value of `$image` to be a string containing the url, but upon inspection the value is an array containing lots of data.

[Link to heading#](https://www.advancedcustomfields.com/resources/debug/#javascript-issues)

## JavaScript issues

Link copied

Much of the ACF plugin uses JS to add interaction to form elements. For example, clicking on an image field ‘Select Image’ button will launch a popup. If an element seems unresponsive, it is most likely that a JS error exists on the page and is preventing the ACF JS from running.

Debugging JS is quite easy. Simply open the console log (via your browser’s inspector tool) and reload the page. With the console log open, look for any errors that may appear on page load or when interacting with the problem element. If an error appears, this is very useful information to include in your support ticket.

You may find that the JS error points to ‘line 1’ of a minified JS file. It is much more helpful to get the error line of an un-minified JS file. To do this, simply add the following code to your `wp-config.php` file:

```php
define('SCRIPT_DEBUG', true);
```

This line of code will notify WP to load in the full versions of each JS script allowing more detailed JS error reporting.

[Link to heading#](https://www.advancedcustomfields.com/resources/debug/#solving)

## Solving

Link copied

Now that you can see the data, take a look at the code that is interacting with it. If the solution is not apparent at first, please spend a few minutes to research the issue by searching for the variable type (array, object, etc), the functions you are using and the issue you are experiencing. You may also find the solution over on the [FAQ](https://www.advancedcustomfields.com/faq/) or [Support](http://support.advancedcustomfields.com/) pages.

If no solution can be found from the above, please contact our support team via the [help desk on the support page](http://support.advancedcustomfields.com/ "Is there a limit on number of fields?") and be sure to include any debugging information you have performed as this will greatly reduce the response time!

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

[Link to heading#](https://www.advancedcustomfields.com/resources/debug/#related)

## Related

Link copied

- Getting Started: [Displaying Values in Your Theme](https://www.advancedcustomfields.com/resources/displaying-custom-field-values-in-your-theme/)
- Field Types: [User](https://www.advancedcustomfields.com/resources/user/)
- Guides: [Troubleshooting Validation Security Nonce Errors](https://www.advancedcustomfields.com/resources/validation-nonce-errors/)
- Guides: [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)
- Guides: [Known Issues](https://www.advancedcustomfields.com/resources/known-issues/)

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

[Got it](https://www.advancedcustomfields.com/resources/debug/#)