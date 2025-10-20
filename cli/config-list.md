---
url: https://developer.wordpress.org/cli/commands/config/list/
scraped_at: 2025-10-20T03:01:38.590Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/config/list/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp config list


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp config](https://developer.wordpress.org/cli/commands/config/)wp config list

Search

# [wp config list](https://developer.wordpress.org/cli/commands/config/list/)

Lists variables, constants, and file includes defined in wp-config.php file.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/config/list/#options)
- [Examples](https://developer.wordpress.org/cli/commands/config/list/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/config/list/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/config/list/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/config-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig-list+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/config-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

### [Options](https://developer.wordpress.org/cli/commands/config/list/\#options)

\[<filter>…\]Name or partial name to filter the list by.\[--fields=<fields>\]Limit the output to specific fields. Defaults to all fields.\[--format=<format>\]Render output in a particular format. Dotenv is limited to non-object values.

—

default: table

options:

– table

– csv

– json

– yaml

– dotenv

—

\[--strict\]Enforce strict matching when a filter is provided.\[--config-file=<path>\]Specify the file path to the config file to be read. Defaults to the root of the WordPress installation and the filename “wp-config.php”.

### [Examples](https://developer.wordpress.org/cli/commands/config/list/\#examples)

```
# List constants and variables defined in wp-config.php file.
$ wp config list
+------------------+------------------------------------------------------------------+----------+
| key              | value                                                            | type     |
+------------------+------------------------------------------------------------------+----------+
| table_prefix     | wp_                                                              | variable |
| DB_NAME          | wp_cli_test                                                      | constant |
| DB_USER          | root                                                             | constant |
| DB_PASSWORD      | root                                                             | constant |
| AUTH_KEY         | r6+@shP1yO&amp;$)1gdu.hl[/j;7Zrvmt~o;#WxSsa0mlQOi24j2cR,7i+QM/#7S:o^ | constant |\
| SECURE_AUTH_KEY  | iO-z!_m--YH$Tx2tf/&amp;V,YW*13Z_HiRLqi)d?$o-tMdY+82pK$`T.NYW~iTLW;xp | constant |\
+------------------+------------------------------------------------------------------+----------+\
\
# List only database user and password from wp-config.php file.\
$ wp config list DB_USER DB_PASSWORD --strict\
+------------------+-------+----------+\
| key              | value | type     |\
+------------------+-------+----------+\
| DB_USER          | root  | constant |\
| DB_PASSWORD      | root  | constant |\
+------------------+-------+----------+\
\
# List all salts from wp-config.php file.\
$ wp config list _SALT\
+------------------+------------------------------------------------------------------+----------+\
| key              | value                                                            | type     |\
+------------------+------------------------------------------------------------------+----------+\
| AUTH_SALT        | n:]Xditk+_7&gt;Qi=>BmtZHiH-6/Ecrvl(V5ceeGP:{&gt;?;BT^=[B3-0&gt;,~F5z$(+Q$ | constant |\
| SECURE_AUTH_SALT | ?Z/p|XhDw3w}?c.z%|+BAr|(Iv*H%%U+Du&amp;kKR y?cJOYyRVRBeB[2zF-`(&gt;+LCC | constant |\
| LOGGED_IN_SALT   | +$@(1{b~Z~s}Cs&gt;8Y]6[m6~TnoCDpE&gt;O%e75u}&amp;6kUH!&gt;q:7uM4lxbB6[1pa_X,q | constant |\
| NONCE_SALT       | _x+F li|QL?0OSQns1_JZ{|Ix3Jleox-71km/gifnyz8kmo=w-;@AE8W,(fP&lt;N}2 | constant |\
+------------------+------------------------------------------------------------------+----------+\
\
```\
\
### [Global Parameters](https://developer.wordpress.org/cli/commands/config/list/\#global-parameters)\
\
These [global parameters](https://make.wordpress.org/cli/handbook/config/) have the same behavior across all commands and affect how WP-CLI interacts with WordPress.\
\
| **Argument** | **Description** |\
| :-- | :-- |\
| `--path=<path>` | Path to the WordPress files. |\
| `--url=<url>` | Pretend request came from given URL. In multisite, this argument is how the target site is specified. |\
| `--ssh=[<scheme>:][<user>@]<host\|container>[:<port>][<path>]` | Perform operation against a remote server over SSH (or a container using scheme of “docker”, “docker-compose”, “docker-compose-run”, “vagrant”). |\
| `--http=<http>` | Perform operation against a remote WordPress installation over HTTP. |\
| `--user=<id\|login\|email>` | Set the WordPress user. |\
| `--skip-plugins[=<plugins>]` | Skip loading all plugins, or a comma-separated list of plugins. Note: mu-plugins are still loaded. |\
| `--skip-themes[=<themes>]` | Skip loading all themes, or a comma-separated list of themes. |\
| `--skip-packages` | Skip loading all installed packages. |\
| `--require=<path>` | Load PHP file before running the command (may be used more than once). |\
| `--exec=<php-code>` | Execute PHP code before running the command (may be used more than once). |\
| `--context=<context>` | Load WordPress in a given context. |\
| `--[no-]color` | Whether to colorize the output. |\
| `--debug[=<group>]` | Show all PHP errors and add verbosity to WP-CLI output. Built-in groups include: bootstrap, commandfactory, and help. |\
| `--prompt[=<assoc>]` | Prompt the user to enter values for all command arguments, or a subset specified as comma-separated values. |\
| `--quiet` | Suppress informational messages. |\
\
_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._\
\
Notifications