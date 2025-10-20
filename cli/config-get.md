---
url: https://developer.wordpress.org/cli/commands/config/get/
scraped_at: 2025-10-20T03:01:30.690Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/config/get/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp config get


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp config](https://developer.wordpress.org/cli/commands/config/)wp config get

Search

# [wp config get](https://developer.wordpress.org/cli/commands/config/get/)

Gets the value of a specific constant or variable defined in wp-config.php file.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/config/get/#options)
- [Examples](https://developer.wordpress.org/cli/commands/config/get/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/config/get/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/config/get/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/config-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-get+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-get+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/config-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

### [Options](https://developer.wordpress.org/cli/commands/config/get/\#options)

<name>Name of the wp-config.php constant or variable.\[--type=<type>\]Type of config value to retrieve. Defaults to ‘all’.

—

default: all

options:

– constant

– variable

– all

—

\[--format=<format>\]Get value in a particular format. Dotenv is limited to non-object values.

—

default: var\_export

options:

– var\_export

– json

– yaml

– dotenv

—

\[--config-file=<path>\]Specify the file path to the config file to be read. Defaults to the root of the WordPress installation and the filename “wp-config.php”.

### [Examples](https://developer.wordpress.org/cli/commands/config/get/\#examples)

```
# Get the table_prefix as defined in wp-config.php file.
$ wp config get table_prefix
wp_

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/config/get/\#global-parameters)

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