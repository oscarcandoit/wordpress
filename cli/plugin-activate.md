---
url: https://developer.wordpress.org/cli/commands/plugin/activate/
scraped_at: 2025-10-20T03:11:12.492Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/plugin/activate/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp plugin activate


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp plugin](https://developer.wordpress.org/cli/commands/plugin/)wp plugin activate

Search

# [wp plugin activate](https://developer.wordpress.org/cli/commands/plugin/activate/)

Activates one or more plugins.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/plugin/activate/#options)
- [Examples](https://developer.wordpress.org/cli/commands/plugin/activate/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/plugin/activate/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/plugin/activate/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/extension-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-activate+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-activate+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/extension-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/plugin/activate/\#options)

\[<plugin>…\]One or more plugins to activate.\[--all\]If set, all plugins will be activated.\[--exclude=<name>\]Comma separated list of plugin slugs to be excluded from activation.\[--network\]If set, the plugin will be activated for the entire multisite network.

### [Examples](https://developer.wordpress.org/cli/commands/plugin/activate/\#examples)

```
# Activate plugin
$ wp plugin activate hello
Plugin 'hello' activated.
Success: Activated 1 of 1 plugins.

# Activate plugin in entire multisite network
$ wp plugin activate hello --network
Plugin 'hello' network activated.
Success: Network activated 1 of 1 plugins.

# Activate plugins that were recently active.
$ wp plugin activate $(wp plugin list --recently-active --field=name)
Plugin 'bbpress' activated.
Plugin 'buddypress' activated.
Success: Activated 2 of 2 plugins.

# Activate plugins that were recently active on a multisite.
$ wp plugin activate $(wp plugin list --recently-active --field=name) --network
Plugin 'bbpress' network activated.
Plugin 'buddypress' network activated.
Success: Activated 2 of 2 plugins.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/plugin/activate/\#global-parameters)

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