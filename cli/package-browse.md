---
url: https://developer.wordpress.org/cli/commands/package/browse/
scraped_at: 2025-10-20T03:09:52.793Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/package/browse/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp package browse


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp package](https://developer.wordpress.org/cli/commands/package/)wp package browse

Search

# [wp package browse](https://developer.wordpress.org/cli/commands/package/browse/)

Browses WP-CLI packages available for installation.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/package/browse/#options)
- [Available Fields](https://developer.wordpress.org/cli/commands/package/browse/#available-fields)
- [Examples](https://developer.wordpress.org/cli/commands/package/browse/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/package/browse/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/package/browse/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/package-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apackage-browse+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apackage-browse+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/package-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

Lists packages available for installation from the [Package Index](http://wp-cli.org/package-index/). Although the package index will remain in place for backward compatibility reasons, it has been deprecated and will not be updated further. Please refer to https://github.com/wp-cli/ideas/issues/51 to read about its potential replacement.

### [Options](https://developer.wordpress.org/cli/commands/package/browse/\#options)

\[--fields=<fields>\]Limit the output to specific fields. Defaults to all fields.\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– ids

– json

– yaml

—

### [Available Fields](https://developer.wordpress.org/cli/commands/package/browse/\#available-fields)

These fields will be displayed by default for each package:

- name
- description
- authors
- version

There are no optionally available fields.

### [Examples](https://developer.wordpress.org/cli/commands/package/browse/\#examples)

```
$ wp package browse --format=yaml
---
10up/mu-migration:
  name: 10up/mu-migration
  description: A set of WP-CLI commands to support the migration of single WordPress instances to multisite
  authors: Nícholas André
  version: dev-main, dev-develop
aaemnnosttv/wp-cli-dotenv-command:
  name: aaemnnosttv/wp-cli-dotenv-command
  description: Dotenv commands for WP-CLI
  authors: Evan Mattson
  version: v0.1, v0.1-beta.1, v0.2, dev-main, dev-dev, dev-develop, dev-tests/behat
aaemnnosttv/wp-cli-http-command:
  name: aaemnnosttv/wp-cli-http-command
  description: WP-CLI command for using the WordPress HTTP API
  authors: Evan Mattson
  version: dev-main

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/package/browse/\#global-parameters)

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