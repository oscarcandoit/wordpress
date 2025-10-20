---
url: https://developer.wordpress.org/cli/commands/config/create/
scraped_at: 2025-10-20T03:01:24.320Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/config/create/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp config create


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp config](https://developer.wordpress.org/cli/commands/config/)wp config create

Search

# [wp config create](https://developer.wordpress.org/cli/commands/config/create/)

Generates a wp-config.php file.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/config/create/#options)
- [Examples](https://developer.wordpress.org/cli/commands/config/create/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/config/create/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/config/create/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/config-command)

[View Open Issues (7)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-create+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (30)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-create+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/config-command/issues/new)

Creates a new wp-config.php with database constants, and verifies that the database constants are correct.

### [Options](https://developer.wordpress.org/cli/commands/config/create/\#options)

--dbname=<dbname>Set the database name.--dbuser=<dbuser>Set the database user.\[--dbpass=<dbpass>\]Set the database user password.\[--dbhost=<dbhost>\]Set the database host.

—

default: localhost

—

\[--dbprefix=<dbprefix>\]Set the database table prefix.

—

default: wp\_

—

\[--dbcharset=<dbcharset>\]Set the database charset.

—

default: utf8

—

\[--dbcollate=<dbcollate>\]Set the database collation.

—

default:

—

\[--locale=<locale>\]Set the WPLANG constant. Defaults to $wp\_local\_package variable.\[--extra-php\]If set, the command copies additional PHP code into wp-config.php from STDIN.\[--skip-salts\]If set, keys and salts won’t be generated, but should instead be passed via `--extra-php`.\[--skip-check\]If set, the database connection is not checked.\[--force\]Overwrites existing files, if present.\[--config-file=<path>\]Specify the file path to the config file to be created. Defaults to the root of the WordPress installation and the filename “wp-config.php”.\[--insecure\]Retry API download without certificate validation if TLS handshake fails. Note: This makes the request vulnerable to a MITM attack.

### [Examples](https://developer.wordpress.org/cli/commands/config/create/\#examples)

```
# Standard wp-config.php file
$ wp config create --dbname=testing --dbuser=wp --dbpass=securepswd --locale=ro_RO
Success: Generated 'wp-config.php' file.

# Enable WP_DEBUG and WP_DEBUG_LOG
$ wp config create --dbname=testing --dbuser=wp --dbpass=securepswd --extra-php <<PHP
define( 'WP_DEBUG', true );
define( 'WP_DEBUG_LOG', true );
PHP
Success: Generated 'wp-config.php' file.

# Avoid disclosing password to bash history by reading from password.txt
# Using --prompt=dbpass will prompt for the 'dbpass' argument
$ wp config create --dbname=testing --dbuser=wp --prompt=dbpass < password.txt
Success: Generated 'wp-config.php' file.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/config/create/\#global-parameters)

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