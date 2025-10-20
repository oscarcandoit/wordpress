---
url: https://developer.wordpress.org/cli/commands/network/meta/
scraped_at: 2025-10-20T03:08:55.562Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/network/meta/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp network meta


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp network](https://developer.wordpress.org/cli/commands/network/)wp network meta

Search

# [wp network meta\  <command>](https://developer.wordpress.org/cli/commands/network/meta/)

Gets, adds, updates, deletes, and lists network custom fields.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/network/meta/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/network/meta/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/network/meta/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Anetwork-meta+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Anetwork-meta+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/network/meta/\#examples)

```
# Get a list of super-admins
$ wp network meta get 1 site_admins
array (
  0 => 'supervisor',
)

```

### [Subcommands](https://developer.wordpress.org/cli/commands/network/meta/\#subcommands)

| Name | Description |
| --- | --- |
| [wp network meta add](https://developer.wordpress.org/cli/commands/network/meta/add/) | Add a meta field. |
| [wp network meta delete](https://developer.wordpress.org/cli/commands/network/meta/delete/) | Delete a meta field. |
| [wp network meta get](https://developer.wordpress.org/cli/commands/network/meta/get/) | Get meta field value. |
| [wp network meta list](https://developer.wordpress.org/cli/commands/network/meta/list/) | List all metadata associated with an object. |
| [wp network meta patch](https://developer.wordpress.org/cli/commands/network/meta/patch/) | Update a nested value for a meta field. |
| [wp network meta pluck](https://developer.wordpress.org/cli/commands/network/meta/pluck/) | Get a nested value from a meta field. |
| [wp network meta update](https://developer.wordpress.org/cli/commands/network/meta/update/) | Update a meta field. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications