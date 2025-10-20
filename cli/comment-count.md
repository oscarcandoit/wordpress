---
url: https://developer.wordpress.org/cli/commands/comment/count/
scraped_at: 2025-10-20T02:59:12.939Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/comment/count/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp comment count


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp comment](https://developer.wordpress.org/cli/commands/comment/)wp comment count

Search

# [wp comment count](https://developer.wordpress.org/cli/commands/comment/count/)

Counts comments, on whole blog or on a given post.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/comment/count/#options)
- [Examples](https://developer.wordpress.org/cli/commands/comment/count/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/comment/count/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/comment/count/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment-count+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment-count+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/comment/count/\#options)

\[<post-id>\]The ID of the post to count comments in.

### [Examples](https://developer.wordpress.org/cli/commands/comment/count/\#examples)

```
# Count comments on whole blog.
$ wp comment count
approved:        33
spam:            3
trash:           1
post-trashed:    0
all:             34
moderated:       1
total_comments:  37

# Count comments in a post.
$ wp comment count 42
approved:        19
spam:            0
trash:           0
post-trashed:    0
all:             19
moderated:       0
total_comments:  19

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/comment/count/\#global-parameters)

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