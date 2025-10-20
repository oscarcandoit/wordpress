---
url: https://developer.wordpress.org/cli/commands/cron/test/
scraped_at: 2025-10-20T03:04:03.310Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cron/test/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cron test


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp cron](https://developer.wordpress.org/cli/commands/cron/)wp cron test

Search

# [wp cron test](https://developer.wordpress.org/cli/commands/cron/test/)

Tests the WP Cron spawning system and reports back its status.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/cron/test/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/cron/test/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cron/test/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/cron-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-test+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (4)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-test+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/cron-command/issues/new)

This command tests the spawning system by performing the following steps:

- Checks to see if the `DISABLE_WP_CRON` constant is set; errors if true because WP-Cron is disabled.
- Checks to see if the `ALTERNATE_WP_CRON` constant is set; warns if true.
- Attempts to spawn WP-Cron over HTTP; warns if non 200 response code is returned.

### [Examples](https://developer.wordpress.org/cli/commands/cron/test/\#examples)

```
# Cron test runs successfully.
$ wp cron test
Success: WP-Cron spawning is working as expected.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/cron/test/\#global-parameters)

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