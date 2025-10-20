---
url: https://developer.wordpress.org/cli/commands/cron/schedule/
scraped_at: 2025-10-20T03:03:00.205Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cron/schedule/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cron schedule


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp cron](https://developer.wordpress.org/cli/commands/cron/)wp cron schedule

Search

# [wp cron schedule\  <command>](https://developer.wordpress.org/cli/commands/cron/schedule/)

Gets WP-Cron schedules.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/cron/schedule/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/cron/schedule/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cron/schedule/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/cron-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-schedule+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-schedule+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/cron-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/cron/schedule/\#examples)

```
# List available cron schedules
$ wp cron schedule list
+------------+-------------+----------+
| name       | display     | interval |
+------------+-------------+----------+
| hourly     | Once Hourly | 3600     |
| twicedaily | Twice Daily | 43200    |
| daily      | Once Daily  | 86400    |
+------------+-------------+----------+

```

### [Subcommands](https://developer.wordpress.org/cli/commands/cron/schedule/\#subcommands)

| Name | Description |
| --- | --- |
| [wp cron schedule list](https://developer.wordpress.org/cli/commands/cron/schedule/list/) | List available cron schedules. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications