---
url: https://developer.wordpress.org/cli/commands/post-type/list/
scraped_at: 2025-10-20T03:14:30.977Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/post-type/list/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp post-type list


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp post-type](https://developer.wordpress.org/cli/commands/post-type/)wp post-type list

Search

# [wp post-type list](https://developer.wordpress.org/cli/commands/post-type/list/)

Lists registered post types.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/post-type/list/#options)
- [Available Fields](https://developer.wordpress.org/cli/commands/post-type/list/#available-fields)
- [Examples](https://developer.wordpress.org/cli/commands/post-type/list/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/post-type/list/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/post-type/list/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-type-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-type-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/post-type/list/\#options)

\[--<field>=<value>\]Filter by one or more fields (see [get\_post\_types()](https://developer.wordpress.org/reference/functions/get_post_types/) first parameter for a list of available fields).\[--field=<field>\]Prints the value of a single field for each post type.\[--fields=<fields>\]Limit the output to specific post type fields.\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– json

– count

– yaml

—

### [Available Fields](https://developer.wordpress.org/cli/commands/post-type/list/\#available-fields)

These fields will be displayed by default for each post type:

- name
- label
- description
- hierarchical
- public
- capability\_type

These fields are optionally available:

- count

### [Examples](https://developer.wordpress.org/cli/commands/post-type/list/\#examples)

```
# List registered post types
$ wp post-type list --format=csv
name,label,description,hierarchical,public,capability_type
post,Posts,,,1,post
page,Pages,,1,1,page
attachment,Media,,,1,post
revision,Revisions,,,,post
nav_menu_item,"Navigation Menu Items",,,,post

# List post types with 'post' capability type
$ wp post-type list --capability_type=post --fields=name,public
+---------------+--------+
| name          | public |
+---------------+--------+
| post          | 1      |
| attachment    | 1      |
| revision      |        |
| nav_menu_item |        |
+---------------+--------+

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/post-type/list/\#global-parameters)

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