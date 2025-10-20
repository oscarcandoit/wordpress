---
url: https://developer.wordpress.org/cli/commands/site/empty/
scraped_at: 2025-10-20T03:16:17.480Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/site/empty/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp site empty


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp site](https://developer.wordpress.org/cli/commands/site/)wp site empty

Search

# [wp site empty](https://developer.wordpress.org/cli/commands/site/empty/)

Empties a site of its content (posts, comments, terms, and meta).

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/site/empty/#options)
- [Examples](https://developer.wordpress.org/cli/commands/site/empty/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/site/empty/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/site/empty/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asite-empty+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (13)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asite-empty+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

Truncates posts, comments, and terms tables to empty a site of its content. Doesn’t affect site configuration (options) or users.

If running a persistent object cache, make sure to flush the cache after emptying the site, as the cache values will be invalid otherwise.

To also empty custom database tables, you’ll need to hook into command execution:

```
WP_CLI::add_hook( 'after_invoke:site empty', function(){
    global $wpdb;
    foreach( array( 'p2p', 'p2pmeta' ) as $table ) {
        $table = $wpdb-&gt;$table;
        $wpdb-&gt;query( "TRUNCATE $table" );
    }
});

```

### [Options](https://developer.wordpress.org/cli/commands/site/empty/\#options)

\[--uploads\]Also delete _all_ files in the site’s uploads directory.\[--yes\]Proceed to empty the site without a confirmation prompt.

### [Examples](https://developer.wordpress.org/cli/commands/site/empty/\#examples)

```
$ wp site empty
Are you sure you want to empty the site at http://www.example.com of all posts, links, comments, and terms? [y/n] y
Success: The site at 'http://www.example.com' was emptied.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/site/empty/\#global-parameters)

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