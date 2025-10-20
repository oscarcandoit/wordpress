---
url: https://wordpress.org/documentation/article/use-image-and-file-attachments
scraped_at: 2025-10-20T02:03:24.641Z
---

[Skip to content](https://wordpress.org/documentation/article/use-image-and-file-attachments/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Use image and file attachments

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Media](https://wordpress.org/documentation/category/media/)Use image and file attachments

Search documentation

# Use image and file attachments

## In this article

Table of Contents

- [Edit Screen Links](https://wordpress.org/documentation/article/use-image-and-file-attachments/#edit-screen-links)
- [Attachment to a Post](https://wordpress.org/documentation/article/use-image-and-file-attachments/#attachment-to-a-post)
- [Inserting in a Post](https://wordpress.org/documentation/article/use-image-and-file-attachments/#inserting-in-a-post)
- [Usage in Themes](https://wordpress.org/documentation/article/use-image-and-file-attachments/#usage-in-themes)
- [Further reading](https://wordpress.org/documentation/article/use-image-and-file-attachments/#further-reading)

[↑ Back to top](https://wordpress.org/documentation/article/use-image-and-file-attachments/#wp--skip-link--target)

In WordPress you can upload, store, and display a variety of file types (media). The most common file types are image, video and audio files, but other file types such as document files, spreadsheet files, and code samples (amongst others) can also be managed within WordPress.

Media can be uploaded via the [Media Add New Screen](https://wordpress.org/documentation/article/media-add-new-screen/) or [Media Library Screen](https://wordpress.org/documentation/article/media-library-screen/) in the admin area, or via quick links on the edit screen.

In order to upload media, you may need to ensure that the correct [file permissions](https://developer.wordpress.org/advanced-administration/server/file-permissions/) are set for the wp-content directory in your WordPress installation.

## [Edit Screen Links](https://wordpress.org/documentation/article/use-image-and-file-attachments/\#edit-screen-links)

By default, above the post editing area is a link to Upload/Insert media in to the post.

## [Attachment to a Post](https://wordpress.org/documentation/article/use-image-and-file-attachments/\#attachment-to-a-post)

If a media file is uploaded within the edit screen, it will automatically be attached to the current post being edited. If it is uploaded via the

[Media Add New Screen](https://wordpress.org/documentation/article/media-add-new-screen/) or [Media Library Screen](https://wordpress.org/documentation/article/media-library-screen/) it will be unattached, but may become attached to a post when it is inserted into post. There also is an option on the [Media Library Screen](https://wordpress.org/documentation/article/media-library-screen/) to attach unattached media items.

Note that media items are also ‘Posts’ in their own right and can be displayed as such via the WordPress [Template Hierarchy](https://developer.wordpress.org/themes/basics/template-hierarchy/). Themes can make use of this to loop over media items or create galleries.

If the parent post of an attached media item is deleted, the media item will become attached to the deleted post’s parent if it exists or if it doesn’t exist, the media item will become unattached and is open for re-attachment to another post.

## [Inserting in a Post](https://wordpress.org/documentation/article/use-image-and-file-attachments/\#inserting-in-a-post)

Once a media file has been uploaded, it may be [inserted in to a post](https://wordpress.org/documentation/article/inserting-images-into-posts-and-pages-block-editor/).

When the media file is inserted you can choose to:

- Link directly to the media file
- Link to the attachment post, in which case the file will be served via the WordPress [Template Hierarchy](https://developer.wordpress.org/themes/basics/template-hierarchy/)
- Not link to the media file (e.g. in the case of images, the image file will still be embedded in the page, but not linked to allow the browser to display the image file by itself)

## [Usage in Themes](https://wordpress.org/documentation/article/use-image-and-file-attachments/\#usage-in-themes)

Themes may use various template tags to display post attachments or utilize the [attachment.php](https://developer.wordpress.org/themes/basics/template-hierarchy/) file to customize the display of attachments. A [shortcode](https://developer.wordpress.org/themes/functionality/media/galleries/#gallery-shortcode) tag is also available to display a gallery of images attached to a post.

## [Further reading](https://wordpress.org/documentation/article/use-image-and-file-attachments/\#further-reading)

- [Use Images](https://wordpress.org/documentation/article/use-images/)
- [Image Size and Quality](https://wordpress.org/documentation/article/image-size-and-quality/)
- [Settings Media Screen](https://wordpress.org/documentation/article/settings-media-screen/)
- [Media library screen](https://wordpress.org/documentation/article/media-library-screen/)
- [Media Add New Screen](https://wordpress.org/documentation/article/media-add-new-screen/)
- [Edit Media](https://wordpress.org/documentation/article/edit-media/)
- [Inserting Images into Posts and Pages (Block Editor)](https://wordpress.org/documentation/article/inserting-images-into-posts-and-pages-block-editor/)
- [Inserting Images into Posts and Pages (Classic Editor)](https://wordpress.org/documentation/article/inserting-images-into-posts-and-pages-classic/)

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/use-image-and-file-attachments/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fuse-image-and-file-attachments%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

March 1, 2019

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