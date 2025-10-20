---
url: https://developer.wordpress.org/cli/commands/language/theme/
scraped_at: 2025-10-20T03:07:17.314Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/language/theme/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp language theme


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp language](https://developer.wordpress.org/cli/commands/language/)wp language theme

Search

# [wp language theme\  <command>](https://developer.wordpress.org/cli/commands/language/theme/)

Installs, activates, and manages theme language packs.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/language/theme/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/language/theme/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/language/theme/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/language-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-theme+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-theme+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/language-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/language/theme/\#examples)

```
# Install the Dutch theme language pack for Twenty Ten.
$ wp language theme install twentyten nl_NL
Downloading translation from https://downloads.wordpress.org/translation/theme/twentyten/4.0/nl_NL.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'nl_NL' installed.
Success: Installed 1 of 1 languages.

# Uninstall the Dutch theme language pack for Twenty Ten.
$ wp language theme uninstall twentyten nl_NL
Language 'nl_NL' for 'twentyten' uninstalled.
+-----------+--------+-------------+
| name      | locale | status      |
+-----------+--------+-------------+
| twentyten | nl_NL  | uninstalled |
+-----------+--------+-------------+
Success: Uninstalled 1 of 1 languages.

# List installed theme language packs for Twenty Ten.
$ wp language theme list twentyten --status=installed
+-----------+----------+--------------+-------------+-----------+--------+---------------------+
| theme     | language | english_name | native_name | status    | update | updated             |
+-----------+----------+--------------+-------------+-----------+--------+---------------------+
| twentyten | nl_NL    | Dutch        | Nederlands  | installed | none   | 2023-12-29 21:21:39 |
+-----------+----------+--------------+-------------+-----------+--------+---------------------+

```

### [Subcommands](https://developer.wordpress.org/cli/commands/language/theme/\#subcommands)

| Name | Description |
| --- | --- |
| [wp language theme install](https://developer.wordpress.org/cli/commands/language/theme/install/) | Installs a given language for a theme. |
| [wp language theme is-installed](https://developer.wordpress.org/cli/commands/language/theme/is-installed/) | Checks if a given language is installed. |
| [wp language theme list](https://developer.wordpress.org/cli/commands/language/theme/list/) | Lists all available languages for one or more themes. |
| [wp language theme uninstall](https://developer.wordpress.org/cli/commands/language/theme/uninstall/) | Uninstalls a given language for a theme. |
| [wp language theme update](https://developer.wordpress.org/cli/commands/language/theme/update/) | Updates installed languages for one or more themes. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications