---
url: https://developer.wordpress.org/cli/commands/rewrite/flush/
scraped_at: 2025-10-20T03:14:37.128Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/rewrite/flush/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp rewrite flush


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp rewrite](https://developer.wordpress.org/cli/commands/rewrite/)wp rewrite flush

Search

# [wp rewrite flush](https://developer.wordpress.org/cli/commands/rewrite/flush/)

Flushes rewrite rules.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/rewrite/flush/#options)
- [Examples](https://developer.wordpress.org/cli/commands/rewrite/flush/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/rewrite/flush/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/rewrite/flush/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/rewrite-command)

[View Open Issues (2)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Arewrite-flush+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (8)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Arewrite-flush+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/rewrite-command/issues/new)

Resets WordPress’ rewrite rules based on registered post types, etc.

To regenerate a .htaccess file with WP-CLI, you’ll need to add the mod\_rewrite module to your wp-cli.yml or config.yml. For example:

```
apache_modules:
  - mod_rewrite

```

### [Options](https://developer.wordpress.org/cli/commands/rewrite/flush/\#options)

\[--hard\]Perform a hard flush – update `.htaccess` rules as well as rewrite rules in database. Works only on single site installs.

### [Examples](https://developer.wordpress.org/cli/commands/rewrite/flush/\#examples)

```
$ wp rewrite flush
Success: Rewrite rules flushed.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/rewrite/flush/\#global-parameters)

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