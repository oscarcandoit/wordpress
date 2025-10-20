---
url: https://developer.wordpress.org/cli/commands/language/core/install/
scraped_at: 2025-10-20T03:06:29.000Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/language/core/install/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp language core install


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp language](https://developer.wordpress.org/cli/commands/language/)[wp language core](https://developer.wordpress.org/cli/commands/language/core/)wp language core install

Search

# [wp language core install](https://developer.wordpress.org/cli/commands/language/core/install/)

Installs a given language.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/language/core/install/#options)
- [Examples](https://developer.wordpress.org/cli/commands/language/core/install/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/language/core/install/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/language/core/install/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/language-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-core-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (7)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-core-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/language-command/issues/new)

Downloads the language pack from WordPress.org. Find your language code at: https://translate.wordpress.org/

### [Options](https://developer.wordpress.org/cli/commands/language/core/install/\#options)

<language>…Language code to install.\[--activate\]If set, the language will be activated immediately after install.

### [Examples](https://developer.wordpress.org/cli/commands/language/core/install/\#examples)

```
# Install the Brazilian Portuguese language.
$ wp language core install pt_BR
Downloading translation from https://downloads.wordpress.org/translation/core/6.5/pt_BR.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'pt_BR' installed.
Success: Installed 1 of 1 languages.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/language/core/install/\#global-parameters)

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