---
url: https://developer.wordpress.org/cli/commands/plugin/auto-updates/
scraped_at: 2025-10-20T03:11:14.429Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/plugin/auto-updates/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp plugin auto-updates


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp plugin](https://developer.wordpress.org/cli/commands/plugin/)wp plugin auto-updates

Search

# [wp plugin auto-updates\  <command>](https://developer.wordpress.org/cli/commands/plugin/auto-updates/)

Manages plugin auto-updates.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/plugin/auto-updates/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/plugin/auto-updates/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/plugin/auto-updates/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/extension-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-auto-updates+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-auto-updates+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/extension-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/plugin/auto-updates/\#examples)

```
# Enable the auto-updates for a plugin
$ wp plugin auto-updates enable hello
Plugin auto-updates for 'hello' enabled.
Success: Enabled 1 of 1 plugin auto-updates.

# Disable the auto-updates for a plugin
$ wp plugin auto-updates disable hello
Plugin auto-updates for 'hello' disabled.
Success: Disabled 1 of 1 plugin auto-updates.

# Get the status of plugin auto-updates
$ wp plugin auto-updates status hello
Auto-updates for plugin 'hello' are disabled.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/plugin/auto-updates/\#subcommands)

| Name | Description |
| --- | --- |
| [wp plugin auto-updates disable](https://developer.wordpress.org/cli/commands/plugin/auto-updates/disable/) | Disables the auto-updates for a plugin. |
| [wp plugin auto-updates enable](https://developer.wordpress.org/cli/commands/plugin/auto-updates/enable/) | Enables the auto-updates for a plugin. |
| [wp plugin auto-updates status](https://developer.wordpress.org/cli/commands/plugin/auto-updates/status/) | Shows the status of auto-updates for a plugin. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications