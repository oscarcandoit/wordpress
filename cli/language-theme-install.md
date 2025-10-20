---
url: https://developer.wordpress.org/cli/commands/language/theme/install/
scraped_at: 2025-10-20T03:07:23.090Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/language/theme/install/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp language theme install


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp language](https://developer.wordpress.org/cli/commands/language/)[wp language theme](https://developer.wordpress.org/cli/commands/language/theme/)wp language theme install

Search

# [wp language theme install](https://developer.wordpress.org/cli/commands/language/theme/install/)

Installs a given language for a theme.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/language/theme/install/#options)
- [Examples](https://developer.wordpress.org/cli/commands/language/theme/install/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/language/theme/install/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/language/theme/install/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/language-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-theme-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-theme-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/language-command/issues/new)

Downloads the language pack from WordPress.org.

### [Options](https://developer.wordpress.org/cli/commands/language/theme/install/\#options)

\[<theme>\]Theme to install language for.\[--all\]If set, languages for all themes will be installed.<language>…Language code to install.\[--format=<format>\]Render output in a particular format. Used when installing languages for all themes.

—

default: table

options:

– table

– csv

– json

– summary

—

### [Examples](https://developer.wordpress.org/cli/commands/language/theme/install/\#examples)

```
# Install the Japanese language for Twenty Seventeen.
$ wp language theme install twentyseventeen ja
Downloading translation from https://downloads.wordpress.org/translation/theme/twentyseventeen/1.3/ja.zip...
Unpacking the update...
Installing the latest version...
Translation updated successfully.
Language 'ja' installed.
Success: Installed 1 of 1 languages.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/language/theme/install/\#global-parameters)

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