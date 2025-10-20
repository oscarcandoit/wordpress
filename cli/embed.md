---
url: https://developer.wordpress.org/cli/commands/embed/
scraped_at: 2025-10-20T03:04:57.174Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/embed-2/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp embed


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp embed

Search

# [wp embed\  <command>](https://developer.wordpress.org/cli/commands/embed-2/)

Inspects oEmbed providers, clears embed cache, and more.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/embed-2/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/embed-2/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/embed-2/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/embed-command)

[View Open Issues (2)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aembed+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (3)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aembed+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/embed-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/embed-2/\#examples)

```
# Get embed HTML for a given URL.
$ wp embed fetch https://www.youtube.com/watch?v=dQw4w9WgXcQ
&lt;iframe width="525" height="295" src="https://www.youtube.com/embed/dQw4w9WgXcQ?feature=oembed" ...

# Find cache post ID for a given URL.
$ wp embed cache find https://www.youtube.com/watch?v=dQw4w9WgXcQ --width=500
123

# List format,endpoint fields of available providers.
$ wp embed provider list
+------------------------------+-----------------------------------------+
| format                       | endpoint                                |
+------------------------------+-----------------------------------------+
| #https?://youtu\.be/.*#i     | https://www.youtube.com/oembed          |
| #https?://flic\.kr/.*#i      | https://www.flickr.com/services/oembed/ |
| #https?://wordpress\.tv/.*#i | https://wordpress.tv/oembed/            |

# List id,regex,priority fields of available handlers.
$ wp embed handler list --fields=priority,id
+----------+-------------------+
| priority | id                |
+----------+-------------------+
| 10       | youtube_embed_url |
| 9999     | audio             |
| 9999     | video             |
+----------+-------------------+

```

### [Subcommands](https://developer.wordpress.org/cli/commands/embed-2/\#subcommands)

| Name | Description |
| --- | --- |
| [wp embed cache](https://developer.wordpress.org/cli/commands/embed-2/cache/) | Finds, triggers, and deletes oEmbed caches. |
| [wp embed fetch](https://developer.wordpress.org/cli/commands/embed-2/fetch/) | Attempts to convert a URL into embed HTML. |
| [wp embed handler](https://developer.wordpress.org/cli/commands/embed-2/handler/) | Retrieves embed handlers. |
| [wp embed provider](https://developer.wordpress.org/cli/commands/embed-2/provider/) | Retrieves oEmbed providers. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications