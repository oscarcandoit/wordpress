---
url: https://developer.wordpress.org/cli/commands/config/delete/
scraped_at: 2025-10-20T03:01:26.442Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/config/delete/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp config delete


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp config](https://developer.wordpress.org/cli/commands/config/)wp config delete

Search

# [wp config delete](https://developer.wordpress.org/cli/commands/config/delete/)

Deletes a specific constant or variable from the wp-config.php file.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/config/delete/#options)
- [Examples](https://developer.wordpress.org/cli/commands/config/delete/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/config/delete/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/config/delete/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/config-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-delete+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-delete+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/config-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

### [Options](https://developer.wordpress.org/cli/commands/config/delete/\#options)

<name>Name of the wp-config.php constant or variable.\[--type=<type>\]Type of the config value to delete. Defaults to ‘all’.

—

default: all

options:

– constant

– variable

– all

—

\[--config-file=<path>\]Specify the file path to the config file to be modified. Defaults to the root of the WordPress installation and the filename “wp-config.php”.

### [Examples](https://developer.wordpress.org/cli/commands/config/delete/\#examples)

```
# Delete the COOKIE_DOMAIN constant from the wp-config.php file.
$ wp config delete COOKIE_DOMAIN
Success: Deleted the constant 'COOKIE_DOMAIN' from the 'wp-config.php' file.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/config/delete/\#global-parameters)

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