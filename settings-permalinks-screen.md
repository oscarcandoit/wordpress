---
url: https://wordpress.org/documentation/article/settings-permalinks-screen
scraped_at: 2025-10-20T02:06:39.076Z
---

[Skip to content](https://wordpress.org/documentation/article/settings-permalinks-screen/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Settings Permalinks screen

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Dashboard](https://wordpress.org/documentation/category/dashboard/)Settings Permalinks screen

Search documentation

# Settings Permalinks screen

## In this article

Table of Contents

- [Customize Permalink structure](https://wordpress.org/documentation/article/settings-permalinks-screen/#customize-permalink-structure)
  - [Common settings](https://wordpress.org/documentation/article/settings-permalinks-screen/#common-settings)
  - [Optional](https://wordpress.org/documentation/article/settings-permalinks-screen/#optional)
  - [Save Changes](https://wordpress.org/documentation/article/settings-permalinks-screen/#save-changes)

[↑ Back to top](https://wordpress.org/documentation/article/settings-permalinks-screen/#wp--skip-link--target)

**Permalinks** are the permanent URLs to your individual pages and blog posts, as well as your category and tag archives. A permalink is the web address used to link to your content. The URL to each post should be permanent and never change — hence the name permalink.

The **Settings Permalinks Screen** allows you to choose your default permalink structure. You can choose from common settings or create custom URL structures. You must click the **Save Changes** button at the bottom of the screen for the new settings to take effect.

By default, WordPress uses web URLs that have day and name in them; however, WordPress offers you the ability to create a custom URL structure for your permalinks and archives. This can improve the aesthetics, usability, and forward compatibility of your links.

For an introduction to Permalinks, read the [Pretty Permalinks](https://wordpress.org/support/article/introduction-to-blogging/#pretty-permalinks) section of [Introduction to Blogging](https://wordpress.org/support/article/introduction-to-blogging/). For a more in-depth description of the way this structure is specified, see the [Using Permalinks](https://wordpress.org/documentation/article/using-permalinks/) article.

[![WordPress permalink settings screen](https://wordpress.org/documentation/files/2022/11/wordpress-permalink-settings.png)](https://wordpress.org/documentation/files/2022/11/wordpress-permalink-settings.png)

## [Customize Permalink structure](https://wordpress.org/documentation/article/settings-permalinks-screen/\#customize-permalink-structure)

A [number of tags are available](https://wordpress.org/support/article/using-permalinks/#structure-tags-1), and here are some examples to get you started.

### [Common settings](https://wordpress.org/documentation/article/settings-permalinks-screen/\#common-settings)

Check one of the radio buttons corresponding to the correct Permalink Structure for your blog.

- **Plain** – An example of the default structure is **http://www.sample.com/?p=123**
- **Day and name** – An example of the day and name based structure is **http://www.sample.com/2008/03/31/sample-post/**

- **Month and name** – An example of the month and name based structure is **http://www.sample.com/2008/03/sample-post/**

- **Numeric** – An example of the numeric structure is **http://www.sample.com/archives/123**

- **Post name** – An example of the post name structure is **http://www.sample.com/sample-post**

- **Custom structure** – In the box specify the custom structure you desire to use. One example is **/archives/%year%/%monthnum%/%day%/%postname%/**. Look at the [Permalink Structure Tags](https://wordpress.org/support/article/using-permalinks/#structure-tags).

### [Optional](https://wordpress.org/documentation/article/settings-permalinks-screen/\#optional)

You may enter custom bases for your category and tag URLs here. For example, using **/topics/** as your category base would make your category links like **http://example.org/topics/uncategorized/**. If you leave these blank the defaults will be used. Again, see the [Permalink Structure Tags](https://wordpress.org/support/article/using-permalinks/#structure-tags).

- **Category base** – Enter a custom prefix for your category URLs here.

- **Tag base** – Enter a custom prefix for your tag URLs here.

### [Save Changes](https://wordpress.org/documentation/article/settings-permalinks-screen/\#save-changes)

Click the **Save Changes** button to ensure any changes you have made to your Settings are saved to your database. Once you click the button, a confirmation text box will appear at the top of the page telling you your settings have been saved.

After you’ve clicked this button, you should receive one of two messages depending on whether your [.htaccess](https://wordpress.org/support/article/glossary/#htaccess) file is writeable.

- If [.htaccess](https://wordpress.org/support/article/glossary/#htaccess) is writeable, you will get a message that says “ **Permalink structure updated.**” You’re all set; WordPress has been able to do everything for you automatically.
- If [.htaccess](https://wp-helphub.com/support/article/glossary/#htaccess) is _not_ writeable, you will see a message at the top of the screen that says “ **You should update your .htaccess now.**“. Near the bottom of the screen you will see “ **If your .htaccess file were writable, we could do this automatically, but it isn’t so these are the mod\_rewrite rules you should have in your [.htaccess](https://wp-helphub.com/support/article/glossary/#htaccess) file. Click in the field and press CTRL + a to select all.**” This means you’ll have to do one extra step yourself. In the text box at the bottom of the Screen, WordPress displays several lines of [rewrite](https://wordpress.org/support/article/glossary/#mod_rewrite) rules associated with the Permalink Structure you designated above. You need to manually copy everything in this text box into your [.htaccess](https://wp-helphub.com/support/article/glossary/#htaccess) file to make your new Permalinks work.

For information on how to make [.htaccess](https://wordpress.org/support/article/glossary/#htaccess) writeable, see [Changing File Permissions](https://codex.wordpress.org/Changing%20File%20Permissions).

**Note**: Visiting the Permalinks screen triggers a flush of rewrite rules. There is no need to save just to flush the rewrite rules.

**Note**: If you’re writing your [.htaccess](https://wordpress.org/support/article/glossary/#htaccess) file on your own local computer, remember, some operating systems do not allow the creation of a file named “ `.htaccess`” because of the initial dot (“ **`.`**“). You can always name the file without the initial dot or with a standard extension (e.g. “ `htaccess.txt`“). Once the file is uploaded to your weblog’s directory, rename it with your [FTP](https://wordpress.org/support/article/glossary/#ftp) software. Most [FTP Clients](https://wordpress.org/support/article/ftp-clients/) should provide you a way to rename files this.

**Also Note**: Files that begin with a dot (“ **`.`**“) like “ `.htaccess`” are hidden on most servers by default. Consult the user guide or FAQ of the FTP software you use to find out how to have the software display these hidden files, and also how to use the software to change file permissions, rename files, etc. For more information on all of this see [Changing File Permissions](https://codex.wordpress.org/Changing%20File%20Permissions).

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/settings-permalinks-screen/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fsettings-permalinks-screen%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

November 6, 2018

Last updated

June 8, 2024

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.