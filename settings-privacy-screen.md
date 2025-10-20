---
url: https://wordpress.org/documentation/article/settings-privacy-screen
scraped_at: 2025-10-20T02:14:03.338Z
---

[Skip to content](https://wordpress.org/documentation/article/settings-privacy-screen/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Settings Privacy screen

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Dashboard](https://wordpress.org/documentation/category/dashboard/)Settings Privacy screen

Search documentation

# Settings Privacy screen

## In this article

Table of Contents

- [Using Privacy Settings tool](https://wordpress.org/documentation/article/settings-privacy-screen/#using-privacy-settings-tool)

[Where is the Privacy Policy page displayed?](https://wordpress.org/documentation/article/settings-privacy-screen/#where-is-the-privacy-policy-page-displayed)
[To Theme Developers](https://wordpress.org/documentation/article/settings-privacy-screen/#to-theme-developers)

[↑ Back to top](https://wordpress.org/documentation/article/settings-privacy-screen/#wp--skip-link--target)

WordPress 4.9.6 included a Privacy Settings tool. Administrator can
create new page or specify existing one as Privacy Policy page of the
site.

Note: The new page will include help and suggestions for your
privacy policy. However, it is your responsibility to use those
resources correctly, to provide the information that your privacy policy
requires, and to keep that information current and accurate.

### [Using Privacy Settings tool](https://wordpress.org/documentation/article/settings-privacy-screen/\#using-privacy-settings-tool)

1\. Select **Settings** -\> **Privacy** from Administration Screens.

[![](https://i2.wp.com/wordpress.org/documentation/files/2019/02/PrivacySettingsTool_4.9.6.jpg?fit=1083%2C673&ssl=1)](https://wordpress.org/support/?attachment_id=11188507)

2\. Click **Create New Page** to generate a Privacy Policy Page. Or, Select an existing page which you want to use from drop down box and click **Use This Page**.

3\. If you click **Create New Page**, then template page titled Privacy Policy will be opened. Modify the contents and click Publish.

Hint: If you need help, click the link of ‘Check out our guide’ for recommendations on what content to include.

[![](https://i0.wp.com/wordpress.org/documentation/files/2019/02/PrivacySettingsTool_Editor_4.9.6.jpg?fit=1089%2C683&ssl=1)](https://wordpress.org/support/?attachment_id=11188509)

## [Where is the Privacy Policy page displayed?](https://wordpress.org/documentation/article/settings-privacy-screen/\#where-is-the-privacy-policy-page-displayed)

The Privacy Policy page will be shown on your login and registration pages. Notice the bottom Link ‘Privacy Policy’.

[![](https://i1.wp.com/wordpress.org/documentation/files/2019/02/PrivacySettingsTool_4.9.6_login.jpg?fit=435%2C568&ssl=1)](https://wordpress.org/support/?attachment_id=11188516)

It is your responsibility to create a link to the Privacy Policy page to every page on your site. But theme will support such function soon. For example, Twenty Seventeen adds the link to the Privacy Policy page at the bottom.

## [To Theme Developers](https://wordpress.org/documentation/article/settings-privacy-screen/\#to-theme-developers)

For users convenience, you should refer these new functions.

- `get_privacy_policy_url()` – Retrieves the URL to the privacy policy page.
- `the_privacy_policy_link()` – Displays the privacy policy link with formatting, when applicable.
- `get_the_privacy_policy_link()` – Returns the privacy policy link with formatting, when applicable.

This is the example from Twenty Seventeen (twentyseventeen/template-parts/footer/site-info.php)

```
if ( function_exists( 'the_privacy_policy_link' ) ) {
    the_privacy_policy_link( '', '<span role="separator" aria-hidden="true"></span>' );
}

```

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/settings-privacy-screen/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fsettings-privacy-screen%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

March 8, 2019

Last updated

June 8, 2024

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.