---
url: https://developer.wordpress.org/cli/commands/site/meta/
scraped_at: 2025-10-20T03:16:32.121Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/site/meta/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp site meta


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp site](https://developer.wordpress.org/cli/commands/site/)wp site meta

Search

# [wp site meta\  <command>](https://developer.wordpress.org/cli/commands/site/meta/)

Adds, updates, deletes, and lists site custom fields.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/site/meta/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/site/meta/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/site/meta/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asite-meta+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asite-meta+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/site/meta/\#examples)

```
# Set site meta
$ wp site meta set 123 bio "Mary is a WordPress developer."
Success: Updated custom field 'bio'.

# Get site meta
$ wp site meta get 123 bio
Mary is a WordPress developer.

# Update site meta
$ wp site meta update 123 bio "Mary is an awesome WordPress developer."
Success: Updated custom field 'bio'.

# Delete site meta
$ wp site meta delete 123 bio
Success: Deleted custom field.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/site/meta/\#subcommands)

| Name | Description |
| --- | --- |
| [wp site meta add](https://developer.wordpress.org/cli/commands/site/meta/add/) | Add a meta field. |
| [wp site meta delete](https://developer.wordpress.org/cli/commands/site/meta/delete/) | Delete a meta field. |
| [wp site meta get](https://developer.wordpress.org/cli/commands/site/meta/get/) | Get meta field value. |
| [wp site meta list](https://developer.wordpress.org/cli/commands/site/meta/list/) | List all metadata associated with an object. |
| [wp site meta patch](https://developer.wordpress.org/cli/commands/site/meta/patch/) | Update a nested value for a meta field. |
| [wp site meta pluck](https://developer.wordpress.org/cli/commands/site/meta/pluck/) | Get a nested value from a meta field. |
| [wp site meta update](https://developer.wordpress.org/cli/commands/site/meta/update/) | Update a meta field. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications