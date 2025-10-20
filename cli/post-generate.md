---
url: https://developer.wordpress.org/cli/commands/post/generate/
scraped_at: 2025-10-20T03:13:33.774Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/post/generate/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp post generate


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp post](https://developer.wordpress.org/cli/commands/post/)wp post generate

Search

# [wp post generate](https://developer.wordpress.org/cli/commands/post/generate/)

Generates some posts.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/post/generate/#options)
- [Examples](https://developer.wordpress.org/cli/commands/post/generate/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/post/generate/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/post/generate/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-generate+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-generate+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

Creates a specified number of new posts with dummy data.

### [Options](https://developer.wordpress.org/cli/commands/post/generate/\#options)

\[--count=<number>\]How many posts to generate?

—

default: 100

—

\[--post\_type=<type>\]The type of the generated posts.

—

default: post

—

\[--post\_status=<status>\]The status of the generated posts.

—

default: publish

—

\[--post\_title=<post\_title>\]The post title.

—

default:

—

\[--post\_author=<login>\]The author of the generated posts.

—

default:

—

\[--post\_date=<yyyy-mm-dd-hh-ii-ss>\]The date of the post. Default is the current time.\[--post\_date\_gmt=<yyyy-mm-dd-hh-ii-ss>\]The date of the post in the GMT timezone. Default is the value of –post\_date.\[--post\_content\]If set, the command reads the post\_content from STDIN.\[--max\_depth=<number>\]For hierarchical post types, generate child posts down to a certain depth.

—

default: 1

—

\[--format=<format>\]Render output in a particular format.

—

default: progress

options:

– progress

– ids

—

### [Examples](https://developer.wordpress.org/cli/commands/post/generate/\#examples)

```
# Generate posts.
$ wp post generate --count=10 --post_type=page --post_date=1999-01-04
Generating posts  100% [================================================] 0:01 / 0:04

# Generate posts with fetched content.
$ curl -N https://loripsum.net/api/5 | wp post generate --post_content --count=10
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  2509  100  2509    0     0    616      0  0:00:04  0:00:04 --:--:--   616
Generating posts  100% [================================================] 0:01 / 0:04

# Add meta to every generated posts.
$ wp post generate --format=ids | xargs -d ' ' -I % wp post meta add % foo bar
Success: Added custom field.
Success: Added custom field.
Success: Added custom field.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/post/generate/\#global-parameters)

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