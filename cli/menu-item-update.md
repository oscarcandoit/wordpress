---
url: https://developer.wordpress.org/cli/commands/menu/item/update/
scraped_at: 2025-10-20T03:08:32.780Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/menu/item/update/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp menu item update


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp menu](https://developer.wordpress.org/cli/commands/menu/)[wp menu item](https://developer.wordpress.org/cli/commands/menu/item/)wp menu item update

Search

# [wp menu item update](https://developer.wordpress.org/cli/commands/menu/item/update/)

Updates a menu item.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/menu/item/update/#options)
- [Examples](https://developer.wordpress.org/cli/commands/menu/item/update/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/menu/item/update/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/menu/item/update/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu-item-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu-item-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/menu/item/update/\#options)

<db-id>Database ID for the menu item.\[--title=<title>\]Set a custom title for the menu item.\[--link=<link>\]Set a custom url for the menu item.\[--description=<description>\]Set a custom description for the menu item.\[--attr-title=<attr-title>\]Set a custom title attribute for the menu item.\[--target=<target>\]Set a custom link target for the menu item.\[--classes=<classes>\]Set a custom link classes for the menu item.\[--position=<position>\]Specify the position of this menu item.\[--parent-id=<parent-id>\]Make this menu item a child of another menu item.

### [Examples](https://developer.wordpress.org/cli/commands/menu/item/update/\#examples)

```
$ wp menu item update 45 --title=WordPress --link='http://wordpress.org' --target=_blank --position=2
Success: Menu item updated.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/menu/item/update/\#global-parameters)

These [global parameters](https://make.wordpress.org/cli/handbook/config/) have the same behavior across all commands and affect how WP-CLI interacts with WordPress.

| **Argument** | **Description** |
| :-- | :-- |
| `--path=<path>` | Path to the WordPress files. |
| `--url=<url>` | Pretend request came from given URL. In multisite, this argument is how the target site is specified. |
| `--ssh=[<scheme>:][<user>@]<host\|container>[:<port>][<path>]` | Perform operation against a remote server over SSH (or a container using scheme of “docker”, “docker-compose”, “docker-compose-run”, “vagrant”). |
| `--http=<http>` | Perform operation against a remote WordPress installation over HTTP. |
| `--user=<id\|login\|email>` | Set the WordPress user. |
| `--skip-plugins[=<plugins>]` | Skip loading all plugins, or a comma-separated list of plugins. Note: mu-plugins are still loaded. |
| `--skip-themes[=<themes>]` | Skip loading all themes, or a comma-separated list of themes. |
| `--skip-packages` | Skip loading all installed packages. |
| `--require=<path>` | Load PHP file before running the command (may be used more than once). |
| `--exec=<php-code>` | Execute PHP code before running the command (may be used more than once). |
| `--context=<context>` | Load WordPress in a given context. |
| `--[no-]color` | Whether to colorize the output. |
| `--debug[=<group>]` | Show all PHP errors and add verbosity to WP-CLI output. Built-in groups include: bootstrap, commandfactory, and help. |
| `--prompt[=<assoc>]` | Prompt the user to enter values for all command arguments, or a subset specified as comma-separated values. |
| `--quiet` | Suppress informational messages. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications