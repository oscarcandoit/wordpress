---
url: https://developer.wordpress.org/cli/commands/menu/
scraped_at: 2025-10-20T03:07:55.511Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/menu/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp menu


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp menu

Search

# [wp menu\  <command>](https://developer.wordpress.org/cli/commands/menu/)

Lists, creates, assigns, and deletes the active theme’s navigation menus.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/menu/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/menu/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/menu/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (22)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

See the [Navigation Menus](https://developer.wordpress.org/themes/functionality/navigation-menus/) reference in the Theme Handbook.

### [Examples](https://developer.wordpress.org/cli/commands/menu/\#examples)

```
# Create a new menu
$ wp menu create "My Menu"
Success: Created menu 200.

# List existing menus
$ wp menu list
+---------+----------+----------+-----------+-------+
| term_id | name     | slug     | locations | count |
+---------+----------+----------+-----------+-------+
| 200     | My Menu  | my-menu  |           | 0     |
| 177     | Top Menu | top-menu | primary   | 7     |
+---------+----------+----------+-----------+-------+

# Create a new menu link item
$ wp menu item add-custom my-menu Apple http://apple.com --porcelain
1922

# Assign the 'my-menu' menu to the 'primary' location
$ wp menu location assign my-menu primary
Success: Assigned location primary to menu my-menu.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/menu/\#subcommands)

| Name | Description |
| --- | --- |
| [wp menu create](https://developer.wordpress.org/cli/commands/menu/create/) | Creates a new menu. |
| [wp menu delete](https://developer.wordpress.org/cli/commands/menu/delete/) | Deletes one or more menus. |
| [wp menu item](https://developer.wordpress.org/cli/commands/menu/item/) | List, add, and delete items associated with a menu. |
| [wp menu list](https://developer.wordpress.org/cli/commands/menu/list/) | Gets a list of menus. |
| [wp menu location](https://developer.wordpress.org/cli/commands/menu/location/) | Assigns, removes, and lists a menu’s locations. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications