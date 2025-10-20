---
url: https://developer.wordpress.org/plugins/cron/simple-testing
scraped_at: 2025-10-20T04:48:37.998Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/cron/simple-testing/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Testing of WP-Cron


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Cron](https://developer.wordpress.org/plugins/cron/)Testing of WP-Cron

Search

# Testing of WP-Cron

## In this article

Table of Contents

- [WP-CLI](https://developer.wordpress.org/plugins/cron/simple-testing/#wp-cli)
- [WP-Cron Management Plugins](https://developer.wordpress.org/plugins/cron/simple-testing/#wp-cron-management-plugins)
- [\_get\_cron\_array()](https://developer.wordpress.org/plugins/cron/simple-testing/#_get_cron_array)
- [wp\_get\_schedules()](https://developer.wordpress.org/plugins/cron/simple-testing/#wp_get_schedules)

[↑ Back to top](https://developer.wordpress.org/plugins/cron/simple-testing/#wp--skip-link--target)

## [WP-CLI](https://developer.wordpress.org/plugins/cron/simple-testing/\#wp-cli)

Cron jobs can be tested using [WP-CLI](https://wp-cli.org/). It offers commands like `wp cron event list` and `wp cron event run {job name}`. [Check the documentation](https://developer.wordpress.org/cli/commands/cron/) for more details.

## [WP-Cron Management Plugins](https://developer.wordpress.org/plugins/cron/simple-testing/\#wp-cron-management-plugins)

[Several plugins are available on the WordPress.org Plugin Directory for viewing, editing, and controlling the scheduled cron events and available schedules on your site.](https://wordpress.org/plugins/tags/cron/)

## [\_get\_cron\_array()](https://developer.wordpress.org/plugins/cron/simple-testing/\#_get_cron_array)

[The `_get_cron_array()` function](https://developer.wordpress.org/reference/functions/_get_cron_array/) returns an array of all currently scheduled cron events. Use this function if you need to inspect the raw list of events.

## [wp\_get\_schedules()](https://developer.wordpress.org/plugins/cron/simple-testing/\#wp_get_schedules)

[The `wp_get_schedules()` function](https://developer.wordpress.org/reference/functions/wp_get_schedules/) returns an array of available event recurrence schedules. Use this function if you need to inspect the raw list of available schedules.

First published

October 19, 2014

Last updated

July 9, 2022

[PreviousScheduling WP Cron EventsPrevious: Scheduling WP Cron Events](https://developer.wordpress.org/plugins/cron/scheduling-wp-cron-events/)

[NextUnderstanding WP-Cron SchedulingNext: Understanding WP-Cron Scheduling](https://developer.wordpress.org/plugins/cron/understanding-wp-cron-scheduling/)

Notifications