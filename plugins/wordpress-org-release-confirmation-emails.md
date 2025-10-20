---
url: https://developer.wordpress.org/plugins/wordpress-org/release-confirmation-emails
scraped_at: 2025-10-20T03:18:03.682Z
---

[Skip to content](https://developer.wordpress.org/plugins/wordpress-org/release-confirmation-emails/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Release Confirmation Emails


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[The WordPress.org Plugin Directory](https://developer.wordpress.org/plugins/wordpress-org/)Release Confirmation Emails

Search

# Release Confirmation Emails

## In this article

Table of Contents

- [Requirements](https://developer.wordpress.org/plugins/wordpress-org/release-confirmation-emails/#requirements)
- [Requiring double approval](https://developer.wordpress.org/plugins/wordpress-org/release-confirmation-emails/#requiring-double-approval)

[↑ Back to top](https://developer.wordpress.org/plugins/wordpress-org/release-confirmation-emails/#wp--skip-link--target)

In order to better protect plugins from inadvertent releases, we’ve added a new **opt-in** feature for plugins: Release Confirmation.

When enabled on a plugin, to release a new version of a plugin you’ll need to tag a new release in SVN as normal, and then confirm on the [Release Management](https://wordpress.org/plugins/developers/releases/) dashboard.

Access to the Release Management dashboard is limited to plugin committers, and all actions require confirmation via a tokenised link which is emailed to you as needed.

When WordPress.org detects a new version has been tagged in SVN, all committers are automatically sent an email notifying them that a new release is pending, who made it, and a link to the dashboard to confirm the release.

Plugin committers will also see a banner on the top of your WordPress.org plugins page directing you to the Release Management dashboard.

Once confirmed, the release will proceed as usual and should update within a few minutes.

## [Requirements](https://developer.wordpress.org/plugins/wordpress-org/release-confirmation-emails/\#requirements)

- Plugins are required to use tags for new versions, you cannot release your plugin from trunk.
- You must still update the `Stable Tag:` header in your trunk/readme.txt file.
- Once released, alterations cannot be made to the tagged version. This includes changing the readme (for tested up to).
- Committers must be able to receive emails directly, and not have it go to a shared inbox or support ticket system.

## [Requiring double approval](https://developer.wordpress.org/plugins/wordpress-org/release-confirmation-emails/\#requiring-double-approval)

Release Confirmations are opt-in, but only requires a singular committer to confirm the release.

If a group would like to require multiple committers to approve a release, please contact the Plugins team with your request.

First published

April 9, 2021

Last updated

November 1, 2022

[PreviousPreviews and BlueprintsPrevious: Previews and Blueprints](https://developer.wordpress.org/plugins/wordpress-org/previews-and-blueprints/)

[NextSpecial User Roles and CapabilitiesNext: Special User Roles and Capabilities](https://developer.wordpress.org/plugins/wordpress-org/special-user-roles-capabilities/)

Notifications