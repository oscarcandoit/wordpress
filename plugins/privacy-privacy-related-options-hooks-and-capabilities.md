---
url: https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities
scraped_at: 2025-10-20T03:19:21.940Z
---

[Skip to content](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Privacy Related Options, Hooks and Capabilities


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Privacy](https://developer.wordpress.org/plugins/privacy/)Privacy Related Options, Hooks and Capabilities

Search

# Privacy Related Options, Hooks and Capabilities

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/#options)
- [Actions](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/#actions)
- [Filters](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/#filters)
- [Capabilities](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/#capabilities)

[↑ Back to top](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/#wp--skip-link--target)

The privacy tools were originally introduced in WordPress 4.9.6. These tools are designed to allow (and encourage) developers to use them as part of the Privacy Exporter, Privacy Eraser and the Privacy Policy Guide.

Since then, several newer hooks have been introduced to expand on the available capabilities. These hooks allow developers to include additional personal data in export and erasure requests, and introduce suggested content for the privacy policy guide.

Along with the ability to control these tools, there are several new filters for use with the request and confirmation emails, enabling finer-grained controls over these notifications.

## [Options](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/\#options)

`wp_page_for_privacy_policy` – contains the page ID of a site’s privacy page

## [Actions](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/\#actions)

`user_request_action_confirmed` – fired when a user confirms a privacy request

`wp_privacy_delete_old_export_files` – a scheduled action used to prune old exports from the personal data exports folder

`wp_privacy_personal_data_erased` – fired after the last page of the last eraser is complete

`wp_privacy_personal_data_export_file` – used to create a personal data export file as part of the export flow

`wp_privacy_personal_data_export_file_created` – fires after a personal data export file has been created

## [Filters](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/\#filters)

`privacy_policy_url` – filters the URL of the privacy policy page.

`the_privacy_policy_link` – filters the privacy policy page link HTML.

`wp_get_default_privacy_policy_content` – filters the default content suggested for inclusion through the privacy policy guide.

`user_request_action_confirmed_message` – allows modifying the action confirmation message displayed to the user

`user_request_action_description` – filters the user action description.

`user_request_action_email_content` – filters the text of the email sent when an account action is attempted.

`user_request_action_email_headers` – filters the headers of the email sent when an account action is attempted.

`user_request_action_email_subject` – filters the subject of the email sent when an account action is attempted.

`user_request_confirmed_email_content` – filters the body of the user request confirmation email.

`user_request_confirmed_email_headers` – filters the headers of the user request confirmation email.

`user_request_confirmed_email_subject` – filters the subject of the user request confirmation email.

`user_request_confirmed_email_to` – filters the recipient of the data request confirmation notification.

`user_request_key_expiration` – filters the expiration time of confirmation keys for user requests.

`wp_privacy_additional_user_profile_data` – filter to extend the user’s profile data for the privacy exporter.

`wp_privacy_export_expiration` – controls how old export files are allowed to get, default is 3 days

`wp_privacy_personal_data_email_content` – allows modifying the email message send to users with their personal data export file link

`wp_privacy_personal_data_email_headers` – filters the headers of the email sent with a personal data export file.

`wp_privacy_personal_data_email_subject` – filters the subject of the email sent when an export request is completed.

`wp_privacy_personal_data_email_to` – filters the recipient of the personal data export email notification.

`wp_privacy_personal_data_email_to` should be used with great caution to avoid sending the data export link to the wrong recipient email address(es).

`wp_privacy_personal_data_erasers` – supports registration of core and plugin personal data erasers

`wp_privacy_personal_data_erasure_page` – Filters a page of personal data eraser data. Allows the erasure response to be consumed by destinations in addition to Ajax.

`wp_privacy_personal_data_exporters` – supports registration of core and plugin personal data exporters

`wp_privacy_personal_data_export_page` – filters a page of personal data exporter data. Used to build the export report. Allows the export response to be consumed by destinations in addition to Ajax.

`wp_privacy_anonymize_data` – filters the anonymous data for each type.

`wp_privacy_exports_dir` – filters the directory used to store personal data export files.

`wp_privacy_exports_url` – filters the URL of the directory used to store personal data export files.

`user_confirmed_action_email_content` – Filters the body of the user request confirmation email. The email is sent to an administrator when an user request is confirmed.

`user_erasure_fulfillment_email_to` – Filters the recipient of the data erasure fulfillment notification.

`user_erasure_complete_email_subject` – Filters the subject of the email sent when an erasure request is completed.

`user_confirmed_action_email_content` – Filters the body of the data erasure fulfillment notification. The email is sent to a user when a their data erasure request is fulfilled by an administrator.

`user_erasure_complete_email_headers` – Filters the headers of the data erasure fulfillment notification.

## [Capabilities](https://developer.wordpress.org/plugins/privacy/privacy-related-options-hooks-and-capabilities/\#capabilities)

Access to the privacy tools is controlled by a few new capabilities. Administrators (on non-multisite installations) have these capabilities by default. These capabilities are:

`erase_others_personal_data` – determines if the Erase Personal Data sub-menu is available under Tools

`export_others_personal_data` – determines if the Export Personal Data sub-menu is available under Tools

`manage_privacy_options` – determines if the Privacy sub-menu is available under Settings

First published

May 17, 2018

Last updated

April 23, 2020

[PreviousAdding the Personal Data Exporter to Your PluginPrevious: Adding the Personal Data Exporter to Your Plugin](https://developer.wordpress.org/plugins/privacy/adding-the-personal-data-exporter-to-your-plugin/)

[NextSuggesting text for the site privacy policyNext: Suggesting text for the site privacy policy](https://developer.wordpress.org/plugins/privacy/suggesting-text-for-the-site-privacy-policy/)

Notifications