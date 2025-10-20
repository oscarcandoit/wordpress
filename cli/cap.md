---
url: https://developer.wordpress.org/cli/commands/cap/
scraped_at: 2025-10-20T02:58:35.633Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cap/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cap


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp cap

Search

# [wp cap\  <command>](https://developer.wordpress.org/cli/commands/cap/)

Adds, removes, and lists capabilities of a user role.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/cap/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/cap/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cap/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/role-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acap+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (20)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acap+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/role-command/issues/new)

See references for [Roles and Capabilities](https://codex.wordpress.org/Roles_and_Capabilities) and [WP User class](https://codex.wordpress.org/Class_Reference/WP_User).

### [Examples](https://developer.wordpress.org/cli/commands/cap/\#examples)

```
# Add 'spectate' capability to 'author' role.
$ wp cap add 'author' 'spectate'
Success: Added 1 capability to 'author' role.

# Add all caps from 'editor' role to 'author' role.
$ wp cap list 'editor' | xargs wp cap add 'author'
Success: Added 24 capabilities to 'author' role.

# Remove all caps from 'editor' role that also appear in 'author' role.
$ wp cap list 'author' | xargs wp cap remove 'editor'
Success: Removed 34 capabilities from 'editor' role.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/cap/\#subcommands)

| Name | Description |
| --- | --- |
| [wp cap add](https://developer.wordpress.org/cli/commands/cap/add/) | Adds capabilities to a given role. |
| [wp cap list](https://developer.wordpress.org/cli/commands/cap/list/) | Lists capabilities for a given role. |
| [wp cap remove](https://developer.wordpress.org/cli/commands/cap/remove/) | Removes capabilities from a given role. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications