---
url: https://developer.wordpress.org/themes/basics/reworking-theme-files-organization
scraped_at: 2025-10-20T03:20:10.458Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Reworking Theme Files & Organization


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Basics](https://developer.wordpress.org/themes/classic-themes/basics/)Reworking Theme Files & Organization

Search

# Reworking Theme Files & Organization

## In this article

Table of Contents

- [Theme folder and file structure](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/#theme-folder-and-file-structure)
  - [Page templates folder](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/#page-templates-folder)
  - [Language folder](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/#language-folder)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/#wp--skip-link--target)

![basics-theme-files-organization-01](https://i0.wp.com/developer.wordpress.org/files/2014/08/basics-theme-files-organization-01.jpg?resize=1024%2C384&ssl=1)

## [Theme folder and file structure](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/\#theme-folder-and-file-structure)

While WordPress themes technically only require two files ( `index.php` and `style.css`), they usually are made up of many files and can become quickly disorganized.

In the last section, [Template Files](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/# "Template Files"), you set up your `header.php, footer.php, page.php, home.php, and single.php` files.

Let’s look at  the [Twenty Twelve theme](https://wordpress.org/themes/twentytwelve) default themes as one example of good file structure and organization.  While this may be a bit overwhelming at first, let’s break it down.  Can you find the templates you just built?

![basics-theme-files-organization-02](https://i0.wp.com/developer.wordpress.org/files/2014/08/basics-theme-files-organization-02.png?resize=629%2C1500&ssl=1)

While there are still a lot of files, their names help provide a context of what they are.  Basically each file handles a feature of WordPress.  I.e. `comments.php` deals with how the theme will handle comments; `image.php` instructs the theme how to handle images, etc.  Don’t worry about adding these files unless you need them.

You can see that the main theme template files are in the theme’s root directory, while JavaScript, languages, CSS, and page template files are placed within their own folders.

At this time there are **no required folders within a WordPress theme**. However, WordPress does recognize the following folders by default:

### [Page templates folder](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/\#page-templates-folder)

![basics-theme-files-organization-03](https://i0.wp.com/developer.wordpress.org/files/2014/08/basics-theme-files-organization-03.png?resize=400%2C124&ssl=1)

The [custom page templates](https://developer.wordpress.org/themes/basics/page-templates/ "Custom Page Templates"), named _page-templates_ (since: 3.4.0) allows for better organization of template files. Custom page template files placed in this folder are automatically recognized by WordPress.

### [Language folder](https://developer.wordpress.org/themes/classic-themes/basics/reworking-theme-files-organization/\#language-folder)

![basics-theme-files-organization-04](https://i0.wp.com/developer.wordpress.org/files/2014/08/basics-theme-files-organization-04.png?resize=400%2C85&ssl=1)

If you wish to [internationalize your theme](https://developer.wordpress.org/themes/functionality/internationalization/ "Internationalization") so it’s usable in other languages, you can create a _languages_ folder to contain translations.

First published

December 9, 2014

Last updated

June 14, 2019

[PreviousPost TypesPrevious: Post Types](https://developer.wordpress.org/themes/classic-themes/basics/post-types/)

[NextTemplate FilesNext: Template Files](https://developer.wordpress.org/themes/classic-themes/basics/template-files/)

Notifications