---
url: https://developer.wordpress.org/cli/commands/embed/provider/
scraped_at: 2025-10-20T03:05:40.227Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/embed-2/provider/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp embed provider


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp embed](https://developer.wordpress.org/cli/commands/embed-2/)wp embed provider

Search

# [wp embed provider\  <command>](https://developer.wordpress.org/cli/commands/embed-2/provider/)

Retrieves oEmbed providers.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/embed-2/provider/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/embed-2/provider/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/embed-2/provider/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/embed-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aembed-provider+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aembed-provider+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/embed-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/embed-2/provider/\#examples)

```
# List format,endpoint fields of available providers.
$ wp embed provider list
+------------------------------+-----------------------------------------+
| format                       | endpoint                                |
+------------------------------+-----------------------------------------+
| #https?://youtu\.be/.*#i     | https://www.youtube.com/oembed          |
| #https?://flic\.kr/.*#i      | https://www.flickr.com/services/oembed/ |
| #https?://wordpress\.tv/.*#i | https://wordpress.tv/oembed/            |

# Get the matching provider for the URL.
$ wp embed provider match https://www.youtube.com/watch?v=dQw4w9WgXcQ
https://www.youtube.com/oembed

```

### [Subcommands](https://developer.wordpress.org/cli/commands/embed-2/provider/\#subcommands)

| Name | Description |
| --- | --- |
| [wp embed provider list](https://developer.wordpress.org/cli/commands/embed-2/provider/list/) | Lists all available oEmbed providers. |
| [wp embed provider match](https://developer.wordpress.org/cli/commands/embed-2/provider/match/) | Gets the matching provider for a given URL. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications