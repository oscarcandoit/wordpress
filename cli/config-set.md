---
url: https://developer.wordpress.org/cli/commands/config/set/
scraped_at: 2025-10-20T03:01:44.741Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/config/set/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp config set


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp config](https://developer.wordpress.org/cli/commands/config/)wp config set

Search

# [wp config set](https://developer.wordpress.org/cli/commands/config/set/)

Sets the value of a specific constant or variable defined in wp-config.php file.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/config/set/#options)
- [Examples](https://developer.wordpress.org/cli/commands/config/set/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/config/set/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/config/set/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/config-command)

[View Open Issues (2)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-set+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (8)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-set+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/config-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

### [Options](https://developer.wordpress.org/cli/commands/config/set/\#options)

<name>Name of the wp-config.php constant or variable.<value>Value to set the wp-config.php constant or variable to.\[--add\]Add the value if it doesn’t exist yet. This is the default behavior, override with –no-add.\[--raw\]Place the value into the wp-config.php file as is, instead of as a quoted string.\[--anchor=<anchor>\]Anchor string where additions of new values are anchored around. Defaults to “/\* That’s all, stop editing!”. The special case “EOF” string uses the end of the file as the anchor.\[--placement=<placement>\]Where to place the new values in relation to the anchor string.

—

default: ‘before’

options:

– before

– after

—

\[--separator=<separator>\]Separator string to put between an added value and its anchor string. The following escape sequences will be recognized and properly interpreted: ‘\\n’ => newline, ‘\\r’ => carriage return, ‘\\t’ => tab. Defaults to a single EOL (“\\n” on \*nix and “\\r\\n” on Windows).\[--type=<type>\]Type of the config value to set. Defaults to ‘all’.

—

default: all

options:

– constant

– variable

– all

—

\[--config-file=<path>\]Specify the file path to the config file to be modified. Defaults to the root of the WordPress installation and the filename “wp-config.php”.

### [Examples](https://developer.wordpress.org/cli/commands/config/set/\#examples)

```
# Set the WP_DEBUG constant to true.
$ wp config set WP_DEBUG true --raw
Success: Updated the constant 'WP_DEBUG' in the 'wp-config.php' file with the raw value 'true'.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/config/set/\#global-parameters)

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