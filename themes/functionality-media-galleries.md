---
url: https://developer.wordpress.org/themes/functionality/media/galleries
scraped_at: 2025-10-20T03:18:03.838Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Galleries


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Functionality](https://developer.wordpress.org/themes/classic-themes/functionality/)[Media](https://developer.wordpress.org/themes/classic-themes/functionality/media/)Galleries

Search

# Galleries

## In this article

Table of Contents

- [Galleries](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#galleries)
  - [Gallery shortcode](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#gallery-shortcode)
  - [Usage](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#usage)
  - [Supported Options](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#supported-options)
  - [References](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#references)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#wp--skip-link--target)

## [Galleries](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#galleries)

[![](https://i0.wp.com/developer.wordpress.org/files/2014/10/Capture.png?resize=711%2C583&ssl=1)](https://i0.wp.com/developer.wordpress.org/files/2014/10/Capture.png?ssl=1)

Image galleries are the best way to showcase your pictures on your WordPress sites. WordPress bundles the **Create Gallery** feature by default in the media uploader which allows you to create a simple gallery.

Note: Before adding a gallery, you must have images in your media library. Otherwise, you need to upload the images into the library and can proceed on gallery creation.

### [Gallery shortcode](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#gallery-shortcode)

The **Gallery** feature allows you to add one or more image galleries to your posts and pages using a simple Shortcode.

The basic form of gallery shortcode is:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
[gallery]
```

If you use the \[gallery\] shortcode without using the `ids` argument in your post or page, only images that are “attached” to that post or page will be displayed.

If you need to add multiple images with ID’s, use the following sample shortcode

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
//Note: 10, 205, 552 and 607 are the IDs of respected image.
[gallery ids="10, 205, 552, 607"]
```

NOTE: find the proper IDs of the images for the gallery. Go to Media library and click on the respected image and ID will appear on the URL.

To use the shortcode from the template file, use the [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) function. Insert the following code into your template file:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
<?php echo do_shortcode( [gallery] ); ?>
```

If you need to use the shortcode with IDs, insert the following code in your template file:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
<?php echo do_shortcode( [gallery ids="10, 205, 552, 607"] ); ?>
```

### [Usage](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#usage)

There are may options that may be specified using the below syntax:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
[gallery option1="value1" option2="value2"]
```

If you want to print the gallery directly on the template file, use \` [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) \` function like below:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
<?php echo do_shortcode( '[gallery option1="value1"]' ); ?>
```

If you need to filter the shortcodes, the following example gives you some tips

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
// Note: 'the_content' filter is used to filter the content of the
// post after it is retrieved from the database and before it is
// printed to the screen.
<?php
$gallery_shortcode = '[gallery id="' . intval( $post->post_parent ) . '"]';
print apply_filters( 'the_content', $gallery_shortcode );
?>
```

### [Supported Options](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#supported-options)

Gallery Shortcodes supports the basic options which are listed below:

#### [Orderby](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#orderby)

‘orderby’ specifies the order the thumbnails show up. The default order is ‘menu\_order’.

- menu\_order: You can reorder the images in the Gallery tab of the Add Media popup
- title: Order by the title of the image in the Media Library
- post\_date: Sort by date/time
- rand: Order randomly
- ID: Specify the post ID

#### [Order](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#order)

order specify the sort order used to display thumbnail; ASC or DESC. For Example, to sort by ID and DESC:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
[gallery order="DESC" orderby="ID"]
```

If you need to print it on template file, use the [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) function;

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
<?php echo do_shortcode( '[gallery]' ); ?>
```

#### [columns](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#columns)

The Columns options specify the number of columns in the gallery. The default value is 3.

If you want to increase the number of column in the galley, use the following shortcode.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
[gallery columns="4"]
```

If you need to print it on your template file, use the [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) function;

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
<?php echo do_shortcode(' [gallery columns="4"] '); ?>
```

#### [IDs](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#ids)

The IDs option on the gallery shortcode loads images with specific post IDs.

If you want to display the attached image with the specific post ID, follow the following code example.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
// Note: remove each space between brackets and 'gallery' and brackets and `123"`.
//Here "123" stands for the post IDs. If you want to display more than
//one ID, separate the IDs by a comma `,`.
[ gallery id="123" ]
```

Use ‘do\_shortcode’ function to print the gallery with IDs on template files like below:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
// Note: remove each space between brackets and 'gallery' and brackets and `123"`.
<?php echo do_shortcode(' [ gallery id="123" ] '); ?>
```

#### [Size](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#size)

Size determines the image size to use for the thumbnail display. Valid values include “thumbnail”, “medium”, “large”, “full” and any other additional image size that was registered with [add\_image\_size()](https://developer.wordpress.org/reference/functions/add_image_size/). The default value is “thumbnail”. The size of the images for “thumbnail”, “medium” and “large” can be configured in WordPress admin panel under Settings > Media.

For example, to display a gallery of medium sized images:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
[gallery size="medium"]
```

Some advanced options are also available on Gallery shortcodes.

#### [itemtag](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#itemtag)

The name of the HTML tag used to enclose each item in the gallery. The default is “dl”.

#### [icontag](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#icontag)

The name of the HTMLtag used to enclose each thumbnail icon in the gallery. The default is “dt”.

#### [captiontag](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#captiontag)

The name of the HTML tag used to enclose each caption. The default is “dd”.

You are allowed to change the defaults.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
[gallery itemtag="div" icontag="span" captiontag="p"]
```

#### [Link](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#link)

Specify where you want the image to link. The default value links to the attachment’s [permalink](https://codex.wordpress.org/Using_Permalinks). Options:

- file – Link directly to image file
- none – No link

Example:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
[gallery link="file"]
```

#### [Include](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#include)

Include allows you to insert an “array” of comma separated attachment IDs to show only the images from these attachments.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```php
[gallery include="23,39,45"]
```

#### [Exclude](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#exclude)

Exclude callows you to insert an “array” of comma separated attachment IDs to not show the images from these attachments. Please note that include and exclude cannot be used together.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/#)

```markup
[gallery exclude="21,32,43"]
```

### [References](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/\#references)

For more technical details take a reference from below links

- [Gallery Shortcode](https://codex.wordpress.org/Gallery_Shortcode)
- [Function do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/)

First published

January 13, 2017

Last updated

November 1, 2022

[PreviousAudioPrevious: Audio](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/)

[NextImagesNext: Images](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/)

Notifications