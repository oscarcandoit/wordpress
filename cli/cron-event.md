---
url: https://developer.wordpress.org/cli/commands/cron/event/
scraped_at: 2025-10-20T03:02:30.445Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/cron/event/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp cron event


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp cron](https://developer.wordpress.org/cli/commands/cron/)wp cron event

Search

# [wp cron event\  <command>](https://developer.wordpress.org/cli/commands/cron/event/)

Schedules, runs, and deletes WP-Cron events.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/cron/event/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/cron/event/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/cron/event/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/cron-command)

[View Open Issues (2)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-event+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (23)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acron-event+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/cron-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/cron/event/\#examples)

```
# Schedule a new cron event
$ wp cron event schedule cron_test
Success: Scheduled event with hook 'cron_test' for 2016-05-31 10:19:16 GMT.

# Run all cron events due right now
$ wp cron event run --due-now
Executed the cron event 'cron_test_1' in 0.01s.
Executed the cron event 'cron_test_2' in 0.006s.
Success: Executed a total of 2 cron events.

# Delete all scheduled cron events for the given hook
$ wp cron event delete cron_test
Success: Deleted a total of 2 cron events.

# List scheduled cron events in JSON
$ wp cron event list --fields=hook,next_run --format=json
[{"hook":"wp_version_check","next_run":"2016-05-31 10:15:13"},{"hook":"wp_update_plugins","next_run":"2016-05-31 10:15:13"},{"hook":"wp_update_themes","next_run":"2016-05-31 10:15:14"}]

```

### [Subcommands](https://developer.wordpress.org/cli/commands/cron/event/\#subcommands)

| Name | Description |
| --- | --- |
| [wp cron event delete](https://developer.wordpress.org/cli/commands/cron/event/delete/) | Deletes all scheduled cron events for the given hook. |
| [wp cron event list](https://developer.wordpress.org/cli/commands/cron/event/list/) | Lists scheduled cron events. |
| [wp cron event run](https://developer.wordpress.org/cli/commands/cron/event/run/) | Runs the next scheduled cron event for the given hook. |
| [wp cron event schedule](https://developer.wordpress.org/cli/commands/cron/event/schedule/) | Schedules a new cron event. |
| [wp cron event unschedule](https://developer.wordpress.org/cli/commands/cron/event/unschedule/) | Unschedules all cron events for a given hook. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications