---
url: https://developer.wordpress.org/cli/commands/option/
scraped_at: 2025-10-20T03:09:29.395Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/option/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp option


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp option

Search

# [wp option\  <command>](https://developer.wordpress.org/cli/commands/option/)

Retrieves and sets site options, including plugin and WordPress settings.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/option/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/option/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/option/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aoption+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

See the [Plugin Settings API](https://developer.wordpress.org/plugins/settings/settings-api/) and the [Theme Options](https://developer.wordpress.org/themes/customize-api/) for more information on adding customized options.

### [Examples](https://developer.wordpress.org/cli/commands/option/\#examples)

```
# Get site URL.
$ wp option get siteurl
http://example.com

# Add option.
$ wp option add my_option foobar
Success: Added 'my_option' option.

# Update option.
$ wp option update my_option '{"foo": "bar"}' --format=json
Success: Updated 'my_option' option.

# Delete option.
$ wp option delete my_option
Success: Deleted 'my_option' option.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/option/\#subcommands)

| Name | Description |
| --- | --- |
| [wp option add](https://developer.wordpress.org/cli/commands/option/add/) | Adds a new option value. |
| [wp option delete](https://developer.wordpress.org/cli/commands/option/delete/) | Deletes an option. |
| [wp option get](https://developer.wordpress.org/cli/commands/option/get/) | Gets the value for an option. |
| [wp option get-autoload](https://developer.wordpress.org/cli/commands/option/get-autoload/) | Gets the ‘autoload’ value for an option. |
| [wp option list](https://developer.wordpress.org/cli/commands/option/list/) | Lists options and their values. |
| [wp option patch](https://developer.wordpress.org/cli/commands/option/patch/) | Updates a nested value in an option. |
| [wp option pluck](https://developer.wordpress.org/cli/commands/option/pluck/) | Gets a nested value from an option. |
| [wp option set-autoload](https://developer.wordpress.org/cli/commands/option/set-autoload/) | Sets the ‘autoload’ value for an option. |
| [wp option update](https://developer.wordpress.org/cli/commands/option/update/) | Updates an option value. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications