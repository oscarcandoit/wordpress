---
url: https://developer.wordpress.org/cli/commands/post/
scraped_at: 2025-10-20T03:13:14.698Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/post/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp post


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp post

Search

# [wp post\  <command>](https://developer.wordpress.org/cli/commands/post/)

Manages posts, content, and meta.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/post/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/post/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/post/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (33)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/post/\#examples)

```
# Create a new post.
$ wp post create --post_type=post --post_title='A sample post'
Success: Created post 123.

# Update an existing post.
$ wp post update 123 --post_status=draft
Success: Updated post 123.

# Delete an existing post.
$ wp post delete 123
Success: Trashed post 123.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/post/\#subcommands)

| Name | Description |
| --- | --- |
| [wp post create](https://developer.wordpress.org/cli/commands/post/create/) | Creates a new post. |
| [wp post delete](https://developer.wordpress.org/cli/commands/post/delete/) | Deletes an existing post. |
| [wp post edit](https://developer.wordpress.org/cli/commands/post/edit/) | Launches system editor to edit post content. |
| [wp post exists](https://developer.wordpress.org/cli/commands/post/exists/) | Verifies whether a post exists. |
| [wp post generate](https://developer.wordpress.org/cli/commands/post/generate/) | Generates some posts. |
| [wp post get](https://developer.wordpress.org/cli/commands/post/get/) | Gets details about a post. |
| [wp post list](https://developer.wordpress.org/cli/commands/post/list/) | Gets a list of posts. |
| [wp post meta](https://developer.wordpress.org/cli/commands/post/meta/) | Adds, updates, deletes, and lists post custom fields. |
| [wp post term](https://developer.wordpress.org/cli/commands/post/term/) | Adds, updates, removes, and lists post terms. |
| [wp post update](https://developer.wordpress.org/cli/commands/post/update/) | Updates one or more existing posts. |
| [wp post url-to-id](https://developer.wordpress.org/cli/commands/post/url-to-id/) | Gets the post ID for a given URL. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications