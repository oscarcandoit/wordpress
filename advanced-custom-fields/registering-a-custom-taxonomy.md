---
url: https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy
scraped_at: 2025-10-20T02:24:58.537Z
---

# Registering a Custom Taxonomy

Last updated Apr 21, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#overview)

## Overview

Link copied

Taxonomies are used to classify and categorize individual posts for a post type. WordPress provides an admin UI for managing terms in a taxonomy and categorizing posts with terms.

![List of taxonomies created with ACF.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-tax-list.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#add-new)

## Add New

Link copied

To register a new taxonomy, navigate to the ‘ACF’ > ‘Taxonomy’ screen and click ‘Add New’. You will see a screen with some basic settings for the taxonomy.

![Adding a new taxonomy with ACF.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-tax-add-new.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#basic-settings)

### Basic Settings

Link copied

The required fields of “Plural Label”, “Singular Label” and “Taxonomy Key” are the minimum required information to create a taxonomy, however, there are other settings available if you want to perform more granular configurations.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#plural-label)

#### Plural Label

Link copied

This is the plural label of the taxonomy you are registering. For example, Genres, Series, Franchises.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#singular-label)

#### Singular Label

Link copied

This is the singular label of the taxonomy you are registering. For example, Genre, Series, Franchise.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#taxonomy-key)

#### Taxonomy Key

Link copied

This is automatically generated from the singular label you enter but can be changed. It must be a string made up of lowercase letters, numbers, underscores and dashes only. It has a 20 character limit.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#post-types)

#### Post Types

Link copied

Select one or more existing post types to connect the taxonomy to, so that objects of the post types can be classified with the taxonomy

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#public)

#### Public

Link copied

This setting controls if the taxonomy is public or private. It is on by default, meaning the taxonomy shows in the admin dashboard and is publicly accessible on the site frontend.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#hierarchical)

#### Hierarchical

Link copied

This setting controls the type of taxonomy when it comes to allowing parent and child relationships between taxonomy terms. The native WordPress Category taxonomy is hierarchical but Tags is not. It is off by default.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#advanced-configuration)

## Advanced Configuration

Link copied

There are a large number of settings that can be configured when registering a taxonomy. To keep things simple, ACF doesn’t show them by default but you can control them when the ‘Advanced Configuration’ toggle is on.

![Advanced Settings when creating a taxonomy with ACF.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-tax-advanced-settings.png)

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#general)

### General

Link copied

The ‘General Settings’ gives you several general settings related to the taxonomy.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#sort-terms)

#### Sort Terms

Link copied

Whether terms in this taxonomy should be sorted in the order they are provided to `wp_set_object_terms()`.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#default-term)

#### Default Term

Link copied

Create a term for the taxonomy that cannot be deleted. It will not be selected for posts by default.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#term-name)

#### Term Name

Link copied

The name of the default term (required).

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#term-slug)

#### Term Slug

Link copied

Single word, no spaces. Underscores and dashes allowed.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#term-description)

#### Term Description

Link copied

A descriptive summary of the term.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#description)

#### Description

Link copied

A descriptive summary of the taxonomy.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#active)

#### Active

Link copied

The active toggle is a quick way to deactivate the taxonomy so it can be turned off without deleting it.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#labels)

### Labels

Link copied

The ‘Labels’ tab allows you to define the label strings used for the taxonomy throughout the admin dashboard. You can quickly either regenerate all labels based on your ‘Plural Label’ and ‘Singular Label’ entered earlier or clear all labels.

All of the [labels used by WordPress](https://developer.wordpress.org/reference/functions/get_taxonomy_labels/) can be configured.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#visibility)

### Visibility

Link copied

The ‘Visibility’ tab contains the settings that control how the taxonomy will be displayed in the admin dashboard and the frontend of the site. Control how it appears in the sidebar menu, remove it from the admin bar, exclude it from search results on the frontend, and more.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#show-in-ui)

#### Show in UI

Link copied

Enabled by default, this means the taxonomy can be edited and managed in the WordPress admin dashboard.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#show-in-admin-menu)

#### Show in Admin Menu

Link copied

Enabled by default, this controls if the taxonomy appears in the sidebar menu in the admin dashboard.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#meta-box)

#### Meta Box

Link copied

Controls the meta box on the content editor screen. By default, the Categories meta box is shown for hierarchical taxonomies, and the Tags meta box is shown for non-hierarchical taxonomies. Allows you to supply a custom meta box callback or disable the meta box completely.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#register-meta-box-callback)

#### Register Meta Box Callback

Link copied

A PHP function name to be called to handle the content of a meta box on your taxonomy.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#meta-box-sanitization-callback)

#### Meta Box Sanitization Callback

Link copied

A PHP function name to be called tor sanitizing taxonomy data saved from a meta box.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#appearance-menus-support)

#### Appearance Menus Support

Link copied

Enabled by default, controls if items can be added to menus in the ‘Appearance’ > ‘Menus’ screen. Must be turned on in ‘Screen options’.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#tag-cloud)

#### Tag Cloud

Link copied

Enabled by default, list the taxonomy in the Tag Cloud Widget controls.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#quick-edit)

#### Quick Edit

Link copied

Enabled by default, show the taxonomy in the quick/bulk edit panel.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#show-admin-column)

#### Show Admin Column

Link copied

Display a column for the taxonomy on post type listing screens.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#urls)

### URLs

Link copied

The ‘URLs’ tab contains the settings that control how the taxonomy appears in URLs. This includes the permalink structure of URLs for terms of the taxonomy, and how to control the query variable settings for the URL.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#permalink-rewrite)

#### Permalink Rewrite

Link copied

Rewrite the URL for an item of the taxonomy using the taxonomy key as the slug, a custom slug or disable it to prevent URL rewriting.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#front-url-prefix)

#### Front URL Prefix

Link copied

Enabled by default, alters the permalink structure to add the `WP_Rewrite::$front` prefix to URLs.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#hierarchical)

#### Hierarchical

Link copied

Enables parent-child terms in URLs for hierarchical taxonomies.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#publicly-queryable)

#### Publicly Queryable

Link copied

Enabled by default, controls if URLs for an item and items can be accessed with a query string.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#query-variable-support)

#### Query Variable Support

Link copied

Controls id items can be accessed using the non-pretty permalink, with the taxonomy key as the query variable, a custom variable or query variable access is disabled.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#rest-api)

### REST API

Link copied

The ‘REST API’ tab contains settings to control the taxonomy’s behavior in the WordPress REST API.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#show-in-rest-api)

#### Show in REST API

Link copied

Enabled by default, controls if this taxonomy is exposed in the REST API.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#base-url)

#### Base URL

Link copied

The base URL for the taxonomy REST API URLs.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#namespace-route)

#### Namespace Route

Link copied

The namespace part of the REST API URL.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#controller-class)

#### Controller Class

Link copied

Optional custom controller to use instead of `WP_REST_Terms_Controller`.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#the-next-step)

## The Next Step

Link copied

Once you have configured the taxonomy and saved your changes, a saved success notice appears along with some helpful links to perform typical next actions.

![The next steps after saving a taxonomy with ACF.](https://www.advancedcustomfields.com/wp-content/uploads/2023/04/acf-tax-next-steps.png)

These include:

- [Creating a new ACF field group for the taxonomy](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#creating-new-field-group)
- [Connecting existing ACF field groups to the taxonomy](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#connecting-existing-field-groups)
- [Creating a new post type for the taxonomy](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/)

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#creating-new-field-group)

### Creating a New Field Group

Link copied

A common workflow is to register a taxonomy then add some fields to it to store other structured data outside of the term title and content. This is made extremely easy by clicking the ‘Add fields to’ link, which takes you to a new field group where the location rule is already set to make the field group appear when editing terms of the new taxonomy.

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#connecting-existing-field-groups)

### Connecting to Existing Field Groups

Link copied

There will be times when a new taxonomy is created and existing field groups should also be displayed when editing terms of the new taxonomy. You can connect existing field groups by clicking the ‘Link existing field groups’ link and selecting the field groups in the modal that appears.

This process adds a new location rule to the selected field groups to make them appear when editing terms of the new taxonomy.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#related)

## Related

Link copied

- Tutorials: [Registering a Custom Post Type](https://www.advancedcustomfields.com/resources/registering-a-custom-post-type/)
- Videos: [Creating a Custom Taxonomy with ACF](https://www.advancedcustomfields.com/resources/creating-a-custom-taxonomy-with-acf/)
- Getting Started: [Post Types and Taxonomies](https://www.advancedcustomfields.com/resources/post-types-and-taxonomies/)
- Field Types: [Taxonomy](https://www.advancedcustomfields.com/resources/taxonomy/)
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

[Got it](https://www.advancedcustomfields.com/resources/registering-a-custom-taxonomy/#)