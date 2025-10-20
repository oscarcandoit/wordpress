---
url: https://developer.wordpress.org/cli/commands/cron/event/list/
scraped_at: 2025-10-20T03:02:43.273Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cron/event/list/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cron event list


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp cron](https://developer.wordpress.org/cli/commands/cron/)[wp cron event](https://developer.wordpress.org/cli/commands/cron/event/)wp cron event list

Search

# [wp cron event list](https://developer.wordpress.org/cli/commands/cron/event/list/)

Lists scheduled cron events.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/cron/event/list/#options)
- [Available Fields](https://developer.wordpress.org/cli/commands/cron/event/list/#available-fields)
- [Examples](https://developer.wordpress.org/cli/commands/cron/event/list/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/cron/event/list/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cron/event/list/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/cron-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-event-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (8)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-event-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/cron-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/cron/event/list/\#options)

\[--fields=<fields>\]Limit the output to specific object fields.\[--<field>=<value>\]Filter by one or more fields.\[--field=<field>\]Prints the value of a single field for each event.\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– ids

– json

– count

– yaml

—

### [Available Fields](https://developer.wordpress.org/cli/commands/cron/event/list/\#available-fields)

These fields will be displayed by default for each cron event:
\\* hook
\\* next\_run\_gmt
\\* next\_run\_relative
\\* recurrence

These fields are optionally available:
\\* time
\\* sig
\\* args
\\* schedule
\\* interval
\\* next\_run

### [Examples](https://developer.wordpress.org/cli/commands/cron/event/list/\#examples)

```
# List scheduled cron events
$ wp cron event list
+-------------------+---------------------+---------------------+------------+
| hook              | next_run_gmt        | next_run_relative   | recurrence |
+-------------------+---------------------+---------------------+------------+
| wp_version_check  | 2016-05-31 22:15:13 | 11 hours 57 minutes | 12 hours   |
| wp_update_plugins | 2016-05-31 22:15:13 | 11 hours 57 minutes | 12 hours   |
| wp_update_themes  | 2016-05-31 22:15:14 | 11 hours 57 minutes | 12 hours   |
+-------------------+---------------------+---------------------+------------+

# List scheduled cron events in JSON
$ wp cron event list --fields=hook,next_run --format=json
[{"hook":"wp_version_check","next_run":"2016-05-31 10:15:13"},{"hook":"wp_update_plugins","next_run":"2016-05-31 10:15:13"},{"hook":"wp_update_themes","next_run":"2016-05-31 10:15:14"}]

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/cron/event/list/\#global-parameters)

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