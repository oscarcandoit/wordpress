---
url: https://developer.wordpress.org/cli/commands/language/core/
scraped_at: 2025-10-20T03:06:21.170Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/language/core/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp language core


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp language](https://developer.wordpress.org/cli/commands/language/)wp language core

Search

# [wp language core\  <command>](https://developer.wordpress.org/cli/commands/language/core/)

Installs, activates, and manages core language packs.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/language/core/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/language/core/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/language/core/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/language-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-core+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage-core+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/language-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/language/core/\#examples)

```
# Install the Dutch core language pack.
$ wp language core install nl_NL
Downloading translation from https://downloads.wordpress.org/translation/core/6.4.3/nl_NL.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'nl_NL' installed.
Success: Installed 1 of 1 languages.

# Activate the Dutch core language pack.
$ wp site switch-language nl_NL
Success: Language activated.

# Uninstall the Dutch core language pack.
$ wp language core uninstall nl_NL
Success: Language uninstalled.

# List installed core language packs.
$ wp language core list --status=installed
+----------+--------------+-------------+-----------+-----------+---------------------+
| language | english_name | native_name | status    | update    | updated             |
+----------+--------------+-------------+-----------+-----------+---------------------+
| nl_NL    | Dutch        | Nederlands  | installed | available | 2024-01-31 10:24:06 |
+----------+--------------+-------------+-----------+-----------+---------------------+

```

### [Subcommands](https://developer.wordpress.org/cli/commands/language/core/\#subcommands)

| Name | Description |
| --- | --- |
| [wp language core activate](https://developer.wordpress.org/cli/commands/language/core/activate/) | Activates a given language. |
| [wp language core install](https://developer.wordpress.org/cli/commands/language/core/install/) | Installs a given language. |
| [wp language core is-installed](https://developer.wordpress.org/cli/commands/language/core/is-installed/) | Checks if a given language is installed. |
| [wp language core list](https://developer.wordpress.org/cli/commands/language/core/list/) | Lists all available languages. |
| [wp language core uninstall](https://developer.wordpress.org/cli/commands/language/core/uninstall/) | Uninstalls a given language. |
| [wp language core update](https://developer.wordpress.org/cli/commands/language/core/update/) | Updates installed languages for core. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications