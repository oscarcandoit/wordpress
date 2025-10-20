---
url: https://developer.wordpress.org/cli/commands/dist-archive/
scraped_at: 2025-10-20T03:04:53.027Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/dist-archive/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp dist-archive


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp dist-archive

Search

# [wp dist-archive](https://developer.wordpress.org/cli/commands/dist-archive/)

Create a distribution archive based on a project’s .distignore file.

## In this article

Table of Contents

- [Installing](https://developer.wordpress.org/cli/commands/dist-archive/#installing)
- [Options](https://developer.wordpress.org/cli/commands/dist-archive/#options)
- [Global Parameters](https://developer.wordpress.org/cli/commands/dist-archive/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/dist-archive/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/dist-archive-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adist-archive+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Adist-archive+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/dist-archive-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

For a plugin in a directory ‘wp-content/plugins/hello-world’, this command creates a distribution archive ‘wp-content/plugins/hello-world.zip’.

You can specify files or directories you’d like to exclude from the archive with a .distignore file in your project repository:

```
.distignore
.editorconfig
.git
.gitignore
.travis.yml
circle.yml

```

Use one distribution archive command for many projects, instead of a bash script in each project.

### [Installing](https://developer.wordpress.org/cli/commands/dist-archive/\#installing)

Use the `wp dist-archive` command by installing the command’s package:

```
wp package install wp-cli/dist-archive-command
```

Once the package is successfully installed, the `wp dist-archive` command will appear in the list of available commands.

### [Options](https://developer.wordpress.org/cli/commands/dist-archive/\#options)

<path>Path to the project that includes a .distignore file.\[<target>\]Path and optional file name for the distribution archive. If only a path is provided, the file name defaults to the project directory name plus the version, if discoverable. Also, if only a path is given, the directory that it points to has to already exist for the command to function correctly.\[--create-target-dir\]Automatically create the target directory as needed.\[--force\]Forces overwriting of the archive file if it already exists.\[--plugin-dirname=<plugin-slug>\]Set the archive extract directory name. Defaults to project directory name.\[--format=<format>\]Choose the format for the archive.

—

default: zip

options:

– zip

– targz

—

\[--filename-format=<filename-format>\]Use a custom format for archive filename. Available substitutions: {name}, {version}. This is ignored if the <target> parameter is provided or the version cannot be determined.

—

default: “{name}.{version}”

—

### [Global Parameters](https://developer.wordpress.org/cli/commands/dist-archive/\#global-parameters)

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