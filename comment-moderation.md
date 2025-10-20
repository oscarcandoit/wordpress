---
url: https://wordpress.org/documentation/article/comment-moderation
scraped_at: 2025-10-20T02:02:51.759Z
---

[Skip to content](https://wordpress.org/documentation/article/comment-moderation/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Comment moderation

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Publishing](https://wordpress.org/documentation/category/publishing/)Comment moderation

Search documentation

# Comment moderation

## In this article

Table of Contents

- [How moderation works](https://wordpress.org/documentation/article/comment-moderation/#how-moderation-works)
- [Controlling moderation](https://wordpress.org/documentation/article/comment-moderation/#controlling-moderation)
- [Comment blocking](https://wordpress.org/documentation/article/comment-moderation/#comment-blocking)
- [Managing incoming comments](https://wordpress.org/documentation/article/comment-moderation/#managing-incoming-comments)
  - [Moderating comments with the comment screen](https://wordpress.org/documentation/article/comment-moderation/#moderating-comments-with-the-comment-screen)
  - [Bulk edit comments](https://wordpress.org/documentation/article/comment-moderation/#bulk-edit-comments)

[↑ Back to top](https://wordpress.org/documentation/article/comment-moderation/#wp--skip-link--target)

Comment moderation is a feature in WordPress that allows you to prevent comments from appearing on your site without your express approval. Moderation can be very useful in addressing [Comment Spam](https://wordpress.org/support/article/comment-spam), but it has more general applications as well. If you would like to learn more about comment spam, see [Fighting Comment Spam](https://wordpress.org/documentation/article/comment-spam/#fighting-comment-spam).

## [How moderation works](https://wordpress.org/documentation/article/comment-moderation/\#how-moderation-works)

WordPress runs a number of tests on each new comment before posting it to your blog. If a comment fails one of these tests, it is not displayed immediately on the site but is placed in a queue for **moderation**, the process of manual approval or deletion by the blog’s administrator.

## [Controlling moderation](https://wordpress.org/documentation/article/comment-moderation/\#controlling-moderation)

You can control which comments get held for moderation on your [Settings Discussion Screen](https://wordpress.org/support/article/settings-discussion-screen/) page, which is located under [Settings](https://wordpress.org/support/article/administration-screens/#settings-configuration-settings) → [Discussion](https://wordpress.org/support/article/administration-screens/#discussion).

If you would like every comment to be held for moderation, check the **Comment must be manually approved** option, listed under **Before a comment appears**.

If you would like to send suspicious comments to the moderation queue, while letting innocent comments through, you will need to specify a set of rules for determining which comments are suspicious. These rules are specified in on the [Settings](https://wordpress.org/documentation/article/administration-screens/#settings-configuration-settings) → [Discussion](https://wordpress.org/documentation/article/administration-screens/#discussion) > Comment Moderation.

The first option is to hold comments for moderation if they contain an unusually large number of hyperlinks. Most normal comments contain at most one or two links while spam comments often have a large number. Look at your own comments and set this to a value that makes sense for your audience. (Note: In version 1.5.2, and possibly others, if you do not put a number in the comment moderation links box, in other words, if this box is completely blank, all anonymous comments (and possibly others) are sent to the Manage Comments SubPanel for moderation, even if the Discussion Options Subpanel has no restrictions set.)

The second option is to specify a set of **moderation keys** which, if present in any part of the comment, will cause it to be held for moderation. These keys are specified one per line in the large text area, which is blank by default. Moderation keys can include Spam Words, swear words, [IP addresses](https://wordpress.org/support/article/glossary#ip-address), and [Regular Expressions](http://en.wikipedia.org/wiki/Regular_expression).

When you add a new moderation key, it’s a good idea to test its validity by checking previous comments. Simply use the link entitled **Check past comments against moderation list**, which is located underneath the text box containing moderation keys. This asks WordPress to check previous comments and tell you which ones would be flagged for moderation under your new set of keys.

Of course this means that there may be a lot of comments that you don’t want on your site caught in the moderation queue, and in this case we’ve tried to make it as easy as possible to manage large numbers of comments quickly. See the articles on [Fighting Comment Spam](https://wordpress.org/documentation/article/comment-spam/#fighting-comment-spam) for more information and resources.

## [Comment blocking](https://wordpress.org/documentation/article/comment-moderation/\#comment-blocking)

The box marked **Disallowed Comment Keys** works in exactly the same way as the comment moderation box, except that comments that match these words will be **deleted immediately** and _**without notification**_. So be careful! Genuine comments could be deleted without you ever knowing they were there.

## [Managing incoming comments](https://wordpress.org/documentation/article/comment-moderation/\#managing-incoming-comments)

Once you start receiving comments on your site, you can check the status of comments quickly by looking at the dashboard, the admin bar, or the left navigation menu. When you log in, the dashboard’s “Activity” box will show you the status of your comments. Hover over a comment to see your moderation options. From “Activity – Comments” you can approve, reply, edit, mark as spam, or trash comments. Alternatively, you can look to see if there is a number next to the comment bubble in the admin bar or “Comments” in the left navigation. This number represents how many pending comments require your attention.

### [Moderating comments with the comment screen](https://wordpress.org/documentation/article/comment-moderation/\#moderating-comments-with-the-comment-screen)

![WordPress comment moderation panel displaying a comment from a user named ‘blogreader.’ The entry shows the user’s avatar, username, website (example.com), email (blogreader@example.com), and IP address (192.168.0.5). The comment, submitted on 2013/12/16 at 8:18 am, reads: ‘By default anybody can leave comments without logging in.’ Below the comment are moderation options: Approve, Reply, Quick Edit, Edit, Spam, and Trash. On the right, the comment is shown as a response to the post titled ‘Hello world!,’ with a link to ‘View Post.’](https://wordpress.org/documentation/files/2023/08/comment_pending_numbered_smaller.png)

WordPress makes moderating your users’ comments a simple process. The [Comments Screen](https://wordpress.org/documentation/article/comments-screen/) lays out the basic information about each comment and lets you decide what to do with it.

01. [Commenter Gravatar](https://wordpress.org/documentation/article/comment-moderation/)
02. Commenter Name
03. Commenter Website URL
04. Commenter Email Address
05. Commenter IP Address
06. [Time and Date](https://wordpress.org/documentation/article/comment-moderation/) Comment was submitted
07. Comment Text
08. Comment Moderation Options. You can approve, spam or trash a comment with one click. Reply, Quick Edit or Edit will open up a new screen for you to write a reply to the comment or edit the comment.
09. Post Name
10. Number of Comments on the Post, Link to View Post

### [Bulk edit comments](https://wordpress.org/documentation/article/comment-moderation/\#bulk-edit-comments)

![WordPress Comments dashboard showing the comment management toolbar. Tabs display counts for All, Mine, Pending, Approved, Spam, and Trash comments. Dropdown menus for ‘Bulk Actions’ and ‘All comment types’ are visible along with ‘Apply’ and ‘Filter’ buttons. A ‘Search Comments’ box appears on the right, and pagination controls.](https://wordpress.org/documentation/files/2023/08/bulk-action.webp)

Like the posts and Pages screens, the Comments screen supplies a Bulk Action drop-down box. Select the comments you want to edit, and then select Unapprove, Approve, Mark as Spam, or Move to Trash from the drop-down and click “Apply.”

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/comment-moderation/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fcomment-moderation%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

March 1, 2019

Last updated

June 24, 2025

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.