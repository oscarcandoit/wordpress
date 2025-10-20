---
url: https://developer.wordpress.org/cli/commands/comment/meta/
scraped_at: 2025-10-20T02:59:28.680Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/comment/meta/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp comment meta


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp comment](https://developer.wordpress.org/cli/commands/comment/)wp comment meta

Search

# [wp comment meta\  <command>](https://developer.wordpress.org/cli/commands/comment/meta/)

Adds, updates, deletes, and lists comment custom fields.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/comment/meta/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/comment/meta/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/comment/meta/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment-meta+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment-meta+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/comment/meta/\#examples)

```
# Set comment meta
$ wp comment meta set 123 description "Mary is a WordPress developer."
Success: Updated custom field 'description'.

# Get comment meta
$ wp comment meta get 123 description
Mary is a WordPress developer.

# Update comment meta
$ wp comment meta update 123 description "Mary is an awesome WordPress developer."
Success: Updated custom field 'description'.

# Delete comment meta
$ wp comment meta delete 123 description
Success: Deleted custom field.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/comment/meta/\#subcommands)

| Name | Description |
| --- | --- |
| [wp comment meta add](https://developer.wordpress.org/cli/commands/comment/meta/add/) | Add a meta field. |
| [wp comment meta delete](https://developer.wordpress.org/cli/commands/comment/meta/delete/) | Delete a meta field. |
| [wp comment meta get](https://developer.wordpress.org/cli/commands/comment/meta/get/) | Get meta field value. |
| [wp comment meta list](https://developer.wordpress.org/cli/commands/comment/meta/list/) | List all metadata associated with an object. |
| [wp comment meta patch](https://developer.wordpress.org/cli/commands/comment/meta/patch/) | Update a nested value for a meta field. |
| [wp comment meta pluck](https://developer.wordpress.org/cli/commands/comment/meta/pluck/) | Get a nested value from a meta field. |
| [wp comment meta update](https://developer.wordpress.org/cli/commands/comment/meta/update/) | Update a meta field. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications