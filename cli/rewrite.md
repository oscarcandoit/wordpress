---
url: https://developer.wordpress.org/cli/commands/rewrite/
scraped_at: 2025-10-20T03:14:34.349Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/rewrite/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp rewrite


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp rewrite

Search

# [wp rewrite\  <command>](https://developer.wordpress.org/cli/commands/rewrite/)

Lists or flushes the site’s rewrite rules, updates the permalink structure.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/rewrite/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/rewrite/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/rewrite/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/rewrite-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Arewrite+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (31)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Arewrite+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/rewrite-command/issues/new)

See the WordPress [Rewrite API](https://codex.wordpress.org/Rewrite_API) and
[WP Rewrite](https://codex.wordpress.org/Class_Reference/WP_Rewrite) class reference.

### [Examples](https://developer.wordpress.org/cli/commands/rewrite/\#examples)

```
# Flush rewrite rules
$ wp rewrite flush
Success: Rewrite rules flushed.

# Update permalink structure
$ wp rewrite structure '/%year%/%monthnum%/%postname%'
Success: Rewrite structure set.

# List rewrite rules
$ wp rewrite list --format=csv
match,query,source
^wp-json/?$,index.php?rest_route=/,other
^wp-json/(.*)?,index.php?rest_route=/$matches[1],other
category/(.+?)/feed/(feed|rdf|rss|rss2|atom)/?$,index.php?category_name=$matches[1]&amp;feed=$matches[2],category
category/(.+?)/(feed|rdf|rss|rss2|atom)/?$,index.php?category_name=$matches[1]&amp;feed=$matches[2],category
category/(.+?)/embed/?$,index.php?category_name=$matches[1]&amp;embed=true,category

```

### [Subcommands](https://developer.wordpress.org/cli/commands/rewrite/\#subcommands)

| Name | Description |
| --- | --- |
| [wp rewrite flush](https://developer.wordpress.org/cli/commands/rewrite/flush/) | Flushes rewrite rules. |
| [wp rewrite list](https://developer.wordpress.org/cli/commands/rewrite/list/) | Gets a list of the current rewrite rules. |
| [wp rewrite structure](https://developer.wordpress.org/cli/commands/rewrite/structure/) | Updates the permalink structure. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications