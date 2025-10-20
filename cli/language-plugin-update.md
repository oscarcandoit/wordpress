---
url: https://developer.wordpress.org/cli/commands/language/plugin/update/
scraped_at: 2025-10-20T03:07:14.879Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/language/plugin/update/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp language plugin update


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp language](https://developer.wordpress.org/cli/commands/language/)[wp language plugin](https://developer.wordpress.org/cli/commands/language/plugin/)wp language plugin update

Search

# [wp language plugin update](https://developer.wordpress.org/cli/commands/language/plugin/update/)

Updates installed languages for one or more plugins.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/language/plugin/update/#options)
- [Examples](https://developer.wordpress.org/cli/commands/language/plugin/update/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/language/plugin/update/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/language/plugin/update/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/language-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-plugin-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (12)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-plugin-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/language-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/language/plugin/update/\#options)

\[<plugin>…\]One or more plugins to update languages for.\[--all\]If set, languages for all plugins will be updated.\[--dry-run\]Preview which translations would be updated.

### [Examples](https://developer.wordpress.org/cli/commands/language/plugin/update/\#examples)

```
# Update all installed language packs for all plugins.
$ wp language plugin update --all
Updating 'Japanese' translation for Akismet 3.1.11...
Downloading translation from https://downloads.wordpress.org/translation/plugin/akismet/3.1.11/ja.zip...
Translation updated successfully.
Success: Updated 1/1 translation.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/language/plugin/update/\#global-parameters)

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