---
url: https://developer.wordpress.org/rest-api/reference/settings
scraped_at: 2025-10-20T02:04:14.561Z
---

[Skip to content](https://developer.wordpress.org/rest-api/reference/settings/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Site Settings


[Home](https://developer.wordpress.org/)[REST API Handbook](https://developer.wordpress.org/rest-api/)[Reference](https://developer.wordpress.org/rest-api/reference/)Site Settings

Search

# Site Settings

## In this article

Table of Contents

- [Schema](https://developer.wordpress.org/rest-api/reference/settings/#schema)
- [Retrieve a Site Setting](https://developer.wordpress.org/rest-api/reference/settings/#retrieve-a-site-setting)
  - [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/settings/#definition-example-request)
- [Update a Site Setting](https://developer.wordpress.org/rest-api/reference/settings/#update-a-site-setting)
  - [Arguments](https://developer.wordpress.org/rest-api/reference/settings/#arguments)
  - [Definition](https://developer.wordpress.org/rest-api/reference/settings/#definition)
  - [Example Request](https://developer.wordpress.org/rest-api/reference/settings/#example-request)

[↑ Back to top](https://developer.wordpress.org/rest-api/reference/settings/#wp--skip-link--target)

## [Schema](https://developer.wordpress.org/rest-api/reference/settings/\#schema)

The schema defines all the fields that exist within a Site Setting record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `title` | Site title.<br>JSON data type: string <br>Context: `` |
| `description` | Site tagline.<br>JSON data type: string <br>Context: `` |
| `url` | Site URL.<br>JSON data type: string,<br>Format: uri<br> <br>Context: `` |
| `email` | This address is used for admin purposes, like new user notification.<br>JSON data type: string,<br>Format: email<br> <br>Context: `` |
| `timezone` | A city in the same timezone as you.<br>JSON data type: string <br>Context: `` |
| `date_format` | A date format for all date strings.<br>JSON data type: string <br>Context: `` |
| `time_format` | A time format for all time strings.<br>JSON data type: string <br>Context: `` |
| `start_of_week` | A day number of the week that the week should start on.<br>JSON data type: integer <br>Context: `` |
| `language` | WordPress locale code.<br>JSON data type: string <br>Context: `` |
| `use_smilies` | Convert emoticons like :-) and :-P to graphics on display.<br>JSON data type: boolean <br>Context: `` |
| `default_category` | Default post category.<br>JSON data type: integer <br>Context: `` |
| `default_post_format` | Default post format.<br>JSON data type: string <br>Context: `` |
| `posts_per_page` | Blog pages show at most.<br>JSON data type: integer <br>Context: `` |
| `show_on_front` | What to show on the front page<br>JSON data type: string <br>Context: `` |
| `page_on_front` | The ID of the page that should be displayed on the front page<br>JSON data type: integer <br>Context: `` |
| `page_for_posts` | The ID of the page that should display the latest posts<br>JSON data type: integer <br>Context: `` |
| `default_ping_status` | Allow link notifications from other blogs (pingbacks and trackbacks) on new articles.<br>JSON data type: string <br>Context: ``<br>One of: `open`, `closed` |
| `default_comment_status` | Allow people to submit comments on new posts.<br>JSON data type: string <br>Context: ``<br>One of: `open`, `closed` |
| `site_logo` | Site logo.<br>JSON data type: integer <br>Context: `` |
| `site_icon` | Site icon.<br>JSON data type: integer <br>Context: `` |

## [Retrieve a Site Setting](https://developer.wordpress.org/rest-api/reference/settings/\#retrieve-a-site-setting)

### [Definition & Example Request](https://developer.wordpress.org/rest-api/reference/settings/\#definition-example-request)

`GET /wp/v2/settings`

Query this endpoint to retrieve a specific Site Setting record.

`$ curl https://example.com/wp-json/wp/v2/settings`

There are no arguments for this endpoint.

## [Update a Site Setting](https://developer.wordpress.org/rest-api/reference/settings/\#update-a-site-setting)

### [Arguments](https://developer.wordpress.org/rest-api/reference/settings/\#arguments)

|     |     |
| --- | --- |
| `[title](https://developer.wordpress.org/rest-api/reference/settings/#schema-title)` | Site title. |
| `[description](https://developer.wordpress.org/rest-api/reference/settings/#schema-description)` | Site tagline. |
| `[url](https://developer.wordpress.org/rest-api/reference/settings/#schema-url)` | Site URL. |
| `[email](https://developer.wordpress.org/rest-api/reference/settings/#schema-email)` | This address is used for admin purposes, like new user notification. |
| `[timezone](https://developer.wordpress.org/rest-api/reference/settings/#schema-timezone)` | A city in the same timezone as you. |
| `[date\_format](https://developer.wordpress.org/rest-api/reference/settings/#schema-date_format)` | A date format for all date strings. |
| `[time\_format](https://developer.wordpress.org/rest-api/reference/settings/#schema-time_format)` | A time format for all time strings. |
| `[start\_of\_week](https://developer.wordpress.org/rest-api/reference/settings/#schema-start_of_week)` | A day number of the week that the week should start on. |
| `[language](https://developer.wordpress.org/rest-api/reference/settings/#schema-language)` | WordPress locale code. |
| `[use\_smilies](https://developer.wordpress.org/rest-api/reference/settings/#schema-use_smilies)` | Convert emoticons like :-) and :-P to graphics on display. |
| `[default\_category](https://developer.wordpress.org/rest-api/reference/settings/#schema-default_category)` | Default post category. |
| `[default\_post\_format](https://developer.wordpress.org/rest-api/reference/settings/#schema-default_post_format)` | Default post format. |
| `[posts\_per\_page](https://developer.wordpress.org/rest-api/reference/settings/#schema-posts_per_page)` | Blog pages show at most. |
| `[show\_on\_front](https://developer.wordpress.org/rest-api/reference/settings/#schema-show_on_front)` | What to show on the front page |
| `[page\_on\_front](https://developer.wordpress.org/rest-api/reference/settings/#schema-page_on_front)` | The ID of the page that should be displayed on the front page |
| `[page\_for\_posts](https://developer.wordpress.org/rest-api/reference/settings/#schema-page_for_posts)` | The ID of the page that should display the latest posts |
| `[default\_ping\_status](https://developer.wordpress.org/rest-api/reference/settings/#schema-default_ping_status)` | Allow link notifications from other blogs (pingbacks and trackbacks) on new articles.<br> One of: `open`, `closed` |
| `[default\_comment\_status](https://developer.wordpress.org/rest-api/reference/settings/#schema-default_comment_status)` | Allow people to submit comments on new posts.<br> One of: `open`, `closed` |
| `[site\_logo](https://developer.wordpress.org/rest-api/reference/settings/#schema-site_logo)` | Site logo. |
| `[site\_icon](https://developer.wordpress.org/rest-api/reference/settings/#schema-site_icon)` | Site icon. |

### [Definition](https://developer.wordpress.org/rest-api/reference/settings/\#definition)

`POST /wp/v2/settings`

### [Example Request](https://developer.wordpress.org/rest-api/reference/settings/\#example-request)

``

First published

December 6, 2016

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Site Settings](https://github.com/WP-API/docs/edit/master/reference/settings.md)

Changelog

[See list of changes: Site Settings](https://github.com/WP-API/docs/commits/master/reference/settings.md)

[PreviousSidebarsPrevious: Sidebars](https://developer.wordpress.org/rest-api/reference/sidebars/)

[NextStatusesNext: Statuses](https://developer.wordpress.org/rest-api/reference/post-statuses/)

Notifications