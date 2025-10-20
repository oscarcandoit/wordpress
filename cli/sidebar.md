---
url: https://developer.wordpress.org/cli/commands/sidebar/
scraped_at: 2025-10-20T03:15:48.858Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/sidebar/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp sidebar


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp sidebar

Search

# [wp sidebar\  <command>](https://developer.wordpress.org/cli/commands/sidebar/)

Lists registered sidebars.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/sidebar/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/sidebar/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/sidebar/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/widget-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asidebar+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (11)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asidebar+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/widget-command/issues/new)

A [sidebar](https://developer.wordpress.org/themes/functionality/sidebars/) is any widgetized area of your theme.

### [Examples](https://developer.wordpress.org/cli/commands/sidebar/\#examples)

```
# List sidebars
$ wp sidebar list --fields=name,id --format=csv
name,id
"Widget Area",sidebar-1
"Inactive Widgets",wp_inactive_widgets

```

### [Subcommands](https://developer.wordpress.org/cli/commands/sidebar/\#subcommands)

| Name | Description |
| --- | --- |
| [wp sidebar list](https://developer.wordpress.org/cli/commands/sidebar/list/) | Lists registered sidebars. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications