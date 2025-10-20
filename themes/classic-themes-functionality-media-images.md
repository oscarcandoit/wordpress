---
url: https://developer.wordpress.org/themes/classic-themes/functionality/media/images
scraped_at: 2025-10-20T03:12:41.368Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Images


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Functionality](https://developer.wordpress.org/themes/classic-themes/functionality/)[Media](https://developer.wordpress.org/themes/classic-themes/functionality/media/)Images

Search

# Images

## In this article

Table of Contents

- [Images](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#images)
  - [Getting img code](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#getting-img-code)
  - [Getting URL of image](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#getting-url-of-image)
  - [Alignments](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#alignments)
  - [Caption](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#caption)
- [WebP support and default MIME type of sub size image output](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#webp-support-and-default-mime-type-of-sub-size-image-output)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#wp--skip-link--target)

## [Images](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/\#images)

This section describes the handling of images in the Media Library. If you want to display the image file located within your theme directory, just specify the location with the img tag, and style it with CSS.

```
<img alt="" src="" />
```

### [Getting img code](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/\#getting-img-code)

To display the image in the Media Library, use `[wp\_get\_attachment\_image()](https://developer.wordpress.org/reference/functions/wp_get_attachment_image/)` function.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#)

```php
echo wp_get_attachment_image( $attachment->ID, 'thumbnail' );
```

You will get the following HTML output with the selected thumbnail size

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#)

```markup
<img width="150" height="150" src="http://example.com/wordpress/wp-content/uploads/2016/11/sample-150x150.jpg" class="attachment-thumbnail size-thumbnail" ... />
```

You can specify other size such as ‘full’ for original image or ‘medium’ and ‘large’ for the sizes set at **Settings > Media** in the [Administration Screen](https://codex.wordpress.org/Administration_Screens), or any pair of width and height as array. You’re also free to set custom size strings with [add\_image\_size()](https://developer.wordpress.org/reference/functions/add_image_size/) ;

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#)

```php
echo wp_get_attachment_image( $attachment->ID, array(640, 480) );
```

### [Getting URL of image](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/\#getting-url-of-image)

If you want to get the URL of the image, use `[wp\_get\_attachment\_image\_src()](https://developer.wordpress.org/reference/functions/wp_get_attachment_image_src/)`. It returns an array (URL, width, height, is\_intermediate), or `false`, if no image is available.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#)

```php
<?php
$image_attributes = wp_get_attachment_image_src( $attachment->ID );
if ( $image_attributes ) : ?>
    <img src="<?php echo $image_attributes[0]; ?>" width="<?php echo $image_attributes[1]; ?>" height="<?php echo $image_attributes[2]; ?>" />
<?php endif; ?>
```

### [Alignments](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/\#alignments)

When adding the image in your site, you can specify the image alignment as right, left, center or none. WordPress core automatically adds CSS classes to align the image:

- alignright
- alignleft
- aligncenter
- alignnone

This is the sample output when center align si chosen

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#)

```markup
<img class="aligncenter size-full wp-image-131" src= ... />
```

In order to take advantage of these CSS classes for alignment and text wrapping, your theme must include the styles in a stylesheet such as the [main stylesheet file](https://developer.wordpress.org/themes/basics/main-stylesheet-style-css/). You can use the `style.css` bundled with official themes such as Twenty Seventeen for reference.

### [Caption](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/\#caption)

If a Caption was specified to image in the Media Library, HTML `img` element was enclosed by the shortcode \[caption\] and \[/caption\].

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#)

```markup
<div class="mceTemp">
  <dl id="attachment_133" class="wp-caption aligncenter" style="width: 1210px">
    <dt class="wp-caption-dt">
      <img class="size-full wp-image-133" src="http://example.com/wordpress/wp-content/uploads/2016/11/sample.jpg" alt="sun set" width="1200" height="400" />
    </dt>
    <dd class="wp-caption-dd">Sun set over the sea</dd>
  </dl>
</div>
```

And, it will be rendered as in HTML as the figure tag:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#)

```markup
<figure id="attachment_133" style="width: 1200px" class="wp-caption aligncenter">
  <img class="size-full wp-image-133" src="http://example.com/wordpress/wp-content/uploads/2016/11/sample.jpg" alt="sun set" width="1200" height="400" srcset= ... />
  <figcaption class="wp-caption-text">Sun set over the sea</figcaption>
</figure>
```

Similar to alignments, your theme must include following styles.

- `wp-caption`
- `wp-caption-text`

## [WebP support and default MIME type of sub size image output](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/\#webp-support-and-default-mime-type-of-sub-size-image-output)

[WordPress 5.8](https://make.wordpress.org/core/2021/06/07/wordpress-5-8-adds-webp-support/) introduces support for [WebP](https://developers.google.com/speed/webp) image format which provides improved lossless and lossy compression for images on the web. WebP images are around 30% smaller on average than their JPEG or PNG equivalents, resulting in sites that are faster and use less bandwidth. WebP is supported in all modern browsers [according to caniuse](https://caniuse.com/webp).

When images are uploaded, WordPress generates smaller sub sizes as defined using `add_image_size()`. By default, WordPress will generate these sub sizes in the same format as the original. Because of the performance benefits of the WebP format, it may be desirable for sub sizes to be generated in WebP instead of the original format.

`image_editor_output_format` filter hook can be used to change the file format used for image sub sizes. This can be used to switch all sub sizes to WebP, or any other desired format (JPEG, etc.).

The following example shows how to generate all sub sizes for JPG images using WebP:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/#)

```php
<?php
function wporg_image_editor_output_format( $formats ) {
    $formats['image/jpg'] = 'image/webp';

    return $formats;
}
add_filter( 'image_editor_output_format', 'wporg_image_editor_output_format' );
```

**Note:** both the GD and ImageMagick libraries support the WebP format in both lossy and lossless. However, only ImageMagick supports animated images.

Setting the output format to WebP will verify if the web server supports it, and if not it will not change the format, i.e. won’t work.

#### [References](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/\#references)

- `[wp\_get\_attachment\_image()](https://developer.wordpress.org/reference/functions/wp_get_attachment_image/)`
- `[wp\_get\_attachment\_image\_src()](https://developer.wordpress.org/reference/functions/wp_get_attachment_image_src/)`
- [Styling Images in Posts and Pages](https://codex.wordpress.org/Styling_Images_in_Posts_and_Pages)
- [CSS (Codex)](https://codex.wordpress.org/CSS)

First published

January 13, 2017

Last updated

November 1, 2022

[PreviousGalleriesPrevious: Galleries](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/)

[NextVideoNext: Video](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/)

Notifications