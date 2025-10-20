---
url: https://developer.wordpress.org/cli/commands/plugin/get/
scraped_at: 2025-10-20T03:11:37.792Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/plugin/get/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp plugin get


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp plugin](https://developer.wordpress.org/cli/commands/plugin/)wp plugin get

Search

# [wp plugin get](https://developer.wordpress.org/cli/commands/plugin/get/)

Gets details about an installed plugin.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/plugin/get/#options)
- [Available Fields](https://developer.wordpress.org/cli/commands/plugin/get/#available-fields)
- [Examples](https://developer.wordpress.org/cli/commands/plugin/get/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/plugin/get/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/plugin/get/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/extension-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-get+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-get+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/extension-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/plugin/get/\#options)

<plugin>The plugin to get.\[--field=<field>\]Instead of returning the whole plugin, returns the value of a single field.\[--fields=<fields>\]Limit the output to specific fields. Defaults to all fields.\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– json

– yaml

—

### [Available Fields](https://developer.wordpress.org/cli/commands/plugin/get/\#available-fields)

These fields will be displayed by default for the plugin:

- name
- title
- author
- version
- description
- status

These fields are optionally available:

- requires\_wp
- requires\_php
- requires\_plugins

### [Examples](https://developer.wordpress.org/cli/commands/plugin/get/\#examples)

```
# Get plugin details.
$ wp plugin get bbpress --format=json
{"name":"bbpress","title":"bbPress","author":"The bbPress Contributors","version":"2.6.9","description":"bbPress is forum software with a twist from the creators of WordPress.","status":"active"}

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/plugin/get/\#global-parameters)

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