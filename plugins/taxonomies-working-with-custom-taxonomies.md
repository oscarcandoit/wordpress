---
url: https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies
scraped_at: 2025-10-20T03:37:33.006Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Working with Custom Taxonomies


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Taxonomies](https://developer.wordpress.org/plugins/taxonomies/)Working with Custom Taxonomies

Search

# Working with Custom Taxonomies

## In this article

Table of Contents

- [Introduction to Taxonomies](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#introduction-to-taxonomies)
- [Custom Taxonomies](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#custom-taxonomies)
- [Why Use Custom Taxonomies?](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#why-use-custom-taxonomies)
- [Example: Courses Taxonomy](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#example-courses-taxonomy)
  - [Step 1: Before You Begin](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#step-1-before-you-begin)
  - [Step 2: Creating a New Plugin](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#step-2-creating-a-new-plugin)
  - [Step 3: Review the Result](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#step-3-review-the-result)
  - [Code Breakdown](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#code-breakdown)
  - [Summary](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#summary)
- [Using Your Taxonomy](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#using-your-taxonomy)

[↑ Back to top](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#wp--skip-link--target)

## [Introduction to Taxonomies](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#introduction-to-taxonomies)

To understand what Taxonomies are and what they do please read the [Taxonomy](https://developer.wordpress.org/plugins/taxonomies/) introduction.

## [Custom Taxonomies](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#custom-taxonomies)

As classification systems go, “Categories” and “Tags” aren’t very structured, so it may be beneficial for a developer to create their own.

WordPress allows developers to create **Custom Taxonomies**. Custom Taxonomies are useful when one wants to create distinct naming systems and make them accessible behind the scenes in a predictable way.

## [Why Use Custom Taxonomies?](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#why-use-custom-taxonomies)

You might ask, “Why bother creating a Custom Taxonomy, when I can organize by Categories and Tags?”

Well… let’s use an example. Suppose we have a client that is a chef who wants you to create a website where she’ll feature original recipes.

One way to organize the website might be to create a Custom Post Type called “Recipes” to store her recipes. Then create a Taxonomy “Courses” to separate “Appetizers” from “Desserts”, and finally a Taxonomy “Ingredients” to separate “Chicken” from “Chocolate” dishes.

These groups _could_ be defined using Categories or Tags, you could have a “Courses” Category with Subcategories for “Appetizers” and “Desserts”, and an “Ingredients” Category with Subcategories for each ingredient.

The main advantage of using Custom Taxonomies is that you can reference “Courses” and “Ingredients” independently of Categories and Tags. They even get their own menus in the Administration area.

In addition, creating Custom Taxonomies allows you to build custom interfaces which will ease the life of your client and make the process of inserting data intuitive to their business nature.

Now imagine that these Custom Taxonomies and the interface is implemented inside a plugin; you’ve just built your own Recipes plugin that can be reused on any WordPress website.

## [Example: Courses Taxonomy](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#example-courses-taxonomy)

The following example will show you how to create a plugin which adds a Custom Taxonomy “Courses” to the default `post` Post Type. Note that the code to add custom taxonomies does not have to be in its own plugin; it can be included in a theme or as part of an existing plugin if desired.

Please make sure to read the [Plugin Basics](https://developer.wordpress.org/plugin/the-basics/ "Plugin Basics") chapter before attempting to create your own plugin.

### [Step 1: Before You Begin](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#step-1-before-you-begin)

Go to **Posts > Add New** page. You will notice that you only have Categories and Tags.

[![No Custom Taxonomy Meta Box (Yet)](https://i0.wp.com/make.wordpress.org/docs/files/2014/02/no-custom-taxonomy-meta-box.png?ssl=1)](https://i0.wp.com/make.wordpress.org/docs/files/2014/02/no-custom-taxonomy-meta-box.png?ssl=1)

### [Step 2: Creating a New Plugin](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#step-2-creating-a-new-plugin)

Register the Taxonomy “course” for the post type “post” using the `init` action hook.

``
[Expand code](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#)

[Copy](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/#)

```php
/*
* Plugin Name: Course Taxonomy
* Description: A short example showing how to add a taxonomy called Course.
* Version: 1.0
* Author: developer.wordpress.org
* Author URI: https://codex.wordpress.org/User:Aternus
*/

function wporg_register_taxonomy_course() {
	 $labels = array(
		 'name'              => _x( 'Courses', 'taxonomy general name' ),
		 'singular_name'     => _x( 'Course', 'taxonomy singular name' ),
		 'search_items'      => __( 'Search Courses' ),
		 'all_items'         => __( 'All Courses' ),
		 'parent_item'       => __( 'Parent Course' ),
		 'parent_item_colon' => __( 'Parent Course:' ),
		 'edit_item'         => __( 'Edit Course' ),
		 'update_item'       => __( 'Update Course' ),
		 'add_new_item'      => __( 'Add New Course' ),
		 'new_item_name'     => __( 'New Course Name' ),
		 'menu_name'         => __( 'Course' ),
	 );
	 $args   = array(
		 'hierarchical'      => true, // make it hierarchical (like categories)
		 'labels'            => $labels,
		 'show_ui'           => true,
		 'show_admin_column' => true,
		 'query_var'         => true,
		 'rewrite'           => [ 'slug' => 'course' ],
	 );
	 register_taxonomy( 'course', [ 'post' ], $args );
}
add_action( 'init', 'wporg_register_taxonomy_course' );
```

### [Step 3: Review the Result](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#step-3-review-the-result)

Activate your plugin, then go to **Posts > Add New**. You should see a new meta box for your “Courses” Taxonomy.

[![courses_taxonomy_post_screen](https://i0.wp.com/make.wordpress.org/docs/files/2014/02/courses_taxonomy_post_screen-1024x545.png?resize=1024%2C545&ssl=1)](https://i0.wp.com/make.wordpress.org/docs/files/2014/02/courses_taxonomy_post_screen.png?ssl=1)

### [Code Breakdown](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#code-breakdown)

The following discussion breaks down the code used above describing the functions and parameters.

The function `wporg_register_taxonomy_course` contains all the steps necessary for registering a Custom Taxonomy.

The `$labels` array holds the labels for the Custom Taxonomy.

These labels will be used for displaying various information about the Taxonomy in the Administration area.

The `$args` array holds the configuration options that will be used when creating our Custom Taxonomy.

The function [register\_taxonomy()](https://developer.wordpress.org/reference/functions/register_taxonomy/) creates a new Taxonomy with the identifier `course` for the `post` Post Type using the `$args` array for configuration.

The function [add\_action()](https://developer.wordpress.org/reference/functions/add_action/) ties the `wporg_register_taxonomy_course` function execution to the `init` action hook.

#### [$args](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#args)

The $args array holds important configuration for the Custom Taxonomy, it instructs WordPress how the Taxonomy should work.

Take a look at [register\_taxonomy()](https://developer.wordpress.org/reference/functions/register_taxonomy/) function for a full list of accepted parameters and what each of these do.

### [Summary](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#summary)

With our Courses Taxonomy example, WordPress will automatically create an archive page and child pages for the `course` Taxonomy.

The archive page will be at `/course/` with child pages spawning under it using the Term’s slug ( `/course/%%term-slug%%/`).

## [Using Your Taxonomy](https://developer.wordpress.org/plugins/taxonomies/working-with-custom-taxonomies/\#using-your-taxonomy)

WordPress has **many** functions for interacting with your Custom Taxonomy and the Terms within it.

Here are some examples:

- `the_terms`: Takes a Taxonomy argument and renders the terms in a list.
- `wp_tag_cloud`: Takes a Taxonomy argument and renders a tag cloud of the terms.
- `is_taxonomy`: Allows you to determine if a given taxonomy exists.

First published

September 24, 2014

Last updated

November 17, 2022

[PreviousTerm Splitting (WordPress 4.2)Previous: Term Splitting (WordPress 4.2)](https://developer.wordpress.org/plugins/taxonomies/split-terms-wp-4-2/)

[NextUsersNext: Users](https://developer.wordpress.org/plugins/users/)

Notifications