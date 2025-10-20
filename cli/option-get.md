---
url: https://developer.wordpress.org/cli/commands/option/get/
scraped_at: 2025-10-20T03:09:40.288Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/option/get/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp option get


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp option](https://developer.wordpress.org/cli/commands/option/)wp option get

Search

# [wp option get](https://developer.wordpress.org/cli/commands/option/get/)

Gets the value for an option.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/option/get/#options)
- [Examples](https://developer.wordpress.org/cli/commands/option/get/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/option/get/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/option/get/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption-get+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption-get+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/option/get/\#options)

<key>Key for the option.\[--format=<format>\]Get value in a particular format.

—

default: var\_export

options:

– var\_export

– json

– yaml

—

### [Examples](https://developer.wordpress.org/cli/commands/option/get/\#examples)

```
# Get option.
$ wp option get home
http://example.com

# Get blog description.
$ wp option get blogdescription
A random blog description

# Get blog name
$ wp option get blogname
A random blog name

# Get admin email.
$ wp option get admin_email
someone@example.com

# Get option in JSON format.
$ wp option get active_plugins --format=json
{"0":"dynamically-dynamic-sidebar\/dynamically-dynamic-sidebar.php","1":"monster-widget\/monster-widget.php","2":"show-current-template\/show-current-template.php","3":"theme-check\/theme-check.php","5":"wordpress-importer\/wordpress-importer.php"}

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/option/get/\#global-parameters)

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