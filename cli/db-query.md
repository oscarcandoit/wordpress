---
url: https://developer.wordpress.org/cli/commands/db/query/
scraped_at: 2025-10-20T03:04:40.045Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/db/query/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp db query


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp db](https://developer.wordpress.org/cli/commands/db/)wp db query

Search

# [wp db query](https://developer.wordpress.org/cli/commands/db/query/)

Executes a SQL query against the database.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/db/query/#options)
- [Examples](https://developer.wordpress.org/cli/commands/db/query/#examples)
- [Multisite Usage](https://developer.wordpress.org/cli/commands/db/query/#multisite-usage)
- [Global Parameters](https://developer.wordpress.org/cli/commands/db/query/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/db/query/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/db-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-query+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adb-query+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/db-command/issues/new)

This command runs on the `after_wp_config_load` hook, after wp-config.php has been loaded into scope.

Executes an arbitrary SQL query using `DB_HOST`, `DB_NAME`, `DB_USER`
and `DB_PASSWORD` database credentials specified in wp-config.php.

Use the `--skip-column-names` MySQL argument to exclude the headers from a SELECT query. Pipe the output to remove the ASCII table entirely.

### [Options](https://developer.wordpress.org/cli/commands/db/query/\#options)

\[<sql>\]A SQL query. If not passed, will try to read from STDIN.\[--dbuser=<value>\]Username to pass to mysql. Defaults to DB\_USER.\[--dbpass=<value>\]Password to pass to mysql. Defaults to DB\_PASSWORD.\[--<field>=<value>\]Extra arguments to pass to mysql. [Refer to mysql docs](https://dev.mysql.com/doc/en/mysql-command-options.html).\[--defaults\]Loads the environment’s MySQL option files. Default behavior is to skip loading them to avoid failures due to misconfiguration.

### [Examples](https://developer.wordpress.org/cli/commands/db/query/\#examples)

```
# Execute a query stored in a file
$ wp db query < debug.sql

# Query for a specific value in the database (pipe the result to remove the ASCII table borders)
$ wp db query 'SELECT option_value FROM wp_options WHERE option_name="home"' --skip-column-names
+---------------------+
| https://example.com |
+---------------------+

# Check all tables in the database
$ wp db query "CHECK TABLE $(wp db tables | paste -s -d, -);"
+---------------------------------------+-------+----------+----------+
| Table                                 | Op    | Msg_type | Msg_text |
+---------------------------------------+-------+----------+----------+
| wordpress_dbase.wp_users              | check | status   | OK       |
| wordpress_dbase.wp_usermeta           | check | status   | OK       |
| wordpress_dbase.wp_posts              | check | status   | OK       |
| wordpress_dbase.wp_comments           | check | status   | OK       |
| wordpress_dbase.wp_links              | check | status   | OK       |
| wordpress_dbase.wp_options            | check | status   | OK       |
| wordpress_dbase.wp_postmeta           | check | status   | OK       |
| wordpress_dbase.wp_terms              | check | status   | OK       |
| wordpress_dbase.wp_term_taxonomy      | check | status   | OK       |
| wordpress_dbase.wp_term_relationships | check | status   | OK       |
| wordpress_dbase.wp_termmeta           | check | status   | OK       |
| wordpress_dbase.wp_commentmeta        | check | status   | OK       |
+---------------------------------------+-------+----------+----------+

# Pass extra arguments through to MySQL
$ wp db query 'SELECT * FROM wp_options WHERE option_name="home"' --skip-column-names
+---+------+------------------------------+-----+
| 2 | home | http://wordpress-develop.dev | yes |
+---+------+------------------------------+-----+

```

### [Multisite Usage](https://developer.wordpress.org/cli/commands/db/query/\#multisite-usage)

Please note that the global `--url` parameter will have no effect on this command. In order to query for data in a site other than your primary site, you will need to manually modify the table names to use the prefix that includes the site’s ID.

For example, to get the `home` option for your second site, modify the example above like so:

```
$ wp db query 'SELECT option_value FROM wp_2_options WHERE option_name="home"' --skip-column-names
+----------------------+
| https://example2.com |
+----------------------+

```

To confirm the ID for the site you want to query, you can use the `wp site list` command:

```
# wp site list --fields=blog_id,url
+---------+-----------------------+
| blog_id | url                   |
+---------+-----------------------+
| 1       | https://example1.com/ |
| 2       | https://example2.com/ |
+---------+-----------------------+

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/db/query/\#global-parameters)

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