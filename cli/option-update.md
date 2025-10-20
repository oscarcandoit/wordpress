---
url: https://developer.wordpress.org/cli/commands/option/update/
scraped_at: 2025-10-20T03:09:48.841Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/option/update/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp option update


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp option](https://developer.wordpress.org/cli/commands/option/)wp option update

Search

# [wp option update](https://developer.wordpress.org/cli/commands/option/update/)

Updates an option value.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/option/update/#options)
- [Examples](https://developer.wordpress.org/cli/commands/option/update/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/option/update/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/option/update/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/option/update/\#options)

<key>The name of the option to update.\[<value>\]The new value. If omitted, the value is read from STDIN.\[--autoload=<autoload>\]Requires WP 4.2. Should this option be automatically loaded.

—

options:

– ‘on’

– ‘off’

– ‘yes’

– ‘no’

—

\[--format=<format>\]The serialization format for the value.

—

default: plaintext

options:

– plaintext

– json

—

### [Examples](https://developer.wordpress.org/cli/commands/option/update/\#examples)

```
# Update an option by reading from a file.
$ wp option update my_option < value.txt
Success: Updated 'my_option' option.

# Update one option on multiple sites using xargs.
$ wp site list --field=url | xargs -n1 -I {} sh -c 'wp --url={} option update my_option my_value'
Success: Updated 'my_option' option.
Success: Updated 'my_option' option.

# Update site blog name.
$ wp option update blogname "Random blog name"
Success: Updated 'blogname' option.

# Update site blog description.
$ wp option update blogdescription "Some random blog description"
Success: Updated 'blogdescription' option.

# Update admin email address.
$ wp option update admin_email someone@example.com
Success: Updated 'admin_email' option.

# Set the default role.
$ wp option update default_role author
Success: Updated 'default_role' option.

# Set the timezone string.
$ wp option update timezone_string "America/New_York"
Success: Updated 'timezone_string' option.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/option/update/\#global-parameters)

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