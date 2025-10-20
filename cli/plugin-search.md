---
url: https://developer.wordpress.org/cli/commands/plugin/search/
scraped_at: 2025-10-20T03:11:58.743Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/plugin/search/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp plugin search


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp plugin](https://developer.wordpress.org/cli/commands/plugin/)wp plugin search

Search

# [wp plugin search](https://developer.wordpress.org/cli/commands/plugin/search/)

Searches the WordPress.org plugin directory.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/plugin/search/#options)
- [Examples](https://developer.wordpress.org/cli/commands/plugin/search/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/plugin/search/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/plugin/search/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/extension-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-search+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (9)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aplugin-search+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/extension-command/issues/new)

Displays plugins in the WordPress.org plugin directory matching a given search query.

### [Options](https://developer.wordpress.org/cli/commands/plugin/search/\#options)

<search>The string to search for.\[--page=<page>\]Optional page to display.

—

default: 1

—

\[--per-page=<per-page>\]Optional number of results to display.

—

default: 10

—

\[--field=<field>\]Prints the value of a single field for each plugin.\[--fields=<fields>\]
Ask for specific fields from the API. Defaults to name,slug,author\_profile,rating. Acceptable values:

**name**: Plugin Name
**slug**: Plugin Slug
**version**: Current Version Number
**author**: Plugin Author
**author\_profile**: Plugin Author Profile
**contributors**: Plugin Contributors
**requires**: Plugin Minimum Requirements
**tested**: Plugin Tested Up To
**compatibility**: Plugin Compatible With
**rating**: Plugin Rating in Percent and Total Number
**ratings**: Plugin Ratings for each star (1-5)
**num\_ratings**: Number of Plugin Ratings
**homepage**: Plugin Author’s Homepage
**description**: Plugin’s Description
**short\_description**: Plugin’s Short Description
**sections**: Plugin Readme Sections: description, installation, FAQ, screenshots, other notes, and changelog
**downloaded**: Plugin Download Count
**last\_updated**: Plugin’s Last Update
**added**: Plugin’s Date Added to wordpress.org Repository
**tags**: Plugin’s Tags
**versions**: Plugin’s Available Versions with D/L Link
**donate\_link**: Plugin’s Donation Link
**banners**: Plugin’s Banner Image Link
**icons**: Plugin’s Icon Image Link
**active\_installs**: Plugin’s Number of Active Installs
**contributors**: Plugin’s List of Contributors
**url**: Plugin’s URL on wordpress.org
\[--format=<format>\]Render output in a particular format.

—

default: table

options:

– table

– csv

– count

– json

– yaml

—

### [Examples](https://developer.wordpress.org/cli/commands/plugin/search/\#examples)

```
$ wp plugin search dsgnwrks --per-page=20 --format=json
Success: Showing 3 of 3 plugins.
[{"name":"DsgnWrks Instagram Importer Debug","slug":"dsgnwrks-instagram-importer-debug","rating":0},{"name":"DsgnWrks Instagram Importer","slug":"dsgnwrks-instagram-importer","rating":84},{"name":"DsgnWrks Twitter Importer","slug":"dsgnwrks-twitter-importer","rating":80}]

$ wp plugin search dsgnwrks --fields=name,version,slug,rating,num_ratings
Success: Showing 3 of 3 plugins.
+-----------------------------------+---------+-----------------------------------+--------+-------------+
| name                              | version | slug                              | rating | num_ratings |
+-----------------------------------+---------+-----------------------------------+--------+-------------+
| DsgnWrks Instagram Importer Debug | 0.1.6   | dsgnwrks-instagram-importer-debug | 0      | 0           |
| DsgnWrks Instagram Importer       | 1.3.7   | dsgnwrks-instagram-importer       | 84     | 23          |
| DsgnWrks Twitter Importer         | 1.1.1   | dsgnwrks-twitter-importer         | 80     | 1           |
+-----------------------------------+---------+-----------------------------------+--------+-------------+

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/plugin/search/\#global-parameters)

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