---
url: https://wordpress.org/documentation/article/video-shortcode
scraped_at: 2025-10-20T02:02:22.871Z
---

[Skip to content](https://wordpress.org/documentation/article/video-shortcode/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Video shortcode

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Dashboard](https://wordpress.org/documentation/category/dashboard/)Video shortcode

Search documentation

# Video shortcode

## In this article

Table of Contents

- [Usage](https://wordpress.org/documentation/article/video-shortcode/#usage)
- [Options](https://wordpress.org/documentation/article/video-shortcode/#options)
- [Related](https://wordpress.org/documentation/article/video-shortcode/#related)

[↑ Back to top](https://wordpress.org/documentation/article/video-shortcode/#wp--skip-link--target)

The **Video** feature allows you to embed video files and play them back using a simple shortcode. This was added as of WordPress [Version 3.6](https://wordpress.org/documentation/wordpress-version/version-3-6/) and is used like this:

```
[video]
```

You can also use built in embeds and simply put the media file on its own line:

```
My cool content
http://my.movies.com/cool/movie/coolest.mp4
More cool content
```

## [Usage](https://wordpress.org/documentation/article/video-shortcode/\#usage)

I have an old post that has an audio file in the Media Library attached to it, and I want to use the new shortcode:

```
[video]
```

Note: Do Not put Space between “\[” and “video”.\
\
I have the URL for an MP3, from the Media Library or external, that I want to play:\
\
```\
[video src="video-source.mp4"]\
```\
\
I have a source URL and fallbacks for other HTML5-supported filetypes:\
\
```\
[video mp4="source.mp4" ogv="source.ogv" webm="source.webm"]\
```\
\
## [Options](https://wordpress.org/documentation/article/video-shortcode/\#options)\
\
The following basic options are supported:\
\
`src`\
\
(string) (optional) The source of your video file. If not included it will auto-populate with the first video file attached to the post. You can use the following options to define specific filetypes, allowing for graceful fallbacks:\
\
- mp4, m4v, webm, ogv, wmv, flv\
\
Default: First video file attached to the post\
\
`poster`\
\
Defines image to show as placeholder before the media plays.\
\
Default: none\
\
`loop`\
\
(string) Allows for the looping of media. Defaults to “off.”\
\
- “off” – (“default”) does not loop the media\
- “on” – media will loop to beginning when finished and automatically continue playing\
\
Default: “off”\
\
`autoplay`\
\
(string) Causes the media to automatically play as soon as the media file is ready. Defaults to “off.”\
\
- “off” – (“default”) does not automatically play the media\
- “on” – Media will play as soon as the media is ready\
\
Default: “off”\
\
`preload`\
\
(string) (optional) Specifies if and how the video should be loaded when the page loads. Defaults to “metadata.”\
\
- “metadata” – (“default”) only metadata should be loaded when the page loads\
- “none” – the video should not be loaded when the page loads\
- “auto” – the video should be loaded entirely when the page loads\
\
Default: “metadata”\
\
`height`\
\
(integer) (required) Defines height of the media. Value is automatically detected on file upload.\
\
Default: \[Media file height\]\
\
`width`\
\
(integer) (required) Defines width of the media. Value is automatically detected on file upload.\
\
Default: \[Media file width\]\
\
## [Related](https://wordpress.org/documentation/article/video-shortcode/\#related)\
\
WordPress Shortcodes: [audio](https://wordpress.org/documentation/article/audio-shortcode/), [caption](https://codex.wordpress.org/Caption_Shortcode), [embed](https://codex.wordpress.org/Embed_Shortcode), [gallery](https://codex.wordpress.org/Gallery_Shortcode), [playlist](https://codex.wordpress.org/Playlist_Shortcode)\
\
#### [Changelog](https://wordpress.org/documentation/article/video-shortcode/\#changelog)\
\
- Updated 2021-10-18\
  - Added changelog\
  - Corrected the links to the codex pages for the caption, embed, gallery and playlist shortcodes\
\
## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/video-shortcode/\#respond)\
\
[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fvideo-shortcode%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).\
\
First published\
\
November 2, 2018\
\
Last updated\
\
June 9, 2024\
\
## Get more help\
\
[Support forums](https://wordpress.org/support/forums/)\
\
Ask questions in the support forums.\
\
[Developers](https://developer.wordpress.org/)\
\
Check out the developer documentation.\
\
[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)\
\
Report an error or change in the documentation issue tracker.\
\
[Get involved](https://make.wordpress.org/docs/)\
\
Learn about the Documentation Team and how to contribute.