---
url: https://www.advancedcustomfields.com/resources/select2-v3-deprecation
scraped_at: 2025-10-20T02:33:52.977Z
---

# Select2 v3 Deprecation

Last updated Jul 22, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/select2-v3-deprecation/#select2-v3-deprecation)

## Select2 v3 Deprecation

Link copied

[Link to heading#](https://www.advancedcustomfields.com/resources/select2-v3-deprecation/#whats-happening)

### What’s Happening?

Link copied

Advanced Custom Fields (ACF) is deprecating support for version 3 of the Select2 JavaScript library. Future versions of ACF will only support Select2 v4.

Select2 v4 has been the default for many years in ACF and the vast majority of users will be unaffected by this change. Using Select2 v3 required specific code in your theme or a plugin.

[Link to heading#](https://www.advancedcustomfields.com/resources/select2-v3-deprecation/#why-is-this-changing)

### Why Is This Changing?

Link copied

- **Select2 v3 is no longer maintained** and does not receive security updates.
- **Select2 v4** offers improved accessibility, performance, and compatibility with modern browsers.
- Many plugins and themes now expect Select2 v4.

[Link to heading#](https://www.advancedcustomfields.com/resources/select2-v3-deprecation/#how-does-this-affect-me)

### How Does This Affect Me?

Link copied

- If your site or plugins force ACF to use Select2 v3 (via `acf_get_setting('select2_version')` or a filter), you will see a notice in your WordPress admin dashboard notifying you that your site is still using Select2 v3.
- Custom code, plugins, or themes that rely on Select2 v3’s API or CSS may break when ACF removes v3 support.
- You may need to update custom JavaScript or CSS that interacts with ACF select fields.

[Link to heading#](https://www.advancedcustomfields.com/resources/select2-v3-deprecation/#what-should-i-do)

### What Should I Do?

Link copied

1. **Test your site** with Select2 v4 enabled:


   - Remove any code or filters that force Select2 v3.
   - Review any Select2 fields and integrations.
2. **Update custom code**:


   - [See the Select2 v4 migration guide](https://select2.org/upgrading/migrating-from-35).
   - Update any JavaScript using old Select2 v3 methods (e.g., `.select2('val', ...)`).
3. **Contact plugin/theme authors** if you rely on third-party code that requires Select2 v3.

[Link to heading#](https://www.advancedcustomfields.com/resources/select2-v3-deprecation/#need-help)

### Need Help?

Link copied

- [Select2 v4 Migration Guide](https://select2.org/upgrading/migrating-from-35)
- [ACF Support](https://www.advancedcustomfields.com/support/)

* * *

**Summary:**

ACF is moving to Select2 v4 for better security and compatibility. Please update your code and test your site to ensure a smooth transition.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/select2-v3-deprecation/#related)

## Related

Link copied

- Guides: [Upgrade Guide – Version 4](https://www.advancedcustomfields.com/resources/upgrade-guide-version-4/)
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

[Got it](https://www.advancedcustomfields.com/resources/select2-v3-deprecation/#)