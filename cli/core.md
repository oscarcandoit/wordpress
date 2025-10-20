---
url: https://developer.wordpress.org/cli/commands/core/
scraped_at: 2025-10-20T03:01:48.139Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/core/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp core


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp core

Search

# [wp core\  <command>](https://developer.wordpress.org/cli/commands/core/)

Downloads, installs, updates, and manages a WordPress installation.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/core/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/core/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/core/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/core-command)

[View Open Issues (7)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (150)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acore+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/core-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/core/\#examples)

```
# Download WordPress core
$ wp core download --locale=nl_NL
Downloading WordPress 4.5.2 (nl_NL)...
md5 hash verified: c5366d05b521831dd0b29dfc386e56a5
Success: WordPress downloaded.

# Install WordPress
$ wp core install --url=example.com --title=Example --admin_user=supervisor --admin_password=strongpassword --admin_email=info@example.com
Success: WordPress installed successfully.

# Display the WordPress version
$ wp core version
4.5.2

```

### [Subcommands](https://developer.wordpress.org/cli/commands/core/\#subcommands)

| Name | Description |
| --- | --- |
| [wp core check-update](https://developer.wordpress.org/cli/commands/core/check-update/) | Checks for WordPress updates via Version Check API. |
| [wp core download](https://developer.wordpress.org/cli/commands/core/download/) | Downloads core WordPress files. |
| [wp core install](https://developer.wordpress.org/cli/commands/core/install/) | Runs the standard WordPress installation process. |
| [wp core is-installed](https://developer.wordpress.org/cli/commands/core/is-installed/) | Checks if WordPress is installed. |
| [wp core multisite-convert](https://developer.wordpress.org/cli/commands/core/multisite-convert/) | Transforms an existing single-site installation into a multisite installation. |
| [wp core multisite-install](https://developer.wordpress.org/cli/commands/core/multisite-install/) | Installs WordPress multisite from scratch. |
| [wp core update](https://developer.wordpress.org/cli/commands/core/update/) | Updates WordPress to a newer version. |
| [wp core update-db](https://developer.wordpress.org/cli/commands/core/update-db/) | Runs the WordPress database update procedure. |
| [wp core verify-checksums](https://developer.wordpress.org/cli/commands/core/verify-checksums/) | Verifies WordPress files against WordPress.org’s checksums. |
| [wp core version](https://developer.wordpress.org/cli/commands/core/version/) | Displays the WordPress version. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications