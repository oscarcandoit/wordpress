---
url: https://wordpress.org/documentation/article/post-status
scraped_at: 2025-10-20T02:02:29.528Z
---

[Skip to content](https://wordpress.org/documentation/article/post-status/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Post Status

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Publishing](https://wordpress.org/documentation/category/publishing/)Post Status

Search documentation

# Post Status

## In this article

Table of Contents

- [Workflow](https://wordpress.org/documentation/article/post-status/#workflow)
- [Default Statuses](https://wordpress.org/documentation/article/post-status/#default-statuses)
  - [Publish](https://wordpress.org/documentation/article/post-status/#publish)
  - [Future](https://wordpress.org/documentation/article/post-status/#future)
  - [Draft](https://wordpress.org/documentation/article/post-status/#draft)
  - [Pending](https://wordpress.org/documentation/article/post-status/#pending)
  - [Private](https://wordpress.org/documentation/article/post-status/#private)
  - [Trash](https://wordpress.org/documentation/article/post-status/#trash)
  - [Auto-Draft](https://wordpress.org/documentation/article/post-status/#auto-draft)
  - [Inherit](https://wordpress.org/documentation/article/post-status/#inherit)
- [Custom Status](https://wordpress.org/documentation/article/post-status/#custom-status)
- [Resources](https://wordpress.org/documentation/article/post-status/#resources)
- [Related](https://wordpress.org/documentation/article/post-status/#related)
- [Code Documentation](https://wordpress.org/documentation/article/post-status/#code-documentation)

[↑ Back to top](https://wordpress.org/documentation/article/post-status/#wp--skip-link--target)

Posts in WordPress can have one of a number of statuses. The status of a given post determines how WordPress handles that post. For instance, public posts viewable by everyone are assigned the publish status, while drafts are assigned the draft status. The status is stored in the post\_status field in the wp\_posts table.

WordPress provides 8 built-in statuses you can use. WordPress 3.0 gave you the capability to add your own custom post status and to use it in different ways.

## [Workflow](https://wordpress.org/documentation/article/post-status/\#workflow)

WordPress provides built-in features that empower some users (based on their [Roles and Capabilities](https://wordpress.org/support/article/roles-and-capabilities/)) to review content submitted to the website before it is published. This is commonly called “workflow.” WordPress’s workflow features rely on the value of a post’s `post_status` field to know which step in the workflow process the post is currently held in.

Most users are already familiar with at least two workflow states:

- Posts that are published and visible to everyone (including users who are logged out) are given [the](https://wordpress.org/support/article/post-status/#publish) `[publish](https://wordpress.org/support/article/post-status/#publish)` [status](https://wordpress.org/support/article/post-status/#publish).
- Drafts that are not yet published are assigned [the](https://wordpress.org/support/article/post-status/#draft) `[draft](https://wordpress.org/support/article/post-status/#draft)` [status](https://wordpress.org/support/article/post-status/#draft).

Internally, WordPress sets the post status to `publish` when you click the “Publish” button, and WordPress sets the post status to `draft` when you click the “Save Draft” button. Similarly, if your website has users granted [the](https://wordpress.org/support/article/roles-and-capabilities/#edit_posts) `[edit\_posts](https://wordpress.org/support/article/roles-and-capabilities/#edit_posts)` [capability](https://wordpress.org/support/article/roles-and-capabilities/#edit_posts) but not [the](https://wordpress.org/support/article/roles-and-capabilities/#publish_posts) `[publish\_posts](https://wordpress.org/support/article/roles-and-capabilities/#publish_posts)` [capability](https://wordpress.org/support/article/roles-and-capabilities/#publish_posts), then when those users start writing a new post, WordPress will display a “Submit for Review” button instead of a “Publish” button. Likewise, WordPress then assigns the post that user created [the](https://wordpress.org/support/article/post-status/#pending) `[pending](https://wordpress.org/support/article/post-status/#pending)` [status](https://wordpress.org/support/article/post-status/#pending) when they press that button.

The status of a post can also be set in the [Administration Screen](https://wordpress.org/support/article/administration-screens/) and [Add New Posts](https://wordpress.org/support/article/writing-posts/) Screen by any user with the capability needed to assign the post to the given status. Internally, all of these posts are stored in the same place (the [`wp_posts`](https://codex.wordpress.org/Database_Description#Table:_wp_posts) table), and are differentiated by a column called `post_status`.

## [Default Statuses](https://wordpress.org/documentation/article/post-status/\#default-statuses)

There are 8 major post statuses that WordPress uses by default.

### [Publish](https://wordpress.org/documentation/article/post-status/\#publish)

Viewable by everyone. (publish)

### [Future](https://wordpress.org/documentation/article/post-status/\#future)

Scheduled to be published in a future date. (future)

### [Draft](https://wordpress.org/documentation/article/post-status/\#draft)

Incomplete post viewable by anyone with proper [user role](https://wordpress.org/support/article/roles-and-capabilities/). (draft)

### [Pending](https://wordpress.org/documentation/article/post-status/\#pending)

Awaiting a user with the `publish_posts` capability (typically a user assigned [the](https://wordpress.org/support/article/roles-and-capabilities/#editor) `[Editor](https://wordpress.org/support/article/roles-and-capabilities/#editor)` [role](https://wordpress.org/support/article/roles-and-capabilities/#editor)) to publish. (pending)

### [Private](https://wordpress.org/documentation/article/post-status/\#private)

Viewable only to WordPress users at Administrator level. (private)

### [Trash](https://wordpress.org/documentation/article/post-status/\#trash)

Posts in the Trash are assigned the `trash` status. (trash)

### [Auto-Draft](https://wordpress.org/documentation/article/post-status/\#auto-draft)

[Revisions](https://codex.wordpress.org/Revisions) that WordPress saves automatically while you are editing. (auto-draft)

### [Inherit](https://wordpress.org/documentation/article/post-status/\#inherit)

Used with a child post (such as [Attachments](https://codex.wordpress.org/Attachments) and [Revisions](https://codex.wordpress.org/Revisions)) to determine the actual status from the parent post. (inherit)

## [Custom Status](https://wordpress.org/documentation/article/post-status/\#custom-status)

**NOTICE:**

This function does NOT add the registered post status to the Administration Screen. This functionality is pending future development. Please refer to [Trac Ticket #12706](https://core.trac.wordpress.org/ticket/12706).

Consider the action hook [post\_submitbox\_misc\_actions](https://core.trac.wordpress.org/browser/tags/3.5.1/wp-admin/includes/meta-boxes.php#L183) for adding this parameter.

A Custom Status is a Post Status you define.

Adding a custom status to WordPress is done via the [register\_post\_status()](https://developer.wordpress.org/reference/functions/register_post_status) function. This function allows you to define the post status and how it operates within WordPress.

Here’s a basic example of adding a custom post status called “Unread”:

```
function custom_post_status(){
	register_post_status( 'unread', array(
		'label'                     => _x( 'Unread', 'post' ),
		'public'                    => true,
		'exclude_from_search'       => false,
		'show_in_admin_all_list'    => true,
		'show_in_admin_status_list' => true,
		'label_count'               => _n_noop( 'Unread (%s)', 'Unread (%s)' ),
	) );
}
add_action( 'init', 'custom_post_status' );
```

## [Resources](https://wordpress.org/documentation/article/post-status/\#resources)

- [WordPress Post Status Generator](http://generatewp.com/post-status/)

## [Related](https://wordpress.org/documentation/article/post-status/\#related)

- [Roles and Capabilities](https://wordpress.org/support/article/roles-and-capabilities/#editor)

## [Code Documentation](https://wordpress.org/documentation/article/post-status/\#code-documentation)

- Function: [get\_post\_status()](https://developer.wordpress.org/reference/functions/get_post_status) – Retrieve the post status based on the Post ID.

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/post-status/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fpost-status%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

November 2, 2018

Last updated

January 13, 2023

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.