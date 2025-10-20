---
url: https://developer.wordpress.org/cli/commands/package/install/
scraped_at: 2025-10-20T03:09:59.519Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/package/install/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp package install


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp package](https://developer.wordpress.org/cli/commands/package/)wp package install

Search

# [wp package install](https://developer.wordpress.org/cli/commands/package/install/)

Installs a WP-CLI package.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/package/install/#options)
- [Examples](https://developer.wordpress.org/cli/commands/package/install/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/package/install/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/package/install/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/package-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apackage-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apackage-install+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/package-command/issues/new)

This command runs on the `before_wp_load` hook, just before the WP load process begins.

Packages are required to be a valid Composer package, and can be specified as:

- Package name from WP-CLI’s package index.
- Git URL accessible by the current shell user.
- Path to a directory on the local machine.
- Local or remote .zip file.

Packages are installed to `~/.wp-cli/packages/` by default. Use the `WP_CLI_PACKAGES_DIR` environment variable to provide a custom path.

When installing a local directory, WP-CLI simply registers a reference to the directory. If you move or delete the directory, WP-CLI’s reference breaks.

When installing a .zip file, WP-CLI extracts the package to `~/.wp-cli/packages/local/&lt;package-name&gt;`.

If Github token authorization is required, a GitHub Personal Access Token (https://github.com/settings/tokens) can be used. The following command will add a GitHub Personal Access Token to Composer’s global configuration:
composer config -g github-oauth.github.com <GITHUB\_TOKEN> Once this has been added, the value used for <GITHUB\_TOKEN> will be used for future authorization requests.

### [Options](https://developer.wordpress.org/cli/commands/package/install/\#options)

<name\|git\|path\|zip>Name, git URL, directory path, or .zip file for the package to install. Names can optionally include a version constraint (e.g. wp-cli/server-command:@stable).\[--insecure\]Retry downloads without certificate validation if TLS handshake fails. Note: This makes the request vulnerable to a MITM attack.

### [Examples](https://developer.wordpress.org/cli/commands/package/install/\#examples)

```
# Install a package hosted at a git URL.
$ wp package install runcommand/hook

# Install the latest stable version.
$ wp package install wp-cli/server-command:@stable

# Install a package hosted at a GitLab.com URL.
$ wp package install https://gitlab.com/foo/wp-cli-bar-command.git

# Install a package in a .zip file.
$ wp package install google-sitemap-generator-cli.zip

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/package/install/\#global-parameters)

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