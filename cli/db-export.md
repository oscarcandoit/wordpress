---
url: https://developer.wordpress.org/cli/commands/db/export/
scraped_at: 2025-10-20T03:04:26.725Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/db/export/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp db export


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp db](https://developer.wordpress.org/cli/commands/db/)wp db export

Search

# [wp db export](https://developer.wordpress.org/cli/commands/db/export/)

Exports the database to a file or to STDOUT.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/db/export/#options)
- [Examples](https://developer.wordpress.org/cli/commands/db/export/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/db/export/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/db/export/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/db-command)

[View Open Issues (2)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-export+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (28)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-export+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/db-command/issues/new)

This command runs on the `after_wp_config_load` hook, after wp-config.php has been loaded into scope.

Runs `mysqldump` utility using `DB_HOST`, `DB_NAME`, `DB_USER` and `DB_PASSWORD` database credentials specified in wp-config.php. Accepts any valid `mysqldump` flags.

### [Options](https://developer.wordpress.org/cli/commands/db/export/\#options)

\[<file>\]The name of the SQL file to export. If ‘-‘, then outputs to STDOUT. If omitted, it will be ‘{dbname}-{Y-m-d}-{random-hash}.sql’.\[--dbuser=<value>\]Username to pass to mysqldump. Defaults to DB\_USER.\[--dbpass=<value>\]Password to pass to mysqldump. Defaults to DB\_PASSWORD.\[--<field>=<value>\]Extra arguments to pass to mysqldump. [Refer to mysqldump docs](https://dev.mysql.com/doc/en/mysqldump.html#mysqldump-option-summary).\[--tables=<tables>\]The comma separated list of specific tables to export. Excluding this parameter will export all tables in the database.\[--exclude\_tables=<tables>\]The comma separated list of specific tables that should be skipped from exporting. Excluding this parameter will export all tables in the database.\[--include-tablespaces\]Skips adding the default –no-tablespaces option to mysqldump.\[--porcelain\]Output filename for the exported database.\[--add-drop-table\]Include a `DROP TABLE IF EXISTS` statement before each `CREATE TABLE` statement.\[--defaults\]Loads the environment’s MySQL option files. Default behavior is to skip loading them to avoid failures due to misconfiguration.

### [Examples](https://developer.wordpress.org/cli/commands/db/export/\#examples)

```
# Export database with drop query included
$ wp db export --add-drop-table
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Export certain tables
$ wp db export --tables=wp_options,wp_users
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Export all tables matching a wildcard
$ wp db export --tables=$(wp db tables 'wp_user*' --format=csv)
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Export all tables matching prefix
$ wp db export --tables=$(wp db tables --all-tables-with-prefix --format=csv)
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Export certain posts without create table statements
$ wp db export --no-create-info=true --tables=wp_posts --where="ID in (100,101,102)"
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Export relating meta for certain posts without create table statements
$ wp db export --no-create-info=true --tables=wp_postmeta --where="post_id in (100,101,102)"
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Skip certain tables from the exported database
$ wp db export --exclude_tables=wp_options,wp_users
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Skip all tables matching a wildcard from the exported database
$ wp db export --exclude_tables=$(wp db tables 'wp_user*' --format=csv)
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Skip all tables matching prefix from the exported database
$ wp db export --exclude_tables=$(wp db tables --all-tables-with-prefix --format=csv)
Success: Exported to 'wordpress_dbase-db72bb5.sql'.

# Export database to STDOUT.
$ wp db export -
-- MySQL dump 10.13  Distrib 5.7.19, for osx10.12 (x86_64)
--
-- Host: localhost    Database: wpdev
-- ------------------------------------------------------
-- Server version    5.7.19
...

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/db/export/\#global-parameters)

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