---
url: https://developer.wordpress.org/cli/commands/i18n/make-json/
scraped_at: 2025-10-20T03:06:05.203Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/i18n/make-json/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp i18n make-json


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp i18n](https://developer.wordpress.org/cli/commands/i18n/)wp i18n make-json

Search

# [wp i18n make-json](https://developer.wordpress.org/cli/commands/i18n/make-json/)

Extract JavaScript strings from PO files and add them to individual JSON files.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/i18n/make-json/#options)
- [Examples](https://developer.wordpress.org/cli/commands/i18n/make-json/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/i18n/make-json/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/i18n/make-json/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/i18n-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Ai18n-make-json+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Ai18n-make-json+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/i18n-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

For JavaScript internationalization purposes, WordPress requires translations to be split up into one Jed-formatted JSON file per JavaScript source file.

See https://make.wordpress.org/core/2018/11/09/new-javascript-i18n-support-in-wordpress/ to learn more about WordPress JavaScript internationalization.

### [Options](https://developer.wordpress.org/cli/commands/i18n/make-json/\#options)

<source>Path to an existing PO file or a directory containing multiple PO files.\[<destination>\]Path to the destination directory for the resulting JSON files. Defaults to the source directory.\[--domain=<domain>\]Text domain to use for the JSON file name. Overrides the default one extracted from the PO file.\[--extensions=<extensions>\]Additional custom JS extensions, comma separated list. By default searches for .min.js and .js extensions.\[--purge\]Whether to purge the strings that were extracted from the original source file. Defaults to true, use `--no-purge` to skip the removal.\[--update-mo-files\]Whether MO files should be updated as well after updating PO files. Only has an effect when used in combination with `--purge`.\[--pretty-print\]Pretty-print resulting JSON files.\[--use-map=<paths\_or\_maps>\]Whether to use a mapping file for the strings, as a JSON value, array to specify multiple. Each element can either be a string (file path) or object (map).

### [Examples](https://developer.wordpress.org/cli/commands/i18n/make-json/\#examples)

```
# Create JSON files for all PO files in the languages directory
$ wp i18n make-json languages

# Create JSON files for my-plugin-de_DE.po and leave the PO file untouched.
$ wp i18n make-json my-plugin-de_DE.po /tmp --no-purge

# Create JSON files with mapping
$ wp i18n make-json languages --use-map=build/map.json

# Create JSON files with multiple mappings
$ wp i18n make-json languages '--use-map=["build/map.json","build/map2.json"]'

# Create JSON files with object mapping
$ wp i18n make-json languages '--use-map={"source/index.js":"build/index.js"}'

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/i18n/make-json/\#global-parameters)

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