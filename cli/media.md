---
url: https://developer.wordpress.org/cli/commands/media/
scraped_at: 2025-10-20T03:07:45.336Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/media/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp media


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp media

Search

# [wp media\  <command>](https://developer.wordpress.org/cli/commands/media/)

Imports files as attachments, regenerates thumbnails, or lists registered image sizes.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/media/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/media/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/media/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/media-command)

[View Open Issues (6)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amedia+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (76)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Amedia+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/media-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/media/\#examples)

```
# Re-generate all thumbnails, without confirmation.
$ wp media regenerate --yes
Found 3 images to regenerate.
1/3 Regenerated thumbnails for "Sydney Harbor Bridge" (ID 760).
2/3 Regenerated thumbnails for "Boardwalk" (ID 757).
3/3 Regenerated thumbnails for "Sunburst Over River" (ID 756).
Success: Regenerated 3 of 3 images.

# Import a local image and set it to be the featured image for a post.
$ wp media import ~/Downloads/image.png --post_id=123 --title="A downloaded picture" --featured_image
Imported file '/home/person/Downloads/image.png' as attachment ID 1753 and attached to post 123 as featured image.
Success: Imported 1 of 1 images.

# List all registered image sizes
$ wp media image-size
+---------------------------+-------+--------+-------+
| name                      | width | height | crop  |
+---------------------------+-------+--------+-------+
| full                      |       |        | N/A   |
| twentyfourteen-full-width | 1038  | 576    | hard  |
| large                     | 1024  | 1024   | soft  |
| medium_large              | 768   | 0      | soft  |
| medium                    | 300   | 300    | soft  |
| thumbnail                 | 150   | 150    | hard  |
+---------------------------+-------+--------+-------+

# Fix orientation for specific images.
$ wp media fix-orientation 63
1/1 Fixing orientation for "Portrait_6" (ID 63).
Success: Fixed 1 of 1 images.

```

### [Subcommands](https://developer.wordpress.org/cli/commands/media/\#subcommands)

| Name | Description |
| --- | --- |
| [wp media fix-orientation](https://developer.wordpress.org/cli/commands/media/fix-orientation/) | Fix image orientation for one or more attachments. |
| [wp media image-size](https://developer.wordpress.org/cli/commands/media/image-size/) | Lists image sizes registered with WordPress. |
| [wp media import](https://developer.wordpress.org/cli/commands/media/import/) | Creates attachments from local files or URLs. |
| [wp media regenerate](https://developer.wordpress.org/cli/commands/media/regenerate/) | Regenerates thumbnails for one or more attachments. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications