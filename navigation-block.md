---
url: https://wordpress.org/documentation/article/navigation-block
scraped_at: 2025-10-20T02:14:13.344Z
---

[Skip to content](https://wordpress.org/documentation/article/navigation-block/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Navigation block

[Home](https://wordpress.org/documentation)[Customization](https://wordpress.org/documentation/customization/)[Theme blocks](https://wordpress.org/documentation/category/theme-blocks/)Navigation block

Search documentation

# Navigation block

## In this article

Table of Contents

- [Block Configuration](https://wordpress.org/documentation/article/navigation-block/#block-configuration)
  - [Creating a new menu](https://wordpress.org/documentation/article/navigation-block/#creating-a-new-menu)
  - [Selecting an existing menu](https://wordpress.org/documentation/article/navigation-block/#selecting-an-existing-menu)
  - [Deleting and managing menus](https://wordpress.org/documentation/article/navigation-block/#deleting-and-managing-menus)
- [Block customization](https://wordpress.org/documentation/article/navigation-block/#block-customization)
  - [Adding menu items](https://wordpress.org/documentation/article/navigation-block/#adding-menu-items)
  - [Adding submenu items](https://wordpress.org/documentation/article/navigation-block/#adding-submenu-items)
  - [Rearranging menu items](https://wordpress.org/documentation/article/navigation-block/#rearranging-menu-items)
  - [Removing menu items](https://wordpress.org/documentation/article/navigation-block/#removing-menu-items)
  - [Editing link settings](https://wordpress.org/documentation/article/navigation-block/#editing-link-settings)
- [Block toolbar](https://wordpress.org/documentation/article/navigation-block/#block-toolbar)
  - [Transform](https://wordpress.org/documentation/article/navigation-block/#transform)
  - [Block moving tools](https://wordpress.org/documentation/article/navigation-block/#block-moving-tools)
  - [Change items justification](https://wordpress.org/documentation/article/navigation-block/#change-items-justification)
  - [Options](https://wordpress.org/documentation/article/navigation-block/#options)
- [Block Settings](https://wordpress.org/documentation/article/navigation-block/#block-settings)
  - [Display](https://wordpress.org/documentation/article/navigation-block/#display)
  - [Layout](https://wordpress.org/documentation/article/navigation-block/#layout)
  - [Color](https://wordpress.org/documentation/article/navigation-block/#color)
  - [Typography](https://wordpress.org/documentation/article/navigation-block/#typography)
  - [Dimensions](https://wordpress.org/documentation/article/navigation-block/#dimensions)
  - [Advanced](https://wordpress.org/documentation/article/navigation-block/#advanced)
- [Changelog](https://wordpress.org/documentation/article/navigation-block/#changelog)

[↑ Back to top](https://wordpress.org/documentation/article/navigation-block/#wp--skip-link--target)

The _Navigation Block_ is an advanced block in WordPress 5.9 that enables you to edit your site’s navigation menu, both in terms of structure and design. The _Navigation block_ can be used with a [block theme](https://wordpress.org/themes/tags/full-site-editing/) or a theme that has support for [template editing](https://wordpress.org/themes/tags/template-editing/).

In order to add a _Navigation block_, click on the add block button and select the _Navigation block_. You can also type “/navigation” and hit enter in a new paragraph block to add one quickly.

[Detailed instructions on adding blocks](https://wordpress.org/documentation/article/adding-a-new-block/)

The _Navigation Block_ has a dedicated list view tab in the settings panel where you can configure and customize the navigation.

## [Block Configuration](https://wordpress.org/documentation/article/navigation-block/\#block-configuration)

When you add a _Navigation_ _block_ for the first time and don’t have any existing menu, it will start with a _Page List block_.

To start editing the menu, open the **Settings** panel, and select **Page List** from the list view. Click **Edit**, and the page list items will transform into _Page Link_ blocks.

![The navigation block with the "Page List" visible and the "Edit" button highlighted.](https://wordpress.org/documentation/files/2023/03/navigation-block-page-list.png)

### [Creating a new menu](https://wordpress.org/documentation/article/navigation-block/\#creating-a-new-menu)

You can create a new menu from scratch via the _Navigation block_’s list view in the settings panel. Click the **Menu** options button and select **Create a new menu**.

![Creating a new menu.](https://wordpress.org/documentation/files/2023/03/navigation-block-create-menu.gif)

The next step is to add individual blocks to your navigation. You can do so from the editor canvas or the list view in the settings panel.

Adding menu items using the sidebarAdding menu items using the canvas editor

### [Selecting an existing menu](https://wordpress.org/documentation/article/navigation-block/\#selecting-an-existing-menu)

To use another menu for a navigation block, you can select different menus from the list view in the settings panel. Click the **Menu** options button and select the available menus from the drop-down.

### [Deleting and managing menus](https://wordpress.org/documentation/article/navigation-block/\#deleting-and-managing-menus)

If you want to delete the selected menu, go to the **Settings** tab on the block settings panel and open the **Advanced** section.

Click the **Delete menu** button, and a prompt will appear to confirm your action.

Once you’ve clicked **Confirm**, the menu will be deleted, and the navigation block will be replaced with a placeholder. You can then start creating a new menu or selecting an existing one from the settings panel.

## [Block customization](https://wordpress.org/documentation/article/navigation-block/\#block-customization)

You can customize the _Navigation block_ content from the block settings list view and the editor canvas.

### [Adding menu items](https://wordpress.org/documentation/article/navigation-block/\#adding-menu-items)

**Using the block settings view**

To add a menu item from the block settings view, click the **Add block** icon ( **+**) and choose or search for the block you want to add. Alternatively, you can click **Browse all** to open the block inserter panel and see all blocks you can add to the navigation.

When you select a block like _Page Link_ or _Custom Link_, a pop-up will appear where you can search or enter the URL for the menu item, toggle the **Open in new tab** option, and transform the block to another type.

**Using the editor canvas**

To add a menu item from the editor canvas, click the **Add block** icon ( **+**) inside the _Navigation block_. It will insert a new _Custom Link_ block, and a pop-up will appear where you can search or enter the URL for the menu item, toggle the **Open in new tab** option, and transform the block to another type.

### [Adding submenu items](https://wordpress.org/documentation/article/navigation-block/\#adding-submenu-items)

**Using the block settings view**

To add a submenu for a menu item, click the **Options** button on the menu and select **Add submenu link**. It will add a _Custom Link_ block as a submenu, and a pop-up will appear where you can search or enter the URL for the menu item, toggle the **Open in new tab** option, and transform the block to _Page List_.

![Adding a submenu item using the navigation block settings in the sidebar](https://wordpress.org/documentation/files/2023/03/navigation-block-adding-submenu-items.gif)

**Using the editor canvas**

To add a submenu from the editor canvas, select the page link where you want to add the submenu and click **Add submenu** button on the toolbar.

![](https://wordpress.org/documentation/files/2023/03/navigation-block-adding-submenu-items-canvas.gif)

It will add a _Custom Link_ block as a submenu, and a pop-up will appear where you can search or enter the URL for the menu item, toggle the **Open in new tab** option, and transform the block to _Page List_.

![Open link in new tab](https://wordpress.org/documentation/files/2023/03/navigation-block-open-new-tab-edited.png)

You can add more submenu items by clicking the **Add block** button on the submenu drop-down.

![Add submenu item to an existing submenu.](https://wordpress.org/documentation/files/2023/03/navigation-block-open-new-submenu-1024x705.png)

### [Rearranging menu items](https://wordpress.org/documentation/article/navigation-block/\#rearranging-menu-items)

**Using the block settings view**

The list view in the _Navigation block_ settings panel lets you rearrange the menu items by dragging and dropping each of them.

To rearrange the order of the menu items, simply drag and drop them to the new position.

![Moving a menu item in the navigation settings sidebar](https://wordpress.org/documentation/files/2023/03/navigation-move-items.gif)

To rearrange a menu item to create a new submenu, drag the menu item slightly right before dropping it. You will notice the blue line will shift towards the right.

![Moving a menu item to a submenu in the navigation settings sidebar](https://wordpress.org/documentation/files/2023/03/navigation-move-items-submenu.gif)

To move a menu item into an existing submenu, drag the menu item into the submenu list.

![Moving a menu item to a different submenu in the navigation settings sidebar](https://wordpress.org/documentation/files/2023/03/navigation-move-items-submenu-2.gif)

**Using the editor canvas**

To rearrange the menu items in the editor canvas, you can use the block moving tools in the menu item’s block toolbar.

![Moving a menu item in the canvas](https://wordpress.org/documentation/files/2023/03/navigation-move-items-canvas-1.gif)

### [Removing menu items](https://wordpress.org/documentation/article/navigation-block/\#removing-menu-items)

**Using the block settings view**

To remove a menu or submenu item via the list view, click the **Options** button on the item and select **Remove \[menu item name\]**.

![](https://wordpress.org/documentation/files/2023/03/navigation-block-remove-item.png)

**Using the editor canvas**

To remove a menu or submenu item from the editor canvas, select the menu item block you want to remove. Open the **Options** menu from the block toolbar and select **Remove \[menu item name\]**.

![](https://wordpress.org/documentation/files/2023/03/navigation-block-remove-item-sidebar-1024x820.png)

### [Editing link settings](https://wordpress.org/documentation/article/navigation-block/\#editing-link-settings)

**Using the block settings view**

To edit the link settings, click on the menu item in the list view, and it will open the settings panel for the selected link block. Here are the settings available:

- Label
- URL
- Description
- Link title
- Link rel

![Links settings](https://wordpress.org/documentation/files/2023/03/navigation-menu-link-settings-1024x817.png)

You can also add a custom CSS class and customize the link typography and dimensions from the settings panel.

![Adding a custom CSS class](https://wordpress.org/documentation/files/2023/03/Screen-Shot-on-2023-03-28-at-154625.png)

**Using the editor canvas**

To edit the link from the editor canvas, select the menu item block you want to edit and click the **Link** button on the block toolbar. It will open a pop-up where you can edit or remove the link and toggle the **Open in new tab** option.If you click the **Edit** button for the link, you can change the menu item text and URL.

## [Block toolbar](https://wordpress.org/documentation/article/navigation-block/\#block-toolbar)

Every block has unique toolbar icons and blocks specific user controls that allow you to manipulate the block right in the editor.

The _Navigation block_ has the following options:

- Transform
- Block moving tools
- Items justification
- Options

### [Transform](https://wordpress.org/documentation/article/navigation-block/\#transform)

When you click the **Transform** button, you can convert the _Navigation block_ into _Columns_ and _Group_ blocks.

![Options to convert the navigation menu into a different block](https://wordpress.org/documentation/files/2023/03/navigation-block-transform.png)

### [Block moving tools](https://wordpress.org/documentation/article/navigation-block/\#block-moving-tools)

To drag and drop the block to a new location on the page template, click and hold the **Drag** button, then drag it to the new location. The blue separator line indicates where the block will be placed. Release the left mouse button when you find the new location to place the block.

![Dragging around a navigation menu](https://wordpress.org/documentation/files/2023/03/navigation-block-drag.gif)

The **Move up** and **Move down** buttons can be used to move the block up and down on the page. If the _Navigation block_ is in a _Row block_, the buttons will change to left and right.

![Moving a navigation menu using arrows](https://wordpress.org/documentation/files/2023/03/navigation-block-move-arrows.gif)

### [Change items justification](https://wordpress.org/documentation/article/navigation-block/\#change-items-justification)

Click the **Change items justification** button in the block toolbar to display the justification drop-down. You can justify the block text to the left, make it center-justified, align it to the right or leave a space between items.

![](https://wordpress.org/documentation/files/2023/03/navigation-block-justification.png)

Alignment options can also be changed from the sidebar settings.

![How to change the justification of the different items inside a Navigation Block](https://wordpress.org/documentation/files/2023/03/navigation-block-alignment.gif)

### [Options](https://wordpress.org/documentation/article/navigation-block/\#options)

The **Options** button on a block toolbar gives you more features to customize the block.

[Read about these and other settings.](https://wordpress.org/support/article/more-options/) When you enable the block lock for the _Navigation block_, you will find the **Restrict editing** option, which will prevent menu items from getting edited.

## [Block Settings](https://wordpress.org/documentation/article/navigation-block/\#block-settings)

Every block has a specific settings panel to customize the block. To open it, click the **Settings** button next to the **Publish** button.

### [Display](https://wordpress.org/documentation/article/navigation-block/\#display)

Currently, this section consists of one setting that allows you to control what is shown for the _Navigation block_ across different screen sizes, allowing for a responsive menu option:

- **Off:** This turns off displaying a menu icon when on smaller screen sizes.
- **Mobile:** This enables a menu icon to be displayed when viewing your site on smaller screens that one can click on to see the entire menu.
- **Always:** This enables the menu icon to be displayed regardless of screen size.

By default, this option is set to **Mobile**, which will automatically show a menu icon on smaller screen sizes. When you click on the menu icon, it will open up an overlay that shows your entire menu.

![Display options on the Navigation block](https://wordpress.org/documentation/files/2023/03/navigation-block-mobile.png)

There are two additional settings specifically for submenus:

- **Open on click:** By default, submenus will open on hover. You can activate this option if you prefer them to open by clicking on them.
- **Show arrow:** By default, menu items that have submenus beneath them will display an arrow to indicate this. You can de-activate this option to hide those arrows.

### [Layout](https://wordpress.org/documentation/article/navigation-block/\#layout)

Layout settings allow you to change the justification and orientation of child blocks nested inside their parent blocks, with layout controls found on the parent blocks.

[This article provides details about layout settings.](https://wordpress.org/documentation/article/layout-settings-overview/)

### [Color](https://wordpress.org/documentation/article/navigation-block/\#color)

These color settings allow you to customize the appearance of your _Navigation block_. Pick a color from the suggestions, or add a custom color using the color picker or by adding a color code.

[See this guide for more information about changing colors.](https://wordpress.org/documentation/article/colors-settings-overview/)

### [Typography](https://wordpress.org/documentation/article/navigation-block/\#typography)

Typography settings allow you to change a block’s font size, appearance, line height, letter casing, and spacing.

[Get more details about changing typography settings.](https://wordpress.org/documentation/article/typography-settings-overview/)

### [Dimensions](https://wordpress.org/documentation/article/navigation-block/\#dimensions)

The _Navigation block_ currently supports Block Spacing, which allows you to add custom spacing between each block. This makes it easy to set a uniform appearance across the entire block.

[Learn more about dimension controls.](https://wordpress.org/documentation/article/dimension-controls-overview/)

### [Advanced](https://wordpress.org/documentation/article/navigation-block/\#advanced)

The advanced tab lets you accomplish a few things:

- Rename the menu.
- Delete the menu.
- Add a CSS class in order to style the block as you’d like.

![Advanced menu options](https://wordpress.org/documentation/files/2023/03/navigation-block-advanced.png)

## [Changelog](https://wordpress.org/documentation/article/navigation-block/\#changelog)

- **Updated 2023**-03-28

  - Updated the article to match the current state in WordPress 6.2
- **Updated** 2023-02-17

  - Updated the Block Configuration section
  - Updated some screenshots
- **Created** 2022-01-05

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/navigation-block/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fnavigation-block%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

January 5, 2022

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