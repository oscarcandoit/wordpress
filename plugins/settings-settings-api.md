---
url: https://developer.wordpress.org/plugins/settings/settings-api
scraped_at: 2025-10-20T03:37:57.377Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/settings/settings-api/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Settings API


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Settings](https://developer.wordpress.org/plugins/settings/)Settings API

Search

# Settings API

## In this article

Table of Contents

- [Why Use the Setting API?](https://developer.wordpress.org/plugins/settings/settings-api/#why-use-the-setting-api)
  - [Visual Consistency](https://developer.wordpress.org/plugins/settings/settings-api/#visual-consistency)
  - [Robustness (Future-Proofing!)](https://developer.wordpress.org/plugins/settings/settings-api/#robustness-future-proofing)
  - [Less Work!](https://developer.wordpress.org/plugins/settings/settings-api/#less-work)
- [Function Reference](https://developer.wordpress.org/plugins/settings/settings-api/#function-reference)

[↑ Back to top](https://developer.wordpress.org/plugins/settings/settings-api/#wp--skip-link--target)

The Settings API, added in WordPress 2.7, allows admin pages containing settings forms to be managed semi-automatically. It lets you define settings pages, sections within those pages and fields within the sections.

New settings pages can be registered along with sections and fields inside them. Existing settings pages can also be added to by registering new settings sections or fields inside of them.

Organizing registration and validation of fields still requires some effort from developers, but avoids a lot of complex debugging of underlying options management.

When using the Settings API, the form POST to `wp-admin/options.php` which provides fairly strict capabilities checking. Users will need the `manage_options` capability (and in Multisite will have to be a Super Admin) to submit the form.

## [Why Use the Setting API?](https://developer.wordpress.org/plugins/settings/settings-api/\#why-use-the-setting-api)

A developer _could_ ignore this API and write their own settings page without it. That begs the question, what benefit does this API bring to the table? Following is a quick rundown of some of the benefits.

### [Visual Consistency](https://developer.wordpress.org/plugins/settings/settings-api/\#visual-consistency)

Using the API to generate your interface elements guarantees that your settings page will look like the rest of the administrative content. Your interface will follow the same styleguide and look like it belongs, and thanks to the talented team of WordPress designers, it’ll look awesome!

### [Robustness (Future-Proofing!)](https://developer.wordpress.org/plugins/settings/settings-api/\#robustness-future-proofing)

Since the API is part of WordPress Core, any updates will automatically consider your plugin’s settings page. If you make your own interface without using Setting API, WordPress Core updates are more likely to break your customizations. There is also a wider audience testing and maintaining that API code, so it will tend to be more stable.

### [Less Work!](https://developer.wordpress.org/plugins/settings/settings-api/\#less-work)

Of course the most immediate benefit is that the WordPress API does a lot of work for you under the hood. Here are a few examples of things the Settings API does besides applying an awesome-looking, integrated design.

- **Handling Form Submissions –** Let WordPress handle retrieving and storing your $\_POST submissions.
- **Include Security Measures –** You get extra security measures such as nonces, etc. for free.
- **Sanitizing Data –** You get access to the same methods that the rest of WordPress uses for ensuring strings are safe to use.

## [Function Reference](https://developer.wordpress.org/plugins/settings/settings-api/\#function-reference)

| Setting Register/Unregister | Add Field/Section |
| --- | --- |
| `[register\_setting()](https://developer.wordpress.org/reference/functions/register_setting/) `<br>`[unregister\_setting()](https://developer.wordpress.org/reference/functions/unregister_setting/) ` | `[add\_settings\_section()](https://developer.wordpress.org/reference/functions/add_settings_section/) `<br>`[add\_settings\_field()](https://developer.wordpress.org/reference/functions/add_settings_field/) ` |

| Options Form Rendering | Errors |
| --- | --- |
| `[settings\_fields()](https://developer.wordpress.org/reference/functions/settings_fields/) `<br>`[do\_settings\_sections()](https://developer.wordpress.org/reference/functions/do_settings_sections/) `<br>`[do\_settings\_fields()](https://developer.wordpress.org/reference/functions/do_settings_fields/) ` | `[add\_settings\_error()](https://developer.wordpress.org/reference/functions/add_settings_error/) `<br>`[get\_settings\_errors()](https://developer.wordpress.org/reference/functions/get_settings_errors/) `<br>`[settings\_errors()](https://developer.wordpress.org/reference/functions/settings_errors/) ` |

First published

September 24, 2014

Last updated

August 29, 2020

[PreviousOptions APIPrevious: Options API](https://developer.wordpress.org/plugins/settings/options-api/)

[NextUsing Settings APINext: Using Settings API](https://developer.wordpress.org/plugins/settings/using-settings-api/)

Notifications