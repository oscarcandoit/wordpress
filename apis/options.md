---
url: https://developer.wordpress.org/apis/options
scraped_at: 2025-10-20T04:06:30.854Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/options/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Options


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Options

Search

# Options

## In this article

Table of Contents

- [Overview](https://developer.wordpress.org/apis/options/#overview)
- [Function Reference](https://developer.wordpress.org/apis/options/#function-reference)
- [Examples](https://developer.wordpress.org/apis/options/#examples)
- [Available options by category](https://developer.wordpress.org/apis/options/#available-options-by-category)
  - [Discussion](https://developer.wordpress.org/apis/options/#discussion)
  - [General](https://developer.wordpress.org/apis/options/#general)
  - [Links](https://developer.wordpress.org/apis/options/#links)
  - [Media](https://developer.wordpress.org/apis/options/#media)
  - [Miscellaneous](https://developer.wordpress.org/apis/options/#miscellaneous)
  - [Permalinks](https://developer.wordpress.org/apis/options/#permalinks)
  - [Privacy](https://developer.wordpress.org/apis/options/#privacy)
  - [Reading](https://developer.wordpress.org/apis/options/#reading)
  - [Themes](https://developer.wordpress.org/apis/options/#themes)
  - [Writing](https://developer.wordpress.org/apis/options/#writing)
  - [Uncategorized](https://developer.wordpress.org/apis/options/#uncategorized)
- [All Settings Screen](https://developer.wordpress.org/apis/options/#all-settings-screen)

[↑ Back to top](https://developer.wordpress.org/apis/options/#wp--skip-link--target)

## [Overview](https://developer.wordpress.org/apis/options/\#overview)

The **Options API** is a simple and standardized way of storing data in the database. The API makes it easy to create, access, update, and delete options. All the data is stored in the [wp\_options table](https://developer.wordpress.org/apis/handbook/database/) under a given custom name.

This page contains the technical documentation needed to use the Options API. A list of default options can be found in the [Option Reference](https://codex.wordpress.org/Option_Reference) (link to Codex version, waiting for content migration to HelpHub).

Note that the `_site_` functions are essentially the same as their counterparts. The only differences occur for WP Multisite, when the options apply network-wide and the data is stored in the [wp\_sitemeta](https://developer.wordpress.org/apis/handbook/database/) table under the given custom name.

## [Function Reference](https://developer.wordpress.org/apis/options/\#function-reference)

**Add/Delete Option**:

- [add\_option()](https://developer.wordpress.org/reference/functions/add_option/)
- [delete\_option()](https://developer.wordpress.org/reference/functions/delete_option/)
- [add\_site\_option()](https://developer.wordpress.org/reference/functions/add_site_option/)
- [delete\_site\_option()](https://developer.wordpress.org/reference/functions/delete_site_option/)

**Get/Update Option:**

- [get\_option()](https://developer.wordpress.org/reference/functions/get_option/)
- [update\_option()](https://developer.wordpress.org/reference/functions/update_option/)
- [get\_site\_option()](https://developer.wordpress.org/reference/functions/get_site_option/)
- [update\_site\_option()](https://developer.wordpress.org/reference/functions/update_site_option/)

## [Examples](https://developer.wordpress.org/apis/options/\#examples)

``
[Copy](https://developer.wordpress.org/apis/options/#)

```php
// Create an option to the database
add_option( $option, $value = , $deprecated = , $autoload = 'yes' );

// Removes option by name.
delete_option( $option );

// Fetch a saved option
get_option( $option, $default = false );

// Update the value of an option that was already added.
update_option( $option, $newvalue );
```

## [Available options by category](https://developer.wordpress.org/apis/options/\#available-options-by-category)

### [Discussion](https://developer.wordpress.org/apis/options/\#discussion)

- `blacklist_keys`: When a comment contains any of these words in its content, name, URL, e-mail, or IP, it will be marked as spam. One word or IP per line. It will match inside words, so “press” will match “WordPress.”

Default: NULL

_Data type:_ **String (possibly multi-line)**
- `comment_max_links`: Hold a comment in the queue if it contains the value of this option or more.

Default: 2

_Data type:_ **Integer**
- `comment_moderation`: Before a comment appears, an administrator must always approve the comment.

**1** : _Yes_

**0** : _False_ (default)

_Data type:_ **Integer**
- `comments_notify`: E-mail me when anyone posts a comment.

**1** : _Yes_ (default)

**0** : _No_

_Data type:_ **Integer**
- `default_comment_status`: Allow comments (can be overridden with individual posts)

**open** : _Allow comments_ (default)

**closed** : _Disallow comments_

_Data type:_ **String**
- `default_ping_status`: Allow link notifications from other blogs (pingbacks and trackbacks).

**open** : _Allow pingbacks and trackbacks from other blogs_ (default)

**closed** : _Disallow pingbacks and trackbacks from other blogs_

_Data type:_ **String**
- `default_pingback_flag`: Attempt to notify any blogs linked to from the article (slows down posting).

**1** : _Yes_ (default)

**0** : _No_

_Data type:_ **Integer**
- `moderation_keys`: When a comment contains any of these words in its content, name, URL, e-mail, or IP, it will be held in the moderation queue. One word or IP per line. It will match inside words, so “press” will match “WordPress.”

Default: NULL

_Data type:_ **String (possibly multi-line)**
- `moderation_notify`: E-mail me when a comment is held for moderation.

**1** : _Yes_ (default)

**0** : _No_

_Data type:_ **Integer**
- `require_name_email`: Before a comment appears, the comment author must fill out his/her name and email.

**1** : _Yes_ (default)

**0** : _No_

_Data type:_ **Integer**
- `thread_comments`: Enable WP-native threaded (nested) comments.

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**
- `thread_comments_depth`: Set the number of threading levels for comments.

**1** thru

**10** : levels

Default: 5

_Data type:_ **Integer**
- `show_avatars`: Avatar Display

**1** : (default) _Show Avatars_

**0** : _Do not show Avatars_

_Data type:_ **Integer**
- `avatar_rating`: Maximum Rating

**G** : (default) _Suitable for all audiences_

**PG** : _Possibly offensive, usually for audiences 13 and above_

**R** : _Intended for adult audiences above 17_

**X** : _Even more mature than above_

_Data type:_ **String**
- `avatar_default`: Default Avatar

**mystery** : (default) _Mystery Man_

**blank** : _Blank_

**gravatar\_default** : _Gravatar Logo_

**identicon** : _Identicon (Generated)_

**wavatar** : _Wavatar (Generated)_

**monsterid** : _MonsterID (Generated)_

**retro** : _Retro (Generated)_

_Data type:_ **String**
- `close_comments_for_old_posts`: Automatically close comments on old articles

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**
- `close_comments_days_old`: Automatically close comments on articles older than x days

Default: 14

_Data type:_ **Integer**
- `show_comments_cookies_opt_in`: Show the cookies opt-in checkbox on the comment form and enable comment cookies

**1** : _Yes_ (default as of 4.9.8)

**0** : _No_

_Data type:_ **Integer**
- `page_comments`: Break comments into pages

**1** : _Yes_ (default)

**0** : _No_

_Data type:_ **Integer**
- `comments_per_page`:

Default: 50

_Data type:_ **Integer**
- `default_comments_page`:

Default: ‘newest’

_Data type:_ **String**
- `comment_order`:

**asc** : (default)

**desc** :

_Data type:_ **String**
- `comment_whitelist`: Comment author must have a previously approved comment

**1** : _Yes_ (default)

**0** : _No_

_Data type:_

### [General](https://developer.wordpress.org/apis/options/\#general)

- `admin_email`: Administrator email

Default: ‘you@example.com’

_Data type:_ **String**
- `blogdescription`: Blog tagline

Default: ‘\_\_(‘Just another WordPress weblog’)’

_Data type:_ **String**
- `blogname`: Blog title

Default: ‘\_\_(‘My Blog’)’

_Data type:_ **String**
- `comment_registration`: Users must be registered and logged in to comment

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**
- `date_format`: Default date format

Default: ‘\_\_(‘F j, Y’)’

_Data type:_ **String**
- `default_role`: The default role of users who register at the blog.

**subscriber** (default)

**administrator**

**editor**

**author**

**contributor**

_Data type:_ **String**
- `gmt_offset`: Times in the blog should differ by this value.

**-6** : _GMT -6 (aka Central Time, USA)_

**0** : _GMT (aka Greenwich Mean Time)_

Default: [date](http://www.php.net/manual/en/function.date.php)(‘Z’) / 3600

_Data type:_ **Integer**
- `home`: Blog address (URL)

Default: [wp\_guess\_url()](https://developer.wordpress.org/reference/functions/wp_guess_url/)

_Data type:_ **String (URI)**
- `siteurl`: WordPress address (URL)

Default `wp_guess_url()`

_Data type:_ **String (URI)**
- `start_of_week`: The starting day of the week.

**0** : _Sunday_

**1** : _Monday_ (default)

**2** : _Tuesday_

**3** : _Wednesday_

**4** : _Thursday_

**5** : _Friday_

**6** : _Saturday_

_Data type:_ **Integer**
- `time_format`: Default time format

Default: ‘\_\_(‘g:i a’)’

_Data type:_ **String**
- `timezone_string`: Timezone

Default: NULL

_Data type:_ **String**
- `users_can_register`: Anyone can register

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**

### [Links](https://developer.wordpress.org/apis/options/\#links)

- `links_updated_date_format`:

Default `__('F j, Y g:i a')`

_Data type:_ **String**
- `links_recently_updated_prepend`:

Default empty

_Data type: **String**_
- `links_recently_updated_append`

_Default_ empty

_Data type:_ **String**
- `links_recently_updated_time`

Default: 120

_Data type:_ **Integer**

### [Media](https://developer.wordpress.org/apis/options/\#media)

- `thumbnail_size_w`:

Default: 150

_Data type:_ **Integer**
- `thumbnail_size_h`:

Default: 150

_Data type:_ **Integer**
- `thumbnail_crop`: Crop thumbnail to exact dimensions (normally thumbnails are proportional)

**1** : _Yes_ (default)

**0** : _No_

_Data type:_ **Integer**
- `medium_size_w`:

Default: 300

_Data type:_ **Integer**
- `medium_size_h`

Default: 300

_Data type:_ **Integer**
- `large_size_w`

Default: 1024

_Data type:_ **Integer**
- `large_size_h`

Default: 1024

_Data type:_ **Integer**
- `embed_autourls`: Attempt to automatically embed all plain text URLs

Default: 1

_Data type:_ **Integer**
- `embed_size_w`

Default: NULL

_Data type:_ **Integer**
- `embed_size_h`

Default: 600

_Data type:_ **Integer**

### [Miscellaneous](https://developer.wordpress.org/apis/options/\#miscellaneous)

- `hack_file`: Use legacy `my-hacks.php` file support

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**
- `html_type`: Default MIME type for blog pages (text/html, text/xml+html, etc.)

Default: ‘text/html’

_Data type:_ **String (MIME type)**
- `secret`: Secret value created during installation used with salting, etc.

Default: wp\_generate\_password(64)

_Data type:_ **String (MD5)**
- `upload_path`: Store uploads in this folder (relative to the WordPress root)

Default: NULL

_Data type:_ **String (relative path)**
- `upload_url_path`: URL path to upload folder (will be blank by default – Editable in “All Settings” Screen.

_Data type:_ **String (URL path)**
- `uploads_use_yearmonth_folders`: Organize my uploads into month- and year-based folders

**1** : _Yes_ (default)

**0** : _No_ (default for safe mode)

_Data type:_ **Integer**
- `use_linksupdate`: Track links’ update times

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**

### [Permalinks](https://developer.wordpress.org/apis/options/\#permalinks)

- `permalink_structure`: The desired structure of your blog’s permalinks. Some examples:

`/%year%/%monthnum%/%day%/%postname%/`: Date and name based

`/archives/%post_id%/`: Numeric

`/%postname%/`: Post name-based

Default: NULL

_Data type:_ **String**
- `category_base`: The default category base of your blog categories permalink.

Default: NULL

_Data type:_ **String**
- `tag_base`: The default tag base for your blog tags permalink.

Default: NULL

_Data type:_ **String**

### [Privacy](https://developer.wordpress.org/apis/options/\#privacy)

- `blog_public`:

**1** : _I would like my blog to be visible to everyone, including search engines (like Google, Sphere, Technorati) and archivers._ (default)

**0** : _I would like to block search engines, but allow normal visitors._

_Data type:_ **Integer**

### [Reading](https://developer.wordpress.org/apis/options/\#reading)

- `blog_charset`: Encoding for pages and feeds. The character encoding you write your blog in (UTF-8 is recommended).

Default: `UTF-8`

_Data type:_ **String**
- `gzipcompression`: WordPress should compress articles (with gzip) if browsers ask for them.

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**
- `page_on_front`: The ID of the page that should be displayed on the front page. Requires `show_on_front`‘s value to be **page**.

_Data type:_ **Integer**
- `page_for_posts`: The ID of the page that displays posts. Useful when `show_on_front`‘s value is **page**.

_Data type:_ **Integer**
- `posts_per_page`: Show at most **x** many posts on blog pages.

Default: 10

_Data type:_ **Integer**
- `posts_per_rss`: Show at most **x** many posts in RSS feeds.

Default: 10

_Data type:_ **Integer**
- `rss_language`: Language for RSS feeds (metadata purposes only)

Default: `en`

_Data type:_ **String (ISO two-letter language code)**
- `rss_use_excerpt`: Show an excerpt instead of the full text of a post in RSS feeds

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**
- `show_on_front`: What to show on the front page

**posts** : _Your latest posts_ (default)

**page** : _A static page (see page\_on\_front)_

_Data type:_ **String**

### [Themes](https://developer.wordpress.org/apis/options/\#themes)

- `template`: The slug of the currently activated theme (how it is accessed by path, ex. `/wp-content/themes/my-theme` ( `my-theme` would be the value of this option).

Default: ‘default’

_Data type:_ **String**
- `stylesheet`: The slug of the currently activated stylesheet (style.css) (how it is accessed by path, ex. `/wp-content/themes/my-style` (my-style would be the value of this option)

Default: ‘default’

_Data type:_ **String**

### [Writing](https://developer.wordpress.org/apis/options/\#writing)

- `default_category`: ID of the category that posts will be put in by default

Default: 1

_Data type:_ **Integer**
- `default_email_category`: ID of the category that posts will be put in by default when written via e-mail

Default: 1

_Data type:_ **Integer**
- `default_link_category`: ID of the category that links will be put in by default

Default: 2

_Data type:_ **Integer**
- `default_post_edit_rows`: Size of the post box (in lines)

Default: 10

_Data type:_ **Integer**
- `mailserver_login`: Mail server username for posting to WordPress by e-mail

Default: ‘login@example.com’

_Data type:_ **String**
- `mailserver_pass`: Mail server password for posting to WordPress by e-mail

Default: ‘password’

_Data type:_ **String**
- `mailserver_port`: Mail server port for posting to WordPress by e-mail

Default: 110

_Data type:_ **Integer**
- `mailserver_url`: Mail server for posting to WordPress by e-mail

Default: ‘mail.example.com’

_Data type:_ **String**
- `ping_sites`: When you publish a new post, WordPress automatically notifies the following site update services. For more about this, see [Update Services](https://codex.wordpress.org/Update_Services). Separate multiple service URLs with line breaks. Requires `blog_public` to have a value of **1**.

Default: ‘ [http://rpc.pingomatic.com/’](http://rpc.pingomatic.com/')

_Data type:_ **String (possibly multi-line)**
- `use_balanceTags`: Correct invalidly-nested XHTML automatically

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**
- `use_smilies`: Convert emoticons like `:-)` and `:P` to graphics when displayed

**1** : _Yes_ (default)

**0** : _No_

_Data type:_ **Integer**
- `use_trackback`: Enable sending and receiving of trackbacks

**1** : _Yes_

**0** : _No_ (default)
- `enable_app`: Enable the Atom Publishing Protocol

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**
- `enable_xmlrpc`: Enable the WordPress, Movable Type, MetaWeblog and Blogger XML-RPC publishing protocols

**1** : _Yes_

**0** : _No_ (default)

_Data type:_ **Integer**

### [Uncategorized](https://developer.wordpress.org/apis/options/\#uncategorized)

- `active_plugins`: Returns an array of strings containing the path of the _main_ php file of the plugin. The path is relative to the _plugins_ folder. An example of path in the array : `/mainpage.php`.

Default: array()

_Data type:_ **Array**
- `advanced_edit`:

Default: 0

_Data type:_ **Integer**
- `recently_edited`:

Default: NULL

_Data type:_
- `image_default_link_type`:

Default: ‘file’

_Data type:_ ‘file’, ‘none’
- `image_default_size`:

Default: NULL

_Data type:_ ‘thumbnail’, ‘medium’, ‘large’ or Custom size
- `image_default_align`:

Default: NULL

_Data type:_ ‘left’, ‘right’, ‘center’, ‘none’
- `sidebars_widgets`: Returns array of sidebar states (list of active and inactive widgets).

Default:

_Data type:_ **Array**
- `sticky_posts`:

Default: array()

_Data type:_
- `widget_categories`:

Default: array()

_Data type:_
- `widget_text`:

Default: array()

_Data type:_
- `widget_rss`:

Default: array()

_Data type:_

## [All Settings Screen](https://developer.wordpress.org/apis/options/\#all-settings-screen)

[WordPress 3.0](https://wordpress.org/documentation/wordpress-version/version-3-0/) removed Settings > Miscellaneous screen and some of the options cannot be reached (e.g. `upload_url_path`). You may use the All Settings Screen to view and change almost all options listed above. It is accessible by visiting `/wp-admin/options.php`

![](https://i0.wp.com/developer.wordpress.org/files/2019/08/all-settings-screen.png?resize=1024%2C640&ssl=1)

First published

August 12, 2019

Last updated

June 14, 2023

[PreviousMetadataPrevious: Metadata](https://developer.wordpress.org/apis/metadata/)

[NextPluginsNext: Plugins](https://developer.wordpress.org/apis/plugins/)

Notifications