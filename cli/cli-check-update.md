---
url: https://developer.wordpress.org/cli/commands/cli/check-update/
scraped_at: 2025-10-20T02:58:50.265Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cli/check-update/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cli check-update


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp cli](https://developer.wordpress.org/cli/commands/cli/)wp cli check-update

Search

# [wp cli check-update](https://developer.wordpress.org/cli/commands/cli/check-update/)

Checks to see if there is a newer version of WP-CLI available.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/cli/check-update/#options)
- [Examples](https://developer.wordpress.org/cli/commands/cli/check-update/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/cli/check-update/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cli/check-update/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/wp-cli)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acli-check-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acli-check-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/wp-cli/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

Queries the GitHub releases API. Returns available versions if there are updates available, or success message if using the latest release.

### [Options](https://developer.wordpress.org/cli/commands/cli/check-update/\#options)

\[--patch\]Only list patch updates.\[--minor\]Only list minor updates.\[--major\]Only list major updates.\[--field=<field>\]Prints the value of a single field for each update.\[--fields=<fields>\]Limit the output to specific object fields. Defaults to version,update\_type,package\_url,status,requires\_php.\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– json

– count

– yaml

—

### [Examples](https://developer.wordpress.org/cli/commands/cli/check-update/\#examples)

```
# Check for update.
$ wp cli check-update
Success: WP-CLI is at the latest version.

# Check for update and new version is available.
$ wp cli check-update
+---------+-------------+-------------------------------------------------------------------------------+
| version | update_type | package_url                                                                   |
+---------+-------------+-------------------------------------------------------------------------------+
| 0.24.1  | patch       | https://github.com/wp-cli/wp-cli/releases/download/v0.24.1/wp-cli-0.24.1.phar |
+---------+-------------+-------------------------------------------------------------------------------+

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/cli/check-update/\#global-parameters)

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