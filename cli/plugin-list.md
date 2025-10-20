---
url: https://developer.wordpress.org/cli/commands/plugin/list/
scraped_at: 2025-10-20T03:11:47.387Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/plugin/list/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp plugin list


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp plugin](https://developer.wordpress.org/cli/commands/plugin/)wp plugin list

Search

# [wp plugin list](https://developer.wordpress.org/cli/commands/plugin/list/)

Gets a list of plugins.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/plugin/list/#options)
- [Available Fields](https://developer.wordpress.org/cli/commands/plugin/list/#available-fields)
- [Examples](https://developer.wordpress.org/cli/commands/plugin/list/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/plugin/list/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/plugin/list/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/extension-command)

[View Open Issues (5)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (39)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/extension-command/issues/new)

Displays a list of the plugins installed on the site with activation status, whether or not there’s an update available, etc.

Use `--status=dropin` to list installed dropins (e.g. `object-cache.php`).

### [Options](https://developer.wordpress.org/cli/commands/plugin/list/\#options)

\[--<field>=<value>\]Filter results based on the value of a field.\[--field=<field>\]Prints the value of a single field for each plugin.\[--fields=<fields>\]Limit the output to specific object fields.\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– count

– json

– yaml

—

\[--status=<status>\]Filter the output by plugin status.

—

options:

– active

– active-network

– dropin

– inactive

– must-use

—

\[--skip-update-check\]If set, the plugin update check will be skipped.\[--recently-active\]If set, only recently active plugins will be shown and the status filter will be ignored.

### [Available Fields](https://developer.wordpress.org/cli/commands/plugin/list/\#available-fields)

These fields will be displayed by default for each plugin:

- name
- status
- update
- version
- update\_version
- auto\_update

These fields are optionally available:

- update\_package
- update\_id
- title
- description
- file
- author
- tested\_up\_to
- requires
- requires\_php
- wporg\_status
- wporg\_last\_updated

### [Examples](https://developer.wordpress.org/cli/commands/plugin/list/\#examples)

```
# List active plugins on the site.
$ wp plugin list --status=active --format=json
[{"name":"dynamic-hostname","status":"active","update":"none","version":"0.4.2","update_version":"","auto_update":"off"},{"name":"tinymce-templates","status":"active","update":"none","version":"4.8.1","update_version":"","auto_update":"off"},{"name":"wp-multibyte-patch","status":"active","update":"none","version":"2.9","update_version":"","auto_update":"off"},{"name":"wp-total-hacks","status":"active","update":"none","version":"4.7.2","update_version":"","auto_update":"off"}]

# List plugins on each site in a network.
$ wp site list --field=url | xargs -I % wp plugin list --url=%
+---------+----------------+-----------+---------+-----------------+------------+
| name    | status         | update    | version | update_version | auto_update |
+---------+----------------+-----------+---------+----------------+-------------+
| akismet | active-network | none      | 5.3.1   |                | on          |
| hello   | inactive       | available | 1.6     | 1.7.2          | off         |
+---------+----------------+-----------+---------+----------------+-------------+
+---------+----------------+-----------+---------+----------------+-------------+
| name    | status         | update    | version | update_version | auto_update |
+---------+----------------+-----------+---------+----------------+-------------+
| akismet | active-network | none      | 5.3.1   |                | on          |
| hello   | inactive       | available | 1.6     | 1.7.2          | off         |
+---------+----------------+-----------+---------+----------------+-------------+

# Check whether plugins are still active on WordPress.org
$ wp plugin list --fields=name,wporg_status,wporg_last_updated
+--------------------+--------------+--------------------+
| name               | wporg_status | wporg_last_updated |
+--------------------+--------------+--------------------+
| akismet            | active       | 2023-12-11         |
| user-switching     | active       | 2023-11-17         |
| wordpress-importer | active       | 2023-04-28         |
| local              |              |                    |
+--------------------+--------------+--------------------+

# List recently active plugins on the site.
$ wp plugin list --recently-active --field=name --format=json
["akismet","bbpress","buddypress"]

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/plugin/list/\#global-parameters)

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