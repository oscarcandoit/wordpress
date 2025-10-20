---
url: https://developer.wordpress.org/themes/functionality/media/video
scraped_at: 2025-10-20T03:16:25.046Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Video


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Functionality](https://developer.wordpress.org/themes/classic-themes/functionality/)[Media](https://developer.wordpress.org/themes/classic-themes/functionality/media/)Video

Search

# Video

## In this article

Table of Contents

- [Video](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#video)
  - [Video shortcode](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#video-shortcode)
  - [Loop and Autoplay](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#loop-and-autoplay)
  - [Initial image and Styling](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#initial-image-and-styling)
  - [References](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#references)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#wp--skip-link--target)

## [Video](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#video)

The WordPress video feature allows you to embed video files and play them back using a simple shortcode **\[video\]**. Supported file types are mp4, m4v, webm, ogv, wmv and flv.

### [Video shortcode](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#video-shortcode)

Following shortcode displays video player that loads pepper.mp4 file:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#)

```php
[video src="pepper.mp4"]
```

To use the shortcode in the template file, use the [do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/) function. If the video file is stored in in your theme directory, get the file url directly using [get\_template\_directory\_uri()](https://developer.wordpress.org/reference/functions/get_template_directory_uri/) or [get\_stylesheet\_uri()](https://developer.wordpress.org/reference/functions/get_stylesheet_uri/) :

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#)

```php
$video_file = get_template_directory_uri() . "/videos/pepper.mp4";
echo do_shortcode( '[video mp4=' . $video_file . ']' );
```

The following video player will be loaded.

### [Loop and Autoplay](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#loop-and-autoplay)

The shortcode video has the same option with audio. Refer to the related section for the [loop and autoplay](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#loop-and-autoplay) options.

The following example starts playing the video immediately after the page load and loops:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#)

```php
echo do_shortcode( '[video mp4=' . $video_file . ' loop="on" autoplay=1]' );
```

### [Initial image and Styling](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#initial-image-and-styling)

The following basic options are supported:

#### [Poster](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#poster)

Defines image to show as placeholder before the media plays.

The following same code takes `album_cover.jpg` stored in `(theme directory)/images` folder as the initial image:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#)

```php
echo do_shortcode( '[video mp4=' . $video_file . ' poster=' . get_template_directory_uri() . '/images/album_cover.jpg]' );
```

#### [Height](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#height)

Defines height of the media. Value is automatically detected on file upload. When you omit this option, the media file height is used.

#### [Width](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#width)

Defines width of the media. Value is automatically detected on file upload. When you omit this option, the media file width is used.

The theme’s content\_width sets the maximum width.

The following example will load the audio player with 320 pixels width and 240 pixels height:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#)

```php
echo do_shortcode( '[video mp4=' . $video_file . ' width=320 height=240]' );
```

#### [Styling](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#styling)

If you want to change look & feel of video player from stylesheet, you can target the class name of “wp-video-shortcode”. If you want to show the audio player like above in 320 x 240 size, insert following code into your stylesheet:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/#)

```css
.wp-video-shortcode {
    height: 240px;
    width: 320px;
}

```

#### [Supported Video format](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#supported-video-format)

- mp4
- m4v
- webm
- ogv
- flv

### [References](https://developer.wordpress.org/themes/classic-themes/functionality/media/video/\#references)

For more technical details such as internal library that enables this function, refer to

- [https://make.wordpress.org/core/2013/04/08/audio-video-support-in-core/](https://make.wordpress.org/core/2013/04/08/audio-video-support-in-core/).
- [Video Shortcode](https://codex.wordpress.org/Video_Shortcode)
- [Function do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/)

First published

January 13, 2017

Last updated

October 25, 2022

[PreviousImagesPrevious: Images](https://developer.wordpress.org/themes/classic-themes/functionality/media/images/)

[NextNavigation MenusNext: Navigation Menus](https://developer.wordpress.org/themes/classic-themes/functionality/navigation-menus/)

Notifications