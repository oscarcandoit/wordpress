---
url: https://developer.wordpress.org/cli/commands/scaffold/taxonomy/
scraped_at: 2025-10-20T03:15:15.246Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp scaffold taxonomy


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp scaffold](https://developer.wordpress.org/cli/commands/scaffold/)wp scaffold taxonomy

Search

# [wp scaffold taxonomy](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/)

Generates PHP code for registering a custom taxonomy.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/#options)
- [Examples](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/scaffold-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Ascaffold-taxonomy+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Ascaffold-taxonomy+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/scaffold-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/\#options)

<slug>The internal name of the taxonomy.\[--post\_types=<post-types>\]Post types to register for use with the taxonomy.\[--label=<label>\]The text used to translate the update messages.\[--textdomain=<textdomain>\]The textdomain to use for the labels.\[--theme\]Create a file in the active theme directory, instead of sending to STDOUT. Specify a theme with `--theme=&lt;theme&gt;` to have the file placed in that theme.\[--plugin=<plugin>\]Create a file in the given plugin’s directory, instead of sending to STDOUT.\[--raw\]Just generate the `register_taxonomy()` call and nothing else.\[--force\]Overwrite files that already exist.

### [Examples](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/\#examples)

```
# Generate PHP code for registering a custom taxonomy and save in a file
$ wp scaffold taxonomy venue --post_types=event,presentation > taxonomy.php

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/\#global-parameters)

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