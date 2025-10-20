---
url: https://developer.wordpress.org/cli/commands/eval-file/
scraped_at: 2025-10-20T03:05:53.745Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/eval-file/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp eval-file


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp eval-file

Search

# [wp eval-file](https://developer.wordpress.org/cli/commands/eval-file/)

Loads and executes a PHP file.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/eval-file/#options)
- [Global Parameters](https://developer.wordpress.org/cli/commands/eval-file/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/eval-file/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/eval-command)

[View Open Issues (2)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aeval-file+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (13)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aeval-file+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/eval-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

Note: because code is executed within a method, global variables need to be explicitly globalized.

### [Options](https://developer.wordpress.org/cli/commands/eval-file/\#options)

<file>The path to the PHP file to execute. Use ‘-‘ to run code from STDIN.\[<arg>…\]One or more positional arguments to pass to the file. They are placed in the $args variable.\[--skip-wordpress\]Load and execute file without loading WordPress.\[--use-include\]Process the provided file via include instead of evaluating its contents.

### [Global Parameters](https://developer.wordpress.org/cli/commands/eval-file/\#global-parameters)

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