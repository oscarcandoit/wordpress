---
url: https://developer.wordpress.org/cli/commands/scaffold/plugin/
scraped_at: 2025-10-20T03:15:05.685Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/scaffold/plugin/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp scaffold plugin


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp scaffold](https://developer.wordpress.org/cli/commands/scaffold/)wp scaffold plugin

Search

# [wp scaffold plugin](https://developer.wordpress.org/cli/commands/scaffold/plugin/)

Generates starter code for a plugin.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/scaffold/plugin/#options)
- [Examples](https://developer.wordpress.org/cli/commands/scaffold/plugin/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/scaffold/plugin/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/scaffold/plugin/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/scaffold-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Ascaffold-plugin+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Ascaffold-plugin+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/scaffold-command/issues/new)

The following files are always generated:

- `plugin-slug.php` is the main PHP plugin file.
- `readme.txt` is the readme file for the plugin.
- `package.json` needed by NPM holds various metadata relevant to the project. Packages: `grunt`, `grunt-wp-i18n` and `grunt-wp-readme-to-markdown`. Scripts: `start`, `readme`, `i18n`.
- `Gruntfile.js` is the JS file containing Grunt tasks. Tasks: `i18n` containing `addtextdomain` and `makepot`, `readme` containing `wp_readme_to_markdown`.
- `.editorconfig` is the configuration file for Editor.
- `.gitignore` tells which files (or patterns) git should ignore.
- `.distignore` tells which files and folders should be ignored in distribution.

The following files are also included unless the `--skip-tests` is used:

- `phpunit.xml.dist` is the configuration file for PHPUnit.
- `.circleci/config.yml` is the configuration file for CircleCI. Use `--ci=&lt;provider&gt;` to select a different service.
- `bin/install-wp-tests.sh` configures the WordPress test suite and a test database.
- `tests/bootstrap.php` is the file that makes the current plugin active when running the test suite.
- `tests/test-sample.php` is a sample file containing test cases.
- `.phpcs.xml.dist` is a collection of PHP\_CodeSniffer rules.

### [Options](https://developer.wordpress.org/cli/commands/scaffold/plugin/\#options)

<slug>The internal name of the plugin.\[--dir=<dirname>\]Put the new plugin in some arbitrary directory path. Plugin directory will be path plus supplied slug.\[--plugin\_name=<title>\]What to put in the ‘Plugin Name:’ header.\[--plugin\_description=<description>\]What to put in the ‘Description:’ header.\[--plugin\_author=<author>\]What to put in the ‘Author:’ header.\[--plugin\_author\_uri=<url>\]What to put in the ‘Author URI:’ header.\[--plugin\_uri=<url>\]What to put in the ‘Plugin URI:’ header.\[--skip-tests\]Don’t generate files for unit testing.\[--ci=<provider>\]Choose a configuration file for a continuous integration provider.

—

default: circle

options:

– circle

– gitlab

– bitbucket

– github

—

\[--activate\]Activate the newly generated plugin.\[--activate-network\]Network activate the newly generated plugin.\[--force\]Overwrite files that already exist.

### [Examples](https://developer.wordpress.org/cli/commands/scaffold/plugin/\#examples)

```
$ wp scaffold plugin sample-plugin
Success: Created plugin files.
Success: Created test files.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/scaffold/plugin/\#global-parameters)

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