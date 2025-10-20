---
url: https://developer.wordpress.org/cli/commands/comment/
scraped_at: 2025-10-20T02:59:08.530Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/comment/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp comment


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp comment

Search

# [wp comment\  <command>](https://developer.wordpress.org/cli/commands/comment/)

Creates, updates, deletes, and moderates comments.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/comment/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/comment/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/comment/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (43)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Acomment+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/comment/\#examples)

```
# Create a new comment.
$ wp comment create --comment_post_ID=15 --comment_content="hello blog" --comment_author="wp-cli"
Success: Created comment 932.

# Update an existing comment.
$ wp comment update 123 --comment_author='That Guy'
Success: Updated comment 123.

# Delete an existing comment.
$ wp comment delete 1337 --force
Success: Deleted comment 1337.

# Trash all spam comments.
$ wp comment delete $(wp comment list --status=spam --format=ids)
Success: Trashed comment 264.
Success: Trashed comment 262.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/comment/\#subcommands)

| Name | Description |
| --- | --- |
| [wp comment approve](https://developer.wordpress.org/cli/commands/comment/approve/) | Approves a comment. |
| [wp comment count](https://developer.wordpress.org/cli/commands/comment/count/) | Counts comments, on whole blog or on a given post. |
| [wp comment create](https://developer.wordpress.org/cli/commands/comment/create/) | Creates a new comment. |
| [wp comment delete](https://developer.wordpress.org/cli/commands/comment/delete/) | Deletes a comment. |
| [wp comment exists](https://developer.wordpress.org/cli/commands/comment/exists/) | Verifies whether a comment exists. |
| [wp comment generate](https://developer.wordpress.org/cli/commands/comment/generate/) | Generates some number of new dummy comments. |
| [wp comment get](https://developer.wordpress.org/cli/commands/comment/get/) | Gets the data of a single comment. |
| [wp comment list](https://developer.wordpress.org/cli/commands/comment/list/) | Gets a list of comments. |
| [wp comment meta](https://developer.wordpress.org/cli/commands/comment/meta/) | Adds, updates, deletes, and lists comment custom fields. |
| [wp comment recount](https://developer.wordpress.org/cli/commands/comment/recount/) | Recalculates the comment\_count value for one or more posts. |
| [wp comment spam](https://developer.wordpress.org/cli/commands/comment/spam/) | Marks a comment as spam. |
| [wp comment status](https://developer.wordpress.org/cli/commands/comment/status/) | Gets the status of a comment. |
| [wp comment trash](https://developer.wordpress.org/cli/commands/comment/trash/) | Trashes a comment. |
| [wp comment unapprove](https://developer.wordpress.org/cli/commands/comment/unapprove/) | Unapproves a comment. |
| [wp comment unspam](https://developer.wordpress.org/cli/commands/comment/unspam/) | Unmarks a comment as spam. |
| [wp comment untrash](https://developer.wordpress.org/cli/commands/comment/untrash/) | Untrashes a comment. |
| [wp comment update](https://developer.wordpress.org/cli/commands/comment/update/) | Updates one or more comments. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications