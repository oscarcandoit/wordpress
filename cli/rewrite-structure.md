---
url: https://developer.wordpress.org/cli/commands/rewrite/structure/
scraped_at: 2025-10-20T03:14:43.940Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/rewrite/structure/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp rewrite structure


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp rewrite](https://developer.wordpress.org/cli/commands/rewrite/)wp rewrite structure

Search

# [wp rewrite structure](https://developer.wordpress.org/cli/commands/rewrite/structure/)

Updates the permalink structure.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/rewrite/structure/#options)
- [Examples](https://developer.wordpress.org/cli/commands/rewrite/structure/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/rewrite/structure/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/rewrite/structure/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/rewrite-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Arewrite-structure+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Arewrite-structure+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/rewrite-command/issues/new)

Sets the post permalink structure to the specified pattern.

To regenerate a .htaccess file with WP-CLI, you’ll need to add the mod\_rewrite module to your [WP-CLI config](https://make.wordpress.org/cli/handbook/config/#config-files). For example:

```
apache_modules:
  - mod_rewrite

```

### [Options](https://developer.wordpress.org/cli/commands/rewrite/structure/\#options)

<permastruct>The new permalink structure to apply.\[--category-base=<base>\]Set the base for category permalinks, i.e. ‘/category/’.\[--tag-base=<base>\]Set the base for tag permalinks, i.e. ‘/tag/’.\[--hard\]Perform a hard flush – update `.htaccess` rules as well as rewrite rules in database.

### [Examples](https://developer.wordpress.org/cli/commands/rewrite/structure/\#examples)

```
$ wp rewrite structure '/%year%/%monthnum%/%postname%/'
Success: Rewrite structure set.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/rewrite/structure/\#global-parameters)

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