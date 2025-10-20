---
url: https://wordpress.org/documentation/article/image-size-and-quality
scraped_at: 2025-10-20T02:09:37.046Z
---

[Skip to content](https://wordpress.org/documentation/article/image-size-and-quality/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Image size and quality

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Media](https://wordpress.org/documentation/category/media/)Image size and quality

Search documentation

# Image size and quality

## In this article

Table of Contents

- [Resizing Images](https://wordpress.org/documentation/article/image-size-and-quality/#resizing-images)
- [Further reading](https://wordpress.org/documentation/article/image-size-and-quality/#further-reading)
- [Resources](https://wordpress.org/documentation/article/image-size-and-quality/#resources)

[↑ Back to top](https://wordpress.org/documentation/article/image-size-and-quality/#wp--skip-link--target)

The size and quality of an image for use on a web page is determined by a variety of things.

**Physical Size**

The physical size of an image is based upon two things: The size of the image on the screen and the file size. Generally, the file size is treated as a different issue.

**File Size**

This is the size of the file on your hard drive or server.

**Resolution**

_Resolution_ refers to the number of pixels in an image. Resolution is sometimes identified by the width and height of the image as well as the total number of pixels in the image.

**File Type**

There are basically X image types popularly found on the Internet: `jpeg,gif,png` and (for [favicons](https://wordpress.org/documentation/article/create-a-favicon/) (the icons next to the address)) `ico`.

The **physical size** of the image is information we need to know in order to determine how much “space” will the image occupy on a web page. If your WordPress Theme features a fixed width content area of 600 pixels and the image you want to use is 800, the image will push the sidebar and layout of your web page around, messing up your design. Images within that 600 pixel width need to be restricted to that maximum width in order to protect the layout of your page. It’s up to you to determine what size they should be from there, matching the image to your overall layout and styles.

**File size** dictates the time it takes to load your page, the larger the file size, often increased because of a high **image resolution** quality, the longer it will take to load. People often don’t have the patience to wait through long web page loads, so keeping your file sizes low speeds up your web page access times. Typically, large high quality images should be kept between 100K and 60K. Smaller images should be closer to 30K and lower.

The **resolution** of the image dictates its clarity. The higher the resolution, though, the larger the file size, so you have to make a compromise between quality and file size.

Luckily, the various file types most commonly used on the Internet have _compression_ features. When you save the file as one of these types, it condenses or _compresses_ the data information in the image file. Internet browsers can _decompress_ this information to display the image on the screen. Some graphic software programs allow you to set the compression rate to control the quality of the image (and file size) at the time you save it. Depending upon your use of the images on your site, you may have to experiment with this to get the right ratio that keeps the resolution quality good while maintaining a small file size.

Websites use four common **file types**. The end of a filename (called the _extension_) tells what type it is. One type, `ico`, is to make a _[favicon](https://wordpress.org/documentation/article/create-a-favicon/)_ file — but this is usually only done when a website is first set up. The other three types are used for general images:

- `jpg` (JPEG) is good for photographs. Saving a photo as `jpg` removes detail from the photo. Good photo editors let you control how much detail is removed (the “compression”). Different photos need different compression; doing this carefully and viewing the result can give you a usable photo with a small file size.
- `gif` can be poor for photographs. It’s better for line art, like logos, with solid areas of the same color.
- `png` is for both photographs and line art. It compresses photos without losing detail, but usually makes larger photo files than JPEGs. Some older browsers don’t completely support `png`, though.

If you aren’t sure which file type is best for a particular image, try saving the image in more than one type and comparing the file sizes. Using the right type can make a big difference! There’s more information in [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types).

## [Resizing Images](https://wordpress.org/documentation/article/image-size-and-quality/\#resizing-images)

Not all graphic software packages allow you to resize images, though most should. Check your graphics software table of contents or index for _resize_, _size_, _transform_, _reduce_, or _enlarge_, all synonyms for the for the same thing. If they don’t have the feature, you may have to find different software.

The process of resizing images is fairly simple. There are usually two methods:

1) You can resize an image through the use of tools provided which allow you to manually shift the edges of an image to deform or resize the image. The best way is to grab a corner, not the edge, to resize the image. The corner “handle” will usually resize the image maintaining the overall height-width ratio. Check your manual for specific instructions.

2) The other method involves simply specifying the image’s final size. The advanced graphics programs allow you to set it by exact dimensions or a percentage of reduction or enlargement.

After resizing the image, the image may be smaller, but it may also be slightly out of focus. You can sharpen the focus of the small image by using the **sharpen** feature in your software.

When you have fine-tuned your small sized image or new thumbnail, export the image as a `jpg, gif,` or `png`.

## [Further reading](https://wordpress.org/documentation/article/image-size-and-quality/\#further-reading)

- [Use Images](https://wordpress.org/documentation/article/use-images/)
- [Use image and file attachments](https://wordpress.org/documentation/article/use-image-and-file-attachments/)
- [Settings Media Screen](https://wordpress.org/documentation/article/settings-media-screen/)
- [Media Add New Screen](https://wordpress.org/documentation/article/media-add-new-screen/)
- [Edit Media](https://wordpress.org/documentation/article/edit-media/)
- [Media library screen](https://wordpress.org/documentation/article/media-library-screen/)
- [Inserting Images into Posts and Pages (Block Editor)](https://wordpress.org/documentation/article/inserting-images-into-posts-and-pages-block-editor/)
- [Inserting Images into Posts and Pages (Classic Editor)](https://wordpress.org/documentation/article/inserting-images-into-posts-and-pages-classic/)

## [Resources](https://wordpress.org/documentation/article/image-size-and-quality/\#resources)

- [Image file type and format guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/image-size-and-quality/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fimage-size-and-quality%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

November 2, 2018

Last updated

July 5, 2023

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.