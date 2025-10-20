---
url: https://www.advancedcustomfields.com/resources/registering-a-custom-post-type
scraped_at: 2025-10-20T02:32:15.538Z
---

# Registering a Custom Post Type

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#overview)

## Overview

Link copied

Post Types are great for storing data objects other than posts and pages, where WordPress provides an [admin UI](https://www.advancedcustomfields.com/blog/customize-wordpress-admin/) for managing your data and a URL structure for viewing them on the frontend of the site.

![The ACF admin screen listing registered custom post types.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-cpts-list.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#add-new)

## Add New

Link copied

To register a new post type, navigate to the ‘ACF’ > ‘Post Types’ screen and click ‘Add New’. You will see a screen with some basic settings for the post type.

![Add a new post type with ACF.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-cpt-add-new.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#basic-settings)

### Basic Settings

Link copied

The required fields of “‘Plural Label”, “Singular Label” and “Post Type Key” are the minimum required information to create a post type, however, there are other settings available if you want to perform more granular configurations.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#plural-label)

#### Plural Label

Link copied

This is the plural label of the date object you are registering. For example, Movies, actors, and books.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#singular-label)

#### Singular Label

Link copied

This is the singular label of the data object you are registering. For example, Movie, actor, and book.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#post-type-key)

#### Post Type Key

Link copied

This is automatically generated from the singular label you enter but can be changed. It must be a string made up of lowercase letters, numbers, underscores and dashes only. It has a 20 character limit.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#public)

#### Public

Link copied

This setting controls if the post type is public or private. It is on by default, meaning the post type shows in the admin dashboard and is publicly accessible on the site frontend.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#hierarchical)

#### Hierarchical

Link copied

This setting controls the type of post type when it comes to allowing parent and child relationships between objects of the post types, like the WordPress ‘Pages’ post type.. It is off by default.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#advanced-configuration)

## Advanced Configuration

Link copied

There are a large number of settings that can be configured when registering a post type. To keep things simple, ACF doesn’t show them by default but you can control them when the ‘Advanced Configuration’ toggle is on.

![Advanced settings when registering a post type with ACF.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-cpt-advanced-settings.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#general)

### General

Link copied

The ‘General Settings’ gives you several general settings related to the post type.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#linked-taxonomies)

#### Linked Taxonomies

Link copied

Select from existing taxonomies that should be used to classify the post type.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#supports)

#### Supports

Link copied

Allows you to define which features of the content edit screen for the post type are supported. Enable the title, featured image, author, and more.

You can also add custom items to allow you to customize the editor for your site.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#description)

#### Description

Link copied

Use this to add a description about your post type that will be displayed in the post type list screen.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#active)

#### Active

Link copied

The active toggle is a quick way to deactivate the post type so it can be turned off without deleting it.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#labels)

### Labels

Link copied

The ‘Labels’ tab allows you to define the label strings used for the post type throughout the admin dashboard. You can quickly either regenerate all labels based on your ‘Plural Label’ and ‘Singular Label’ entered earlier or clear all labels.

All of the [labels used by WordPress](https://developer.wordpress.org/reference/functions/get_post_type_labels/) can be configured.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#visibility)

### Visibility

Link copied

The ‘Visibility’ tab contains the settings that control how the post type will be displayed in the admin dashboard and the frontend of the site. Control how it appears in the sidebar menu, remove it from the admin bar, exclude it from search results on the frontend, and more.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#show-in-ui)

#### Show in UI

Link copied

Enabled by default, this means the post type can be edited and managed in the WordPress admin dashboard.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#show-in-admin-menu)

#### Show in Admin Menu

Link copied

Enabled by default, this controls if the post type appears in the sidebar menu in the admin dashboard.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#admin-menu-parent)

#### Admin Menu Parent

Link copied

By default the post type will get a new top level item in the admin menu. If an existing top level item is supplied here, the post type will be added as a submenu item under it.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#menu-position)

#### Menu Position

Link copied

A number that controls the position of the menu item in the admin dashboard sidebar menu.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#menu-icon)

#### Menu Icon

Link copied

This is the icon used for the post type menu item in the admin dashboard. Can be a URL or [Dashicon class name](https://developer.wordpress.org/resource/dashicons/) to use for the icon.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#custom-meta-box-callback)

#### Custom Meta Box Callback

Link copied

A PHP function name to be called when setting up the meta boxes for the edit screen.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#show-in-admin-bar)

#### Show In Admin Bar

Link copied

Enabled by default, controls if the post type should appear as an item in the ‘New’ menu in the admin bar.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#appearance-menus-support)

#### Appearance Menus Support

Link copied

Enabled by default, controls if items can be added to menus in the ‘Appearance’ > ‘Menus’ screen. Must be turned on in ‘Screen options’.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#exclude-from-search)

#### Exclude From Search

Link copied

Sets whether posts should be excluded from search results.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#urls)

### URLs

Link copied

The ‘URLs’ tab contains the settings that control how the post type appears in URLs. This includes the permalink structure of URLs for items of the post type, if the post type should have an archive page URL, and how to control the query variable settings for the URL.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#permalink-rewrite)

#### Permalink Rewrite

Link copied

Rewrite the URL for an item of the post type using the post type key as the slug, a custom slug or disable it to prevent URL rewriting.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#front-url-prefix)

#### Front URL Prefix

Link copied

Enabled by default, alters the permalink structure to add the `WP_Rewrite::$front` prefix to URLs.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#feed-url)

#### Feed URL

Link copied

Enables an RSS feed URL for the post type items.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#pagination)

#### Pagination

Link copied

Enabled by default, allows pagination support for the items URLs such as the archives.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#archive)

#### Archive

Link copied

Controls if the post type has an item archive that can be customized with an archive template file in your theme.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#publicly-queryable)

#### Publicly Queryable

Link copied

Enabled by default, controls if URLs for an item and items can be accessed with a query string.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#query-variable-support)

#### Query Variable Support

Link copied

Controls id items can be accessed using the non-pretty permalink, with the post type key as the query variable, a custom variable or query variable access is disabled.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#permissions)

### Permissions

Link copied

The ‘Permissions’ tab contains settings all about accessing the post type.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#rename-capabilities)

#### Rename Capabilities

Link copied

By default the capabilities of the post type will inherit the ‘Post’ capability names, eg. edit\_post, delete\_posts. Enable to use post type specific capabilities, eg. edit\_{singular}, delete\_{plural}.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#singular-capability-name)

#### Singular Capability Name

Link copied

Choose another post type to base the capabilities for this post type.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#plural-capability-name)

#### Plural Capability Name

Link copied

Optionally provide a plural to be used in capabilities.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#can-export)

#### Can Export

Link copied

Enabled by default, controls if the post type to be exported from ‘Tools’ > ‘Export’.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#delete-with-user)

#### Delete With User

Link copied

Controls if the items by a user are deleted when that user is deleted.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#rest-api)

### REST API

Link copied

The ‘REST API’ tab contains settings to control the post type’s behavior in the WordPress REST API.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#show-in-rest-api)

#### Show in REST API

Link copied

Enabled by default, controls if this post type is exposed in the REST API. Required to use the block editor.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#base-url)

#### Base URL

Link copied

The base slug for the post type REST API URLs.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#namespace-route)

#### Namespace Route

Link copied

The namespace part of the REST API URL.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#controller-class)

#### Controller Class

Link copied

Optional custom PHP controller class to use instead of `WP_REST_Posts_Controller`.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#the-next-step)

## The Next Step

Link copied

Once you have configured the post type and saved your changes, a saved success notice appears along with some helpful links to perform typical next actions.

![Post type actions to perform after saving.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-cpt-post-save-actions.png)

These include:

- [Creating a new ACF field group for the post type](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#creating-new-field-group)
- [Connecting existing ACF field groups to the post type](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#connecting-existing-field-groups)
- [Creating a new taxonomy for the post type](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/)

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#creating-new-field-group)

### Creating a New Field Group

Link copied

A common workflow is to register a post type then add some fields to it to store other structured data outside of the post title and content. This is made extremely easy by clicking the ‘Add fields to’ link, which takes you to a new field group where the location rule is already set to make the field group appear when editing posts of the new post type.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#connecting-existing-field-groups)

### Connecting to Existing Field Groups

Link copied

There will be times when a new post type is created and existing field groups should also be displayed when editing posts of the new post type. You can connect existing field groups by clicking the ‘Link existing field groups’ link and selecting the field groups in the modal that appears.

This process adds a new location rule to the selected field groups to make them appear when editing posts of the new post type.

![Connect a post type with existing field groups with ACF.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-cpt-link-field-groups.png)

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#related)

## Related

Link copied

- Guides: [Registering a Custom Taxonomy](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/)
- Videos: [Creating a Custom Taxonomy with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/)
- Getting Started: [Post Types and Taxonomies](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/)
- Videos: [Creating a Custom Post Type with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-post-type-with-acf/)
- Features: [WP REST API Integration](https://www.advancedcustomfields.com/resources/wp-rest-api-integration/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/#)