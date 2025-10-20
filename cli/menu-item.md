---
url: https://developer.wordpress.org/cli/commands/menu/item/
scraped_at: 2025-10-20T03:08:01.854Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/menu/item/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp menu item


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp menu](https://developer.wordpress.org/cli/commands/menu/)wp menu item

Search

# [wp menu item\  <command>](https://developer.wordpress.org/cli/commands/menu/item/)

List, add, and delete items associated with a menu.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/menu/item/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/menu/item/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/menu/item/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu-item+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu-item+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/menu/item/\#examples)

```
# Add an existing post to an existing menu
$ wp menu item add-post sidebar-menu 33 --title="Custom Test Post"
Success: Menu item added.

# Create a new menu link item
$ wp menu item add-custom sidebar-menu Apple http://apple.com
Success: Menu item added.

# Delete menu item
$ wp menu item delete 45
Success: Deleted 1 of 1 menu items.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/menu/item/\#subcommands)

| Name | Description |
| --- | --- |
| [wp menu item add-custom](https://developer.wordpress.org/cli/commands/menu/item/add-custom/) | Adds a custom menu item. |
| [wp menu item add-post](https://developer.wordpress.org/cli/commands/menu/item/add-post/) | Adds a post as a menu item. |
| [wp menu item add-term](https://developer.wordpress.org/cli/commands/menu/item/add-term/) | Adds a taxonomy term as a menu item. |
| [wp menu item delete](https://developer.wordpress.org/cli/commands/menu/item/delete/) | Deletes one or more items from a menu. |
| [wp menu item list](https://developer.wordpress.org/cli/commands/menu/item/list/) | Gets a list of items associated with a menu. |
| [wp menu item update](https://developer.wordpress.org/cli/commands/menu/item/update/) | Updates a menu item. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications