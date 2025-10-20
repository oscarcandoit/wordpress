---
url: https://developer.wordpress.org/cli/commands/site/
scraped_at: 2025-10-20T03:15:55.482Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/site/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp site


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp site

Search

# [wp site\  <command>](https://developer.wordpress.org/cli/commands/site/)

Creates, deletes, empties, moderates, and lists one or more sites on a multisite installation.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/site/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/site/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/site/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asite+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Asite+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/site/\#examples)

```
# Create site
$ wp site create --slug=example
Success: Site 3 created: www.example.com/example/

# Output a simple list of site URLs
$ wp site list --field=url
http://www.example.com/
http://www.example.com/subdir/

# Delete site
$ wp site delete 123
Are you sure you want to delete the 'http://www.example.com/example' site? [y/n] y
Success: The site at 'http://www.example.com/example' was deleted.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/site/\#subcommands)

| Name | Description |
| --- | --- |
| [wp site activate](https://developer.wordpress.org/cli/commands/site/activate/) | Activates one or more sites. |
| [wp site archive](https://developer.wordpress.org/cli/commands/site/archive/) | Archives one or more sites. |
| [wp site create](https://developer.wordpress.org/cli/commands/site/create/) | Creates a site in a multisite installation. |
| [wp site deactivate](https://developer.wordpress.org/cli/commands/site/deactivate/) | Deactivates one or more sites. |
| [wp site delete](https://developer.wordpress.org/cli/commands/site/delete/) | Deletes a site in a multisite installation. |
| [wp site empty](https://developer.wordpress.org/cli/commands/site/empty/) | Empties a site of its content (posts, comments, terms, and meta). |
| [wp site generate](https://developer.wordpress.org/cli/commands/site/generate/) | Generate some sites. |
| [wp site list](https://developer.wordpress.org/cli/commands/site/list/) | Lists all sites in a multisite installation. |
| [wp site mature](https://developer.wordpress.org/cli/commands/site/mature/) | Sets one or more sites as mature. |
| [wp site meta](https://developer.wordpress.org/cli/commands/site/meta/) | Adds, updates, deletes, and lists site custom fields. |
| [wp site option](https://developer.wordpress.org/cli/commands/site/option/) | Adds, updates, deletes, and lists site options in a multisite installation. |
| [wp site private](https://developer.wordpress.org/cli/commands/site/private/) | Sets one or more sites as private. |
| [wp site public](https://developer.wordpress.org/cli/commands/site/public/) | Sets one or more sites as public. |
| [wp site spam](https://developer.wordpress.org/cli/commands/site/spam/) | Marks one or more sites as spam. |
| [wp site switch-language](https://developer.wordpress.org/cli/commands/site/switch-language/) | Activates a given language. |
| [wp site unarchive](https://developer.wordpress.org/cli/commands/site/unarchive/) | Unarchives one or more sites. |
| [wp site unmature](https://developer.wordpress.org/cli/commands/site/unmature/) | Sets one or more sites as immature. |
| [wp site unspam](https://developer.wordpress.org/cli/commands/site/unspam/) | Removes one or more sites from spam. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications