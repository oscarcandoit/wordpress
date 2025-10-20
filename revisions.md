---
url: https://wordpress.org/documentation/article/revisions
scraped_at: 2025-10-20T02:04:10.595Z
---

[Skip to content](https://wordpress.org/documentation/article/revisions/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Revisions

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Publishing](https://wordpress.org/documentation/category/publishing/)Revisions

Search documentation

# Revisions

## In this article

Table of Contents

- [Description](https://wordpress.org/documentation/article/revisions/#description)
- [Autosaves](https://wordpress.org/documentation/article/revisions/#autosaves)
- [Revision Options](https://wordpress.org/documentation/article/revisions/#revision-options)
- [Revision Storage Method](https://wordpress.org/documentation/article/revisions/#revision-storage-method)
- [Revision Management](https://wordpress.org/documentation/article/revisions/#revision-management)
- [Displaying Rendered Revisions](https://wordpress.org/documentation/article/revisions/#displaying-rendered-revisions)

[↑ Back to top](https://wordpress.org/documentation/article/revisions/#wp--skip-link--target)

## [Description](https://wordpress.org/documentation/article/revisions/\#description)

The WordPress revisions system stores a record of each saved draft or published update. The revision system allows you to see what changes were made in each revision by dragging a slider (or using the Next/Previous buttons). The display indicates what has changed in each revision – what was added, what remained unchanged, and what was removed. Lines added or removed are highlighted, and individual character changes get additional highlighting. Click the ‘Restore This Revision’ button to restore a revision.

The revisions page also includes a ‘compare any two revisions’ mode that allows you to compare any two individual revisions. In this mode, the slider has two handles, one representing the revision you are comparing from and one representing the revision you are comparing to. Drag the handles to see what has changed between any two specific revisions. **Note:** the ‘Restore This Revision’ button _always restores the revision you are comparing to_.

To return to the post edit screen without restoring a revision, click on the post title at the top of the page.

## [Autosaves](https://wordpress.org/documentation/article/revisions/\#autosaves)

There is only ever a maximum of one [autosave](https://wordpress.org/support/article/glossary#autosave) per user for any given post. New autosaves overwrite old autosaves. This means that no, your tables do not grow by one row every 60 seconds. In multi-user settings, one autosave is stored for each user.

Autosaves are enabled for all posts and pages but do not overwrite published content. Autosaves are stored as a special type of revision; they do not overwrite the actual post. In fact, whether your power goes out, your browser crashes, or you lose your internet connection, when you go back to edit that post, WP will toss up a warning telling you that it has a backup of your post and a link to restore the backup. When reviewing revisions, autosaves are clearly marked.

## [Revision Options](https://wordpress.org/documentation/article/revisions/\#revision-options)

Limit the number of posts revisions that WordPress stores in the database.

The [wp\_revisions\_to\_keep](https://codex.wordpress.org/Plugin_API/Filter_Reference/wp_revisions_to_keep) filter allows developers to easily alter how many revisions are kept for a given post.

Alternately, the limit can be set in wp-config.php:

```
define( 'WP_POST_REVISIONS', 3 );

```

WP\_POST\_REVISIONS:

- true (default), -1: store every revision
- false, 0: do not store any revisions (except the one autosave per post)
- (int) > 0: store that many revisions (+1 autosave per user) per post. Old revisions are automatically deleted when the post is updated again.

## [Revision Storage Method](https://wordpress.org/documentation/article/revisions/\#revision-storage-method)

Revisions are stored in the posts table.

Revisions are stored as children of their associated post (the same thing we do for attachments). They are given a post\_status of ‘inherit’, a post\_type of ‘revision’, and a post\_name of {parent ID}- revision(-#) for regular revisions and {parent ID}-autosave for autosaves.

By default, WP keeps track of the changes to title, author, content, excerpt.

## [Revision Management](https://wordpress.org/documentation/article/revisions/\#revision-management)

Deleting: There is an API function to delete revisions, but there is no UI. That can certainly change.

## [Displaying Rendered Revisions](https://wordpress.org/documentation/article/revisions/\#displaying-rendered-revisions)

Currently revision comparison “diffs” are rendered in Text (or HTML) view; proposed filters would allow plugin developers to customize diff encoding/rendering. (see Trac ticket [#24908](https://core.trac.wordpress.org/ticket/24908))

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/revisions/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Frevisions%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

February 24, 2019

Last updated

April 14, 2023

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.