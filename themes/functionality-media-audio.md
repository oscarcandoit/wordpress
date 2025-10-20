---
url: https://developer.wordpress.org/themes/functionality/media/audio
scraped_at: 2025-10-20T03:17:52.210Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Audio


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Functionality](https://developer.wordpress.org/themes/classic-themes/functionality/)[Media](https://developer.wordpress.org/themes/classic-themes/functionality/media/)Audio

Search

# Audio

## In this article

Table of Contents

- [Audio](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#audio)
  - [Audio shortcode](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#audio-shortcode)
  - [Loop and Autoplay](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#loop-and-autoplay)
  - [Styling](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#styling)
  - [References](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#references)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#wp--skip-link--target)

## [Audio](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/\#audio)

You can directly embed audio files and play them back using a simple shortcode **\[audio\]**. Supported file types are mp3, ogg, wma, m4a and wav.

### [Audio shortcode](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/\#audio-shortcode)

Following shortcode displays audio player that loads music.mp3 file:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#)

```php
[[audio src="music.mp3"]]
```

To use the shortcode from template file, use do\_shortcode function. When music.mp3 file was stored in (theme\_directory)/sounds directory, insert following code into your template file:

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#)

```php
$music_file = get_template_directory_uri() . "/sounds/music.mp3";
echo do_shortcode('[[audio mp3=' . $music_file . ']]');
```

The shortcode creates the audio player as shown in the screenshot below.

![Audio player](https://i0.wp.com/developer.wordpress.org/files/2014/10/audio_shortcode_basic.jpg?resize=558%2C66&ssl=1)

### [Loop and Autoplay](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/\#loop-and-autoplay)

The following basic options are supported:

#### [loop](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/\#loop)

Allows for the looping of media.

- “off” – Do not loop the media. Default.
- “on” – Media will loop to beginning when finished and automatically continue playing.

#### [autoplay](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/\#autoplay)

Causes the media to automatically play as soon as the media file is ready.

- 0 – Do not automatically play the media. Default.
- 1 – Media will play as soon as it is ready.

The following example starts playing music immediately after the page load and loops.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#)

```php
echo do_shortcode('[[audio mp3=' . $music_file . ' loop = "on" autoplay = 1]]');
```

### [Styling](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/\#styling)

If you want to change the look & feel of audio player, you can do so by targeting the default class name of “wp-audio-shortcode”. If you insert following code into your style.css, half width of audio player will be displayed.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/#)

```css
.wp-audio-shortcode {
  width: 50%;
}
```

#### [Supported Audio format](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/\#supported-audio-format)

- mp3
- ogg
- wma
- m4a
- wav

### [References](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/\#references)

For more technical details such as the internal library that enables this function, refer to

- [https://make.wordpress.org/core/2013/04/08/audio-video-support-in-core/](https://make.wordpress.org/core/2013/04/08/audio-video-support-in-core/).
- [Audio Shortcode](https://codex.wordpress.org/Audio_Shortcode)
- [Function do\_shortcode()](https://developer.wordpress.org/reference/functions/do_shortcode/)

First published

January 13, 2017

Last updated

January 15, 2017

[PreviousMediaPrevious: Media](https://developer.wordpress.org/themes/classic-themes/functionality/media/)

[NextGalleriesNext: Galleries](https://developer.wordpress.org/themes/classic-themes/functionality/media/galleries/)

Notifications