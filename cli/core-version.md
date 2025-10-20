---
url: https://developer.wordpress.org/cli/commands/core/version/
scraped_at: 2025-10-20T03:02:26.159Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/core/version/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp core version


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp core](https://developer.wordpress.org/cli/commands/core/)wp core version

Search

# [wp core version](https://developer.wordpress.org/cli/commands/core/version/)

Displays the WordPress version.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/core/version/#options)
- [Examples](https://developer.wordpress.org/cli/commands/core/version/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/core/version/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/core/version/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/core-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore-version+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore-version+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/core-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

### [Options](https://developer.wordpress.org/cli/commands/core/version/\#options)

\[--extra\]Show extended version information.

### [Examples](https://developer.wordpress.org/cli/commands/core/version/\#examples)

```
# Display the WordPress version
$ wp core version
4.5.2

# Display WordPress version along with other information
$ wp core version --extra
WordPress version: 4.5.2
Database revision: 36686
TinyMCE version:   4.310 (4310-20160418)
Package language:  en_US

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/core/version/\#global-parameters)

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