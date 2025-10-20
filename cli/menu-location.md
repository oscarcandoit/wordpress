---
url: https://developer.wordpress.org/cli/commands/menu/location/
scraped_at: 2025-10-20T03:08:36.885Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/menu/location/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp menu location


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp menu](https://developer.wordpress.org/cli/commands/menu/)wp menu location

Search

# [wp menu location\  <command>](https://developer.wordpress.org/cli/commands/menu/location/)

Assigns, removes, and lists a menu’s locations.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/menu/location/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/menu/location/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/menu/location/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu-location+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu-location+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/menu/location/\#examples)

```
# List available menu locations
$ wp menu location list
+----------+-------------------+
| location | description       |
+----------+-------------------+
| primary  | Primary Menu      |
| social   | Social Links Menu |
+----------+-------------------+

# Assign the 'primary-menu' menu to the 'primary' location
$ wp menu location assign primary-menu primary
Success: Assigned location primary to menu primary-menu.

# Remove the 'primary-menu' menu from the 'primary' location
$ wp menu location remove primary-menu primary
Success: Removed location from menu.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/menu/location/\#subcommands)

| Name | Description |
| --- | --- |
| [wp menu location assign](https://developer.wordpress.org/cli/commands/menu/location/assign/) | Assigns a location to a menu. |
| [wp menu location list](https://developer.wordpress.org/cli/commands/menu/location/list/) | Lists locations for the current theme. |
| [wp menu location remove](https://developer.wordpress.org/cli/commands/menu/location/remove/) | Removes a location from a menu. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications