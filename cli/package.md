---
url: https://developer.wordpress.org/cli/commands/package/
scraped_at: 2025-10-20T03:09:50.840Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/package/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp package


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp package

Search

# [wp package\  <command>](https://developer.wordpress.org/cli/commands/package/)

Lists, installs, and removes WP-CLI packages.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/package/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/package/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/package/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/package-command)

[View Open Issues (6)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apackage+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (96)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apackage+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/package-command/issues/new)

Unless overridden, these commands run on the `before_wp_load` hook, just before the WP load process begins.

WP-CLI packages are community-maintained projects built on WP-CLI. They can contain WP-CLI commands, but they can also just extend WP-CLI in some way.

Learn how to create your own command from the
[Commands Cookbook](https://make.wordpress.org/cli/handbook/guides/commands-cookbook/)

### [Examples](https://developer.wordpress.org/cli/commands/package/\#examples)

```
# List installed packages.
$ wp package list
+-----------------------+------------------+----------+-----------+----------------+
| name                  | authors          | version  | update    | update_version |
+-----------------------+------------------+----------+-----------+----------------+
| wp-cli/server-command | Daniel Bachhuber | dev-main | available | 2.x-dev        |
+-----------------------+------------------+----------+-----------+----------------+

# Install the latest development version of the package.
$ wp package install wp-cli/server-command
Installing package wp-cli/server-command (dev-main)
Updating /home/person/.wp-cli/packages/composer.json to require the package...
Using Composer to install the package...
---
Loading composer repositories with package information
Updating dependencies
Resolving dependencies through SAT
Dependency resolution completed in 0.005 seconds
Analyzed 732 packages to resolve dependencies
Analyzed 1034 rules to resolve dependencies
 - Installing package
Writing lock file
Generating autoload files
---
Success: Package installed.

# Uninstall package.
$ wp package uninstall wp-cli/server-command
Removing require statement for package 'wp-cli/server-command' from /home/person/.wp-cli/packages/composer.json
Removing repository details from /home/person/.wp-cli/packages/composer.json
Removing package directories and regenerating autoloader...
Success: Uninstalled package.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/package/\#subcommands)

| Name | Description |
| --- | --- |
| [wp package browse](https://developer.wordpress.org/cli/commands/package/browse/) | Browses WP-CLI packages available for installation. |
| [wp package install](https://developer.wordpress.org/cli/commands/package/install/) | Installs a WP-CLI package. |
| [wp package list](https://developer.wordpress.org/cli/commands/package/list/) | Lists installed WP-CLI packages. |
| [wp package path](https://developer.wordpress.org/cli/commands/package/path/) | Gets the path to an installed WP-CLI package, or the package directory. |
| [wp package uninstall](https://developer.wordpress.org/cli/commands/package/uninstall/) | Uninstalls a WP-CLI package. |
| [wp package update](https://developer.wordpress.org/cli/commands/package/update/) | Updates all installed WP-CLI packages to their latest version. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications