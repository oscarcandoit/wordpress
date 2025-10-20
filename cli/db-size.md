---
url: https://developer.wordpress.org/cli/commands/db/size/
scraped_at: 2025-10-20T03:04:48.955Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/db/size/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp db size


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp db](https://developer.wordpress.org/cli/commands/db/)wp db size

Search

# [wp db size](https://developer.wordpress.org/cli/commands/db/size/)

Displays the database name and size.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/db/size/#options)
- [Examples](https://developer.wordpress.org/cli/commands/db/size/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/db/size/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/db/size/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/db-command)

[View Open Issues (2)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-size+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (24)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-size+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/db-command/issues/new)

Display the database name and size for `DB_NAME` specified in wp-config.php. The size defaults to a human-readable number.

Available size formats include:
\\* b (bytes)
\\* kb (kilobytes)
\\* mb (megabytes)
\\* gb (gigabytes)
\\* tb (terabytes)
\\* B (ISO Byte setting, with no conversion)
\\* KB (ISO Kilobyte setting, with 1 KB = 1,000 B)
\\* KiB (ISO Kibibyte setting, with 1 KiB = 1,024 B)
\\* MB (ISO Megabyte setting, with 1 MB = 1,000 KB)
\\* MiB (ISO Mebibyte setting, with 1 MiB = 1,024 KiB)
\\* GB (ISO Gigabyte setting, with 1 GB = 1,000 MB)
\\* GiB (ISO Gibibyte setting, with 1 GiB = 1,024 MiB)
\\* TB (ISO Terabyte setting, with 1 TB = 1,000 GB)
\\* TiB (ISO Tebibyte setting, with 1 TiB = 1,024 GiB)

### [Options](https://developer.wordpress.org/cli/commands/db/size/\#options)

\[--size\_format=<format>\]Display the database size only, as a bare number.

—

options:

– b

– kb

– mb

– gb

– tb

– B

– KB

– KiB

– MB

– MiB

– GB

– GiB

– TB

– TiB

—

\[--tables\]Display each table name and size instead of the database size.\[--human-readable\]Display database sizes in human readable formats.\[--format=<format>\]Render output in a particular format.

—

options:

– table

– csv

– json

– yaml

—

\[--scope=<scope>\]Can be all, global, ms\_global, blog, or old tables. Defaults to all.\[--network\]List all the tables in a multisite install.\[--decimals=<decimals>\]Number of digits after decimal point. Defaults to 0.\[--all-tables-with-prefix\]List all tables that match the table prefix even if not registered on $ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/). Overrides –network.\[--all-tables\]List all tables in the database, regardless of the prefix, and even if not registered on $ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/). Overrides –all-tables-with-prefix.\[--order=<order>\]Ascending or Descending order.

—

default: asc

options:

– asc

– desc

—

\[--orderby=<orderby>\]Order by fields.

—

default: name

options:

– name

– size

—

### [Examples](https://developer.wordpress.org/cli/commands/db/size/\#examples)

```
$ wp db size
+-------------------+------+
| Name              | Size |
+-------------------+------+
| wordpress_default | 6 MB |
+-------------------+------+

$ wp db size --tables
+-----------------------+-------+
| Name                  | Size  |
+-----------------------+-------+
| wp_users              | 64 KB |
| wp_usermeta           | 48 KB |
| wp_posts              | 80 KB |
| wp_comments           | 96 KB |
| wp_links              | 32 KB |
| wp_options            | 32 KB |
| wp_postmeta           | 48 KB |
| wp_terms              | 48 KB |
| wp_term_taxonomy      | 48 KB |
| wp_term_relationships | 32 KB |
| wp_termmeta           | 48 KB |
| wp_commentmeta        | 48 KB |
+-----------------------+-------+

$ wp db size --size_format=b
5865472

$ wp db size --size_format=kb
5728

$ wp db size --size_format=mb
6

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/db/size/\#global-parameters)

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