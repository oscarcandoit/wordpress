---
url: https://developer.wordpress.org/cli/commands/embed/cache/
scraped_at: 2025-10-20T03:05:01.362Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cache/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cache


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp cache

Search

# [wp cache\  <command>](https://developer.wordpress.org/cli/commands/cache/)

Adds, removes, fetches, and flushes the WP Object Cache object.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/cache/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/cache/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cache/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/cache-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acache+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acache+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/cache-command/issues/new)

By default, the WP Object Cache exists in PHP memory for the length of the request (and is emptied at the end). Use a persistent object cache drop-in to persist the object cache between requests.

[Read the codex article](https://codex.wordpress.org/Class_Reference/WP_Object_Cache) for more detail.

### [Examples](https://developer.wordpress.org/cli/commands/cache/\#examples)

```
# Set cache.
$ wp cache set my_key my_value my_group 300
Success: Set object 'my_key' in group 'my_group'.

# Get cache.
$ wp cache get my_key my_group
my_value

```

### [Subcommands](https://developer.wordpress.org/cli/commands/cache/\#subcommands)

| Name | Description |
| --- | --- |
| [wp cache add](https://developer.wordpress.org/cli/commands/cache/add/) | Adds a value to the object cache. |
| [wp cache decr](https://developer.wordpress.org/cli/commands/cache/decr/) | Decrements a value in the object cache. |
| [wp cache delete](https://developer.wordpress.org/cli/commands/cache/delete/) | Removes a value from the object cache. |
| [wp cache flush](https://developer.wordpress.org/cli/commands/cache/flush/) | Flushes the object cache. |
| [wp cache flush-group](https://developer.wordpress.org/cli/commands/cache/flush-group/) | Removes all cache items in a group, if the object cache implementation supports it. |
| [wp cache get](https://developer.wordpress.org/cli/commands/cache/get/) | Gets a value from the object cache. |
| [wp cache incr](https://developer.wordpress.org/cli/commands/cache/incr/) | Increments a value in the object cache. |
| [wp cache replace](https://developer.wordpress.org/cli/commands/cache/replace/) | Replaces a value in the object cache, if the value already exists. |
| [wp cache set](https://developer.wordpress.org/cli/commands/cache/set/) | Sets a value to the object cache, regardless of whether it already exists. |
| [wp cache supports](https://developer.wordpress.org/cli/commands/cache/supports/) | Determines whether the object cache implementation supports a particular feature. |
| [wp cache type](https://developer.wordpress.org/cli/commands/cache/type/) | Attempts to determine which object cache is being used. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications