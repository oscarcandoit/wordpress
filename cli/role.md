---
url: https://developer.wordpress.org/cli/commands/role/
scraped_at: 2025-10-20T03:14:46.966Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/role/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp role


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp role

Search

# [wp role\  <command>](https://developer.wordpress.org/cli/commands/role/)

Manages user roles, including creating new roles and resetting to defaults.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/role/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/role/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/role/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/role-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Arole+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (27)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Arole+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/role-command/issues/new)

See references for [Roles and Capabilities](https://codex.wordpress.org/Roles_and_Capabilities) and [WP User class](https://codex.wordpress.org/Class_Reference/WP_User).

### [Examples](https://developer.wordpress.org/cli/commands/role/\#examples)

```
# List roles.
$ wp role list --fields=role --format=csv
role
administrator
editor
author
contributor
subscriber

# Check to see if a role exists.
$ wp role exists editor
Success: Role with ID 'editor' exists.

# Create a new role.
$ wp role create approver Approver
Success: Role with key 'approver' created.

# Delete an existing role.
$ wp role delete approver
Success: Role with key 'approver' deleted.

# Reset existing roles to their default capabilities.
$ wp role reset administrator author contributor
Success: Reset 3/3 roles.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/role/\#subcommands)

| Name | Description |
| --- | --- |
| [wp role create](https://developer.wordpress.org/cli/commands/role/create/) | Creates a new role. |
| [wp role delete](https://developer.wordpress.org/cli/commands/role/delete/) | Deletes an existing role. |
| [wp role exists](https://developer.wordpress.org/cli/commands/role/exists/) | Checks if a role exists. |
| [wp role list](https://developer.wordpress.org/cli/commands/role/list/) | Lists all roles. |
| [wp role reset](https://developer.wordpress.org/cli/commands/role/reset/) | Resets any default role to default capabilities. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications