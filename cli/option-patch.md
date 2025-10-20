---
url: https://developer.wordpress.org/cli/commands/option/patch/
scraped_at: 2025-10-20T03:09:44.718Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/option/patch/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp option patch


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp option](https://developer.wordpress.org/cli/commands/option/)wp option patch

Search

# [wp option patch](https://developer.wordpress.org/cli/commands/option/patch/)

Updates a nested value in an option.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/option/patch/#options)
- [Examples](https://developer.wordpress.org/cli/commands/option/patch/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/option/patch/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/option/patch/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption-patch+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption-patch+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/option/patch/\#options)

<action>Patch action to perform.

—

options:

– insert

– update

– delete

—

<key>The option name.<key-path>…The name(s) of the keys within the value to locate the value to patch.\[<value>\]The new value. If omitted, the value is read from STDIN.\[--format=<format>\]The serialization format for the value.

—

default: plaintext

options:

– plaintext

– json

—

### [Examples](https://developer.wordpress.org/cli/commands/option/patch/\#examples)

```
# Add 'bar' to the 'foo' key on an option with name 'option_name'
$ wp option patch insert option_name foo bar
Success: Updated 'option_name' option.

# Update the value of 'foo' key to 'new' on an option with name 'option_name'
$ wp option patch update option_name foo new
Success: Updated 'option_name' option.

# Set nested value of 'bar' key to value we have in the patch file on an option with name 'option_name'.
$ wp option patch update option_name foo bar < patch
Success: Updated 'option_name' option.

# Update the value for the key 'not-a-key' which is not exist on an option with name 'option_name'.
$ wp option patch update option_name foo not-a-key new-value
Error: No data exists for key "not-a-key"

# Update the value for the key 'foo' without passing value on an option with name 'option_name'.
$ wp option patch update option_name foo
Error: Please provide value to update.

# Delete the nested key 'bar' under 'foo' key on an option with name 'option_name'.
$ wp option patch delete option_name foo bar
Success: Updated 'option_name' option.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/option/patch/\#global-parameters)

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