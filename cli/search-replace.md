---
url: https://developer.wordpress.org/cli/commands/search-replace/
scraped_at: 2025-10-20T03:15:38.065Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/search-replace/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp search-replace


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp search-replace

Search

# [wp search-replace](https://developer.wordpress.org/cli/commands/search-replace/)

Searches/replaces strings in the database.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/search-replace/#options)
- [Examples](https://developer.wordpress.org/cli/commands/search-replace/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/search-replace/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/search-replace/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/search-replace-command)

[View Open Issues (16)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asearch-replace+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (142)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asearch-replace+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/search-replace-command/issues/new)

Searches through all rows in a selection of tables and replaces appearances of the first string with the second string.

By default, the command uses tables registered to the `$wpdb` object. On multisite, this will just be the tables for the current site unless `--network` is specified.

Search/replace intelligently handles PHP serialized data, and does not change primary key values.

### [Options](https://developer.wordpress.org/cli/commands/search-replace/\#options)

<old>A string to search for within the database.<new>Replace instances of the first string with this new string.\[<table>…\]List of database tables to restrict the replacement to. Wildcards are supported, e.g. `'wp_*options'` or `'wp_post*'`.\[--dry-run\]Run the entire search/replace operation and show report, but don’t save changes to the database.\[--network\]Search/replace through all the tables registered to $ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/) in a multisite install.\[--all-tables-with-prefix\]Enable replacement on any tables that match the table prefix even if not registered on $ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/).\[--all-tables\]Enable replacement on ALL tables in the database, regardless of the prefix, and even if not registered on $ [wpdb](https://developer.wordpress.org/reference/classes/wpdb/). Overrides –network and –all-tables-with-prefix.\[--export\[=<file>\]\]Write transformed data as SQL file instead of saving replacements to the database. If <file> is not supplied, will output to STDOUT.\[--export\_insert\_size=<rows>\]Define number of rows in single INSERT statement when doing SQL export. You might want to change this depending on your database configuration (e.g. if you need to do fewer queries). Default: 50\[--skip-tables=<tables>\]Do not perform the replacement on specific tables. Use commas to specify multiple tables. Wildcards are supported, e.g. `'wp_*options'` or `'wp_post*'`.\[--skip-columns=<columns>\]Do not perform the replacement on specific columns. Use commas to specify multiple columns.\[--include-columns=<columns>\]Perform the replacement on specific columns. Use commas to specify multiple columns.\[--precise\]Force the use of PHP (instead of SQL) which is more thorough, but slower.\[--recurse-objects\]Enable recursing into objects to replace strings. Defaults to true; pass –no-recurse-objects to disable.\[--verbose\]Prints rows to the console as they’re updated.\[--regex\]Runs the search using a regular expression (without delimiters). Warning: search-replace will take about 15-20x longer when using –regex.\[--regex-flags=<regex-flags>\]Pass PCRE modifiers to regex search-replace (e.g. ‘i’ for case-insensitivity).\[--regex-delimiter=<regex-delimiter>\]The delimiter to use for the regex. It must be escaped if it appears in the search string. The default value is the result of `chr(1)`.\[--regex-limit=<regex-limit>\]The maximum possible replacements for the regex per row (or per unserialized data bit per row). Defaults to -1 (no limit).\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– count

—

\[--report\]Produce report. Defaults to true.\[--report-changed-only\]Report changed fields only. Defaults to false, unless logging, when it defaults to true.\[--log\[=<file>\]\]Log the items changed. If <file> is not supplied or is “-“, will output to STDOUT. Warning: causes a significant slow down, similar or worse to enabling –precise or –regex.\[--before\_context=<num>\]For logging, number of characters to display before the old match and the new replacement. Default 40. Ignored if not logging.\[--after\_context=<num>\]For logging, number of characters to display after the old match and the new replacement. Default 40. Ignored if not logging.

### [Examples](https://developer.wordpress.org/cli/commands/search-replace/\#examples)

```
# Search and replace but skip one column
$ wp search-replace 'http://example.test' 'http://example.com' --skip-columns=guid

# Run search/replace operation but dont save in database
$ wp search-replace 'foo' 'bar' wp_posts wp_postmeta wp_terms --dry-run

# Run case-insensitive regex search/replace operation (slow)
$ wp search-replace '\[foo id="([0-9]+)"' '[bar id="\1"' --regex --regex-flags='i'\
\
# Turn your production multisite database into a local dev database\
$ wp search-replace --url=example.com example.com example.test 'wp_*options' wp_blogs wp_site --network\
\
# Search/replace to a SQL file without transforming the database\
$ wp search-replace foo bar --export=database.sql\
\
# Bash script: Search/replace production to development url (multisite compatible)\
#!/bin/bash\
if $(wp --url=http://example.com core is-installed --network); then\
    wp search-replace --url=http://example.com 'http://example.com' 'http://example.test' --recurse-objects --network --skip-columns=guid --skip-tables=wp_users\
else\
    wp search-replace 'http://example.com' 'http://example.test' --recurse-objects --skip-columns=guid --skip-tables=wp_users\
fi\
\
```\
\
### [Global Parameters](https://developer.wordpress.org/cli/commands/search-replace/\#global-parameters)\
\
These [global parameters](https://make.wordpress.org/cli/handbook/config/) have the same behavior across all commands and affect how WP-CLI interacts with WordPress.\
\
| **Argument** | **Description** |\
| :-- | :-- |\
| `--path=<path>` | Path to the WordPress files. |\
| `--url=<url>` | Pretend request came from given URL. In multisite, this argument is how the target site is specified. |\
| `--ssh=[<scheme>:][<user>@]<host\|container>[:<port>][<path>]` | Perform operation against a remote server over SSH (or a container using scheme of “docker”, “docker-compose”, “docker-compose-run”, “vagrant”). |\
| `--http=<http>` | Perform operation against a remote WordPress installation over HTTP. |\
| `--user=<id\|login\|email>` | Set the WordPress user. |\
| `--skip-plugins[=<plugins>]` | Skip loading all plugins, or a comma-separated list of plugins. Note: mu-plugins are still loaded. |\
| `--skip-themes[=<themes>]` | Skip loading all themes, or a comma-separated list of themes. |\
| `--skip-packages` | Skip loading all installed packages. |\
| `--require=<path>` | Load PHP file before running the command (may be used more than once). |\
| `--exec=<php-code>` | Execute PHP code before running the command (may be used more than once). |\
| `--context=<context>` | Load WordPress in a given context. |\
| `--[no-]color` | Whether to colorize the output. |\
| `--debug[=<group>]` | Show all PHP errors and add verbosity to WP-CLI output. Built-in groups include: bootstrap, commandfactory, and help. |\
| `--prompt[=<assoc>]` | Prompt the user to enter values for all command arguments, or a subset specified as comma-separated values. |\
| `--quiet` | Suppress informational messages. |\
\
_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._\
\
Notifications