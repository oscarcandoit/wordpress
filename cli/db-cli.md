---
url: https://developer.wordpress.org/cli/commands/db/cli/
scraped_at: 2025-10-20T03:04:18.233Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/db/cli/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp db cli


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp db](https://developer.wordpress.org/cli/commands/db/)wp db cli

Search

# [wp db cli](https://developer.wordpress.org/cli/commands/db/cli/)

Opens a MySQL console using credentials from wp-config.php

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/db/cli/#options)
- [Examples](https://developer.wordpress.org/cli/commands/db/cli/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/db/cli/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/db/cli/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/db-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-cli+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-cli+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/db-command/issues/new)

This command runs on the `after_wp_config_load` hook, after wp-config.php has been loaded into scope.

### [Options](https://developer.wordpress.org/cli/commands/db/cli/\#options)

\[--database=<database>\]Use a specific database. Defaults to DB\_NAME.\[--default-character-set=<character-set>\]Use a specific character set. Defaults to DB\_CHARSET when defined.\[--dbuser=<value>\]Username to pass to mysql. Defaults to DB\_USER.\[--dbpass=<value>\]Password to pass to mysql. Defaults to DB\_PASSWORD.\[--<field>=<value>\]Extra arguments to pass to mysql. [Refer to mysql docs](https://dev.mysql.com/doc/en/mysql-command-options.html).\[--defaults\]Loads the environment’s MySQL option files. Default behavior is to skip loading them to avoid failures due to misconfiguration.

### [Examples](https://developer.wordpress.org/cli/commands/db/cli/\#examples)

```
# Open MySQL console
$ wp db cli
mysql&gt;

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/db/cli/\#global-parameters)

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