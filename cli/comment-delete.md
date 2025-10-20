---
url: https://developer.wordpress.org/cli/commands/comment/delete/
scraped_at: 2025-10-20T02:59:17.354Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/comment/delete/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp comment delete


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp comment](https://developer.wordpress.org/cli/commands/comment/)wp comment delete

Search

# [wp comment delete](https://developer.wordpress.org/cli/commands/comment/delete/)

Deletes a comment.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/comment/delete/#options)
- [Examples](https://developer.wordpress.org/cli/commands/comment/delete/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/comment/delete/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/comment/delete/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment-delete+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment-delete+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/comment/delete/\#options)

<id>…One or more IDs of comments to delete.\[--force\]Skip the trash bin.

### [Examples](https://developer.wordpress.org/cli/commands/comment/delete/\#examples)

```
# Delete comment.
$ wp comment delete 1337 --force
Success: Deleted comment 1337.

# Delete multiple comments.
$ wp comment delete 1337 2341 --force
Success: Deleted comment 1337.
Success: Deleted comment 2341.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/comment/delete/\#global-parameters)

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