---
url: https://developer.wordpress.org/cli/commands/option/list/
scraped_at: 2025-10-20T03:09:42.563Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/option/list/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp option list


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp option](https://developer.wordpress.org/cli/commands/option/)wp option list

Search

# [wp option list](https://developer.wordpress.org/cli/commands/option/list/)

Lists options and their values.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/option/list/#options)
- [Available Fields](https://developer.wordpress.org/cli/commands/option/list/#available-fields)
- [Examples](https://developer.wordpress.org/cli/commands/option/list/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/option/list/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/option/list/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/option/list/\#options)

\[--search=<pattern>\]Use wildcards ( \* and ? ) to match option name.\[--exclude=<pattern>\]Pattern to exclude. Use wildcards ( \* and ? ) to match option name.\[--autoload=<value>\]Match only autoload options when value is on, and only not-autoload option when off.\[--transients\]List only transients. Use `--no-transients` to ignore all transients.\[--unserialize\]Unserialize option values in output.\[--field=<field>\]Prints the value of a single field.\[--fields=<fields>\]Limit the output to specific object fields.\[--format=<format>\]The serialization format for the value. total\_bytes displays the total size of matching options in bytes.

—

default: table

options:

– table

– json

– csv

– count

– yaml

– total\_bytes

—

\[--orderby=<fields>\]Set orderby which field.

—

default: option\_id

options:

– option\_id

– option\_name

– option\_value

—

\[--order=<order>\]Set ascending or descending order.

—

default: asc

options:

– asc

– desc

—

### [Available Fields](https://developer.wordpress.org/cli/commands/option/list/\#available-fields)

This field will be displayed by default for each matching option:

- option\_name
- option\_value

These fields are optionally available:

- autoload
- size\_bytes

### [Examples](https://developer.wordpress.org/cli/commands/option/list/\#examples)

```
# Get the total size of all autoload options.
$ wp option list --autoload=on --format=total_bytes
33198

# Find biggest transients.
$ wp option list --search="*_transient_*" --fields=option_name,size_bytes | sort -n -k 2 | tail
option_name size_bytes
_site_transient_timeout_theme_roots 10
_site_transient_theme_roots 76
_site_transient_update_themes   181
_site_transient_update_core 808
_site_transient_update_plugins  6645

# List all options beginning with "i2f_".
$ wp option list --search="i2f_*"
+-------------+--------------+
| option_name | option_value |
+-------------+--------------+
| i2f_version | 0.1.0        |
+-------------+--------------+

# Delete all options beginning with "theme_mods_".
$ wp option list --search="theme_mods_*" --field=option_name | xargs -I % wp option delete %
Success: Deleted 'theme_mods_twentysixteen' option.
Success: Deleted 'theme_mods_twentyfifteen' option.
Success: Deleted 'theme_mods_twentyfourteen' option.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/option/list/\#global-parameters)

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