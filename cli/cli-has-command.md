---
url: https://developer.wordpress.org/cli/commands/cli/has-command/
scraped_at: 2025-10-20T02:58:56.539Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cli/has-command/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cli has-command


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp cli](https://developer.wordpress.org/cli/commands/cli/)wp cli has-command

Search

# [wp cli has-command](https://developer.wordpress.org/cli/commands/cli/has-command/)

Detects if a command exists

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/cli/has-command/#options)
- [Examples](https://developer.wordpress.org/cli/commands/cli/has-command/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/cli/has-command/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cli/has-command/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/wp-cli)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acli-has-command+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acli-has-command+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/wp-cli/issues/new)

This commands checks if a command is registered with WP-CLI. If the command is found then it returns with exit status 0. If the command doesn’t exist, then it will exit with status 1.

### [Options](https://developer.wordpress.org/cli/commands/cli/has-command/\#options)

<command\_name>…The command

### [Examples](https://developer.wordpress.org/cli/commands/cli/has-command/\#examples)

```
# The "site delete" command is registered.
$ wp cli has-command "site delete"
$ echo $?
0

# The "foo bar" command is not registered.
$ wp cli has-command "foo bar"
$ echo $?
1

# Install a WP-CLI package if not already installed
$ if ! $(wp cli has-command doctor); then wp package install wp-cli/doctor-command; fi
Installing package wp-cli/doctor-command (dev-main || dev-master || dev-trunk)
Updating /home/person/.wp-cli/packages/composer.json to require the package...
Using Composer to install the package...
---
Success: Package installed.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/cli/has-command/\#global-parameters)

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