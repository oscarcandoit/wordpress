---
url: https://wordpress.org/documentation/article/plugins-screen
scraped_at: 2025-10-20T02:07:15.530Z
---

[Skip to content](https://wordpress.org/documentation/article/plugins-screen/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Plugins screen

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Dashboard](https://wordpress.org/documentation/category/dashboard/)Plugins screen

Search documentation

# Plugins screen

## In this article

Table of Contents

- [Manage Plugins](https://wordpress.org/documentation/article/plugins-screen/#manage-plugins)
  - [Table of Plugins](https://wordpress.org/documentation/article/plugins-screen/#table-of-plugins)
  - [Filtering Options](https://wordpress.org/documentation/article/plugins-screen/#filtering-options)
  - [Using Selection, Actions, and Apply](https://wordpress.org/documentation/article/plugins-screen/#using-selection-actions-and-apply)

[↑ Back to top](https://wordpress.org/documentation/article/plugins-screen/#wp--skip-link--target)

The **Plugins Screen** enables you to manage your Plugins. Management of Plugins entails activating, deactivating, updating, editing, and deleting Plugins that are **installed**.

Visit the [Plugins Add New Screen](https://wordpress.org/support/articles/plugins-add-new-screen) to install new plugins by clicking Add New link at the top of this screen or Select **Plugins > Add New** from left side menu. Once a plugin has been installed, you may activate it here.

## [Manage Plugins](https://wordpress.org/documentation/article/plugins-screen/\#manage-plugins)

Once a plugin is installed, you may activate it, deactivate it, edit
the Plugin file, delete the Plugin, or Upgrade the Plugin. As a special
note regarding the Plugin Upgrade process–when Plugins need to be
updated, the left navigation menu Plugin option will display a balloon,
with a number inside the balloon. That number represents the number of
Plugins that need to be Updated.

On visiting the **Plugins Screen**, there may be a splash warning message, similar to, _The plugin “some plugin name” has been **deactivated** due to an error: xxxxxxxxxxxx._
If such a message is displayed, investigation is required to find out
why a particular Plugin was deactivated. Possible causes for the
deactivation are, (1) an incomplete set of plugin files, (2) the plugin
is coded incorrectly, or (3) the Plugin is dependent on another Plugin,
and that Plugin is missing, deactivated, or has problems.

### [Table of Plugins](https://wordpress.org/documentation/article/plugins-screen/\#table-of-plugins)

A table lists all of your Plugins, by row. The plugins are listed in alphabetical order.

[![](https://i0.wp.com/wordpress.org/documentation/files/2019/01/plugins-screen.png?fit=1221%2C400&ssl=1)](https://wordpress.org/support/?attachment_id=11136857)

The table of Plugins contains the following columns:

- **\[ \]** – This checkbox, when clicked (checked), ‘selects’ that particular plugin to be processed by a Bulk Action.
- **Plugin** – The name of the Plugin.
- **Description** – information about its Plugin. Includes version
number, Plugin author name and link to the plugin’s web site for more
detail information or support.

#### [Page Navigation](https://wordpress.org/documentation/article/plugins-screen/\#page-navigation)

Above and below the Table, to the right, the number of Plugins
displayed per page is determined. If more then one page of Plugins is
available, two double-arrow boxes to move to the first and last page are
provided. Also two single-arrow boxes are displayed to move one page
backward or forward. Finally, a box showing the current page number can
be used to enter a page to directly display.

#### [Screen Options](https://wordpress.org/documentation/article/plugins-screen/\#screen-options)

**Screen Options**, displayed as a hanging tab under **the toolbar**, allow you to choose which columns are displayed, or not displayed, in the underlying Table. Clicking on the Screen Options tab shows a list of the columns with a check-box next to each column. Check the box for each column you want displayed in the Table, or uncheck the box to not display that column. Click the Screen Options tab again to close the Screen Options. In addition, the number of Plugins per page can be set.

[![](https://i2.wp.com/wordpress.org/documentation/files/2019/01/plugins-screen-options.png?fit=235%2C174&ssl=1)](https://wordpress.org/support/?attachment_id=11136868) screen options

#### [Search](https://wordpress.org/documentation/article/plugins-screen/\#search)

Above the Table, to the right, is a search box where you can enter a
word, or series of words, and click the “Search Installed Plugins”
button to search and display all the Posts meeting your search words.

### [Filtering Options](https://wordpress.org/documentation/article/plugins-screen/\#filtering-options)

At the top of this Screen are links such as All, Active, Inactive, Recently Active, Update Available, that when clicked, will cause just the Plugins of that type to be displayed in the underlying Table.

**All**: lists all installed Plugins.

**Active**: lists currently active Plugins. Note that each Active Plugin is displayed in a light green background.

**Inactive**: lists installed, but inactive Plugins.

**Recently Active**: lists recently deactivated Plugins. When a plugin has been inactive for more than 7 days it will be dropped off.

**Update Available**: lists upgrade available Plugins at the [WordPress Plugin Directory](https://wordpress.org/plugins/).

### [Using Selection, Actions, and Apply](https://wordpress.org/documentation/article/plugins-screen/\#using-selection-actions-and-apply)

#### [Selection](https://wordpress.org/documentation/article/plugins-screen/\#selection)

The Screen allows Bulk Actions to be performed on one or more Plugins selected in the Table. For Bulk Actions to be performed on multiple Plugins at once, those Plugins must be first **selected** via one of these methods:

The various Tables in this Screen allow Actions to be performed on one or more Plugins. For Actions to be performed on multiple Plugins at once, those Plugins must be first **selected** via one of these methods:

- **Select one Plugin at a time** – To select a Plugin, the
checkbox to the left of the Plugin entry must be checked (clicked). It
is possible to keep selecting more Plugins by checking their respective
checkbox.
- **Select all Plugins in given Table** – All Plugins in a given
table can be selected by checking the checkbox in the Table’s title, or
footer bar. Of course, unchecking the header or footer title bar
checkbox will cause all entries in that Table to be unchecked (NOT
selected).
- **Reverse Selection** – A Reverse Selection means checked items
become unchecked, and unchecked items become checked. A Reverse
Selection is accomplished by holding the Shift key on the keyboard and
clicking the header or footer title bar checkbox.

#### [Actions](https://wordpress.org/documentation/article/plugins-screen/\#actions)

Actions describe the process to be performed on particular
Plugins. There are two styles of Actions that will be referred to as _Bulk Actions_ and _Immediate Actions_. The follow describes these Actions:

- **Bulk Actions** – These Actions can be performed on one, or more Plugins, at one time, if those Plugins have been previously selected. Bulk Actions are available, when appropriate, as choices in the Actions **pull-down** box, above each Table. The Bulk Actions are Activate, Deactivate, Update and Delete.
- **Immediate Actions** – Immediate Actions are performed immediately, on an individual Plugin, by clicking the Activate, Deactivate, Edit, or Delete links, displayed under the Action column in that Plugin row. The Upgrade Action is also an Immediate Action, but the Upgrade link is seen in the upgrade message below the Plugin row, and the Upgrade **nag** message only appears if there is an upgrade available at the WordPress Plugins site.

The list of Actions available are described below:

- **Activate** – This Action enables a Plugin, or better yet, turns the Plugin on. Activating a Plugin is necessary to use the features of a Plugin. Only Inactive Plugins can be activated. Activate can be either a Bulk Action, or an Immediate Action.

Note: Successful activation will display a splash message at the top of the Screen (e.g. _Plugin **activated**._ or _Selected plugins **activated**._) **Failure to activate** a Plugin results in the message _Plugin could not be activated because it triggered a **fatal error**_
– this should be further investigated. Likely causes of failure are
(1) an incomplete set of plugin files, (2) the plugin is coded
incorrectly, (3) or the Plugin is dependent on another Plugin before it
can be successfully activated.

- **Deactivate** – This Action disables, or turns off, a
Plugin. Only Active Plugins can be deactivated. Deactivate is either a
Bulk Action, or an Immediate Action.

Note: Successful deactivation will display a splash message at the top of the Screen (e.g. _Plugin **deactivated**_. or _Selected plugins **deactivated**._)

- **Delete** – This Action deletes the Plugins files. Only Inactive Plugins can be deleted. Delete is either a Bulk Action, or an Immediate Action.
- **Upgrade** – This Action initiates the Plugin upgrade process.
- **Edit** – This Immediate Action places the Plugin code in the Plugins Editor text box for editing. **Warning**: Making changes to active plugins is not recommended. If your changes cause a fatal error, the plugin will be automatically deactivated.

#### [Apply](https://wordpress.org/documentation/article/plugins-screen/\#apply)

After one or more Plugins are _selected_, and after a _Bulk_ Action is specified, the **Apply** button performs the given Action on the selected Plugins.

- **Apply** – Click the Apply button to execute the Bulk Action, specified in the Actions pull-down, on the selected Plugins. Remember, prior to executing Actions, one or more Plugins must be **selected**, as described before.

Successful application of the Action is noted in a splash message at the top of the Screen. For instance, when the Activate Action is applied, the message _Selected plugins activated._” is displayed.

#### [Deleting Plugins](https://wordpress.org/documentation/article/plugins-screen/\#deleting-plugins)

When the Delete Action is Applied to selected Plugin(s), a Screen similar to the follow is displayed:

_Deleting the selected plugins will remove the following plugin(s) and their files:_

_\\* Plugin xyx by John Doe_

_\\* Plugin abc by Jane JoeAre you sure you wish to delete these files?_

- **Yes Delete these Files** – This is the final chance, because clicking this will delete the Plugin(s), and return to the **Plugins Screen** with the _The selected plugins have been deleted._ splash message displayed.

Note: If deletion is unsuccessful The message _Plugin could not be deleted due to an error: xxxxxxxxx._ This should be further investigated.

- **No, Return me to the plugin list** – Click this to be returned to the **Plugins Screen**
- **Click to view entire list of files which will be deleted** – Clicking this causes a listing of all the files that are part of the Plugins being deleted.

#### [Upgrading Plugins](https://wordpress.org/documentation/article/plugins-screen/\#upgrading-plugins)

**Important note:** If a Plugin is hosted at the [WordPress Plugins Directory](https://wordpress.org/plugins/) Upgrade notices will be displayed, when appropriate, for a given Plugin. If the Plugin is hosted elsewhere, such as the Plugin author’s site, it is important for you to check for available updates for those Plugins.

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/plugins-screen/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fplugins-screen%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

January 28, 2019

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