---
url: https://developer.wordpress.org/cli/commands/cron/event/schedule/
scraped_at: 2025-10-20T03:02:58.220Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cron/event/schedule/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cron event schedule


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp cron](https://developer.wordpress.org/cli/commands/cron/)[wp cron event](https://developer.wordpress.org/cli/commands/cron/event/)wp cron event schedule

Search

# [wp cron event schedule](https://developer.wordpress.org/cli/commands/cron/event/schedule/)

Schedules a new cron event.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/cron/event/schedule/#options)
- [Examples](https://developer.wordpress.org/cli/commands/cron/event/schedule/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/cron/event/schedule/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cron/event/schedule/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/cron-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-event-schedule+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (2)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-event-schedule+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/cron-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/cron/event/schedule/\#options)

<hook>The hook name.\[<next-run>\]A Unix timestamp or an English textual datetime description compatible with `strtotime()`. Defaults to now.\[<recurrence>\]How often the event should recur. See `wp cron schedule list` for available schedule names. Defaults to no recurrence.\[--<field>=<value>\]Arguments to pass to the hook for the event. <field> should be a numeric key, not a string.

### [Examples](https://developer.wordpress.org/cli/commands/cron/event/schedule/\#examples)

```
# Schedule a new cron event
$ wp cron event schedule cron_test
Success: Scheduled event with hook 'cron_test' for 2016-05-31 10:19:16 GMT.

# Schedule new cron event with hourly recurrence
$ wp cron event schedule cron_test now hourly
Success: Scheduled event with hook 'cron_test' for 2016-05-31 10:20:32 GMT.

# Schedule new cron event and pass arguments
$ wp cron event schedule cron_test '+1 hour' --0=first-argument --1=second-argument
Success: Scheduled event with hook 'cron_test' for 2016-05-31 11:21:35 GMT.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/cron/event/schedule/\#global-parameters)

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