---
url: https://developer.wordpress.org/cli/commands/post/meta/
scraped_at: 2025-10-20T03:13:43.095Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/post/meta/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp post meta


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp post](https://developer.wordpress.org/cli/commands/post/)wp post meta

Search

# [wp post meta\  <command>](https://developer.wordpress.org/cli/commands/post/meta/)

Adds, updates, deletes, and lists post custom fields.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/post/meta/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/post/meta/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/post/meta/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-meta+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-meta+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/post/meta/\#examples)

```
# Set post meta
$ wp post meta set 123 _wp_page_template about.php
Success: Updated custom field '_wp_page_template'.

# Get post meta
$ wp post meta get 123 _wp_page_template
about.php

# Update post meta
$ wp post meta update 123 _wp_page_template contact.php
Success: Updated custom field '_wp_page_template'.

# Delete post meta
$ wp post meta delete 123 _wp_page_template
Success: Deleted custom field.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/post/meta/\#subcommands)

| Name | Description |
| --- | --- |
| [wp post meta add](https://developer.wordpress.org/cli/commands/post/meta/add/) | Add a meta field. |
| [wp post meta clean-duplicates](https://developer.wordpress.org/cli/commands/post/meta/clean-duplicates/) | Cleans up duplicate post meta values on a post. |
| [wp post meta delete](https://developer.wordpress.org/cli/commands/post/meta/delete/) | Delete a meta field. |
| [wp post meta get](https://developer.wordpress.org/cli/commands/post/meta/get/) | Get meta field value. |
| [wp post meta list](https://developer.wordpress.org/cli/commands/post/meta/list/) | List all metadata associated with an object. |
| [wp post meta patch](https://developer.wordpress.org/cli/commands/post/meta/patch/) | Update a nested value for a meta field. |
| [wp post meta pluck](https://developer.wordpress.org/cli/commands/post/meta/pluck/) | Get a nested value from a meta field. |
| [wp post meta update](https://developer.wordpress.org/cli/commands/post/meta/update/) | Update a meta field. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications