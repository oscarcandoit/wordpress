---
url: https://wordpress.org/documentation/article/query-loop-block
scraped_at: 2025-10-20T02:03:22.592Z
---

[Skip to content](https://wordpress.org/documentation/article/query-loop-block/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Query Loop block

[Home](https://wordpress.org/documentation)[Customization](https://wordpress.org/documentation/customization/)[Theme blocks](https://wordpress.org/documentation/category/theme-blocks/)Query Loop block

Search documentation

# Query Loop block

## In this article

Table of Contents

- [Anatomy of the Query Loop block](https://wordpress.org/documentation/article/query-loop-block/#anatomy-of-the-query-loop-block)
- [Adding the Query Loop block](https://wordpress.org/documentation/article/query-loop-block/#adding-the-query-loop-block)
- [Block configuration](https://wordpress.org/documentation/article/query-loop-block/#block-configuration)
  - [How to choose a pattern](https://wordpress.org/documentation/article/query-loop-block/#how-to-choose-a-pattern)
  - [How to start blank](https://wordpress.org/documentation/article/query-loop-block/#how-to-start-blank)
  - [How to customize the appearance](https://wordpress.org/documentation/article/query-loop-block/#how-to-customize-the-appearance)
- [Block toolbar](https://wordpress.org/documentation/article/query-loop-block/#block-toolbar)
  - [Transform to](https://wordpress.org/documentation/article/query-loop-block/#transform-to)
  - [Drag icon](https://wordpress.org/documentation/article/query-loop-block/#drag-icon)
  - [Move arrows](https://wordpress.org/documentation/article/query-loop-block/#move-arrows)
  - [Align](https://wordpress.org/documentation/article/query-loop-block/#align)
  - [Display settings](https://wordpress.org/documentation/article/query-loop-block/#display-settings)
  - [Replace](https://wordpress.org/documentation/article/query-loop-block/#replace)
  - [List view (default)](https://wordpress.org/documentation/article/query-loop-block/#list-view-default)
  - [Grid view](https://wordpress.org/documentation/article/query-loop-block/#grid-view)
- [Options](https://wordpress.org/documentation/article/query-loop-block/#options)
- [Block Settings](https://wordpress.org/documentation/article/query-loop-block/#block-settings)
  - [Color](https://wordpress.org/documentation/article/query-loop-block/#color)
  - [Inner blocks use content width](https://wordpress.org/documentation/article/query-loop-block/#inner-blocks-use-content-width)
  - [Inherit query from template](https://wordpress.org/documentation/article/query-loop-block/#inherit-query-from-template)
  - [Post type](https://wordpress.org/documentation/article/query-loop-block/#post-type)
  - [Order by](https://wordpress.org/documentation/article/query-loop-block/#order-by)
  - [Sticky posts](https://wordpress.org/documentation/article/query-loop-block/#sticky-posts)
  - [Filters](https://wordpress.org/documentation/article/query-loop-block/#filters)
- [Advanced Settings](https://wordpress.org/documentation/article/query-loop-block/#advanced-settings)
- [Resources](https://wordpress.org/documentation/article/query-loop-block/#resources)
- [Changelog](https://wordpress.org/documentation/article/query-loop-block/#changelog)

[↑ Back to top](https://wordpress.org/documentation/article/query-loop-block/#wp--skip-link--target)

[Go back to the list of **Blocks**](https://wordpress.org/documentation/article/blocks/)

The _Query Loop block_ is an advanced block that allows you to display posts based on specified parameters, like a PHP loop without the code. You can think of it as a more complex and powerful [_Latest Posts Block_](https://wordpress.org/documentation/article/latest-posts-block/). With various block patterns integrated into the block setup, you can do things like create a portfolio or a page full of your favorite recipes.

![Query loop block in the editor](https://wordpress.org/documentation/files/2023/03/query-loop-main.png)

## [Anatomy of the Query Loop block](https://wordpress.org/documentation/article/query-loop-block/\#anatomy-of-the-query-loop-block)

The block inspector provides a quick overview of the Query Loop block’s structure. Each part gives you access to different settings:

- **Query Loop:** Configure the query parameters, such as post type or category.
- **Post Template**: Choose how the content is displayed, either in a list or grid format.
- **Pagination**: Select which navigation elements to include, such as next/previous buttons or page numbers.
- **No Results**: Set a message to display hen a query returns no results.

![image showing the query loop anatomy](https://wordpress.org/documentation/files/2021/07/query-loop-block.jpg)

## [Adding the Query Loop block](https://wordpress.org/documentation/article/query-loop-block/\#adding-the-query-loop-block)

To add the _Query Loop_ block to a page, click the **block inserter** (+) icon to open the block inserter pop-up window and choose the _Query Loop_ block.

![Adding a query loop block](https://wordpress.org/documentation/files/2023/03/adding-query-loop-pattern.gif)

You can also use the keyboard shortcut `/query-loop` to quickly insert a _Query Loop_ block.

[Detailed instructions on adding blocks](https://wordpress.org/documentation/article/adding-a-new-block/)

## [Block configuration](https://wordpress.org/documentation/article/query-loop-block/\#block-configuration)

After adding the _Query Loop_ block you will see two options:

- **Choose**
- **Start blank**

![Query loop block placeholder](https://wordpress.org/documentation/files/2023/03/placeholder-1.png)

### [How to choose a pattern](https://wordpress.org/documentation/article/query-loop-block/\#how-to-choose-a-pattern)

If you select the _Choose_ option, you will have various pattern options. Just select one that you like, and it will be added. Each _Query Loop block_ is made up of various nested blocks, like the _Post Title block_ and [_Pagination block_](https://wordpress.org/documentation/article/pagination-block/), so depending on which pattern you choose, nested blocks can differ.

### [How to start blank](https://wordpress.org/documentation/article/query-loop-block/\#how-to-start-blank)

If you select the _Start blank_ option, you’ll see four variations you can choose from. Select the one you want to use.

![Adding a blank query loop block](https://wordpress.org/documentation/files/2023/03/adding-blank-query-loop.gif)

### [How to customize the appearance](https://wordpress.org/documentation/article/query-loop-block/\#how-to-customize-the-appearance)

There are numerous ways to customize the _Query Loop block,_ partially because it’s made up of nested blocks that you can rearrange, add to, and more. When you customize one block in the _Query Loop block_, the changes will apply to all blocks of the same type. While customizing this block, it might help to use the List View found in the top toolbar. Here are some ideas for customization to get you started:

- You can **change the width** of various aspects of the _Query Loop block_.
- You can **change the alignmen** t of blocks within the _Query Loop_ _block._
- You can **add blocks** into the _Query Loop block_, like _Post Author_ or _Post Excerpt_.
- You can **rearrange the blocks** to your liking, dragging and dropping or using the movers to do so.
- You can **change the number of posts** listed by selecting the _Query Loop block_ and adjusting the Display Settings option in the block toolbar.
- You can **set various color options** for the nested blocks.
- You can **add featured images** by adding the _Featured Image block_.

It’s also possible to add text or blocks when the _Query Loop_ block returns no results:

![No results text for query loop block](https://wordpress.org/documentation/files/2023/03/no-results.png)

## [Block toolbar](https://wordpress.org/documentation/article/query-loop-block/\#block-toolbar)

To view the block toolbar, click on the block, and the toolbar will be displayed.

Every block has unique toolbar icons and blocks specific user controls that allow you to manipulate the block right in the editor.

The _Query Loop_ block shows nine buttons in the block toolbar:

![Query loop block toolbar](https://wordpress.org/documentation/files/2023/03/toolbar-2.png)

- Transform to
- Drag icon
- Move arrows
- Align
- Display settings
- Replace
- List view/Grid view
- More options

### [Transform to](https://wordpress.org/documentation/article/query-loop-block/\#transform-to)

![Transform to tool for query loop block](https://wordpress.org/documentation/files/2023/03/transform-4.png)

Click on the “Transform” button to convert the _Query Loop_ block into a “Group” or “Columns” block.

### [Drag icon](https://wordpress.org/documentation/article/query-loop-block/\#drag-icon)

![Drag tool for query loop block](https://wordpress.org/documentation/files/2023/03/drag-and-drop.png)

To drag and drop the block to a new location on the page template, click and hold the rectangle of dots, then drag it to the new location. The blue separator line indicates where the block will be placed. Release the left mouse button when you find the new location to place the block.

### [Move arrows](https://wordpress.org/documentation/article/query-loop-block/\#move-arrows)

![Move handles for query loop block](https://wordpress.org/documentation/files/2023/03/arrows-2.png)

The up and down arrow icons can be used to move the block up and down on the page.

Detailed instructions on moving a block within the editor can be found [here](https://wordpress.org/support/article/moving-blocks/)

### [Align](https://wordpress.org/documentation/article/query-loop-block/\#align)

![Alignment tool for query loop block](https://wordpress.org/documentation/files/2023/03/block-alignment.png)

Use the change alignment tool to align the _Query Loop_ block. Choose one of the following options:

- **None –** leaves the block the current size.
- **Wide width –** increase the width of the block beyond the content size.
- **Full width –** extend the block to cover the full width of the screen.

The “Wide width” and “Full width” alignment settings must be enabled by your WordPress theme.

### [Display settings](https://wordpress.org/documentation/article/query-loop-block/\#display-settings)

![Display settings for query loop block](https://wordpress.org/documentation/files/2023/03/display-settings.png)

Use the display settings tool to change various options for the _Query Loop_ block. Choose one of the following options:

- **Items per Page** – Choose how many posts you want to show within the _Query Loop block_.
- **Offset** – Enable the _Query Loop block_ to skip a certain number of WordPress posts before starting output.
- **Max page to show** – Limits how many pieces of content to show.

If you don’t see this section, it’s because you need to toggle off the “Inherit query from template” setting.

### [Replace](https://wordpress.org/documentation/article/query-loop-block/\#replace)

![](https://wordpress.org/documentation/files/2023/03/replace.png)

Use the replace option to replace the current pattern with a new one.

### [List view (default)](https://wordpress.org/documentation/article/query-loop-block/\#list-view-default)

Displays your post in a stacked list.

![List view tool for query loop block](https://wordpress.org/documentation/files/2023/03/list-view-2-1024x771.png)

### [Grid view](https://wordpress.org/documentation/article/query-loop-block/\#grid-view)

Displays your posts in a grid view.

![Grid view tool for query loop block](https://wordpress.org/documentation/files/2023/03/grid-view-1024x550.png)

## [Options](https://wordpress.org/documentation/article/query-loop-block/\#options)

The Options button on a block toolbar gives you more features to customize the block.

[Read about these and other settings.](https://wordpress.org/support/article/more-options/)

## [Block Settings](https://wordpress.org/documentation/article/query-loop-block/\#block-settings)

The block settings panel contains customization options specific to the block. To open it, select the block and click the settings icon next to the **Publish/Update** button.

![Block settings button in the editor](https://wordpress.org/documentation/files/2023/03/block-settings-1.png)

Here are the options for the _Query Loop_ block:

### [Color](https://wordpress.org/documentation/article/query-loop-block/\#color)

Starting from WordPress 6.2, the Query Loop block will no longer support color settings. As a result, you will need to change the colors of the individual blocks that are within the _Query Loop_ block instead:

![Customizing query loop block color](https://wordpress.org/documentation/files/2023/03/color.png)

[See this guide for more information about changing colors.](https://wordpress.org/documentation/article/colors-settings-overview/)

### [Inner blocks use content width](https://wordpress.org/documentation/article/query-loop-block/\#inner-blocks-use-content-width)

This option allows you to configure justification, content, and wide width settings for all nested blocks within the Query _Loop_ block.

![Customizing query loop block with content width](https://wordpress.org/documentation/files/2023/03/query-loop-layout-settings.gif)

### [Inherit query from template](https://wordpress.org/documentation/article/query-loop-block/\#inherit-query-from-template)

This is an option you can toggle on and off, depending on whether you want to customize the query the loop relies upon. WordPress will otherwise rely on the template being used to determine what posts appear. If you toggle it on, certain customization options will be hidden. If you toggle it off, more customization options will appear.

### [Post type](https://wordpress.org/documentation/article/query-loop-block/\#post-type)

WordPress contains different types of content, and they are divided into collections called “Post types”. By default, there are a few different ones, such as blog posts and pages, but plugins could add more.

### [Order by](https://wordpress.org/documentation/article/query-loop-block/\#order-by)

- Newest to Oldest (default)
- Oldest to Newest
- Alphabetical A to Z
- Alphabetical Z to A
- Ascending by order
- Descending by order

### [Sticky posts](https://wordpress.org/documentation/article/query-loop-block/\#sticky-posts)

This option allows you to choose between three options:

- Include (default) – Displays sticky posts.
- Exclude – Removes sticky posts.
- Ignore – Ignore sticky posts.
- Only – Shows only sticky posts.

### [Filters](https://wordpress.org/documentation/article/query-loop-block/\#filters)

This option allows you to customize further what posts are being displayed. If you don’t see this section, it’s because you need to toggle off the “Inherit query from template” setting.

![Filtering query loop block](https://wordpress.org/documentation/files/2023/03/query-loop-filters.gif)

- **Categories –** List any categories you want included.
- **Tags –** List any tags you want included.
- **Authors –** Search for an author and add it to the list, multiple authors are allowed.
- **Keyword –** Enter any keywords you want included.

Mind that custom taxonomies filtering is also possible. Check the following example for the WooCommerce product categories filter:

If you choose a hierarchical post type like Page, these options will be shown:

- **Authors –** Search for an author and add it to the list, multiple authors are allowed.
- **Keyword –** Enter any keywords you want included.
- **Parents** **–** List any parents you want included.

## [Advanced Settings](https://wordpress.org/documentation/article/query-loop-block/\#advanced-settings)

The advanced tab lets you add a CSS class to your block, allowing you to write custom CSS and style the block as you see fit. It also allows you to assign an HTML element.

![Advanced settings for query loop block](https://wordpress.org/documentation/files/2023/03/advanced-2.png)

## [Resources](https://wordpress.org/documentation/article/query-loop-block/\#resources)

- [Query Loop: The Ins and Outs of One of WordPress 5.8’s Most Powerful Features](https://wptavern.com/query-loop-the-ins-and-outs-of-one-of-wordpress-5-8s-most-powerful-features)

## [Changelog](https://wordpress.org/documentation/article/query-loop-block/\#changelog)

- Updated 2025-07-05
  - Updated Order by to include new Ascending and Descending order

    Updated Sticky posts to include new Ignore option
- Updated 2023-03-26
  - Revised formatting for the whole article
  - Added videos/screenshots where applicable
  - Updated Block Settings Color section
  - Updated Filters section flow along with new parent filter, multiple author, and custom taxonomies filtering
  - Updated block creation and replacement flows
  - Added a mention and a screenshot on customizing what is shown when the Query Loop block shows no results
  - Added a link to Pagination block
  - Updated all the screenshots for 6.2
- Added in resources section on 2021-07-14
- **Created** 2021-07-08

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/query-loop-block/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fquery-loop-block%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

July 8, 2021

Last updated

July 5, 2025

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.