---
url: https://developer.wordpress.org/cli/commands/core/download/
scraped_at: 2025-10-20T03:01:52.131Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/core/download/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp core download


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp core](https://developer.wordpress.org/cli/commands/core/)wp core download

Search

# [wp core download](https://developer.wordpress.org/cli/commands/core/download/)

Downloads core WordPress files.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/core/download/#options)
- [Examples](https://developer.wordpress.org/cli/commands/core/download/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/core/download/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/core/download/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/core-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore-download+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore-download+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/core-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

Downloads and extracts WordPress core files to the specified path. Uses current directory when no path is specified. Downloaded build is verified to have the correct md5 and then cached to the local filesystem. Subsequent uses of command will use the local cache if it still exists.

### [Options](https://developer.wordpress.org/cli/commands/core/download/\#options)

\[<download-url>\]Download directly from a provided URL instead of fetching the URL from the wordpress.org servers.\[--path=<path>\]Specify the path in which to install WordPress. Defaults to current directory.\[--locale=<locale>\]Select which language you want to download.\[--version=<version>\]Select which version you want to download. Accepts a version number, ‘latest’ or ‘nightly’.\[--skip-content\]Download WP without the default themes and plugins.\[--force\]Overwrites existing files, if present.\[--insecure\]Retry download without certificate validation if TLS handshake fails. Note: This makes the request vulnerable to a MITM attack.\[--extract\]Whether to extract the downloaded file. Defaults to true.

### [Examples](https://developer.wordpress.org/cli/commands/core/download/\#examples)

```
$ wp core download --locale=nl_NL
Downloading WordPress 4.5.2 (nl_NL)...
md5 hash verified: c5366d05b521831dd0b29dfc386e56a5
Success: WordPress downloaded.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/core/download/\#global-parameters)

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