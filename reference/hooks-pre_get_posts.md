---
url: https://developer.wordpress.org/reference/hooks/pre_get_posts
scraped_at: 2025-10-20T03:41:40.431Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/hooks/pre_get_posts/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

pre\_get\_posts


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)[WP\_Query::get\_posts](https://developer.wordpress.org/reference/classes/wp_query/get_posts/)pre\_get\_posts

Search

# do\_action\_ref\_array( ‘pre\_get\_posts’, WP\_Query$query )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/pre_get_posts/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/pre_get_posts/#parameters)
- [More Information](https://developer.wordpress.org/reference/hooks/pre_get_posts/#more-information)
  - [Targeting the right query](https://developer.wordpress.org/reference/hooks/pre_get_posts/#targeting-the-right-query)
  - [Default main query arguments](https://developer.wordpress.org/reference/hooks/pre_get_posts/#default-main-query-arguments)
  - [A Warning About Conditional Functions](https://developer.wordpress.org/reference/hooks/pre_get_posts/#a-warning-about-conditional-functions)
  - [Offsets & Pagination](https://developer.wordpress.org/reference/hooks/pre_get_posts/#offsets-pagination)
  - [Basic Examples](https://developer.wordpress.org/reference/hooks/pre_get_posts/#basic-examples)
- [Source](https://developer.wordpress.org/reference/hooks/pre_get_posts/#source)
- [Related](https://developer.wordpress.org/reference/hooks/pre_get_posts/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/pre_get_posts/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/pre_get_posts/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/pre_get_posts/#wp--skip-link--target)

Fires after the query variable object is created, but before the actual query is run.

## [Description](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#description)

Note: If using conditional tags, use the method versions within the passed instance (e.g. $this->is\_main\_query() instead of [is\_main\_query()](https://developer.wordpress.org/reference/functions/is_main_query/) ). This is because the functions like [is\_main\_query()](https://developer.wordpress.org/reference/functions/is_main_query/) test against the global $wp\_query instance, not the passed one.

## [Parameters](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#parameters)

`$query` [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/)

The [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) instance (passed by reference).

## [More Information](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#more-information)

### [Targeting the right query](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#targeting-the-right-query)

Be aware of the queries you are changing when using the `pre_get_posts` action. Make use of [conditional tags](https://developer.wordpress.org/themes/basics/conditional-tags/) to target the right query. For example, its recommended to use the the [is\_admin()](https://developer.wordpress.org/reference/functions/is_admin/) conditional to **not** change queries in the admin screens. With the `$query->is_main_query()` conditional from the query object you can target the main query of a page request. The main query is used by the primary [post loop](https://developer.wordpress.org/themes/basics/the-loop/) that displays the main content for a post, page or archive. Without these conditionals you could unintentionally be changing the query for custom loops in sidebars, footers, or elsewhere.

Example targeting the main query for category archives:

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

```php
function target_main_category_query_with_conditional_tags( $query ) {
if ( ! is_admin() && $query->is_main_query() ) {
// Not a query for an admin page.
// It's the main query for a front end page of your site.

if ( is_category() ) {
// It's the main query for a category archive.

// Let's change the query for category archives.
$query->set( 'posts_per_page', 15 );
}
}
}
add_action( 'pre_get_posts', 'target_main_category_query_with_conditional_tags' );
```

### [Default main query arguments](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#default-main-query-arguments)

The _main query_ (object) already has some default properties set depending on the page request. For example, for single posts the `$query->is_single` property is set to true. This means you can’t simply change a _single post or page query_ into an _archive of posts query_ (or the other way around). To achieve this you’ll have to reset these properties in the query object itself. Unless you are intimately familiar with these settings and are willing to coordinate them yourself, it’s suggested that you replace the main query by using [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) in the page.php or single.php (child) [theme template files](https://developer.wordpress.org/themes/template-files-section/).

### [A Warning About Conditional Functions](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#a-warning-about-conditional-functions)

`pre_get_posts` runs **before** [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/ "Class Reference/WP Query") has been set up. Some [template tags](https://developer.wordpress.org/themes/basics/template-tags/) and conditional functions that rely on [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) will not work. For example, `[is\_front\_page()](https://developer.wordpress.org/reference/functions/is_front_page/)` will **not** work, although `[is\_home()](https://developer.wordpress.org/reference/functions/is_home/ "Function Reference/is home")` _will_ work. In such cases, you will need to work directly with the query vars, which are passed to the `pre_get_posts` hook as an argument ( `$query` in examples on this page).

### [Offsets & Pagination](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#offsets-pagination)

Using the offset argument in **any** WordPress query can break pagination. If you need to use offset and preserve pagination, please keep in mind that you will need to handle pagination manually. Read the codex article [Making Custom Queries using Offset and Pagination](https://codex.wordpress.org/Making_Custom_Queries_using_Offset_and_Pagination "Making Custom Queries using Offset and Pagination") for more information.

### [Basic Examples](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#basic-examples)

#### [Exclude Single Posts by ID From Home Page](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#exclude-single-posts-by-id-from-home-page)

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

```php
function exclude_single_posts_home($query) {
if ( $query->is_home() && $query->is_main_query() ) {
$query->set( 'post__not_in', array( 7, 11 ) );
}
}
add_action( 'pre_get_posts', 'exclude_single_posts_home' );
```

#### [Exclude Pages from Search Results](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#exclude-pages-from-search-results)

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

```php
function search_filter($query) {
if ( ! is_admin() && $query->is_main_query() ) {
if ( $query->is_search ) {
$query->set( 'post_type', 'post' );
}
}
}
add_action( 'pre_get_posts', 'search_filter' );
```

#### [Only Display Search Results After Specific Date](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#only-display-search-results-after-specific-date)

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

```php
function date_search_filter($query) {
if ( ! is_admin() && $query->is_main_query() ) {
if ( $query->is_search ) {
$query->set( 'date_query', array(
array(
'after' => 'May 17, 2019',
)
) );
}
}
}
add_action( 'pre_get_posts', 'date_search_filter' );
```

#### [Change the number of posts per page by post type](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#change-the-number-of-posts-per-page-by-post-type)

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

```php
function hwl_home_pagesize( $query ) {
if ( ! is_admin() && $query->is_main_query() && is_post_type_archive( 'movie' ) ) {
// Display 50 posts for a custom post type called 'movie'
$query->set( 'posts_per_page', 50 );
return;
}
}
add_action( 'pre_get_posts', 'hwl_home_pagesize', 1 );
```

## [Source](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#source)

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

```php
do_action_ref_array( 'pre_get_posts', array( &$this ) );

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-query.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-query.php#L1910) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-query.php#L1910-L1910)

## [Related](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#related)

| Used by | Description |
| --- | --- |
| [WP\_Query::get\_posts()](https://developer.wordpress.org/reference/classes/wp_query/get_posts/) `wp-includes/class-wp-query.php` | Retrieves an array of posts based on query variables. |

## [Changelog](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#changelog)

| Version | Description |
| --- | --- |
| [2.0.0](https://developer.wordpress.org/reference/since/2.0.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/pre_get_posts/\#user-contributed-notes)

1. [Skip to note 8 content](https://developer.wordpress.org/reference/hooks/pre_get_posts/#comment-content-2571)



Example for how to universally adjust queries for an ‘event’ post type:





`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)




```php
function university_adjust_queries($query){
      if ( ! is_admin() && is_post_type_archive( 'event' ) && $query->is_main_query() ) {
           $query->set( 'meta_key', 'event_date' );
           $query->set( 'orderby', 'meta_value_num' );
           $query->set( 'order', 'ASC');
           $query->set( 'meta_query', array(
               array(
                   'key'     => 'event_date',
                   'compare' => '>=',
                   'value'   => date('Ymd'),
                   'type'    => 'numeric',
               )
           ) );
      }
}
add_action( 'pre_get_posts', 'university_adjust_queries' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_get_posts%2F%3Freplytocom%3D2571%23feedback-editor-2571)

2. [Skip to note 9 content](https://developer.wordpress.org/reference/hooks/pre_get_posts/#comment-content-2154)





`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)




```php
/**
    *
    *	The Code below will modify the main WordPress loop, before the queries fired,
    *	to only show posts in the halloween category on the home page.
    *
    */
   	function wpdocs_exclude_category( $query ) {
   		if ( $query->is_home() && $query->is_main_query() && ! is_admin() ) {
   			$query->set( 'category_name', 'halloween' );
   		}
   	}
   	add_action( 'pre_get_posts', 'wpdocs_exclude_category' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_get_posts%2F%3Freplytocom%3D2154%23feedback-editor-2154)

3. [Skip to note 10 content](https://developer.wordpress.org/reference/hooks/pre_get_posts/#comment-content-3296)



Include Custom Post Types in the homepage





`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)




```php
function add_custom_pt( $query ) {
     if ( !is_admin() && $query->is_main_query() ) {
       $query->set( 'post_type', array( 'post', 'the_custom_pt' ) );
     }
}
add_action( 'pre_get_posts', 'add_custom_pt' );
```





Include in Search Results





`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)




```php
function add_custom_pt( $query ) {
     if ( !is_admin() && $query->is_main_query() ) {
       if ( $query->is_search ) {
         $query->set( 'post_type', array( 'post', 'the_custom_pt' ) );
       }
     }
}
add_action( 'pre_get_posts', 'add_custom_pt' );
```





Replace ‘the\_custom\_pt’ with the name of your custom post type.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_get_posts%2F%3Freplytocom%3D3296%23feedback-editor-3296)

4. [Skip to note 11 content](https://developer.wordpress.org/reference/hooks/pre_get_posts/#comment-content-5534)



You can filter posts or pages from ‘Recent Posts’ or other widgets that do not contain a meta key. In this example ‘transk\_lang’ is a language meta key assigned to posts and pages.





`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)




```php
add_action( 'pre_get_posts', 'wpdocs_pre_get_posts' );

function wpdocs_pre_get_posts( $query ) {
       // avoid main query
       if ( $query->is_main_query() ) {
           return;
       }

       // avoid filtering menu items
       if ( 'nav_menu_item' === $query->query_vars['post_type'] ) {
           return;
       }

       // add meta query
       $meta_query = $query->get( 'meta_query' );
       if ( ! is_array( $meta_query ) ) {
           $meta_query = array();
       }

       $meta_query[] = array(
           'key'     => 'transk_lang',
           'value'   => get_user_locale(),
           'compare' => '==',
       );

       $query->set( 'meta_query', $meta_query );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_get_posts%2F%3Freplytocom%3D5534%23feedback-editor-5534)

5. [Skip to note 12 content](https://developer.wordpress.org/reference/hooks/pre_get_posts/#comment-content-6129)



If you want to use URL parameters to alter the search query and search for custom meta that returns a single item:


e.g. [https://site.com/?s=searchTerm&single\_custom\_meta=value](https://site.com/?s=searchTerm&single_custom_meta=value)





`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)




```php
add_action( 'pre_get_posts', 'wpdocs_url_search_modifications' );

function wpdocs_url_search_modifications( $query ) {
     if ( $query->is_search && ! is_admin() ) {
       if ( isset($_GET['single_custom_meta'] ) ) {
         $query->set( 'meta_key', 'single_custom_meta' );
         $query->set( 'meta_value', sanitize_text_field( $_GET['single_custom_meta'] ) );
       }
     }

     return $query;
}
```





If you need to use a comma-delineated list of terms to search for multiple terms with custom meta that returns an array.


e.g. [https://site.com/?s=searchTerm&multiple\_custom\_meta=valueone,valuetwo](https://site.com/?s=searchTerm&multiple_custom_meta=valueone,valuetwo)





`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)




```php
add_action( 'pre_get_posts', 'wpdocs_url_search_modifications' );

function wpdocs_url_search_modifications( $query ) {
     if ( $query->is_search && ! is_admin() ) {
       if ( isset( $_GET['multiple_custom_meta'] ) ) {
         // Make our query string an array
         $multiple_custom_meta_values = explode( ',', sanitize_text_field( $_GET['multiple_custom_meta'] ) );

         // Generate the meta query array you can change this to your liking
         $meta_query_array = array( 'relation' => 'OR' );

         // Add a query for each item in our list
         foreach ( $multiple_custom_meta_values as $key => $value ) {
           $meta_query_array[] = array(
             'key' => 'multiple_custom_meta',
             'value' => $value,
             'compare' => 'LIKE'
           );
         }

         //set the meta query
         $query->set( 'meta_query', $meta_query_array );
       }
     };

     return $query;
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_get_posts%2F%3Freplytocom%3D6129%23feedback-editor-6129)

6. [Skip to note 13 content](https://developer.wordpress.org/reference/hooks/pre_get_posts/#comment-content-6364)



This example helps you to exclude specific categories using their IDs. You can replace the IDs 1, 2, & 3 with the specific category IDs you want to exclude.





`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)

[Copy](https://developer.wordpress.org/reference/hooks/pre_get_posts/#)




```php
add_action( 'pre_get_posts', 'wpdocs_exclude_categories' );

function wpdocs_exclude_categories( $query ) {
   	if ( is_admin() ) {
   		return;
   	}

   	if ( ! $query->is_home() || ! $query->is_main_query() ) {
   		return;
   	}

   	$query->set( 'cat', '-1,-2,-3' );
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_get_posts%2F%3Freplytocom%3D6364%23feedback-editor-6364)

7. [Skip to note 14 content](https://developer.wordpress.org/reference/hooks/pre_get_posts/#comment-content-7329)



/\*\*


\\* Exclude all sticky posts from the archive.


\*


\\* @param \ [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) $query Query.


\*/


function wpdocs\_exclude\_sticky\_posts\_from\_archive( $query ) {


if ( $query->is\_main\_query() && ! [is\_admin()](https://developer.wordpress.org/reference/functions/is_admin/) && $query->is\_archive() ) {


$sticky\_posts = get\_option( ‘sticky\_posts’ );


if ( ! empty( $sticky\_posts ) ) {


$query->set( ‘post\_\_not\_in’, $sticky\_posts );


}


}


}


add\_action( ‘pre\_get\_posts’, ‘wpdocs\_exclude\_sticky\_posts\_from\_archive’ );





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_get_posts%2F%3Freplytocom%3D7329%23feedback-editor-7329)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_get_posts%2F) before being able to contribute a note or feedback.

Notifications