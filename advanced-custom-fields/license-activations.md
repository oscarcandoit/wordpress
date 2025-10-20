---
url: https://www.advancedcustomfields.com/resources/license-activations
scraped_at: 2025-10-20T02:31:27.508Z
---

# License Activations

Last updated Jul 21, 2024

[Link to heading#](https://www.advancedcustomfields.com/resources/license-activations/#overview)

## Overview

Link copied

ACF PRO has always required a license to use PRO features and this will shortly be enforced in the plugin. Sites without an active license will display a warning in the ACF screens as of ACF 6.2.3, and will have the following restrictions in place starting with ACF 6.2.8.

Activating your ACF PRO license key on a site enables automatic plugin updates and gives access to the premium features.

[Link to heading#](https://www.advancedcustomfields.com/resources/license-activations/#how-it-works)

## How it Works

Link copied

**The editor experience for ACF fields, ACF Blocks, and Options Pages will not change, and your site editors will be able to use all features as they do now. The following restrictions will only apply to ACF’s admin screens for editing field groups.**

Until a valid license key has been activated for the site, it won’t be possible to create new or edit existing PRO fields (Gallery, Repeater, Flexible Content, or Clone), or use the premium features such as Options Pages and ACF Blocks.

If you previously activated a license and the subscription has expired, you will not be able to create new PRO fields, but you will be able to edit existing PRO field definitions.

**To be clear, the editing and display of field data anywhere outside of the ACF admin screens will be unaffected by the status of the license**.

The use of ACF on a site is in 3 different areas, and to clarify how these changes affect those areas take a look at the following table:

|  | ACF Admin | Editing Posts | Displaying Data |
| --- | --: | --: | --- |
|  | _Where you create and edit field groups, fields, and Options Pages in the ACF admin screen using PRO field types_ | _Where content editors enter field values and ACF Blocks when editing posts, pages & custom post types_ | _How the field values are rendered on the front end of the site by the theme or a page builder_ |
| **Valid license activated** | 🟢 No impact | 🟢 No impact | 🟢 No impact |
| **Expired license activated** | 🟢 Can edit existing ACF PRO fields, ACF Blocks, and Options Pages<br>🟠 Cannot create new ACF PRO fields, ACF Blocks, and Options Pages | 🟢 No impact | 🟢 No impact |
| **No license activated** | 🟠 Cannot edit existing ACF PRO fields, ACF Blocks, and Options Pages<br>🟠 Cannot create new ACF PRO fields, ACF Blocks, and Options Pages | 🟢 No impact | 🟢 No impact |

[Link to heading#](https://www.advancedcustomfields.com/resources/license-activations/#development--staging-activations)

## Development & Staging Activations

Link copied

ACF PRO licenses have a limit on the number of production sites they can be activated on. However, we allow unlimited activations on development and staging sites. We detect if a site is a development or staging site using the following ruleset:

- **Dev:** Is URL a single segment? (localhost)
- **Dev:** Is URL an IP address? (192.168.0.1)
- **Dev:** Does the URL contain a dev-related subdomain? (test., testing., sandbox., dev., local.)
- **Dev:** Does the URL contain a dev-related not publicly accessible TLD? (.local, .loc, .localhost, .test)​​
- **Stage:** Does the URL contain a stage-related subdomain? (stage., staging.)
- **Stage:** Does the URL contain a stage-related parent? (sitename.wpengine.com, sitename.wpenginepowered.com, staging-sitename.kinsta.cloud, sitename.flywheelstaging.com)
- **Prod:** All other URLs

If your development or staging URL uses a different format then it will be classified as a production site and will count towards your license limit. To avoid that, please alter your URL or upgrade your subscription to a license with a larger site limit.

Any sites served in a subdirectory will be the root domain for its site type. For example, https://mysite.com/staging would be treated as a production URL.

[Link to heading#](https://www.advancedcustomfields.com/resources/license-activations/#composer-installations)

## Composer Installations

Link copied

For users who install ACF via [Composer](https://www.advancedcustomfields.com/resources/installing-acf-pro-with-composer/), we recommend you [define your license key in code](https://www.advancedcustomfields.com/resources/how-to-activate/#wp-configphp).

ACF automatically activates your license when downloading the plugin via Composer for the site URL you provide in your `auth.json` file, and this will now be checked by the plugin to ensure the URL you provided is correct for that site before you can use PRO features.

Alternatively, you’ll need to activate ACF as usual by entering a key manually in the ‘Updates’ page of ACF’s admin.

[Link to heading#](https://www.advancedcustomfields.com/resources/license-activations/#multisite-installations)

## Multisite Installations

Link copied

If you have purchased an ACF PRO license to use on a WordPress multisite network, you must ensure that you have activated your license key for the main site of the network to enable automatic updates of the plugin.

If you purchased a license on or after 1st Feb 2024, you are required to activate your license key on any subsite which has the ACF PRO activated and you intend to use it on. Therefore, your license needs to have enough activations available for the subsites you require. You’ll also need to activate ACF on the network’s main site in order to receive automatic updates.

If you purchased a license before 1st Feb 2024, you do not need to activate the license key on individual subsites, just the main site of the network. The updates page will not be visible on any subsites.

[Link to heading#](https://www.advancedcustomfields.com/resources/license-activations/#bundling-acf-pro-with-other-plugins)

## Bundling ACF PRO With Other Plugins

Link copied

If you have [bundled ACF PRO](https://www.advancedcustomfields.com/resources/including-acf-within-a-plugin-or-theme/) with your theme or plugin, you must ensure that the bundling has been done as the bundling documentation has always required so your users aren’t impacted by these restrictions.

The bundling should be done as follows:

- The ‘ACF’ menu should be removed, so your users can’t create fields
- The field groups, fields, and options pages for your theme or plugin should be defined using PHP or JSON
- The ACF ‘Updates’ page where the license key can be activated should be hidden
- If a later version of ACF PRO is installed on the site, the bundling code should not execute

Learn more about the way to [bundle ACF PRO in a third-party plugin or theme](https://www.advancedcustomfields.com/resources/including-acf-within-a-plugin-or-theme/).

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

[Link to heading#](https://www.advancedcustomfields.com/resources/license-activations/#related)

## Related

Link copied

- Guides: [How to Activate ACF PRO](https://www.advancedcustomfields.com/resources/how-to-activate/)
- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)
- Videos: [Installing ACF and ACF PRO](https://www.advancedcustomfields.com/resources/installing-acf-and-acf-pro/)
- Features: [Options Page](https://www.advancedcustomfields.com/resources/options-page/)
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

[Got it](https://www.advancedcustomfields.com/resources/license-activations/#)