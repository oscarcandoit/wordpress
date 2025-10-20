---
url: https://developer.wordpress.org/cli/commands/export/
scraped_at: 2025-10-20T03:05:55.788Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/export/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp export


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp export

Search

# [wp export](https://developer.wordpress.org/cli/commands/export/)

Exports WordPress content to a WXR file.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/export/#options)
- [Filters](https://developer.wordpress.org/cli/commands/export/#filters)
- [Examples](https://developer.wordpress.org/cli/commands/export/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/export/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/export/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/export-command)

[View Open Issues (6)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aexport+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (72)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aexport+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/export-command/issues/new)

Generates one or more WXR files containing authors, terms, posts, comments, and attachments. WXR files do not include site configuration (options) or the attachment files themselves.

### [Options](https://developer.wordpress.org/cli/commands/export/\#options)

\[--dir=<dirname>\]Full path to directory where WXR export files should be stored. Defaults to current working directory.\[--stdout\]Output the whole XML using standard output (incompatible with –dir=)\[--skip\_comments\]Don’t include comments in the WXR export file.\[--max\_file\_size=<MB>\]A single export file should have this many megabytes. -1 for unlimited.

—

default: 15

—

\[--filename\_format=<format>\]Use a custom format for export filenames. Defaults to ‘{site}.wordpress.{date}.{n}.xml’.\[--include\_once=<before\_posts>\]Include specified export section only in the first export file. Valid options are categories, tags, nav\_menu\_items, custom\_taxonomies\_terms. Separate multiple sections with a comma. Defaults to none.\[--allow\_orphan\_terms\]Export orphaned terms with `parent=0`, instead of throwing an exception.

### [Filters](https://developer.wordpress.org/cli/commands/export/\#filters)

\[--start\_date=<date>\]Export only posts published after this date, in format YYYY-MM-DD.\[--end\_date=<date>\]Export only posts published before this date, in format YYYY-MM-DD.\[--post\_type=<post-type>\]Export only posts with this post\_type. Separate multiple post types with a comma.

—

default: any

—

\[--post\_type\_\_not\_in=<post-type>\]Export all post types except those identified. Separate multiple post types with a comma. Defaults to none.\[--post\_\_in=<pid>\]Export all posts specified as a comma-separated or space-separated list of IDs. Post’s attachments won’t be exported unless –with\_attachments is specified.\[--with\_attachments\]Force including attachments in case –post\_\_in has been specified.\[--start\_id=<pid>\]Export only posts with IDs greater than or equal to this post ID.\[--max\_num\_posts=<num>\]Export no more than <num> posts (excluding attachments).\[--author=<author>\]Export only posts by this author. Can be either user login or user ID.\[--category=<name\|id>\]Export only posts in this category.\[--post\_status=<status>\]Export only posts with this status.

### [Examples](https://developer.wordpress.org/cli/commands/export/\#examples)

```
# Export posts published by the user between given start and end date
$ wp export --dir=/tmp/ --user=admin --post_type=post --start_date=2011-01-01 --end_date=2011-12-31
Starting export process...
Writing to file /tmp/staging.wordpress.2016-05-24.000.xml
Success: All done with export.

# Export posts by IDs
$ wp export --dir=/tmp/ --post__in=123,124,125
Starting export process...
Writing to file /tmp/staging.wordpress.2016-05-24.000.xml
Success: All done with export.

# Export a random subset of content
$ wp export --post__in="$(wp post list --post_type=post --orderby=rand --posts_per_page=8 --format=ids)"
Starting export process...
Writing to file /var/www/example.com/public_html/staging.wordpress.2016-05-24.000.xml
Success: All done with export.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/export/\#global-parameters)

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