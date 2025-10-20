---
url: https://developer.wordpress.org/cli/commands/menu/item/list/
scraped_at: 2025-10-20T03:08:25.272Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/menu/item/list/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp menu item list


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp menu](https://developer.wordpress.org/cli/commands/menu/)[wp menu item](https://developer.wordpress.org/cli/commands/menu/item/)wp menu item list

Search

# [wp menu item list](https://developer.wordpress.org/cli/commands/menu/item/list/)

Gets a list of items associated with a menu.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/menu/item/list/#options)
- [Available Fields](https://developer.wordpress.org/cli/commands/menu/item/list/#available-fields)
- [Examples](https://developer.wordpress.org/cli/commands/menu/item/list/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/menu/item/list/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/menu/item/list/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu-item-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amenu-item-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/menu/item/list/\#options)

<menu>The name, slug, or term ID for the menu.\[--fields=<fields>\]Limit the output to specific object fields.\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– json

– count

– ids

– yaml

—

### [Available Fields](https://developer.wordpress.org/cli/commands/menu/item/list/\#available-fields)

These fields will be displayed by default for each menu item:

- db\_id
- type
- title
- link
- position

These fields are optionally available:

- menu\_item\_parent
- object\_id
- object
- type
- type\_label
- target
- attr\_title
- description
- classes
- xfn

### [Examples](https://developer.wordpress.org/cli/commands/menu/item/list/\#examples)

```
$ wp menu item list main-menu
+-------+-----------+-------------+---------------------------------+----------+
| db_id | type      | title       | link                            | position |
+-------+-----------+-------------+---------------------------------+----------+
| 5     | custom    | Home        | http://example.com              | 1        |
| 6     | post_type | Sample Page | http://example.com/sample-page/ | 2        |
+-------+-----------+-------------+---------------------------------+----------+

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/menu/item/list/\#global-parameters)

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