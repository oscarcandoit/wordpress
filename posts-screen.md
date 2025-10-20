---
url: https://wordpress.org/documentation/article/posts-screen
scraped_at: 2025-10-20T02:08:09.535Z
---

[Skip to content](https://wordpress.org/documentation/article/posts-screen/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Posts screen

[Home](https://wordpress.org/documentation)[Support guides](https://wordpress.org/documentation/support-guides/)[Dashboard](https://wordpress.org/documentation/category/dashboard/)Posts screen

Search documentation

# Posts screen

## In this article

Table of Contents

- [Edit Posts](https://wordpress.org/documentation/article/posts-screen/#edit-posts)
  - [Table of Posts](https://wordpress.org/documentation/article/posts-screen/#table-of-posts)
  - [Filtering Options](https://wordpress.org/documentation/article/posts-screen/#filtering-options)
  - [Using Selection, Actions, and Apply](https://wordpress.org/documentation/article/posts-screen/#using-selection-actions-and-apply)

[↑ Back to top](https://wordpress.org/documentation/article/posts-screen/#wp--skip-link--target)

The Posts Screen provides the facility to manage all the Posts in a blog. Via this Screen, Posts can be edited, deleted, and viewed. Filtering, and searching, also makes it easy to quickly find Posts matching certain criteria.

A powerful bulk edit feature allows Posts to be edited in bulk (en masse) allowing fields such as Author, Comments Allowed, Status, Pings Allowed, and Sticky to be changed for a whole batch of Posts. It is important to note that Categories and Tags can be ADDED in bulk to a set of Posts, but it is not possible to CHANGE, or DELETE, a Category, or Tag, for those Posts. In addition, a Quick Edit feature provides an easy method to change a mulititude of values, such as Title, Slug, Date, and Category, for a given Post.

## [Edit Posts](https://wordpress.org/documentation/article/posts-screen/\#edit-posts)

### [Table of Posts](https://wordpress.org/documentation/article/posts-screen/\#table-of-posts)

A table lists all of your Posts, by row. The Posts are listed with the newest Post first.

[![WordPress administration post list screen](https://wordpress.org/documentation/files/2018/11/manageposts-768x528.png)](https://wordpress.org/documentation/files/2018/11/manageposts-768x528.png) Administration post list screen

The table of Posts contains the following columns:

- **\[ \]** – This checkbox, when clicked (checked), ‘selects’ that particular Post to be processed by a Bulk Action.
- **Title** – This is the Post’s Title displayed as a link. Click the Title link to allow this Post to be edited. Next to the Title, if a Post is of a Draft, Private, Pending, Sticky, or Password Protected nature, bold text will display showing that.
- **“ID”** – This is not a column in the Table, but by hovering the mouse over the Post Title, the Post ID is revealed as part of the URL displayed in the browser status bar (in Firefox the status bar is displayed at the bottom of the screen). A Post’s ID number is the unique number WordPress’ database uses to identify individual Posts.
- **Author** – Displayed in the form of a link, this is the [author](https://wordpress.org/documentation/article/users-your-profile-screen/) who wrote the Post. Clicking the author link causes all the Posts authored by that user to be displayed in the Table of Posts (thus allowing a Bulk Action to be applied to all Posts for a given author).
- **Categories** – Displays all the Categories, in the form of links, to which this Post belongs. Each Category link, when clicked will cause the list of Posts assigned that Category to be displayed in the Table of Posts (note the Category Filter box at the top of the Table will depict the Category being displayed).
- **Tags** – Displays all the Tags, in the form of links, associated with a Post. Each Tag link, when clicked will cause the list of Posts assigned that Tag to be displayed in the Table of Posts.
- **comment bubble** – A comment bubble is the column heading, and each Post row has comment bubble with the number of comments for that Post. If a Posts has any comments, then the number comments is displayed in a blue bubble. Clicking on a blue comment bubble causes the [Comments Screen](https://wordpress.org/support/article/comments-in-wordpress/) to be displayed to allow moderation of those comments.
- **Date** – The Date column for each Post shows the Date ‘Published’ for Published Posts or the Date ‘Last Modified’ for other Posts. If the Post is a “future Post,” the scheduled date for publishing is displayed.

#### [Sortable Columns](https://wordpress.org/documentation/article/posts-screen/\#sortable-columns)

Some column headings, such as the Title, Author, and Date, can be clicked to sort the Table of Posts in ascending or descending order. Hover over the column title, for example Title, to see the up-arrow or down-arrow. Click the heading to change the sort order.

#### [View](https://wordpress.org/documentation/article/posts-screen/\#view)

Just to the right above the Table of Posts, two icons, List View, and Excerpt View, can be clicked to determine the amount of information listed with each Post. The default view is the List View and only the Post Title is listed for each Post. Click the Excerpt View to cause an [excerpt](https://wordpress.org/support/article/glossary#excerpt) for the Post to be displayed just below the Post Title.

#### [Page Navigation](https://wordpress.org/documentation/article/posts-screen/\#page-navigation)

Under the Screen Options, the number of Posts displayed per page is determined. If more then one page of Posts is available, two double-arrow boxes to move to the first and last page are provided. Also two single-arrow boxes are displayed to move one page backward or forward. Finally, a box showing the current page number can be used to enter a page to directly display.

#### [Screen Options](https://wordpress.org/documentation/article/posts-screen/\#screen-options)

The Screen Options allow you to choose which columns are displayed, or not displayed, in the underlying Table. Clicking on the Screen Options tab shows a list of the columns with a check-box next to each column. Check the box for each column you want displayed in the Table, or uncheck the box to not display that column. Click the Screen Options tab again to close the Screen Options. In addition, the number of Posts per page can be set.

#### [Search](https://wordpress.org/documentation/article/posts-screen/\#search)

Above the Table, to the right, is a search box where you can enter a word, or series of words, and click the “Search Posts” button to search and display all the Posts meeting your search words.

### [Filtering Options](https://wordpress.org/documentation/article/posts-screen/\#filtering-options)

At the top of this Screen are links such as All, Published, Schedules, Pending Review, Draft, Private, that when clicked, will cause just the Posts of that type to be displayed in the underlying Table.

Below that, and to the right of the [Bulk Actions](https://wordpress.org/documentation/article/posts-screen/#actions) [Apply button](https://wordpress.org/documentation/article/posts-screen/#apply), are two other filter options:

**Show all dates**

This dropdown allows you to select, by date, which Posts are displayed in the [Table of Posts](https://wordpress.org/documentation/article/posts-screen/#table-of-posts). By default, “Show all dates” is selected and all of your Posts are displayed.

**View all categories**

This dropdown allows you to select, by Category, which Posts are displayed in the [Table of Posts](https://wordpress.org/documentation/article/posts-screen/#table-of-posts). By default, “Show all categories” is selected and all of your Posts are displayed.

**Filter**

Clicking this button applies the settings you select in the dropdowns.

### [Using Selection, Actions, and Apply](https://wordpress.org/documentation/article/posts-screen/\#using-selection-actions-and-apply)

#### [Selection](https://wordpress.org/documentation/article/posts-screen/\#selection)

This Screen allows Bulk Actions to be performed on one or more Posts selected in the Table. For Bulk Actions to be performed on multiple Posts at once, those Posts must be first **selected** via one of these methods:

- **Select one Post at a time** – To select a Post, the checkbox to the left of the Post entry must be checked (clicked). It is possible to keep selecting more Posts by checking their respective checkbox.

#### [Actions](https://wordpress.org/documentation/article/posts-screen/\#actions)

Actions describe the process to be performed on particular Posts. There are two styles of Actions that will be referred to as _Bulk Actions_ and _Immediate Actions_. The following describes these Actions:

- **Bulk Actions** – These Actions can be performed on one, or more Posts, at one time, if those Posts have been previously [selected](https://wordpress.org/documentation/article/posts-screen/#selection). Bulk Actions are available, when appropriate, as choices in the Bulk Actions pulldown box, above the Table. The only Bulk Actions allowed are Edit and Delete.

The available Actions are described below:

- **Edit** – This Action can be either an “Immediate Action” or a “Bulk Action”. The Immediate Action, initiated by click on the Post Title or clicking on the Edit option just below the Post Title, causes the [Edit Posts screen](https://wordpress.org/documentation/article/writing-posts/#post-field-descriptions) to display. Edit is also available as a Bulk Action for the selected Posts, so see the [Bulk Edit section](https://wordpress.org/documentation/article/posts-screen/#bulk-edit) for details on the Bulk Editing process.

##### [Bulk Edit](https://wordpress.org/documentation/article/posts-screen/\#bulk-edit)

The Bulk Edit Posts ‘screen’ is displayed below the Table Of Posts header once, one, or more Posts, have been [selected](https://wordpress.org/documentation/article/posts-screen/#selection), and the [Bulk Action](https://wordpress.org/documentation/article/posts-screen/#action) of Edit is [Applied](https://wordpress.org/documentation/article/posts-screen/#apply). Bulk Edit allows the fields, Author, Comments Allowed, Status, Pings Allowed, and Sticky, to be changed for all the selected Posts. **It is important to note, Categories and Tags can be ADDED in bulk to a set of Posts, but it is not possible to CHANGE, or DELETE, a Category, or Tag, for those Posts.**

- **Cancel** – Click Cancel to cancel and abort the Bulk Edit of these Posts.

##### [Quick Edit](https://wordpress.org/documentation/article/posts-screen/\#quick-edit)

Quick Edit is an Immediate Action performed on one Post by clicking the Quick Edit link, under the Post Title in the Table of Posts. Quick Edit is just an in-line edit that allows you to change the following items–Title, Slug, Date, Author, Password or Private post box, Categories, Tags, Allow Comments, Allow Pings, Status, and Make this a post-sticky.

- **Cancel** – Click Cancel to cancel and abort the Edit of this Post.

##### [Editing Individual Posts](https://wordpress.org/documentation/article/posts-screen/\#editing-individual-posts)

This mode is essentially the same as the [Posts Add New Screen](https://wordpress.org/documentation/article/writing-posts/) so see the [Posts\_Add\_New\_Screen](https://wordpress.org/documentation/article/writing-posts/) for the specific details of writing a Post. The only difference is that the button to save your work is called “ **Update**” instead of “ **Publish**“.

#### [Apply](https://wordpress.org/documentation/article/posts-screen/\#apply)

After one or more Posts are _selected_, and after a _Bulk_ Action is specified, the **Apply** button performs the given Action on the selected Posts.

- **Apply** – Click the Apply button to execute the Bulk Action, specified in the Actions pulldown, on the selected Posts. Remember, prior to executing Actions, one or more Posts must be **selected**, as described before.

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/posts-screen/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fposts-screen%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

November 6, 2018

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