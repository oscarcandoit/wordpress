---
url: https://wordpress.org/documentation/article/rss-block
scraped_at: 2025-10-20T02:03:18.884Z
---

[Skip to content](https://wordpress.org/documentation/article/rss-block/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

RSS block

[Home](https://wordpress.org/documentation)[Customization](https://wordpress.org/documentation/customization/)[Widget blocks](https://wordpress.org/documentation/category/widget-blocks/)RSS block

Search documentation

# RSS block

## In this article

Table of Contents

- [Block toolbar](https://wordpress.org/documentation/article/rss-block/#block-toolbar)
- [Block settings](https://wordpress.org/documentation/article/rss-block/#settings)
  - [Dimensions](https://wordpress.org/documentation/article/rss-block/#dimensions)
  - [Border](https://wordpress.org/documentation/article/rss-block/#border)
- [Resources](https://wordpress.org/documentation/article/rss-block/#resources)
- [Changelog](https://wordpress.org/documentation/article/rss-block/#changelog)

[↑ Back to top](https://wordpress.org/documentation/article/rss-block/#wp--skip-link--target)

[Go back to the list of **Blocks**](https://wordpress.org/documentation/article/blocks/)

An RSS feed is a machine-readable version of the content of a blog or a website.

With the _RSS_ block, you can display content from any site’s RSS feed on your website. You can choose to display the Title, Author, Date, and Excerpt for each item in the feed. You can display the items in a list or as a grid in a set number of columns.

Steps to embed an RSS block

1. First, you need to know the URL of the RSS feed that you want to embed. Some websites display an orange icon ![](https://wordpress.org/documentation/files/2019/11/RSS-feed-icon.png) with the link of the feed. You can usually find this icon together with social network icons.

Our example uses the feed of the [News](https://wordpress.org/news/) section on WordPress.org.  [https://wordpress.org/news/feed](https://wordpress.org/news/feed)

2. Click the **Block Inserter** (+) icon to add an _RSS_ block to your WordPress page/post. Alternatively, you can type `/rss` and hit enter in a new _paragraph block_ to add one quickly.

![Adding RSS block via the WordPress slash command /rss](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-1.png)

[Detailed instructions on adding blocks](https://wordpress.org/documentation/article/adding-a-new-block/)

3. Paste the link of the RSS feed into the text box and click on the **Use URL** button

![Enter URL here user interface for the RSS block.](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-2-1024x430.png)

The _RSS_ block now displays the titles of the feed items.

![Display of the RSS feed.](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-3-1024x361.png)

If you use an URL that can’t be embedded, the block shows the message _“RSS Error: WP HTTP Error: A valid URL was not provided.”_.

![Example of a URL that cannot be used in the RSS block.](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-6-1024x435.png)

Use the options in the **Block Toolbar** and the controls in the **Block Settings** panel in your editor’s sidebar to fine-tune the display.

## [Block toolbar](https://wordpress.org/documentation/article/rss-block/\#block-toolbar)

Besides the _Mover_ and _Drag & Drop_ handle, the Block Toolbar for the _RSS_ block shows six other buttons:

- Transform To
- Change alignment
- Edit RSS URL
- List view
- Grid view
- More options

![Block toolbar for the RSS block.](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-4-1.png)

**Transform** **to**

You can transform the **RSS block** into **Columns, Details**, or a **Group** block to better suit your layout and design preferences:

- **Group** – Wrap the RSS block in a Group to gain access to additional layout and styling options, such as background color, spacing, and borders.
- **Columns** – Organize the RSS feed into multiple columns for a more structured, grid-like layout.
- **Details** – Use the Details block to wrap the RSS content inside a collapsible section, helping manage long or dense feeds.

![Transform options for the RSS block.](https://wordpress.org/documentation/files/2019/11/rss-transforms.png)

**Change alignment**

- **Align left** – Make the block left-aligned.
- **Align center** – Make the block alignment centered.
- **Align right**– Make the block right-aligned.
- **Wide width** – Increase the width of the block beyond the content size.
- **Full width** – Extend the block to cover the full width of the screen.

![Change alignment options for RSS block.](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-7.png)

The “Wide width” and “Full width” alignment settings must be enabled by your WordPress theme.

**Edit RSS URL**

Via the edit URL, you can change the RSS feed URL in the block. Overwrite the existing URL and click on the **Use URL** button.

![Edit RSS Feed URL in the block.](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-2-1024x430.png)

**List** **view**

The **List view** option displays the feed items in an unordered list. Use the Block settings controls to customize the **List view**.

![List view for the RSS block.](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-8-1024x362.png)

**Grid view**

Display the feed items in a grid. Use the Block settings controls to adjust the number of columns and the other display options.

![Grid view for the RSS block.](https://wordpress.org/documentation/files/2022/09/RSS-Feed-HelpHub-SS-9-1024x519.png)

**More options**

These controls give you the option to copy, duplicate, and edit your block as HTML.

[Detailed instructions on adding blocks](https://wordpress.org/documentation/article/adding-a-new-block/)

## [Block settings](https://wordpress.org/documentation/article/rss-block/\#settings)

Every block has specific options in the editor sidebar in addition to the options found in the block toolbar. _If you do not see the sidebar, simply click the ‘cog’ icon._

![Cog icon to display the Block sidebar](https://wordpress.org/documentation/files/2022/06/Screen-Shot-2022-06-23-at-9.39.34-AM.png)![Block settings for the RSS block.](https://wordpress.org/documentation/files/2022/11/197761657-5fa6467c-b73a-41ca-9c38-b79833af866e.png)

**Settings**

**Number of items**: Slider and number box to adjust the number of feed items you’d like to display. To change the number move the dot on the slider or update the number in the box next to it.

**Display author**: Switch on/off the display of the author’s name

**Display date**: Switch on/off the display of the published date of the feed items

**Display excerpt**: Switch on/off the display of an excerpt from the feed items’ content.

**Max number of words in excerpt**: Slider and number box to choose the maximum number of words that can be displayed in the excerpt. The minimum number is 10. This section is not visible if **Display excerpt** is in the OFF position.

**Columns**: Slider and number box to control the number of columns for the grid view. This option is only visible when you select the **Grid view** on the Block Toolbar.

### [Dimensions](https://wordpress.org/documentation/article/rss-block/\#dimensions)

The _paragraph_ block provides various options to adjust its dimensions, such as width and height, allowing you to customize the text layout to ensure visual consistency.

For details refer to this support article: [Dimension settings overview](https://wordpress.org/documentation/article/dimension-controls-overview/)

### [Border](https://wordpress.org/documentation/article/rss-block/\#border)

The _paragraph_ block provides border settings options to add border color, width, and radius.

For details refer to this support article: [Border settings overview](https://wordpress.org/documentation/article/border-settings-overview/)

**Advanced**

The advanced tab lets you add a CSS class to your block, allowing you to write custom CSS and style the block as you see fit.

![Advanced option in the selected Block](https://lh6.googleusercontent.com/HCaeEAd-xkijY3husAGN8FkRfOokz6h-mLa1vQoT11JIf366WEE4Y3jtoy6CTOJGTpBZELgZPdIewg2ug8pURV5XtFciGwLHJiNwleOvlGte5WnWTug0SYe4p-qBR54_8oR1NwHM)Advanced option in the selected Block

## [Resources](https://wordpress.org/documentation/article/rss-block/\#resources)

- [Learn more about RSS on Wikipedia](https://en.wikipedia.org/wiki/RSS)
- [Learn more about WordPress Feeds](https://wordpress.org/documentation/article/wordpress-feeds/)

## [Changelog](https://wordpress.org/documentation/article/rss-block/\#changelog)

- Update 2025-04-22 (props to [@karthickmurugan](https://profiles.wordpress.org/karthickmurugan/))

  - Add Border and Spacing support.
  - Add Dimensions support.
  - Update screenshots and videos to 6.8.
  - Add missing ALT tags.
  - Update headings to sentence case.
- Updated 2022-11-20
  - Aligned images for mobile view
  - Removed redundant content
  - Added heading
- Updated 2022-11-08
  - Updated “RSS Settings” screenshot
- Updated 2022-09-28
  - Fixed font sizing under “Block Settings”
- Updated 2022-09-12

  - Video walkthrough created

  - Updated with images from WordPress 6.0
  - Added new “Transform to” setting (Column)
  - Added “Lock” information under More Options
  - Added ALT tags for the images
- Updated 2022-02-08
  - Update screenshots for 5.9
- Updated 2020-08-17
  - Converted More Options reusable block to regular blocks
- Updated 2020-04-28
  - changed category to “Widget Blocks”
  - changed dates in Changelog to universal format
- Updated 2020-04-18
  - Converted reusable block to regular blocks
  - Added to “Core Blocks” category
- Updated: 2019-11-25
  - change the first sentence and
  - aligned images to the right of the text where it adds to readability
- Created: 2019-11-23 / WordPress 5.3

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/rss-block/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Frss-block%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

November 23, 2019

Last updated

April 22, 2025

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.