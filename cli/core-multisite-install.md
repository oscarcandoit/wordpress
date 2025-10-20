---
url: https://developer.wordpress.org/cli/commands/core/multisite-install/
scraped_at: 2025-10-20T03:02:05.942Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/core/multisite-install/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp core multisite-install


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp core](https://developer.wordpress.org/cli/commands/core/)wp core multisite-install

Search

# [wp core multisite-install](https://developer.wordpress.org/cli/commands/core/multisite-install/)

Installs WordPress multisite from scratch.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/core/multisite-install/#options)
- [Examples](https://developer.wordpress.org/cli/commands/core/multisite-install/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/core/multisite-install/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/core/multisite-install/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/core-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore-multisite-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (17)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore-multisite-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/core-command/issues/new)

Creates the WordPress tables in the database using the URL, title, and default admin user details provided. Then, creates the multisite tables in the database and adds multisite constants to the wp-config.php.

For those using WordPress with Apache, remember to update the `.htaccess` file with the appropriate multisite rewrite rules.

### [Options](https://developer.wordpress.org/cli/commands/core/multisite-install/\#options)

\[--url=<url>\]The address of the new site.\[--base=<url-path>\]Base path after the domain name that each site url in the network will start with.

—

default: /

—

\[--subdomains\]If passed, the network will use subdomains, instead of subdirectories. Doesn’t work with ‘localhost’.--title=<site-title>The title of the new site.--admin\_user=<username>The name of the admin user.

—

default: admin

—

\[--admin\_password=<password>\]The password for the admin user. Defaults to randomly generated string.--admin\_email=<email>The email address for the admin user.\[--skip-email\]Don’t send an email notification to the new admin user.\[--skip-config\]Don’t add multisite constants to wp-config.php.

### [Examples](https://developer.wordpress.org/cli/commands/core/multisite-install/\#examples)

```
$ wp core multisite-install --title="Welcome to the WordPress" \
> --admin_user="admin" --admin_password="password" \
> --admin_email="user@example.com"
Single site database tables already present.
Set up multisite database tables.
Added multisite constants to wp-config.php.
Success: Network installed. Don't forget to set up rewrite rules.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/core/multisite-install/\#global-parameters)

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