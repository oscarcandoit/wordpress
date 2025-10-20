---
url: https://developer.wordpress.org/cli/commands/post-type/
scraped_at: 2025-10-20T03:14:25.008Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/post-type/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp post-type


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp post-type

Search

# [wp post-type\  <command>](https://developer.wordpress.org/cli/commands/post-type/)

Retrieves details on the site’s registered post types.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/post-type/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/post-type/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/post-type/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-type+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-type+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

Get information on WordPress’ built-in and the site’s [custom post types](https://developer.wordpress.org/plugins/post-types/).

### [Examples](https://developer.wordpress.org/cli/commands/post-type/\#examples)

```
# Get details about a post type
$ wp post-type get page --fields=name,label,hierarchical --format=json
{"name":"page","label":"Pages","hierarchical":true}

# List post types with 'post' capability type
$ wp post-type list --capability_type=post --fields=name,public
+---------------+--------+
| name          | public |
+---------------+--------+
| post          | 1      |
| attachment    | 1      |
| revision      |        |
| nav_menu_item |        |
+---------------+--------+

```

### [Subcommands](https://developer.wordpress.org/cli/commands/post-type/\#subcommands)

| Name | Description |
| --- | --- |
| [wp post-type get](https://developer.wordpress.org/cli/commands/post-type/get/) | Gets details about a registered post type. |
| [wp post-type list](https://developer.wordpress.org/cli/commands/post-type/list/) | Lists registered post types. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications