---
url: https://developer.wordpress.org/cli/commands/embed/handler/
scraped_at: 2025-10-20T03:05:32.166Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/embed-2/handler/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp embed handler


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp embed](https://developer.wordpress.org/cli/commands/embed-2/)wp embed handler

Search

# [wp embed handler\  <command>](https://developer.wordpress.org/cli/commands/embed-2/handler/)

Retrieves embed handlers.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/embed-2/handler/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/embed-2/handler/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/embed-2/handler/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/embed-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aembed-handler+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aembed-handler+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/embed-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/embed-2/handler/\#examples)

```
# List id,regex,priority fields of available handlers.
$ wp embed handler list --fields=priority,id
+----------+-------------------+
| priority | id                |
+----------+-------------------+
| 10       | youtube_embed_url |
| 9999     | audio             |
| 9999     | video             |

```

### [Subcommands](https://developer.wordpress.org/cli/commands/embed-2/handler/\#subcommands)

| Name | Description |
| --- | --- |
| [wp embed handler list](https://developer.wordpress.org/cli/commands/embed-2/handler/list/) | Lists all available embed handlers. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications