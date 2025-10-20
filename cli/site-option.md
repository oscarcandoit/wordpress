---
url: https://developer.wordpress.org/cli/commands/site/option/
scraped_at: 2025-10-20T03:16:38.969Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/site/option/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp site option


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp site](https://developer.wordpress.org/cli/commands/site/)wp site option

Search

# [wp site option\  <command>](https://developer.wordpress.org/cli/commands/site/option/)

Adds, updates, deletes, and lists site options in a multisite installation.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/site/option/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/site/option/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/site/option/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asite-option+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (13)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asite-option+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/site/option/\#examples)

```
# Get site registration
$ wp site option get registration
none

# Add site option
$ wp site option add my_option foobar
Success: Added 'my_option' site option.

# Update site option
$ wp site option update my_option '{"foo": "bar"}' --format=json
Success: Updated 'my_option' site option.

# Delete site option
$ wp site option delete my_option
Success: Deleted 'my_option' site option.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/site/option/\#subcommands)

| Name | Description |
| --- | --- |
| [wp site option add](https://developer.wordpress.org/cli/commands/site/option/add/) | Adds a site option. |
| [wp site option delete](https://developer.wordpress.org/cli/commands/site/option/delete/) | Deletes a site option. |
| [wp site option get](https://developer.wordpress.org/cli/commands/site/option/get/) | Gets a site option. |
| [wp site option list](https://developer.wordpress.org/cli/commands/site/option/list/) | Lists site options. |
| [wp site option patch](https://developer.wordpress.org/cli/commands/site/option/patch/) | Updates a nested value in an option. |
| [wp site option pluck](https://developer.wordpress.org/cli/commands/site/option/pluck/) | Gets a nested value from an option. |
| [wp site option update](https://developer.wordpress.org/cli/commands/site/option/update/) | Updates a site option. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications