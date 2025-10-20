---
url: https://developer.wordpress.org/cli/commands/comment/create/
scraped_at: 2025-10-20T02:59:15.441Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/comment/create/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp comment create


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp comment](https://developer.wordpress.org/cli/commands/comment/)wp comment create

Search

# [wp comment create](https://developer.wordpress.org/cli/commands/comment/create/)

Creates a new comment.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/comment/create/#options)
- [Examples](https://developer.wordpress.org/cli/commands/comment/create/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/comment/create/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/comment/create/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment-create+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment-create+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/comment/create/\#options)

\[--<field>=<value>\]Associative args for the new comment. See [wp\_insert\_comment()](https://developer.wordpress.org/reference/functions/wp_insert_comment/) .\[--porcelain\]Output just the new comment id.

### [Examples](https://developer.wordpress.org/cli/commands/comment/create/\#examples)

```
# Create comment.
$ wp comment create --comment_post_ID=15 --comment_content="hello blog" --comment_author="wp-cli"
Success: Created comment 932.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/comment/create/\#global-parameters)

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