---
url: https://developer.wordpress.org/cli/commands/db/
scraped_at: 2025-10-20T03:04:06.608Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/db/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp db


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp db

Search

# [wp db\  <command>](https://developer.wordpress.org/cli/commands/db/)

Performs basic database operations using credentials stored in wp-config.php.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/db/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/db/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/db/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/db-command)

[View Open Issues (9)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (109)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/db-command/issues/new)

Unless overridden, these commands run on the `after_wp_config_load` hook, after wp-config.php has been loaded into scope.

### [Examples](https://developer.wordpress.org/cli/commands/db/\#examples)

```
# Create a new database.
$ wp db create
Success: Database created.

# Drop an existing database.
$ wp db drop --yes
Success: Database dropped.

# Reset the current database.
$ wp db reset --yes
Success: Database reset.

# Execute a SQL query stored in a file.
$ wp db query < debug.sql

```

### [Subcommands](https://developer.wordpress.org/cli/commands/db/\#subcommands)

| Name | Description |
| --- | --- |
| [wp db check](https://developer.wordpress.org/cli/commands/db/check/) | Checks the current status of the database. |
| [wp db clean](https://developer.wordpress.org/cli/commands/db/clean/) | Removes all tables with \`$table\_prefix\` from the database. |
| [wp db cli](https://developer.wordpress.org/cli/commands/db/cli/) | Opens a MySQL console using credentials from wp-config.php |
| [wp db columns](https://developer.wordpress.org/cli/commands/db/columns/) | Displays information about a given table. |
| [wp db create](https://developer.wordpress.org/cli/commands/db/create/) | Creates a new database. |
| [wp db drop](https://developer.wordpress.org/cli/commands/db/drop/) | Deletes the existing database. |
| [wp db export](https://developer.wordpress.org/cli/commands/db/export/) | Exports the database to a file or to STDOUT. |
| [wp db import](https://developer.wordpress.org/cli/commands/db/import/) | Imports a database from a file or from STDIN. |
| [wp db optimize](https://developer.wordpress.org/cli/commands/db/optimize/) | Optimizes the database. |
| [wp db prefix](https://developer.wordpress.org/cli/commands/db/prefix/) | Displays the database table prefix. |
| [wp db query](https://developer.wordpress.org/cli/commands/db/query/) | Executes a SQL query against the database. |
| [wp db repair](https://developer.wordpress.org/cli/commands/db/repair/) | Repairs the database. |
| [wp db reset](https://developer.wordpress.org/cli/commands/db/reset/) | Removes all tables from the database. |
| [wp db search](https://developer.wordpress.org/cli/commands/db/search/) | Finds a string in the database. |
| [wp db size](https://developer.wordpress.org/cli/commands/db/size/) | Displays the database name and size. |
| [wp db tables](https://developer.wordpress.org/cli/commands/db/tables/) | Lists the database tables. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications