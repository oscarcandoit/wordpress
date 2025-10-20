---
url: https://developer.wordpress.org/cli/commands/core/install/
scraped_at: 2025-10-20T03:01:54.358Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/core/install/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp core install


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp core](https://developer.wordpress.org/cli/commands/core/)wp core install

Search

# [wp core install](https://developer.wordpress.org/cli/commands/core/install/)

Runs the standard WordPress installation process.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/core/install/#options)
- [Examples](https://developer.wordpress.org/cli/commands/core/install/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/core/install/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/core/install/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/core-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/core-command/issues/new)

Creates the WordPress tables in the database using the URL, title, and default admin user details provided. Performs the famous 5 minute install in seconds or less.

Note: if you’ve installed WordPress in a subdirectory, then you’ll need to `wp option update siteurl` after `wp core install`. For instance, if WordPress is installed in the `/wp` directory and your domain is example.com, then you’ll need to run \`wp option update siteurl http://example.com/wp\` for your WordPress installation to function properly.

Note: When using custom user tables (e.g. `CUSTOM_USER_TABLE`), the admin email and password are ignored if the user\_login already exists. If the user\_login doesn’t exist, a new user will be created.

### [Options](https://developer.wordpress.org/cli/commands/core/install/\#options)

--url=<url>The address of the new site.--title=<site-title>The title of the new site.--admin\_user=<username>The name of the admin user.\[--admin\_password=<password>\]The password for the admin user. Defaults to randomly generated string.--admin\_email=<email>The email address for the admin user.\[--locale=<locale>\]The locale/language for the installation (e.g. `de_DE`). Default is `en_US`.\[--skip-email\]Don’t send an email notification to the new admin user.

### [Examples](https://developer.wordpress.org/cli/commands/core/install/\#examples)

```
# Install WordPress in 5 seconds
$ wp core install --url=example.com --title=Example --admin_user=supervisor --admin_password=strongpassword --admin_email=info@example.com
Success: WordPress installed successfully.

# Install WordPress without disclosing admin_password to bash history
$ wp core install --url=example.com --title=Example --admin_user=supervisor --admin_email=info@example.com --prompt=admin_password < admin_password.txt

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/core/install/\#global-parameters)

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