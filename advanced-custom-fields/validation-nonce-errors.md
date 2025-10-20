---
url: https://www.advancedcustomfields.com/resources/validation-nonce-errors
scraped_at: 2025-10-20T02:32:11.250Z
---

# Troubleshooting Validation Security Nonce Errors

Last updated Jan 21, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/validation-nonce-errors/#overview)

## Overview

Link copied

With ACF 6.3.12 and above, there are two potential errors that can appear if ACF is unable to verify the security [nonce](https://en.wikipedia.org/wiki/Cryptographic_nonce) while validating your fields.

[Link to heading#](https://www.advancedcustomfields.com/resources/validation-nonce-errors/#acf-was-unable-to-perform-validation-because-the-provided-nonce-failed-verification)

### ACF was unable to perform validation because the provided nonce failed verification.

Link copied

This error indicates that ACF received a security nonce, but the nonce failed verification. This can occur if you’ve left the browser open for a long time while editing a page. To confirm if that’s the case, try logging out and back in again.

If that doesn’t help, and you have a development/staging version of the site, you can try deactivating any other plugins and themes to rule out a potential conflict.

[Link to heading#](https://www.advancedcustomfields.com/resources/validation-nonce-errors/#acf-was-unable-to-perform-validation-because-no-nonce-was-received-by-the-server)

### ACF was unable to perform validation because no nonce was received by the server.

Link copied

This happens when ACF doesn’t receive a security nonce at all. This most commonly happens when the PHP `max_input_vars` setting is too low and there are lots of ACF fields present on the page. To correct this, ask your host to see what your current `max_input_vars` setting is, and if it can be increased to at least 10,000.

If you’ve tried the above and are still running into this issue, please contact our support team and we’ll be glad to help troubleshoot further.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/validation-nonce-errors/#related)

## Related

Link copied

- Filters: [acf/validate\_value](https://www.advancedcustomfields.com/resources/acf-validate_value/)
- Guides: [Debug, diagnose and solve](https://www.advancedcustomfields.com/resources/debug/)
- Guides: [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)
- Guides: [Known Issues](https://www.advancedcustomfields.com/resources/known-issues/)
- Guides: [How to Update](https://www.advancedcustomfields.com/resources/how-to-update/)

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

[Got it](https://www.advancedcustomfields.com/resources/validation-nonce-errors/#)