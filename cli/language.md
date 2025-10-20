---
url: https://developer.wordpress.org/cli/commands/language/
scraped_at: 2025-10-20T03:06:18.781Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/language/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp language


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp language

Search

# [wp language\  <command>](https://developer.wordpress.org/cli/commands/language/)

Installs, activates, and manages language packs.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/language/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/language/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/language/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/language-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (26)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Alanguage+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/language-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/language/\#examples)

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

# Install the Dutch theme language pack for Twenty Ten.
$ wp language theme install twentyten nl_NL
Downloading translation from https://downloads.wordpress.org/translation/theme/twentyten/4.0/nl_NL.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'nl_NL' installed.
Success: Installed 1 of 1 languages.

# Install the Dutch plugin language pack for Hello Dolly.
$ wp language plugin install hello-dolly nl_NL
Downloading translation from https://downloads.wordpress.org/translation/plugin/hello-dolly/1.7.2/nl_NL.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'nl_NL' installed.
Success: Installed 1 of 1 languages.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/language/\#subcommands)

| Name | Description |
| --- | --- |
| [wp language core](https://developer.wordpress.org/cli/commands/language/core/) | Installs, activates, and manages core language packs. |
| [wp language plugin](https://developer.wordpress.org/cli/commands/language/plugin/) | Installs, activates, and manages plugin language packs. |
| [wp language theme](https://developer.wordpress.org/cli/commands/language/theme/) | Installs, activates, and manages theme language packs. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications