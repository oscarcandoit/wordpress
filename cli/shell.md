---
url: https://developer.wordpress.org/cli/commands/shell/
scraped_at: 2025-10-20T03:15:44.810Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/shell/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp shell


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp shell

Search

# [wp shell](https://developer.wordpress.org/cli/commands/shell/)

Opens an interactive PHP console for running and testing PHP code.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/shell/#options)
- [Examples](https://developer.wordpress.org/cli/commands/shell/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/shell/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/shell/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/shell-command)

[View Open Issues (4)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Ashell+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (25)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Ashell+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/shell-command/issues/new)

`wp shell` allows you to evaluate PHP statements and expressions interactively, from within a WordPress environment. Type a bit of code, hit enter, and see the code execute right before you. Because WordPress is loaded, you have access to all the functions, classes and globals that you can use within a WordPress plugin, for example.

### [Options](https://developer.wordpress.org/cli/commands/shell/\#options)

\[--basic\]Force the use of WP-CLI’s built-in PHP REPL, even if the Boris or PsySH PHP REPLs are available.

### [Examples](https://developer.wordpress.org/cli/commands/shell/\#examples)

```
# Call get_bloginfo() to get the name of the site.
$ wp shell
wp> get_bloginfo( 'name' );
=> string(6) "WP-CLI"

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/shell/\#global-parameters)

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