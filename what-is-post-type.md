---
url: https://wordpress.org/documentation/article/what-is-post-type
scraped_at: 2025-10-20T02:06:41.022Z
---

[Skip to content](https://wordpress.org/documentation/article/what-is-post-type/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

What is Post Type?

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Dashboard](https://wordpress.org/documentation/category/dashboard/)What is Post Type?

Search documentation

# What is Post Type?

## In this article

Table of Contents

- [Default Post Types](https://wordpress.org/documentation/article/what-is-post-type/#default-post-types)
  - [Posts](https://wordpress.org/documentation/article/what-is-post-type/#posts)
  - [Pages](https://wordpress.org/documentation/article/what-is-post-type/#pages)
  - [Attachments](https://wordpress.org/documentation/article/what-is-post-type/#attachments)
  - [Revisions](https://wordpress.org/documentation/article/what-is-post-type/#revisions)
  - [Menus](https://wordpress.org/documentation/article/what-is-post-type/#menus)
  - [Custom CSS](https://wordpress.org/documentation/article/what-is-post-type/#custom-css)
  - [Changesets](https://wordpress.org/documentation/article/what-is-post-type/#changesets)
- [Custom Post Types](https://wordpress.org/documentation/article/what-is-post-type/#custom-post-types)
- [Template Files](https://wordpress.org/documentation/article/what-is-post-type/#template-files)
- [Post Type Queries](https://wordpress.org/documentation/article/what-is-post-type/#post-type-queries)
- [The Posts Query](https://wordpress.org/documentation/article/what-is-post-type/#the-posts-query)

[↑ Back to top](https://wordpress.org/documentation/article/what-is-post-type/#wp--skip-link--target)

WordPress houses lots of different types of content and they are divided into something called **_Post Types﻿_**. A single item is called a _**post**_ however this is also the name of a standard post type called _**posts**_. By default WordPress comes with a few different post types which are all stored in the database under the _**wp\_posts**_ table.

## [Default Post Types](https://wordpress.org/documentation/article/what-is-post-type/\#default-post-types)

The default post types that are always included within a WordPress installation unless otherwise removed are:

- Posts
- Pages
- Attachments
- Revisions
- Navigation Menus
- Custom CSS
- Changesets


### [Posts](https://wordpress.org/documentation/article/what-is-post-type/\#posts)

A **_post_** in WordPress is a _post type_ that is typical for, and most used by blogs. _Posts_ are normally displayed in a blog in reverse sequential order by time (newest posts first). Posts are also used for creating RSS feeds.

### [Pages](https://wordpress.org/documentation/article/what-is-post-type/\#pages)

A page is similar to posts however they have some very important differences. Pages aren’t displayed in a reversed time-based order. They can also be placed into a hierarchical order where a page can be the parent or child of another page creating a page structure. Traditionally, pages also do not make use of categories and tags like posts do.

### [Attachments](https://wordpress.org/documentation/article/what-is-post-type/\#attachments)

Attachments are another post type that is special as these hold information about any media that is uploaded to your WordPress website. Not only is the main post information stored where other posts are, attachments also make use of the wp\_postmeta table for storing extra information like metadata for images and videos that you’ve added.

### [Revisions](https://wordpress.org/documentation/article/what-is-post-type/\#revisions)

Revisions are a particularly special post type as they are used to create a history of other post types in case you make a mistake and want to rollback to a previous version. Whilst you technically can’t edit revisions directly unless you restore a revision, they are editable just like posts and are stored in the _**wp\_posts**_ table like any other post type.

### [Menus](https://wordpress.org/documentation/article/what-is-post-type/\#menus)

Menus in WordPress are lists of links that can be used to navigate your website. This allows you to create custom lists of links to various locations on your website that is used by your visitors and are edited in the theme section of the dashboard away from traditional post types like posts or pages.

### [Custom CSS](https://wordpress.org/documentation/article/what-is-post-type/\#custom-css)

Custom CSS﻿ is a theme specific post type used to store CSS saved from The Customizers _**Additional CSS**_ screen. Each theme can have its own custom CSS post but only the active themes \`custom\_css\` post is actually used.

### [Changesets](https://wordpress.org/documentation/article/what-is-post-type/\#changesets)

Changesets are similar to revisions but specifically for the Customizer. This is to keep the Customizer in a persistent state. WordPress will attempt to keep content changes made through the Customizer during the user session in a \`customize\_changeset\` post and attempt to restore them should you exit your current session.

## [Custom Post Types](https://wordpress.org/documentation/article/what-is-post-type/\#custom-post-types)

Whilst there are already lots of standard post types within WordPress, you may want to extend the amount of post types you have if you want to break things down into smaller categories. For example, if you want to have a section on Books, it would be better suited to creating a custom post type for them. This can be done using the [register\_post\_type](https://developer.wordpress.org/reference/functions/register_post_type/) function.

It’s highly recommended that you define custom post types within a plugin or must-use plugin to ensure that if you switch themes, the post type isn’t lost. That way you can ensure your content is always accessible.

## [Template Files](https://wordpress.org/documentation/article/what-is-post-type/\#template-files)

By default WordPress makes use of the index.php, single.php and archive.php files in a theme to display posts of any type of the front-end of a website. However, if you’ve made a custom post type, you may find that you want to show this information in a different way to other types. You can do this by using post type specific [custom templates](https://developer.wordpress.org/themes/template-files-section/custom-post-type-template-files/) within your theme.

If you create a post type called Books like in the example above, you can create a template file called single-books.php which will show the individual book posts that you publish. Again, to show all your books in a custom archive page (where they are all listed), you can create an archive-books.php template file and this will show all the book posts that you’ve published.

## [Post Type Queries](https://wordpress.org/documentation/article/what-is-post-type/\#post-type-queries)

In the event that you want to get a list of your custom posts called Books, you can create a new [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) instance and fetch them all. This is handy if you want to create a custom loop somewhere on your website and show them in a different way to other posts.

## [The Posts Query](https://wordpress.org/documentation/article/what-is-post-type/\#the-posts-query)

You might find that in some cases you want to include custom posts into your main query of blog posts. You can do this by using the [pre\_get\_posts](https://developer.wordpress.org/reference/hooks/pre_get_posts/) filter hook which lets you customize the query that gets your posts before it’s shown on the front-end of the website.

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/what-is-post-type/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fwhat-is-post-type%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

October 27, 2018

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