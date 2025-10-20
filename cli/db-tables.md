---
url: https://developer.wordpress.org/cli/commands/db/tables/
scraped_at: 2025-10-20T03:04:50.877Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/db/tables/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp db tables


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp db](https://developer.wordpress.org/cli/commands/db/)wp db tables

Search

# [wp db tables](https://developer.wordpress.org/cli/commands/db/tables/)

Lists the database tables.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/db/tables/#options)
- [Examples](https://developer.wordpress.org/cli/commands/db/tables/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/db/tables/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/db/tables/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/db-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-tables+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-tables+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/db-command/issues/new)

Defaults to all tables registered to the $ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/) database handler.

### [Options](https://developer.wordpress.org/cli/commands/db/tables/\#options)

\[<table>…\]List tables based on wildcard search, e.g. ‘wp\_\*\_options’ or ‘wp\_post?’.\[--scope=<scope>\]Can be all, global, ms\_global, blog, or old tables. Defaults to all.\[--network\]List all the tables in a multisite install.\[--all-tables-with-prefix\]List all tables that match the table prefix even if not registered on $ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/). Overrides –network.\[--all-tables\]List all tables in the database, regardless of the prefix, and even if not registered on $ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/). Overrides –all-tables-with-prefix.\[--format=<format>\]Render output in a particular format.

—

default: list

options:

– list

– csv

—

### [Examples](https://developer.wordpress.org/cli/commands/db/tables/\#examples)

```
# List tables for a single site, without shared tables like 'wp_users'
$ wp db tables --scope=blog --url=sub.example.com
wp_3_posts
wp_3_comments
wp_3_options
wp_3_postmeta
wp_3_terms
wp_3_term_taxonomy
wp_3_term_relationships
wp_3_termmeta
wp_3_commentmeta

# Export only tables for a single site
$ wp db export --tables=$(wp db tables --url=sub.example.com --format=csv)
Success: Exported to wordpress_dbase.sql

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/db/tables/\#global-parameters)

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