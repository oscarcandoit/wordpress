---
url: https://wordpress.org/documentation/article/settings-general-screen
scraped_at: 2025-10-20T02:03:00.632Z
---

[Skip to content](https://wordpress.org/documentation/article/settings-general-screen/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Settings General screen

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Dashboard](https://wordpress.org/documentation/category/dashboard/)Settings General screen

Search documentation

# Settings General screen

## In this article

Table of Contents

- [General Settings](https://wordpress.org/documentation/article/settings-general-screen/#general-settings)
  - [Site title](https://wordpress.org/documentation/article/settings-general-screen/#site-title)
  - [Tagline](https://wordpress.org/documentation/article/settings-general-screen/#tagline)
  - [WordPress Address (URL)](https://wordpress.org/documentation/article/settings-general-screen/#wordpress-address-url)
  - [Site Address (URL)](https://wordpress.org/documentation/article/settings-general-screen/#site-address-url)
  - [E-mail Address](https://wordpress.org/documentation/article/settings-general-screen/#email-address)
  - [Membership](https://wordpress.org/documentation/article/settings-general-screen/#membership)
  - [New User Default Role](https://wordpress.org/documentation/article/settings-general-screen/#new-user-default-role)
  - [Site Language](https://wordpress.org/documentation/article/settings-general-screen/#site-language)
  - [Timezone](https://wordpress.org/documentation/article/settings-general-screen/#timezone)
  - [Date Format](https://wordpress.org/documentation/article/settings-general-screen/#date-format)
  - [Time Format](https://wordpress.org/documentation/article/settings-general-screen/#time-format)
  - [Week Starts On](https://wordpress.org/documentation/article/settings-general-screen/#week-starts-on)
  - [Save Changes](https://wordpress.org/documentation/article/settings-general-screen/#save-changes)
- [Changelog](https://wordpress.org/documentation/article/settings-general-screen/#changelog)

[↑ Back to top](https://wordpress.org/documentation/article/settings-general-screen/#wp--skip-link--target)

This Settings General Screen is the default Screen in the [Settings Administration Screen](https://wordpress.org/support/article/administration-screens/#settings-configuration-settings) and controls some of the most basic configuration settings for your site: your site’s title and location, who may register an account at your site, and how dates and times are calculated and displayed.

[![](https://wordpress.org/documentation/files/2018/11/760px-options-general.png)](https://wordpress.org/documentation/files/2018/11/760px-options-general.png)

## [General Settings](https://wordpress.org/documentation/article/settings-general-screen/\#general-settings)

### [Site title](https://wordpress.org/documentation/article/settings-general-screen/\#site-title)

Enter the name of your site (or blog) here. Most themes will display this title, at the top of every page, and in the reader’s browser titlebar. WordPress also uses this title as the identifying name for your [Syndication](https://wordpress.org/support/article/introduction-to-blogging/#syndication) feeds.

### [Tagline](https://wordpress.org/documentation/article/settings-general-screen/\#tagline)

In a few words, explain what your site is about. Your sites’ slogan, or tagline, might be entered here. A tagline is short phrase, or sentence, used to convey the essence of the site and is often funny or eye-catching. The default tagline is an empty string.

### [WordPress Address (URL)](https://wordpress.org/documentation/article/settings-general-screen/\#wordpress-address-url)

Enter the full URL of the directory containing your WordPress core application files (e.g., wp-config.php, wp-admin, wp-content, and wp-includes). For example, if you installed WordPress into a directory called “blog”, then the WordPress address would be `http://example.net/blog` (where example.net is your domain). If you installed WordPress into your web root, this address will be the root URL `http://example.net`. WordPress will trim a slash ( `/`) from the end. If you defined the **WP\_SITEURL** constant in your [`wp-config.php`](https://codex.wordpress.org/Editing_wp-config.php#WordPress_address_.28URL.29) file, that value will appear in this field and you will not be able to make changes to it from the WordPress administration screen.

### [Site Address (URL)](https://wordpress.org/documentation/article/settings-general-screen/\#site-address-url)

Enter the address you want people to type in their browser to reach your WordPress site. This is the directory where WordPress’s main `index.php` file is installed. The _Site address (URL)_ is identical to the _WordPress address (URL)_ (above) unless you are [giving WordPress its own directory](https://wordpress.org/support/article/giving-wordpress-its-own-directory/). WordPress will trim a slash ( `/`) from the end. If you defined the **WP\_HOME** constant in your [`wp-config.php`](https://codex.wordpress.org/Editing_wp-config.php#Blog_address_.28URL.29) file, that value will appear in this field and you will not be able to make changes to it from the WordPress administration screen.

### [E-mail Address](https://wordpress.org/documentation/article/settings-general-screen/\#email-address)

Enter the e-mail address to which you want WordPress to send messages regarding the administration and maintenance of your WordPress site. For example, if you allow new users to register as a member of your site (see Membership below), then a notification will be sent through e-mail to this address. In addition, if the option, **An administrator must always approve the comment**, is set in [Administration](https://wordpress.org/support/article/administration-screens/) \> [Settings](https://wordpress.org/support/article/administration-screens/#discussion) \> [Discussion](https://wordpress.org/support/article/settings-discussion-screen/), this e-mail address will receive notification that the comment is being held for moderation. Please note this is different than the address you supplied for the **admin** user account; the **admin** account e-mail address is sent an e-mail only when someone submits a comment to a post by **admin**. The address you enter here will never be displayed on the site. You can send messages to multiple admins by using an email address which forwards email to multiple recipients.

### [Membership](https://wordpress.org/documentation/article/settings-general-screen/\#membership)

**Anyone can register** – Check this checkbox if you want anyone to be able to register an account on your site.

### [New User Default Role](https://wordpress.org/documentation/article/settings-general-screen/\#new-user-default-role)

This drop-down box allows you to select the default [Role](https://wordpress.org/support/article/roles-and-capabilities/) that is assigned to new users. This Default [Role](https://wordpress.org/support/article/roles-and-capabilities/) will be assigned to newly registered members or users added via the [Administration](https://wordpress.org/support/article/administration-screens/) \> [Users](https://wordpress.org/support/article/administration-screens/#users-your-blogging-family) \> [Users Screen](https://codex.wordpress.org/Users_Screen). Valid choices are [Administrator](https://wordpress.org/support/article/roles-and-capabilities/#administrator), [Editor](https://wordpress.org/support/article/roles-and-capabilities/#editor), [Author](https://wordpress.org/support/article/roles-and-capabilities/#author), [Contributor](https://wordpress.org/support/article/roles-and-capabilities/#contributor), or [Subscriber](https://wordpress.org/support/article/roles-and-capabilities/#subscriber).

### [Site Language](https://wordpress.org/documentation/article/settings-general-screen/\#site-language)

The WordPress dashboard language.

### [Timezone](https://wordpress.org/documentation/article/settings-general-screen/\#timezone)

From the drop-down box, choose a city in the same timezone as you. For example, under America, select New York if you reside in the Eastern Timezone of the United States that honors daylight savings times. If you can’t identify a city in your timezone, select one of the **Etc GMT** settings that represents the number of hours by which your time differs from [Greenwich Mean Time](https://en.wikipedia.org/wiki/Greenwich_Mean_Time). Click the **Save Changes** button and the [UTC time](https://en.wikipedia.org/wiki/Coordinated_Universal_Time) and “Local time” will display to confirm the correct Timezone was selected.

### [Date Format](https://wordpress.org/documentation/article/settings-general-screen/\#date-format)

The format in which to display dates on your site. The Date Format setting is intended to be used by theme designers in displaying dates on your site, but does not control how the date is displayed in the Administrative Screens (e.g. Manage Posts). Click the **Save Changes** button and the “Output” example below will show the current date in the format entered. See [Formatting Date and Time](https://wordpress.org/support/article/formatting-date-and-time/) for some of the formats available.

### [Time Format](https://wordpress.org/documentation/article/settings-general-screen/\#time-format)

The format in which to display times on your site. The Time Format setting is intended to be used by theme designers in displaying time on your site, but does not control how the time is displayed in the Administrative Screens (e.g. Write Post edit of timestamp). Click the **Save Changes** button and the “Output” example below will show the current time in the format entered. See [Formatting Date and Time](https://wordpress.org/support/article/formatting-date-and-time/) for some of the formats available.

### [Week Starts On](https://wordpress.org/documentation/article/settings-general-screen/\#week-starts-on)

Select your preferred start date for WordPress calendars from the drop-down box. Monday is the default setting for this drop-down, meaning a monthly calendar will show Monday in the first column. If you want your calendar to show Sunday as the first column, then select Sunday from the drop-down.

### [Save Changes](https://wordpress.org/documentation/article/settings-general-screen/\#save-changes)

Click the **Save Changes** button to ensure any changes you have made to your Settings are saved to your database. Once you click the button, a confirmation text box will appear at the top of the page telling you your settings have been saved.

## [Changelog](https://wordpress.org/documentation/article/settings-general-screen/\#changelog)

- Updated 2024-08-24
  - Spacing/typos
  - Tagline default of empty string added

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/settings-general-screen/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fsettings-general-screen%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

November 5, 2018

Last updated

June 8, 2024

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.