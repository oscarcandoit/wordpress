---
url: https://developer.wordpress.org/cli/commands/language/plugin/
scraped_at: 2025-10-20T03:06:43.019Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/language/plugin/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp language plugin


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp language](https://developer.wordpress.org/cli/commands/language/)wp language plugin

Search

# [wp language plugin\  <command>](https://developer.wordpress.org/cli/commands/language/plugin/)

Installs, activates, and manages plugin language packs.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/language/plugin/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/language/plugin/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/language/plugin/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/language-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-plugin+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-plugin+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/language-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/language/plugin/\#examples)

```
# Install the Dutch plugin language pack for Hello Dolly.
$ wp language plugin install hello-dolly nl_NL
Downloading translation from https://downloads.wordpress.org/translation/plugin/hello-dolly/1.7.2/nl_NL.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'nl_NL' installed.
Success: Installed 1 of 1 languages.

# Uninstall the Dutch plugin language pack for Hello Dolly.
$ wp language plugin uninstall hello-dolly nl_NL
Language 'nl_NL' for 'hello-dolly' uninstalled.
+-------------+--------+-------------+
| name        | locale | status      |
+-------------+--------+-------------+
| hello-dolly | nl_NL  | uninstalled |
+-------------+--------+-------------+
Success: Uninstalled 1 of 1 languages.

# List installed plugin language packs for Hello Dolly.
$ wp language plugin list hello-dolly --status=installed
+-------------+----------+--------------+-------------+-----------+--------+---------------------+
| plugin      | language | english_name | native_name | status    | update | updated             |
+-------------+----------+--------------+-------------+-----------+--------+---------------------+
| hello-dolly | nl_NL    | Dutch        | Nederlands  | installed | none   | 2023-11-13 12:34:15 |
+-------------+----------+--------------+-------------+-----------+--------+---------------------+

```

### [Subcommands](https://developer.wordpress.org/cli/commands/language/plugin/\#subcommands)

| Name | Description |
| --- | --- |
| [wp language plugin install](https://developer.wordpress.org/cli/commands/language/plugin/install/) | Installs a given language for a plugin. |
| [wp language plugin is-installed](https://developer.wordpress.org/cli/commands/language/plugin/is-installed/) | Checks if a given language is installed. |
| [wp language plugin list](https://developer.wordpress.org/cli/commands/language/plugin/list/) | Lists all available languages for one or more plugins. |
| [wp language plugin uninstall](https://developer.wordpress.org/cli/commands/language/plugin/uninstall/) | Uninstalls a given language for a plugin. |
| [wp language plugin update](https://developer.wordpress.org/cli/commands/language/plugin/update/) | Updates installed languages for one or more plugins. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications