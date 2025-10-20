---
url: https://developer.wordpress.org/themes/functionality/media
scraped_at: 2025-10-20T03:20:43.564Z
---

[Skip to content](https://developer.wordpress.org/themes/classic-themes/functionality/media/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Media


[Home](https://developer.wordpress.org/)[Theme Handbook](https://developer.wordpress.org/themes/)[Classic themes](https://developer.wordpress.org/themes/classic-themes/)[Theme Functionality](https://developer.wordpress.org/themes/classic-themes/functionality/)Media

Search

# Media

## In this article

Table of Contents

- [General](https://developer.wordpress.org/themes/classic-themes/functionality/media/#general)
  - [Retrieving attachment ID or image ID](https://developer.wordpress.org/themes/classic-themes/functionality/media/#retrieving-attachment-id-or-image-id)
- [Special considerations](https://developer.wordpress.org/themes/classic-themes/functionality/media/#special-considerations)
  - [Compatible media formats](https://developer.wordpress.org/themes/classic-themes/functionality/media/#compatible-media-formats)
  - [Troubleshooting:](https://developer.wordpress.org/themes/classic-themes/functionality/media/#troubleshooting)

[↑ Back to top](https://developer.wordpress.org/themes/classic-themes/functionality/media/#wp--skip-link--target)

WordPress enables theme developers to customize the look, feel, and functionality of the platform’s core media capabilities.

## [General](https://developer.wordpress.org/themes/classic-themes/functionality/media/\#general)

In WordPress you can upload, store, and display a variety of media such as image, video and audio files. Media can be uploaded via the **Media > Add New** in the [Administration Screen](https://codex.wordpress.org/Administration_Screens), or Add Media button on the Post/Page Editor.

If a media file is uploaded within the edit screen, it will be automatically attached to the current post being created or edited. If it is uploaded via the Media’s Add New Screen or the Media Library Screen, it will be unattached, but may become attached to a post when it is inserted into a post later on.

### [Retrieving attachment ID or image ID](https://developer.wordpress.org/themes/classic-themes/functionality/media/\#retrieving-attachment-id-or-image-id)

To retrieve the attachment ID, use `[get\_posts()](https://developer.wordpress.org/reference/functions/get_posts/)` or `[get\_children()](https://developer.wordpress.org/reference/functions/get_children/)` function. This example retrieves the all attachments of the current post and getting all metadata of attachment by specifying the ID.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/#)

```php
// Insert into the Loop
$args = array(
    'post_parent'    => get_the_ID(),
    'post_type'      => 'attachment',
);
$attachments = get_posts( $args );
if ( $attachments ) {
    foreach ( $attachments as $attachment ) {
        $meta_data = wp_get_attachment_metadata( $attachment->ID, false );
    }
}
```

If you want to retrieve images from the post ID only, specify post\_mime\_type as image.

``
[Copy](https://developer.wordpress.org/themes/classic-themes/functionality/media/#)

```php
$args = array(
    'post_parent'    => get_the_ID(),
    'post_type'      => 'attachment',
    'post_mime_type' => 'image',
);
```

#### [References](https://developer.wordpress.org/themes/classic-themes/functionality/media/\#references)

- `[get\_posts()](https://developer.wordpress.org/reference/functions/get_posts/)`
- `[get\_children()](https://developer.wordpress.org/reference/functions/get_children/)`
- `[wp\_get\_attachment\_metadata()](https://developer.wordpress.org/reference/functions/wp_get_attachment_metadata/)`

## [Special considerations](https://developer.wordpress.org/themes/classic-themes/functionality/media/\#special-considerations)

### [Compatible media formats](https://developer.wordpress.org/themes/classic-themes/functionality/media/\#compatible-media-formats)

In the Media Library, you can upload any file (with the network administrator’s unfiltered\_upload) and not just images or videos but text files, office documents or even binary files. Single site administrators do not have the unfiltered\_upload capability by default and requires that definition to be set for the capability to kick in. Audio and Video files are processed by the internal library `MediaElement.js`.

- [Supported Audio format](https://developer.wordpress.org/?post_type=theme-handbook&p=25145#supported-audio-format)
- [Supported Video format](https://developer.wordpress.org/themes/functionality/media/video/#supported-video-format)

### [Troubleshooting:](https://developer.wordpress.org/themes/classic-themes/functionality/media/\#troubleshooting)

#### [Cannot retrieve attachment](https://developer.wordpress.org/themes/classic-themes/functionality/media/\#cannot-retrieve-attachment)

When you cannot get your attached media by `[get\_posts()](https://developer.wordpress.org/reference/functions/get_posts/)` or `[get\_children()](https://developer.wordpress.org/reference/functions/get_children/)` function, confirm your media is really attached to the post.

From the [Administration Screen](https://codex.wordpress.org/Administration_Screens), Click **Media > Library** to open the Media Library and confirm the value in “Uploaded to” column of the media.

First published

October 23, 2014

Last updated

January 15, 2017

[PreviousLocalizationPrevious: Localization](https://developer.wordpress.org/themes/classic-themes/functionality/localization/)

[NextAudioNext: Audio](https://developer.wordpress.org/themes/classic-themes/functionality/media/audio/)

Notifications