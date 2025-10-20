---
url: https://developer.wordpress.org/cli/commands/post/update/
scraped_at: 2025-10-20T03:14:21.910Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/post/update/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp post update


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp post](https://developer.wordpress.org/cli/commands/post/)wp post update

Search

# [wp post update](https://developer.wordpress.org/cli/commands/post/update/)

Updates one or more existing posts.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/post/update/#options)
- [Examples](https://developer.wordpress.org/cli/commands/post/update/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/post/update/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/post/update/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

[View Open Issues (1)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (13)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Apost-update+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/entity-command/issues/new)

### [Options](https://developer.wordpress.org/cli/commands/post/update/\#options)

<id>…One or more IDs of posts to update.\[--post\_author=<post\_author>\]The ID of the user who added the post. Default is the current user ID.\[--post\_date=<post\_date>\]The date of the post. Default is the current time.\[--post\_date\_gmt=<post\_date\_gmt>\]The date of the post in the GMT timezone. Default is the value of $post\_date.\[--post\_content=<post\_content>\]The post content. Default empty.\[--post\_content\_filtered=<post\_content\_filtered>\]The filtered post content. Default empty.\[--post\_title=<post\_title>\]The post title. Default empty.\[--post\_excerpt=<post\_excerpt>\]The post excerpt. Default empty.\[--post\_status=<post\_status>\]The post status. Default ‘draft’.\[--post\_type=<post\_type>\]The post type. Default ‘post’.\[--comment\_status=<comment\_status>\]Whether the post can accept comments. Accepts ‘open’ or ‘closed’. Default is the value of ‘default\_comment\_status’ option.\[--ping\_status=<ping\_status>\]Whether the post can accept pings. Accepts ‘open’ or ‘closed’. Default is the value of ‘default\_ping\_status’ option.\[--post\_password=<post\_password>\]The password to access the post. Default empty.\[--post\_name=<post\_name>\]The post name. Default is the sanitized post title when creating a new post.\[--to\_ping=<to\_ping>\]Space or carriage return-separated list of URLs to ping. Default empty.\[--pinged=<pinged>\]Space or carriage return-separated list of URLs that have been pinged. Default empty.\[--post\_modified=<post\_modified>\]The date when the post was last modified. Default is the current time.\[--post\_modified\_gmt=<post\_modified\_gmt>\]The date when the post was last modified in the GMT timezone. Default is the current time.\[--post\_parent=<post\_parent>\]Set this for the post it belongs to, if any. Default 0.\[--menu\_order=<menu\_order>\]The order the post should be displayed in. Default 0.\[--post\_mime\_type=<post\_mime\_type>\]The mime type of the post. Default empty.\[--guid=<guid>\]Global Unique ID for referencing the post. Default empty.\[--post\_category=<post\_category>\]Array of category names, slugs, or IDs. Defaults to value of the ‘default\_category’ option.\[--tags\_input=<tags\_input>\]Array of tag names, slugs, or IDs. Default empty.\[--tax\_input=<tax\_input>\]Array of taxonomy terms keyed by their taxonomy name. Default empty.\[--meta\_input=<meta\_input>\]Array in JSON format of post meta values keyed by their post meta key. Default empty.\[<file>\]
Read post content from <file>. If this value is present, the
`--post_content` argument will be ignored.

Passing `-` as the filename will cause post content to
be read from STDIN.
--<field>=<value>One or more fields to update. See [wp\_insert\_post()](https://developer.wordpress.org/reference/functions/wp_insert_post/) .\[--defer-term-counting\]Recalculate term count in batch, for a performance boost.

### [Examples](https://developer.wordpress.org/cli/commands/post/update/\#examples)

```
$ wp post update 123 --post_name=something --post_status=draft
Success: Updated post 123.

# Update a post with multiple meta values.
$ wp post update 123 --meta_input='{"key1":"value1","key2":"value2"}'
Success: Updated post 123.

# Update multiple posts at once.
$ wp post update 123 456 --post_author=789
Success: Updated post 123.
Success: Updated post 456.

# Update all posts of a given post type at once.
$ wp post update $(wp post list --post_type=page --format=ids) --post_author=123
Success: Updated post 123.
Success: Updated post 456.

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/post/update/\#global-parameters)

These [global parameters](https://make.wordpress.org/cli/handbook/config/) have the same behavior across all commands and affect how WP-CLI interacts with WordPress.

| **Argument** | **Description** |
| :-- | :-- |
| `--path=<path>` | Path to the WordPress files. |
| `--url=<url>` | Pretend request came from given URL. In multisite, this argument is how the target site is specified. |
| `--ssh=[<scheme>:][<user>@]<host\|container>[:<port>][<path>]` | Perform operation against a remote server over SSH (or a container using scheme of “docker”, “docker-compose”, “docker-compose-run”, “vagrant”). |
| `--http=<http>` | Perform operation against a remote WordPress installation over HTTP. |
| `--user=<id\|login\|email>` | Set the WordPress user. |
| `--skip-plugins[=<plugins>]` | Skip loading all plugins, or a comma-separated list of plugins. Note: mu-plugins are still loaded. |
| `--skip-themes[=<themes>]` | Skip loading all themes, or a comma-separated list of themes. |
| `--skip-packages` | Skip loading all installed packages. |
| `--require=<path>` | Load PHP file before running the command (may be used more than once). |
| `--exec=<php-code>` | Execute PHP code before running the command (may be used more than once). |
| `--context=<context>` | Load WordPress in a given context. |
| `--[no-]color` | Whether to colorize the output. |
| `--debug[=<group>]` | Show all PHP errors and add verbosity to WP-CLI output. Built-in groups include: bootstrap, commandfactory, and help. |
| `--prompt[=<assoc>]` | Prompt the user to enter values for all command arguments, or a subset specified as comma-separated values. |
| `--quiet` | Suppress informational messages. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications