---
url: https://wordpress.org/documentation/article/audio-shortcode
scraped_at: 2025-10-20T02:06:17.060Z
---

[Skip to content](https://wordpress.org/documentation/article/audio-shortcode/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Audio Shortcode

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Media](https://wordpress.org/documentation/category/media/)Audio Shortcode

Search documentation

# Audio Shortcode

## In this article

Table of Contents

- [Usage](https://wordpress.org/documentation/article/audio-shortcode/#usage)
- [Options](https://wordpress.org/documentation/article/audio-shortcode/#options)
- [Related](https://wordpress.org/documentation/article/audio-shortcode/#related)

[↑ Back to top](https://wordpress.org/documentation/article/audio-shortcode/#wp--skip-link--target)

The Audio feature allows you to embed audio files and play them back using a simple Shortcode. This was added as of WordPress 3.6 and is used like this:

```
[ audio]
```

Note: Do not put space between “\[” and “audio”.\
\
You can also use build-in embeds and simply put the media file on its own line:\
\
```\
My cool content\
http://my.mp3s.com/cool/songs/coolest.mp3\
More cool content\
```\
\
## [Usage](https://wordpress.org/documentation/article/audio-shortcode/\#usage)\
\
I have an old post that has an audio file in the Media Library attached to it, and I want to use the new shortcode:\
\
```\
[ audio]\
```\
\
Note: Do Not put Space between “\[” and “audio”.\
\
I have the URL for an MP3, from the Media Library or external, that I want to play:\
\
```\
[audio src="audio-source.mp3"]\
```\
\
I have a source URL and fallbacks for other HTML5-supported filetypes:\
\
```\
[audio mp3="source.mp3" ogg="source.ogg" wav="source.wav"]\
```\
\
## [Options](https://wordpress.org/documentation/article/audio-shortcode/\#options)\
\
The following basic options are supported:\
\
`src`\
\
( [string](https://wordpress.org/documentation/article/glossary/#string)) (optional) The source of your audio file. If not included it will auto-populate with the first audio file attached to the post. You can use the following options to define specific filetypes, allowing for graceful fallbacks:\
\
- ‘mp3’, ‘m4a’, ‘ogg’, ‘wav’, ‘wma’\
\
Default: First audio file attached to the post\
\
`loop`\
\
( [string](https://wordpress.org/documentation/article/glossary/#string)) (optional) Allows for the looping of media.\
\
- “off” – Do not loop the media.\
- “on” – Media will loop to the beginning when finished and automatically continue playing.\
\
Default: “off”\
\
`autoplay`\
\
( [string](https://wordpress.org/documentation/article/glossary/#string)) (optional) Causes the media to automatically play as soon as the media file is ready.\
\
- “off” – Do not automatically play the media.\
- “on” – Media will play as soon as it is ready.\
\
Default: “off”\
\
`preload`\
\
( [string](https://wordpress.org/documentation/article/glossary/#string)) (optional) Specifies if and how the audio should be loaded when the page loads. Defaults to “none”\
\
- “none” – The audio should not be loaded when the page loads.\
- “auto” – The audio should be loaded entirely when the page loads.\
- “metadata” – Only metadata should be loaded when the page loads.\
\
Default: “none”\
\
## [Related](https://wordpress.org/documentation/article/audio-shortcode/\#related)\
\
WordPress Shortcodes: [video](https://wordpress.org/documentation/article/video-shortcode/), [caption](https://codex.wordpress.org/Caption_Shortcode), [embed](https://codex.wordpress.org/Embed_Shortcode), [gallery](https://codex.wordpress.org/Gallery_Shortcode), [playlist](https://codex.wordpress.org/Playlist_Shortcode)\
\
#### [Changelog](https://wordpress.org/documentation/article/audio-shortcode/\#changelog)\
\
- Updated 2021-10-18\
  - Added changelog\
  - Corrected the links to the codex pages for the caption, embed, gallery and playlist shortcodes\
\
## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/audio-shortcode/\#respond)\
\
[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Faudio-shortcode%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).\
\
First published\
\
November 2, 2018\
\
Last updated\
\
January 11, 2023\
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