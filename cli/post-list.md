---
url: https://developer.wordpress.org/cli/commands/post/list/
scraped_at: 2025-10-20T03:13:39.420Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/post/list/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp post list


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp post](https://developer.wordpress.org/cli/commands/post/)wp post list

Search

# [wp post list](https://developer.wordpress.org/cli/commands/post/list/)

Gets a list of posts.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/post/list/#options)
- [Available Fields](https://developer.wordpress.org/cli/commands/post/list/#available-fields)
- [Examples](https://developer.wordpress.org/cli/commands/post/list/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/post/list/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/post/list/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (14)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

Display posts based on all arguments supported by [WP\_Query()](https://developer.wordpress.org/reference/classes/wp_query/). Only shows post types marked as post by default.

### [Options](https://developer.wordpress.org/cli/commands/post/list/\#options)

\[--<field>=<value>\]One or more args to pass to [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/).\[--field=<field>\]Prints the value of a single field for each post.\[--fields=<fields>\]Limit the output to specific object fields.\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– ids

– json

– count

– yaml

—

### [Available Fields](https://developer.wordpress.org/cli/commands/post/list/\#available-fields)

These fields will be displayed by default for each post:

- ID
- post\_title
- post\_name
- post\_date
- post\_status

These fields are optionally available:

- post\_author
- post\_date\_gmt
- post\_content
- post\_excerpt
- comment\_status
- ping\_status
- post\_password
- to\_ping
- pinged
- post\_modified
- post\_modified\_gmt
- post\_content\_filtered
- post\_parent
- guid
- menu\_order
- post\_type
- post\_mime\_type
- comment\_count
- filter
- url

### [Examples](https://developer.wordpress.org/cli/commands/post/list/\#examples)

```
# List post
$ wp post list --field=ID
568
829
1329
1695

# List posts in JSON
$ wp post list --post_type=post --posts_per_page=5 --format=json
[{"ID":1,"post_title":"Hello world!","post_name":"hello-world","post_date":"2015-06-20 09:00:10","post_status":"publish"},{"ID":1178,"post_title":"Markup: HTML Tags and Formatting","post_name":"markup-html-tags-and-formatting","post_date":"2013-01-11 20:22:19","post_status":"draft"}]

# List all pages
$ wp post list --post_type=page --fields=post_title,post_status
+-------------+-------------+
| post_title  | post_status |
+-------------+-------------+
| Sample Page | publish     |
+-------------+-------------+

# List ids of all pages and posts
$ wp post list --post_type=page,post --format=ids
15 25 34 37 198

# List given posts
$ wp post list --post__in=1,3
+----+--------------+-------------+---------------------+-------------+
| ID | post_title   | post_name   | post_date           | post_status |
+----+--------------+-------------+---------------------+-------------+
| 3  | Lorem Ipsum  | lorem-ipsum | 2016-06-01 14:34:36 | publish     |
| 1  | Hello world! | hello-world | 2016-06-01 14:31:12 | publish     |
+----+--------------+-------------+---------------------+-------------+

# List given post by a specific author
$ wp post list --author=2
+----+-------------------+-------------------+---------------------+-------------+
| ID | post_title        | post_name         | post_date           | post_status |
+----+-------------------+-------------------+---------------------+-------------+
| 14 | New documentation | new-documentation | 2021-06-18 21:05:11 | publish     |
+----+-------------------+-------------------+---------------------+-------------+

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/post/list/\#global-parameters)

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