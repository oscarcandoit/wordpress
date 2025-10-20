---
url: https://wordpress.org/documentation/article/understand-comment-spam
scraped_at: 2025-10-20T02:06:27.095Z
---

[Skip to content](https://wordpress.org/documentation/article/understand-comment-spam/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Understand comment spam

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Publishing](https://wordpress.org/documentation/category/publishing/)Understand comment spam

Search documentation

# Understand comment spam

## In this article

Table of Contents

- [Comment Spam and Search Engines](https://wordpress.org/documentation/article/understand-comment-spam/#comment-spam-and-search-engines)
- [Fighting Comment Spam](https://wordpress.org/documentation/article/understand-comment-spam/#fighting-comment-spam)
- [Stealth Spam](https://wordpress.org/documentation/article/understand-comment-spam/#stealth-spam)
- [FAQ](https://wordpress.org/documentation/article/understand-comment-spam/#faq)

[↑ Back to top](https://wordpress.org/documentation/article/understand-comment-spam/#wp--skip-link--target)

If you’ve been on the internet for any amount of time you’re probably familiar with “spam” in your email inbox. For the uninitiated, spam is an unsolicited commercial message, or something you didn’t ask for trying to sell you something.

So what does this have to do with blogs? Well just like you can get spam messages in your inbox, people will leave spam comments on your blog. However unlike email spam where the target is you, comment spam generally targets search engines.

## [Comment Spam and Search Engines](https://wordpress.org/documentation/article/understand-comment-spam/\#comment-spam-and-search-engines)

Why on earth would a spammer use your blog to target a search engine? Let’s start from the beginning. Several years ago, Google pioneered a search technique called [PageRank](http://en.wikipedia.org/wiki/PageRank). Basically, in addition to looking at the content of the page being indexed, Google also takes into account who links to the page and what those links say. This technology meant Google was very good at returning relevant results, making it the most popular search engine today. Because their ranking system relies so heavily on PageRank, people sometimes game the system using a technique called “Google Bombing.”

A [google bomb](http://en.wikipedia.org/wiki/Google_bomb) is when a large number of different websites link to a page with the same link text to influence the ranking of that page for a search term.

This brings us back to the spammers. A spammer might have a site that sells “mydrug” and wants to be at the top of search results for “mydrug” on Google. They leave comments on hundreds or thousands of weblogs linking to their site with the link text “mydrug.” They don’t really care if you see their google bomb text—in fact they’d rather you didn’t in case you decide to delete it! They just want the search engine to see it when they index your page.

## [Fighting Comment Spam](https://wordpress.org/documentation/article/understand-comment-spam/\#fighting-comment-spam)

[Comment Moderation](https://wordpress.org/support/article/comment-moderation/) is very effective in addressing unwanted comments. The best defense against comment spam is just watching your comments. Under `Manage → Comments` it shows a listing of the latest comments on any post and you can quickly scan the comment activity on your site. The faster you respond to comment spam on your site, the less likely the spammers will return.

## [Stealth Spam](https://wordpress.org/documentation/article/understand-comment-spam/\#stealth-spam)

Spammers find new and creative ways to be sneaky all the time. You may notice that posters leave comments on your site which look perfectly normal except for the commenter’s name or URL, which likely references a product or a site selling something.

It’s good practice to visit the URLs of people who leave comments on your blog to determine whether the poster is sincere or spammy. If you see one that looks suspicious, you can choose to delete the comment entirely or leave the comment and just delete the URL.

Another way of stealth is to use a div-tag around a bundle of hundreds of links. This becomes more and more common because many software displays directly the given HTML tags and not the HTML code. To avoid this the software must “strip-out”, other word: filter the HTML tags while inserting the comment into the database.

## [FAQ](https://wordpress.org/documentation/article/understand-comment-spam/\#faq)

Why are they spamming me?

Apart from _because they can_, the need to raise page ranking in search engines gives rise to the need to create a lot of links to a web page so the search engine thinks that page is important.

Where can I find WordPress anti-spam plugins?

[Plugins for handling comment spam](https://wordpress.org/plugins/tags/anti-spam) can be found in the [Official WordPress Plugin Directory](https://wordpress.org/plugins/).

Which is the best plugin?

This is not an easy answer. Spammers use different tactics, and each plugin will use different tactics in response. There is no plugin that will keep you spam-free forever. Comment spammers can download the plugins, see how they work, and figure out a way around them.

Check plugin authors’ sites for updates. WordPress makes it easy to find updates via the [Plugins screen](https://wordpress.org/documentation/article/plugins-screen/) and the link to the plugin author’s website.

Comment spam technology is changing fast on both sides, so keep updated with the latest news on comment spam techniques and WordPress Plugin options.

I have a problem with a plugin

Visit the plugin author’s site to see if they have already offered a solution, and if they offer support directly. If not, **search the forums first** before posting as the answer may be there. If there is no answer, then post a support request on that plugin’s support forum.

What happens to comments that are marked as “Spam”?

Comments that are marked as \[spam\] will be held in your database to educate “intelligent” anti-spam plugins, such as [Akismet](https://akismet.com/).

I have spam appear as soon as I post!

If you do not have comment spam plugins or the [latest version of WordPress](https://wordpress.org/download/) installed, this may happen. [Upgrade](https://wordpress.org/documentation/article/updating-wordpress/) or install one of the comment spam plugins and manually delete the comment spam from your [Manage > Comments](https://wordpress.org/documentation/article/administration-screens/) panel.

Why is every comment going into the moderation queue?

Go to the [Settings > Discussion](https://wordpress.org/documentation/article/administration-screens/) panel and make sure that **An administrator must approve the comment (regardless of any matches below)** is unchecked. With that option selected, all comments are sent to the moderation queue to await approval. Make sure that **Hold a comment in the queue if it contains more than x links** is not blank and contains a number higher than zero. If this value is blank or zero, all comments containing links will be moderated. If the option mentioned above is unchecked, the link moderation value is higher than zero, and you still have this problem, your Spam Words list probably has blank lines, punctuation marks, or single letters between the information in the list. There should be spaces between the listed items or each item must be on its own line. If you have done this, then upgrade the comment spam plugins you have installed. If this continues to be a problem, deactivate the comment spam plugins one by one to determine the culprit and contact the plugin author for help.

I have disabled comments, but comments continue to be posted

If you have unchecked **Allow people to post comments on the article** on the [Options > Discussion](https://wordpress.org/documentation/article/administration-screens/) panel, then you have only disabled comments on _future posts_. To completely disable comments, you will have to edit each past post and uncheck **Allow Comments**. Alternatively, you could delete the wp-comments-post.php file, or run this MySQL query, from the command line on a shell account, or using [phpMyAdmin](https://codex.wordpress.org/phpMyAdmin): `UPDATE wp_posts SET comment_status="closed";`

I have disabled trackbacks, but trackbacks continue to be posted

If you have unchecked **Allow link notifications from other Weblogs (pingbacks and trackbacks.)** on the Options > Discussion panel, then you have only disabled trackbacks on _future posts_. To completely disable trackbacks, you will have to edit each past post and uncheck **Allow Pings** from the Write Post SubPanel. Alternatively, you could just simply delete the wp-trackback.php file, or run this MySQL query, from the command line on a shell account, or using PHPMyAdmin: `UPDATE wp_posts SET ping_status="closed";`

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/understand-comment-spam/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Funderstand-comment-spam%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

March 1, 2019

Last updated

March 26, 2025

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.