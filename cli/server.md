---
url: https://developer.wordpress.org/cli/commands/server/
scraped_at: 2025-10-20T03:15:40.612Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/server/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp server


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp server

Search

# [wp server](https://developer.wordpress.org/cli/commands/server/)

Launches PHP’s built-in web server for a specific WordPress installation.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/server/#options)
- [Examples](https://developer.wordpress.org/cli/commands/server/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/server/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/server/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/server-command)

[View Open Issues (4)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aserver+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (35)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aserver+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/server-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

Uses `php -S` to launch a web server serving the WordPress webroot.
<http://php.net/manual/en/features.commandline.webserver.php>

Importantly, PHP’s built-in web server doesn’t support `.htaccess` files. If this is a requirement, please use a more advanced web server.

### [Options](https://developer.wordpress.org/cli/commands/server/\#options)

\[--host=<host>\]The hostname to bind the server to.

—

default: localhost

—

\[--port=<port>\]The port number to bind the server to.

—

default: 8080

—

\[--docroot=<path>\]The path to use as the document root. If the path global parameter is set, the default value is it.\[--config=<file>\]Configure the server with a specific .ini file.

### [Examples](https://developer.wordpress.org/cli/commands/server/\#examples)

```
# Make the instance available on any address (with port 8080)
$ wp server --host=0.0.0.0
PHP 5.6.9 Development Server started at Tue May 24 01:27:11 2016
Listening on http://0.0.0.0:8080
Document root is /
Press Ctrl-C to quit.

# Run on port 80 (for multisite)
$ wp server --host=localhost.localdomain --port=80
PHP 5.6.9 Development Server started at Tue May 24 01:30:06 2016
Listening on http://localhost1.localdomain1:80
Document root is /
Press Ctrl-C to quit.

# Configure the server with a specific .ini file
$ wp server --config=development.ini
PHP 7.0.9 Development Server started at Mon Aug 22 12:09:04 2016
Listening on http://localhost:8080
Document root is /
Press Ctrl-C to quit.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/server/\#global-parameters)

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