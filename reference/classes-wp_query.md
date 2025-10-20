---
url: https://developer.wordpress.org/reference/classes/wp_query
scraped_at: 2025-10-20T03:40:17.781Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/classes/wp_query/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

WP\_Query


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Classes](https://developer.wordpress.org/reference/classes/)WP\_Query

Search

# class WP\_Query {}

## In this article

Table of Contents

- [More Information](https://developer.wordpress.org/reference/classes/wp_query/#more-information)
- [Usage](https://developer.wordpress.org/reference/classes/wp_query/#usage)
  - [Standard Loop](https://developer.wordpress.org/reference/classes/wp_query/#standard-loop)
  - [Standard Loop (Alternate)](https://developer.wordpress.org/reference/classes/wp_query/#standard-loop-alternate)
  - [Multiple Loops](https://developer.wordpress.org/reference/classes/wp_query/#multiple-loops)
- [Properties and Methods](https://developer.wordpress.org/reference/classes/wp_query/#properties-and-methods)
  - [Properties](https://developer.wordpress.org/reference/classes/wp_query/#properties)
- [Parameters](https://developer.wordpress.org/reference/classes/wp_query/#parameters)
  - [Author Parameters](https://developer.wordpress.org/reference/classes/wp_query/#author-parameters)
  - [Category Parameters](https://developer.wordpress.org/reference/classes/wp_query/#category-parameters)
  - [Tag Parameters](https://developer.wordpress.org/reference/classes/wp_query/#tag-parameters)
  - [Taxonomy Parameters](https://developer.wordpress.org/reference/classes/wp_query/#taxonomy-parameters)
  - [Search Parameters](https://developer.wordpress.org/reference/classes/wp_query/#search-parameters)
  - [Post & Page Parameters](https://developer.wordpress.org/reference/classes/wp_query/#post-page-parameters)
  - [Password Parameters](https://developer.wordpress.org/reference/classes/wp_query/#password-parameters)
  - [Post Type Parameters](https://developer.wordpress.org/reference/classes/wp_query/#post-type-parameters)
  - [Status Parameters](https://developer.wordpress.org/reference/classes/wp_query/#status-parameters)
  - [Comment Parameters](https://developer.wordpress.org/reference/classes/wp_query/#comment-parameters)
  - [Pagination Parameters](https://developer.wordpress.org/reference/classes/wp_query/#pagination-parameters)
  - [Order & Orderby Parameters](https://developer.wordpress.org/reference/classes/wp_query/#order-orderby-parameters)
  - [Date Parameters](https://developer.wordpress.org/reference/classes/wp_query/#date-parameters)
  - [Custom Field (post meta) Parameters](https://developer.wordpress.org/reference/classes/wp_query/#custom-field-post-meta-parameters)
  - [Permission Parameters](https://developer.wordpress.org/reference/classes/wp_query/#permission-parameters)
  - [Mime Type Parameters](https://developer.wordpress.org/reference/classes/wp_query/#mime-type-parameters)
  - [Caching Parameters](https://developer.wordpress.org/reference/classes/wp_query/#caching-parameters)
  - [Return Fields Parameter](https://developer.wordpress.org/reference/classes/wp_query/#return-fields-parameter)
- [Methods](https://developer.wordpress.org/reference/classes/wp_query/#methods)
- [Source](https://developer.wordpress.org/reference/classes/wp_query/#source)
- [Changelog](https://developer.wordpress.org/reference/classes/wp_query/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/classes/wp_query/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/classes/wp_query/#wp--skip-link--target)

The WordPress Query class.

## [More Information](https://developer.wordpress.org/reference/classes/wp_query/\#more-information)

Most of the time you can find the information you want without actually dealing with the class internals and global variables. There are a whole bunch of functions that you can call from anywhere that will enable you to get the information you need.

There are two main scenarios you might want to use `WP_Query` in. The first is to find out what type of request WordPress is currently dealing with. The `$is_*` properties are designed to hold this information: use the [Conditional Tags](https://developer.wordpress.org/themes/basics/conditional-tags/) to interact here. This is the more common scenario to plugin writers (the second normally applies to theme writers).

The second is during [The Loop](https://developer.wordpress.org/themes/basics/the-loop/). `WP_Query` provides numerous functions for common tasks within [The Loop](https://developer.wordpress.org/themes/basics/the-loop/). To begin with, [have\_posts()](https://developer.wordpress.org/reference/functions/have_posts/) , which calls `$wp_query->have_posts()`, is called to see if there are any posts to show. If there are, a `while` loop is begun, using [have\_posts()](https://developer.wordpress.org/reference/functions/have_posts/) as the condition. This will iterate around as long as there are posts to show. In each iteration, [the\_post()](https://developer.wordpress.org/reference/functions/the_post/) , which calls `$wp_query->the_post()` is called, setting up internal variables within `$wp_query` and the global `$post` variable (which the [Template Tags](https://developer.wordpress.org/themes/basics/template-tags/) rely on), as above. These are the functions you should use when writing a theme file that needs a loop.

**Note:** If you use [the\_post()](https://developer.wordpress.org/reference/functions/the_post/) with your query, you need to run [wp\_reset\_postdata()](https://developer.wordpress.org/reference/functions/wp_reset_postdata/) afterwards to have template tags use the main query’s current post again.

**Note:** [Ticket #18408](https://core.trac.wordpress.org/ticket/18408) For querying posts in the admin, consider using [get\_posts()](https://developer.wordpress.org/reference/functions/get_posts/) as [wp\_reset\_postdata()](https://developer.wordpress.org/reference/functions/wp_reset_postdata/) might not behave as expected.

## [Usage](https://developer.wordpress.org/reference/classes/wp_query/\#usage)

### [Standard Loop](https://developer.wordpress.org/reference/classes/wp_query/\#standard-loop)

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
<?php
// The Query.
$the_query = new WP_Query( $args );

// The Loop.
if ( $the_query->have_posts() ) {
	echo '<ul>';
	while ( $the_query->have_posts() ) {
		$the_query->the_post();
		echo '<li>' . esc_html( get_the_title() ) . '</li>';
	}
	echo '</ul>';
} else {
	esc_html_e( 'Sorry, no posts matched your criteria.' );
}
// Restore original Post Data.
wp_reset_postdata();

```

* * *

### [Standard Loop (Alternate)](https://developer.wordpress.org/reference/classes/wp_query/\#standard-loop-alternate)

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
<?php
// the query.
$the_query = new WP_Query( $args ); ?>

<?php if ( $the_query->have_posts() ) : ?>
	<!-- pagination here -->

	<!-- the loop -->
	<?php
	while ( $the_query->have_posts() ) :
		$the_query->the_post();
		?>
		<?php the_title( '<h2>', '</h2>' ); ?>
	<?php endwhile; ?>
	<!-- end of the loop -->

	<!-- pagination here -->

	<?php wp_reset_postdata(); ?>

<?php else : ?>
	<p><?php esc_html_e( 'Sorry, no posts matched your criteria.' ); ?></p>
<?php endif; ?>

```

* * *

### [Multiple Loops](https://developer.wordpress.org/reference/classes/wp_query/\#multiple-loops)

If you have multiple queries, you need to perform multiple loops. Like so…

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
<?php

// The Query
$query1 = new WP_Query( $args );

// The Loop
while ( $query1->have_posts() ) {
$query1->the_post();
echo '<li>' . get_the_title() . '</li>';
}

/* Restore original Post Data
* NB: Because we are using new WP_Query we aren't stomping on the
* original $wp_query and it does not need to be reset with
* wp_reset_query(). We just need to set the post data back up with
* wp_reset_postdata().
*/
wp_reset_postdata();

/* The 2nd Query (without global var) */
$query2 = new WP_Query( $args2 );

// The 2nd Loop
while ( $query2->have_posts() ) {
$query2->the_post();
echo '<li>' . get_the_title( $query2->post->ID ) . '</li>';
}

// Restore original Post Data
wp_reset_postdata();

?>
```

## [Properties and Methods](https://developer.wordpress.org/reference/classes/wp_query/\#properties-and-methods)

This is the formal documentation of `WP_Query`. You shouldn’t alter the properties directly, but instead use the [methods (see methods list below)](https://developer.wordpress.org/reference/classes/wp_query/#methods) to interact with them.

* * *

### [Properties](https://developer.wordpress.org/reference/classes/wp_query/\#properties)

- `$query`


Holds the query string that was passed to the `$wp_query` object by WP class.
- `$query_vars`


An associative array containing the dissected `$query`: an array of the query variables and their respective values.
- `$queried_object`


Applicable if the request is a category, author, permalink or Page. Holds information on the requested category, author, post or Page.
- `$queried_object_id`


If the request is a category, author, permalink or post / page, holds the corresponding ID.
- `$posts`


Gets filled with the requested posts from the database.
- `$post_count`


The number of posts being displayed.
- `$found_posts`


The total number of posts found matching the current query parameters
- `$max_num_pages`


The total number of pages. Is the result of $found\_posts / $posts\_per\_page
- `$current_post`


(available during The Loop) Index of the post currently being displayed.
- `$post`


(available during The Loop) The post currently being displayed.
- `$is_single`, `$is_page`, `$is_archive`, `$is_preview`, `$is_date`, `$is_year`, `$is_month`, `$is_time`, `$is_author`, `$is_category`, `$is_tag`, `$is_tax`, `$is_search`, `$is_feed`, `$is_comment_feed`, `$is_trackback`, `$is_home`, `$is_404`, `$is_comments_popup`, `$is_admin`, `$is_attachment`, `$is_singular`, `$is_robots`, `$is_posts_page`, `$is_paged`


Booleans dictating what type of request this is. For example, the first three represent ‘is it a permalink?’, ‘is it a Page?’, ‘is it any type of archive page?’, respectively. See also [Conditional Tags](https://developer.wordpress.org/themes/basics/conditional-tags/).

* * *

## [Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#parameters)

### [Author Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#author-parameters)

Show posts associated with certain author.

- **`author`** ( _int_) – use author id.
- **`author_name`** ( _string_) – use ‘ `user_nicename`‘ – NOT name.
- **`author__in`** ( _array_) – use author id (available since version 3.7).
- **`author__not_in`** ( _array_) – use author id (available since version 3.7).

**Show Posts for one Author**

Display posts by author, using author id:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'author' => 123 ) );
```

Display posts by author, using author ‘ `user_nicename`‘:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'author_name' => 'rami' ) );
```

**Show Posts From Several Authors**

Display posts from several specific authors:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'author' => '2,6,17,38' ) );
```

**Exclude Posts Belonging to an Author**

Display all posts _except_ those from an author(singular) by prefixing its id with a ‘-‘ (minus) sign:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'author' => -12 ) );
```

**Multiple Author Handling**

Display posts from multiple authors:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'author__in' => array( 2, 6 ) ) );
```

You can also exclude multiple author this way:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'author__not_in' => array( 2, 6 ) ) );
```

* * *

### [Category Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#category-parameters)

Show posts associated with certain categories.

- **`cat`** ( _int_) – use category id.
- **`category_name`** ( _string_) – use category slug.
- **`category__and`** ( _array_) – use category id.
- **`category__in`** ( _array_) – use category id.
- **`category__not_in`** ( _array_) – use category id.

**Display posts that have one category (and any children of that category), using category id:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'cat' => 4 ) );
```

**Display posts that have this category (and any children of that category), using category slug:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'category_name' => 'staff' ) );
```

**Display posts that have this category (not children of that category), using category id:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'category__in' => 4 ) );
```

**Display posts that have several categories, using category id:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'cat' => '2,6,17,38' ) );
```

**Display posts that have these categories, using category slug:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'category_name' => 'staff,news' ) );
```

**Display posts that have “all” of these categories:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'category_name' => 'staff+news' ) );
```

**Display all posts _except_ those from a category by prefixing its id with a ‘-‘ (minus) sign.**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'cat' => '-12,-34,-56' ) );
```

**Display posts that are in multiple categories. This shows posts that are in both categories 2 and 6:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'category__and' => array( 2, 6 ) ) );
```

To display posts from either category 2 OR 6, you could use `cat` as mentioned above, or by using `category__in` (note this does not show posts from any children of these categories):

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'category__in' => array( 2, 6 ) ) );
```

You can also exclude multiple categories this way:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'category__not_in' => array( 2, 6 ) ) );
```

* * *

### [Tag Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#tag-parameters)

Show posts associated with certain tags.

- **`tag`** ( _string_) – use tag slug.
- **`tag_id`** ( _int_) – use tag id.
- **`tag__and`** ( _array_) – use tag ids.
- **`tag__in`** ( _array_) – use tag ids.
- **`tag__not_in`** ( _array_) – use tag ids.
- **`tag_slug__and`** ( _array_) – use tag slugs.
- **`tag_slug__in`** ( _array_) – use tag slugs.

**Display posts that have one tag, using tag slug:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'tag' => 'cooking' ) );
```

**Display posts that have this tag, using tag id:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'tag_id' => 13 ) );
```

**Display posts that have “either” of these tags:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'tag' => 'bread,baking' ) );
```

**Display posts that have “all” of these tags:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'tag' => 'bread+baking+recipe' ) );
```

**Display posts that are tagged with both tag id 37 and tag id 47:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'tag__and' => array( 37, 47 ) ) );
```

To display posts from either tag id 37 or 47, you could use `tag` as mentioned above, or explicitly specify by using `tag__in`:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'tag__in' => array( 37, 47 ) ) );
```

**Display posts that do not have any of the two tag ids 37 and 47:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'tag__not_in' => array( 37, 47 ) ) );
```

The `tag_slug__in` and `tag_slug__and` behave much the same, except match against the tag’s slug.

* * *

### [Taxonomy Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#taxonomy-parameters)

Show posts associated with certain taxonomy.

- **`{tax}`** ( _string_) – use taxonomy slug. ( **Deprecated** since version 3.1 in favor of ‘ `tax_query`‘).
- **`tax_query`** ( _array_) – use taxonomy parameters (available since version 3.1).

  - **`relation`** ( _string_) – The logical relationship between each inner taxonomy array when there is more than one. Possible values are ‘AND’, ‘OR’. Do not use with a single inner taxonomy array.

    - **`taxonomy`** ( _string_) – Taxonomy.
    - **`field`** ( _string_) – Select taxonomy term by. Possible values are ‘term\_id’, ‘name’, ‘slug’ or ‘term\_taxonomy\_id’. Default value is ‘term\_id’.
    - **`terms`** ( _int/string/array_) – Taxonomy term(s).
    - **`include_children`** ( _boolean_) – Whether or not to include children for hierarchical taxonomies. Defaults to true.
    - **`operator`** ( _string_) – Operator to test. Possible values are ‘IN’, ‘NOT IN’, ‘AND’, ‘EXISTS’ and ‘NOT EXISTS’. Default value is ‘IN’.

**Important Note:** `tax_query` takes an **array** of tax query arguments **arrays** (it takes an array of arrays).

This construct allows you to query multiple taxonomies by using the **`relation`** parameter in the first (outer) array to describe the boolean relationship between the taxonomy arrays.

**Simple Taxonomy Query:**

Display **posts** tagged with **bob**, under **people** custom taxonomy:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'post',
'tax_query' => array(
array(
'taxonomy' => 'people',
'field' => 'slug',
'terms' => 'bob',
),
),
);
$query = new WP_Query( $args );
```

**Multiple Taxonomy Handling:**

Display **posts** from several custom taxonomies:

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'post',
'tax_query' => array(
'relation' => 'AND',
array(
'taxonomy' => 'movie_genre',
'field' => 'slug',
'terms' => array( 'action', 'comedy' ),
),
array(
'taxonomy' => 'actor',
'field' => 'term_id',
'terms' => array( 103, 115, 206 ),
'operator' => 'NOT IN',
),
),
);
$query = new WP_Query( $args );
```

Display **posts** that are in the **quotes** category OR have the **quote** post format:

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'post',
'tax_query' => array(
'relation' => 'OR',
array(
'taxonomy' => 'category',
'field' => 'slug',
'terms' => array( 'quotes' ),
),
array(
'taxonomy' => 'post_format',
'field' => 'slug',
'terms' => array( 'post-format-quote' ),
),
),
);
$query = new WP_Query( $args );
```

**Nested Taxonomy Handling:**

The `'tax_query'` clauses can be nested, to create more complex queries. Example: Display **posts** that are in the **quotes** category OR both have the **quote** post format AND are in the **wisdom** category:

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'post',
'tax_query' => array(
'relation' => 'OR',
array(
'taxonomy' => 'category',
'field' => 'slug',
'terms' => array( 'quotes' ),
),
array(
'relation' => 'AND',
array(
'taxonomy' => 'post_format',
'field' => 'slug',
'terms' => array( 'post-format-quote' ),
),
array(
'taxonomy' => 'category',
'field' => 'slug',
'terms' => array( 'wisdom' ),
),
),
),
);
$query = new WP_Query( $args );
```

* * *

### [Search Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#search-parameters)

Show posts based on a keyword search.

- **`s`** ( _string_) – Search keyword.

**Show Posts based on a keyword search**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 's' => 'keyword' ) );
```

Prepending a term with a hyphen will exclude posts matching that term. Eg, `'pillow -sofa'` will return posts containing ‘pillow’ but not ‘sofa’ (available since Version 4.4).

* * *

### [Post & Page Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#post-page-parameters)

Display content based on post and page parameters. Remember that default `post_type` is only set to display posts but not pages.

- **`p`** ( _int_) – use post id.
- **`name`** ( _string_) – use post slug.
- **`page_id`** ( _int_) – use page id.
- **`pagename`** ( _string_) – use page slug.
- **`post_parent`** ( _int_) – use page id to return only child pages. Set to 0 to return only top-level entries.
- **`post_parent__in`** ( _array_) – use post ids. Specify posts whose parent is in an array (available since version 3.6).
- **`post_parent__not_in`** ( _array_) – use post ids. Specify posts whose parent is not in an array (available since version 3.6).
- **`post__in`** ( _array_) – use post ids. Specify posts to retrieve. **ATTENTION** If you use sticky posts, they will be included (prepended!) in the posts you retrieve whether you want it or not. To suppress this behaviour use `ignore_sticky_posts`.
- **`post__not_in`** ( _array_) – use post ids. Specify post NOT to retrieve.
- **`post_name__in`** ( _array_) – use post slugs. Specify posts to retrieve (available since version 4.4).
- `title` (string) – use DB field `post_title`. Must be an exact match. Specify posts to retrieve (available since version 4.4).

**NOTE:** [Ticket #28099](https://core.trac.wordpress.org/ticket/28099): Passing an empty array to `post__in` will return `has_posts()` as true (and all posts will be returned). Logic should be used before hand to determine if `WP_Query` should be used in the event that the array being passed to `post__in` is empty.

**Display post by ID:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'p' => 7 ) );
```

**Display page by ID:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'page_id' => 7 ) );
```

**Show post/page by slug**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'name' => 'about-my-life' ) );
```

**Display page by `slug`:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'pagename' => 'contact' ) );
```

**Display posts by title:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'title' => 'Hello World!' ) );
```

Note: the title must be an **exact** match.

**Display child page using the slug of the parent and the child page, separated by a slash (e.g. ‘parent\_slug/child\_slug’):**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'pagename' => 'contact_us/canada' ) );
```

**Display child pages using parent page ID:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_parent' => 93 ) );
```

**Display only top-level pages, exclude all child pages:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_parent' => 0 ) );
```

**Display posts whose parent is in an array:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_parent__in' => array( 2, 5, 12, 14, 20 ) ) );
```

**Display only the specific posts:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_type' => 'page', 'post__in' => array( 2, 5, 12, 14, 20 ) ) );
```

**Display all posts but NOT the specified ones:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_type' => 'post', 'post__not_in' => array( 2, 5, 12, 14, 20 ) ) );
```

**Note:** you cannot combine `post__in` and `post__not_in` in the same query.

Also note that using a string containing a comma separated list will not work here. If you’re passing a variable, make sure it’s a proper array of integer values:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
// This will NOT work
$exclude_ids = '1,2,3';
$query = new WP_Query( array( 'post__not_in' => array( $exclude_ids ) ) );

// This WILL work
$exclude_ids = array( 1, 2, 3 );
$query = new WP_Query( array( 'post__not_in' => $exclude_ids ) );
```

* * *

### [Password Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#password-parameters)

Show content based on post and page parameters. Remember that default `post_type` is only set to display posts but not pages.

- **`has_password`** ( _bool_) – true for posts with passwords ; false for posts without passwords ; null for all posts with and without passwords (available since version 3.9).
- **`post_password`** ( _string_) – show posts with a particular password (available since version 3.9)

**Display only password protected posts:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'has_password' => true ) );
```

**Display only posts without passwords:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'has_password' => false ) );
```

**Display only posts with and without passwords:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'has_password' => null ) );
```

**Display posts with a particular password:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_password' => 'zxcvbn' ) );
```

* * *

### [Post Type Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#post-type-parameters)

Show posts associated with certain [type](https://developer.wordpress.org/themes/basics/post-types/).

- **`post_type`** ( _string_ / _array_) – use post types. Retrieves posts by post types, default value is ‘ `post`‘. If ‘ `tax_query`‘ is set for a query, the default value becomes ‘ `any`‘;

  - ‘ `post`‘ – a post.
  - ‘ `page`‘ – a page.
  - ‘ `revision`‘ – a revision.
  - ‘ `attachment`‘ – an attachment. Whilst the default [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) `post_status` is ‘publish’, attachments have a default `post_status` of ‘inherit’. This means no attachments will be returned unless you also explicitly set `post_status` to ‘inherit’ or ‘any’. See [Status parameters](https://developer.wordpress.org/reference/classes/wp_query/#status-parameters) section below.
  - ‘ `nav_menu_item`‘ – a navigation menu item
  - ‘ `any`‘ – retrieves any type except revisions and types with ‘exclude\_from\_search’ set to true.


    \\*\\* Custom Post Types (e.g. movies)

**Display only pages:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_type' => 'page' ) );
```

**Display ‘ `any`‘ post type (retrieves any type except revisions and types with ‘exclude\_from\_search’ set to TRUE):**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_type' => 'any' ) );
```

**Display multiple post types, including custom post types:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => array( 'post', 'page', 'movie', 'book' )
);
$query = new WP_Query( $args );
```

* * *

### [Status Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#status-parameters)

Show posts associated with certain [post status](https://wordpress.org/support/article/post-status/).

- **`post_status`** ( _string_ / _array_) – use post status. Retrieves posts by post status. Default value is ‘ `publish`‘, but if the user is logged in, ‘ `private`‘ is added. Public [custom post statuses](https://wordpress.org/support/article/post-status/#custom-status) are also included by default. And if the query is run in an admin context (administration area or AJAX call), protected statuses are added too. By default protected statuses are ‘ `future`‘, ‘ `draft`‘ and ‘ `pending`‘.

  - ‘ `publish`‘ – a published post or page.
  - ‘ `pending`‘ – post is pending review.
  - ‘ `draft`‘ – a post in draft status.
  - ‘ `auto-draft`‘ – a newly created post, with no content.
  - ‘ `future`‘ – a post to publish in the future.
  - ‘ `private`‘ – not visible to users who are not logged in.
  - ‘ `inherit`‘ – a revision. see [get\_children()](https://developer.wordpress.org/reference/functions/get_children/) .
  - ‘ `trash`‘ – post is in trashbin (available since version 2.9).
  - ‘ `any`‘ – retrieves any status except for ‘inherit’, ‘trash’ and ‘auto-draft’. Custom post statuses with ‘exclude\_from\_search’ set to true are also excluded.

**Display only posts with the ‘ `draft`‘ status:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post_status' => 'draft' ) );
```

**Display multiple post status:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_status' => array( 'pending', 'draft', 'future' )
);
$query = new WP_Query( $args );
```

**Display all attachments:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_status' => 'any',
'post_type' => 'attachment'
);
$query = new WP_Query( $args );
```

* * *

### [Comment Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#comment-parameters)

Since Version 4.9 Introduced the \`$comment\_count\` parameter. It can be either an Integer or an Array.

- **`comment_count`** ( _int_) – The amount of comments your CPT has to have ( Search operator will do a ‘=’ operation )
- **`comment_count`** ( _Array_) – If comment\_count is an array, it should have two arguments:

  - ‘ `value`‘ – The amount of comments your post has to have when comparing
  - ‘ `compare`‘ – The search operator. Possible values are ‘=’, ‘!=’, ‘>’, ‘>=’, ‘<‘, ‘<=’. Default value is ‘=’.

**Display posts with 20 comments:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'post',
'comment_count' => 20,
);
$query = new WP_Query( $args );
```

**Display posts with 25 comments or more:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'post',
'comment_count' => array(
'value' => 25,
'compare' => '>=',
)
);
$query = new WP_Query( $args );
```

* * *

### [Pagination Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#pagination-parameters)

- **`nopaging`** ( _boolean_) – show all posts or use pagination. Default value is ‘false’, use paging.
- **`posts_per_page`** ( _int_) – number of post to show per page (available since version 2.1, replaced **`showposts`** parameter). Use `'posts_per_page'=>-1` to show all posts (the `'offset'` parameter is ignored with a `-1` value). Set the ‘paged’ parameter if pagination is off after using this parameter. _Note_: if the query is in a feed, wordpress overwrites this parameter with the stored ‘posts\_per\_rss’ option. To reimpose the limit, try using the ‘ `post_limits`’ filter, or filter ‘ `pre_option_posts_per_rss`’ and return a very large number (if you want to return all posts) such as PHP constant `PHP_INT_MAX` so that on most cases all entries are outputted.
- **`posts_per_archive_page`** ( _int_) – number of posts to show per page – on archive pages only. Over-rides **`posts_per_page`** and **`showposts`** on pages where [is\_archive()](https://developer.wordpress.org/reference/functions/is_archive/) or [is\_search()](https://developer.wordpress.org/reference/functions/is_search/) would be true.
- **`offset`** ( _int_) – number of post to _displace_ or pass over. _Warning_: Setting the offset parameter overrides/ignores the paged parameter and breaks pagination. The `'offset'` parameter is ignored when `'posts_per_page'=>-1` (show all posts) is used.
- **`paged`** ( _int_) – number of page. Show the posts that would normally show up just on page X when using the “Older Entries” link.
- **`page`** ( _int_) – number of page for a static front page. Show the posts that would normally show up just on page X of a Static Front Page.
- **`ignore_sticky_posts`** ( _boolean_) – ignore post stickiness (available since version 3.1, replaced **`caller_get_posts`** parameter). `false` (default): move sticky posts to the start of the set. `true`: do not move sticky posts to the start of the set.

**Display x posts per page:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'posts_per_page' => 3 ) );
```

**Display all posts in one page:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'posts_per_page' => -1 ) );
```

**Display all posts by disabling pagination:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'nopaging' => true ) );
```

**Display posts from the 4th one:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'offset' => 3 ) );
```

**Display 5 posts per page which follow the 3 most recent posts:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'posts_per_page' => 5, 'offset' => 3 ) );
```

**Display posts from page number x:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'paged' => 6 ) );
```

**Display posts from current page:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'paged' => get_query_var( 'paged' ) ) );
```

Display posts from the current page and set the ‘paged’ parameter to 1 when the query variable is not set (first page).

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$paged = ( get_query_var('paged') ) ? get_query_var('paged') : 1;
$query = new WP_Query( array( 'paged' => $paged ) );
```

Pagination Note: Use `get_query_var('page');` if you want your query to work in a [page template](https://developer.wordpress.org/themes/template-files-section/page-template-files/) that you’ve set as your [static front page](https://wordpress.org/support/article/creating-a-static-front-page/). The query variable ‘page’ also holds the pagenumber for a single paginated Post or Page that includes the `<!--nextpage-->` quicktag in the post content.

**Display posts from current page on a [static front page](https://wordpress.org/support/article/creating-a-static-front-page/):**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$paged = ( get_query_var('page') ) ? get_query_var('page') : 1;
$query = new WP_Query( array( 'paged' => $paged ) );
```

**Display just the first sticky post:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$sticky = get_option( 'sticky_posts' );
$query = new WP_Query( array( 'p' => $sticky[0] ) );
```

**Display just the first sticky post, if none return the last post published:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'posts_per_page' => 1,
'post__in' => get_option( 'sticky_posts' ),
'ignore_sticky_posts' => 1,
);
$query = new WP_Query( $args );
```

**Display just the first sticky post, if none return nothing:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$sticky = get_option( 'sticky_posts' );
$args = array(
'posts_per_page' => 1,
'post__in' => $sticky,
'ignore_sticky_posts' => 1,
);
$query = new WP_Query( $args );
if ( $sticky[0] ) {
// insert here your stuff...
}
```

**Exclude all sticky posts from the query:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'post__not_in' => get_option( 'sticky_posts' ) ) );
```

**Exclude sticky posts from a category:**

Return ALL posts within the category, but don’t show sticky posts at the top. The ‘sticky posts’ will still show in their natural position (e.g. by date):

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'ignore_sticky_posts' => 1, 'posts_per_page' => 3, 'cat' => 6 );
```

**Exclude sticky posts from a category:**

Return posts within the category, but exclude sticky posts completely, and adhere to paging rules:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$paged = get_query_var( 'paged' ) ? get_query_var( 'paged' ) : 1;
$sticky = get_option( 'sticky_posts' );
$args = array(
'cat' => 3,
'ignore_sticky_posts' => 1,
'post__not_in' => $sticky,
'paged' => $paged,
);
$query = new WP_Query( $args );
```

* * *

### [Order & Orderby Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#order-orderby-parameters)

Sort retrieved posts.

- **`order`** ( _string \| array_) – Designates the ascending or descending order of the ‘ `orderby`‘ parameter. Defaults to ‘DESC’. An array can be used for multiple order/orderby sets.

  - ‘ `ASC`‘ – ascending order from lowest to highest values (1, 2, 3; a, b, c).
  - ‘ `DESC`‘ – descending order from highest to lowest values (3, 2, 1; c, b, a).
- **`orderby`** ( _string \| array_) – Sort retrieved posts by parameter. Defaults to ‘date (post\_date)’. One or more options can be passed.

  - ‘ `none`‘ – No order (available since version 2.8).
  - ‘ `ID`‘ – Order by post id. Note the capitalization.
  - ‘ `author`‘ – Order by author.
  - ‘ `title`‘ – Order by title.
  - ‘ `name`‘ – Order by post name (post slug).
  - ‘ `type`‘ – Order by post type (available since version 4.0).
  - ‘ `date`‘ – Order by date.
  - ‘ `modified`‘ – Order by last modified date.
  - ‘ `parent`‘ – Order by post/page parent id.
  - ‘ `rand`‘ – Random order.
  - ‘ `comment_count`‘ – Order by number of comments (available since version 2.9).
  - ‘ `relevance`‘ – Order by search terms in the following order: First, whether the entire sentence is matched. Second, if all the search terms are within the titles. Third, if any of the search terms appear in the titles. And, fourth, if the full sentence appears in the contents.
  - ‘ `menu_order`‘ – Order by Page Order. Used most often for pages ( _Order_ field in the Edit Page Attributes box) and for attachments (the integer fields in the Insert / Upload Media Gallery dialog), but could be used for any post type with distinct ‘ `menu_order`‘ values (they all default to 0).
  - ‘ `meta_value`‘ – Note that a ‘ `meta_key=keyname`‘ must also be present in the query. Note also that the sorting will be alphabetical which is fine for strings (i.e. words), but can be unexpected for numbers (e.g. 1, 3, 34, 4, 56, 6, etc, rather than 1, 3, 4, 6, 34, 56 as you might naturally expect). Use ‘ `meta_value_num`‘ instead for numeric values. You may also specify ‘ `meta_type`‘ if you want to cast the meta value as a specific type. Possible values are ‘NUMERIC’, ‘BINARY’, ‘CHAR’, ‘DATE’, ‘DATETIME’, ‘DECIMAL’, ‘SIGNED’, ‘TIME’, ‘UNSIGNED’, same as in ‘ `$meta_query`‘.
  - ‘ `meta_value_num`‘ – Order by numeric meta value (available since version 2.8). Also note that a ‘ `meta_key=keyname`‘ must also be present in the query. This value allows for numerical sorting as noted above in ‘ `meta_value`‘.
  - ‘ `post__in`‘ – Preserve post ID order given in the post\_\_in array (available since version 3.5). Note – the value of the order parameter does not change the resulting sort order.
  - ‘ `post_name__in`‘ – Preserve post slug order given in the ‘post\_name\_\_in’ array (available since Version 4.6). Note – the value of the order parameter does not change the resulting sort order.
  - ‘ `post_parent__in`‘ -Preserve post parent order given in the ‘post\_parent\_\_in’ array (available since Version 4.6). Note – the value of the order parameter does not change the resulting sort order.

**Display posts sorted by post ‘title’ in a descending order:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'orderby' => 'title',
'order' => 'DESC',
);
$query = new WP_Query( $args );
```

**Display posts sorted by ‘menu\_order’ with a fallback to post ‘title’, in a descending order:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'orderby' => 'menu_order title',
'order' => 'DESC',
);
$query = new WP_Query( $args );
```

**Display one random post:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'orderby' => 'rand',
'posts_per_page' => '1',
);
$query = new WP_Query( $args );
```

**Display posts ordered by comment count (popularity):**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'orderby' => 'comment_count'
);
$query = new WP_Query( $args );
```

**Display posts with ‘Product’ type ordered by ‘Price’ custom field:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'product',
'orderby' => 'meta_value_num',
'meta_key' => 'price',
);
$query = new WP_Query( $args );
```

**Display pages ordered by ‘title’ and ‘menu\_order’. (title is dominant):**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'page',
'orderby' => 'title menu_order',
'order' => 'ASC',
);
$query = new WP_Query( $args );
```

**Display pages ordered by ‘title’ and ‘menu\_order’ with different sort orders (ASC/DESC) (available since version 4.0):**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'orderby' => array( 'title' => 'DESC', 'menu_order' => 'ASC' )
);
$query = new WP_Query( $args );
```

Related article: [A more powerful ORDER BY in WordPress 4.0](https://make.wordpress.org/core/2014/08/29/a-more-powerful-order-by-in-wordpress-4-0/).

**Mulitiple orderby/order pairs**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'orderby' => array( 'meta_value_num' => 'DESC', 'title' => 'ASC' ),
'meta_key' => 'age'
);
$query = new WP_Query( $args );
```

**‘orderby’ with ‘meta\_value’ and custom post type**

Display posts of type ‘my\_custom\_post\_type’, ordered by ‘age’, and filtered to show only ages 3 and 4 (using meta\_query).

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'my_custom_post_type',
'meta_key' => 'age',
'orderby' => 'meta_value_num',
'order' => 'ASC',
'meta_query' => array(
array(
'key' => 'age',
'value' => array( 3, 4 ),
'compare' => 'IN',
),
),
);
$query = new WP_Query( $args );
```

**‘orderby’ with multiple ‘meta\_key’s**

If you wish to order by two different pieces of postmeta (for example, City first and State second), you need to combine and link your meta query to your orderby array using ‘named meta queries’. See the example below:

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$q = new WP_Query( array(
'meta_query' => array(
'relation' => 'AND',
'state_clause' => array(
'key' => 'state',
'value' => 'Wisconsin',
),
'city_clause' => array(
'key' => 'city',
'compare' => 'EXISTS',
),
),
'orderby' => array(
'city_clause' => 'ASC',
'state_clause' => 'DESC',
),
) );
```

(props to cybmeta on WPSE for [this example](http://wordpress.stackexchange.com/a/246358/3687)).

* * *

### [Date Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#date-parameters)

Show posts associated with a certain time and date period.

- **`year`** ( _int_) – 4 digit year (e.g. 2011).
- **`monthnum`** ( _int_) – Month number (from 1 to 12).
- **`w`** ( _int_) – Week of the year (from 0 to 53). Uses [MySQL WEEK command](http://dev.mysql.com/doc/refman/5.1/en/date-and-time-functions.html#function_week). The mode is dependent on the “start\_of\_week” option.
- **`day`** ( _int_) – Day of the month (from 1 to 31).
- **`hour`** ( _int_) – Hour (from 0 to 23).
- **`minute`** ( _int_) – Minute (from 0 to 60).
- **`second`** ( _int_) – Second (0 to 60).
- **`m`** ( _int_) – YearMonth (For e.g.: **`201307`**).
- **`date_query`** ( _array_) – Date parameters (available since version 3.7).

  - **`year`** ( _int_) – 4 digit year (e.g. 2011).
  - **`month`** ( _int_) – Month number (from 1 to 12).
  - **`week`** ( _int_) – Week of the year (from 0 to 53).
  - **`day`** ( _int_) – Day of the month (from 1 to 31).
  - **`hour`** ( _int_) – Hour (from 0 to 23).
  - **`minute`** ( _int_) – Minute (from 0 to 59).
  - **`second`** ( _int_) – Second (0 to 59).
  - **`after`** ( _string/array_) – Date to retrieve posts after. Accepts `[strtotime()](http://php.net/strtotime)`-compatible string, or array of ‘year’, ‘month’, ‘day’ values:

    - **`year`** ( _string_) Accepts any four-digit year. Default is empty.
    - **`month`** ( _string_) The month of the year. Accepts numbers 1-12. Default: 12.
    - **`day`** ( _string_) The day of the month. Accepts numbers 1-31. Default: last day of month.
  - **`before`** ( _string/array_) – Date to retrieve posts before. Accepts `[strtotime()](http://php.net/strtotime)`-compatible string, or array of ‘year’, ‘month’, ‘day’ values:

    - **`year`** ( _string_) Accepts any four-digit year. Default is empty.
    - **`month`** ( _string_) The month of the year. Accepts numbers 1-12. Default: 1.
    - **`day`** ( _string_) The day of the month. Accepts numbers 1-31. Default: 1.
  - **`inclusive`** ( _boolean_) – For after/before, whether exact value should be matched or not’.
  - **`compare`** ( _string_) – See [WP\_Date\_Query::get\_compare()](https://developer.wordpress.org/reference/classes/wp_date_query/get_compare/).
  - **`column`** ( _string_) – Posts column to query against. Default: ‘post\_date’.
  - **`relation`** ( _string_) – OR or AND, how the sub-arrays should be compared. Default: AND.

**Returns posts dated December 12, 2012:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( 'year=2012&monthnum=12&day=12' );
```

or:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'date_query' => array(
array(
'year' => 2012,
'month' => 12,
'day' => 12,
),
),
);
$query = new WP_Query( $args );
```

**Returns posts for today:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$today = getdate();
$query = new WP_Query( 'year=' . $today['year'] . '&monthnum=' . $today['mon'] . '&day=' . $today['mday'] );
```

or:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$today = getdate();
$args = array(
'date_query' => array(
array(
'year' => $today['year'],
'month' => $today['mon'],
'day' => $today['mday'],
),
),
);
$query = new WP_Query( $args );
```

**Returns posts for this week:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$week = date( 'W' );
$year = date( 'Y' );
$query = new WP_Query( 'year=' . $year . '&w=' . $week );
```

or:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'date_query' => array(
array(
'year' => date( 'Y' ),
'week' => date( 'W' ),
),
),
);
$query = new WP_Query( $args );
```

**Return posts between 9AM to 5PM on weekdays**

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'date_query' => array(
array(
'hour' => 9,
'compare' => '>=',
),
array(
'hour' => 17,
'compare' => '<=',
),
array(
'dayofweek' => array( 2, 6 ),
'compare' => 'BETWEEN',
),
),
'posts_per_page' => -1,
);
$query = new WP_Query( $args );
```

**Return posts from January 1st to February 28th**

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'date_query' => array(
array(
'after' => 'January 1st, 2013',
'before' => array(
'year' => 2013,
'month' => 2,
'day' => 28,
),
'inclusive' => true,
),
),
'posts_per_page' => -1,
);
$query = new WP_Query( $args );
```

Note that if a `[strtotime()](http://php.net/strtotime)`-compatible string with just a date was passed in the `before` parameter, this will be converted to 00:00:00 on that date. In this case, even if `inclusive` was set to true, the date would not be included in the query. If you want a before date to be inclusive, include the time as well, such as `'before' => '2013-02-28 23:59:59'`, or use the array format, which is adjusted automatically if `inclusive` is set.

**Return posts made over a year ago but modified in the past month**

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'date_query' => array(
array(
'column' => 'post_date_gmt',
'before' => '1 year ago',
),
array(
'column' => 'post_modified_gmt',
'after' => '1 month ago',
),
),
'posts_per_page' => -1,
);
$query = new WP_Query( $args );
```

The `'date_query'` clauses can be nested, in order to construct complex queries. See [Taxonomy Parameters](https://developer.wordpress.org/reference/classes/wp_query/#taxonomy-parameters) for details on the syntax.

* * *

### [Custom Field (post meta) Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#custom-field-post-meta-parameters)

Show posts associated with a certain custom field.

This part of the query is parsed by [WP\_Meta\_Query](https://developer.wordpress.org/reference/classes/wp_meta_query/), so check the docs for it as well in case this list of arguments isn’t up to date.

- **`meta_key`** ( _string_) – Custom field key.
- **`meta_value`** ( _string_) – Custom field value.
- **`meta_compare`** ( _string_) – Operator to test the ‘ `meta_value`‘. Possible values are ‘=’, ‘!=’, ‘>’, ‘>=’, ‘<‘, ‘<=’, ‘LIKE’, ‘NOT LIKE’, ‘IN’, ‘NOT IN’, ‘BETWEEN’, ‘NOT BETWEEN’, ‘NOT EXISTS’, ‘REGEXP’, ‘NOT REGEXP’ or ‘RLIKE’. Default value is ‘=’.
- **`meta_query`** ( _array_) – Custom field parameters (available since version 3.1).

  - **`relation`** ( _string_) – The logical relationship between each inner meta\_query array when there is more than one. Possible values are ‘AND’, ‘OR’. Do not use with a single inner meta\_query array.

`meta_query` also contains one or more arrays with the following keys:

- **`key`** ( _string_) – Custom field key.
- **`value`** ( _string_ \| _array_) – Custom field value. It can be an array only when `compare` is `'IN'`, `'NOT IN'`, `'BETWEEN'`, or `'NOT BETWEEN'`. You don’t have to specify a value when using the `'EXISTS'` or `'NOT EXISTS'` comparisons in WordPress 3.9 and up.


( **Note:** Due to [bug #23268](https://core.trac.wordpress.org/ticket/23268), `value` is required for `NOT EXISTS` comparisons to work correctly prior to 3.9. You must supply _some_ string for the `value` parameter. An empty string or NULL will NOT work. However, any other string will do the trick and will NOT show up in your SQL when using `NOT EXISTS`. Need inspiration? How about `'bug #23268'`.)
- **`compare`** ( _string_) – Operator to test. Possible values are ‘=’, ‘!=’, ‘>’, ‘>=’, ‘<‘, ‘<=’, ‘LIKE’, ‘NOT LIKE’, ‘IN’, ‘NOT IN’, ‘BETWEEN’, ‘NOT BETWEEN’, ‘EXISTS’ and ‘NOT EXISTS’. Default value is ‘=’.
- **`type`** ( _string_) – Custom field type. Possible values are ‘NUMERIC’, ‘BINARY’, ‘CHAR’, ‘DATE’, ‘DATETIME’, ‘DECIMAL’, ‘SIGNED’, ‘TIME’, ‘UNSIGNED’. Default value is ‘CHAR’.

The ‘type’ DATE works with the ‘compare’ value BETWEEN only if the date is stored at the format YYYY-MM-DD and tested with this format.

**Important Note:** `meta_query` takes an **array** of meta query arguments **arrays** (it takes an array of arrays) – you can see this in the examples below.

This construct allows you to query multiple metadatas by using the **`relation`** parameter in the first (outer) array to describe the boolean relationship between the meta queries. Accepted arguments are ‘AND’, ‘OR’. The default is ‘AND’.

**Simple Custom Field Query:**

Display posts where the custom field key is ‘color’, regardless of the custom field value:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'meta_key' => 'color' ) );
```

Display posts where the custom field value is ‘blue’, regardless of the custom field key:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$query = new WP_Query( array( 'meta_value' => 'blue' ) );
```

Display page where the custom field value is ‘blue’, regardless of the custom field key:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'meta_value' => 'blue',
'post_type' => 'page'
);
$query = new WP_Query( $args );
```

Display posts where the custom field key is ‘color’ and the custom field value is ‘blue’:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'meta_key' => 'color',
'meta_value' => 'blue'
);
$query = new WP_Query( $args );
```

Display posts where the custom field key is ‘color’ and the custom field value IS NOT ‘blue’:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'meta_key' => 'color',
'meta_value' => 'blue',
'meta_compare' => '!='
);
$query = new WP_Query( $args );
```

Display posts where the custom field key is a set date and the custom field value is now. Displays only posts which date has not passed.

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'event',
'meta_key' => 'event_date',
'meta_value' => date( "Ymd" ), // change to how "event date" is stored
'meta_compare' => '>',
);
$query = new WP_Query( $args );
```

Display ‘product'(s) where the custom field key is ‘price’ and the custom field value that is LESS THAN OR EQUAL TO 22.

_By using the ‘meta\_value’ parameter the value 99 will be considered greater than 100 as the data are stored as strings, not numbers. For number comparison use the ‘meta\_type’ argument._

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'meta_key' => 'price',
'meta_value' => '22',
'meta_compare' => '<=',
'post_type' => 'product'
);
$query = new WP_Query( $args );
```

Display posts with a custom field value of zero (0), regardless of the custom field key:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'meta_value' => '_wp_zero_value'
);
$query = new WP_Query( $args );
```

**Display posts from a single custom field:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'product',
'meta_query' => array(
array(
'key' => 'color',
'value' => 'blue',
'compare' => 'NOT LIKE',
),
),
);
$query = new WP_Query( $args );
```

(Note that meta\_query expects nested arrays, even if you only have one query.)

**Display posts from several custom fields:**

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'product',
'meta_query' => array(
array(
'key' => 'color',
'value' => 'blue',
'compare' => 'NOT LIKE',
),
array(
'key' => 'price',
'value' => array( 20, 100 ),
'type' => 'numeric',
'compare' => 'BETWEEN',
),
),
);
$query = new WP_Query( $args );
```

**Display posts that have meta key ‘color’ NOT LIKE value ‘blue’ OR meta key ‘price’ with values BETWEEN 20 and 100:**

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'product',
'meta_query' => array(
'relation' => 'OR',
array(
'key' => 'color',
'value' => 'blue',
'compare' => 'NOT LIKE',
),
array(
'key' => 'price',
'value' => array( 20, 100 ),
'type' => 'numeric',
'compare' => 'BETWEEN',
),
),
);
$query = new WP_Query( $args );
```

The `'meta_query'` clauses can be nested in order to construct complex queries. For example, show productss where **color=orange** OR **color=red&size=small** translates to the following:

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'product',
'meta_query' => array(
'relation' => 'OR',
array(
'key' => 'color',
'value' => 'orange',
'compare' => '=',
),
array(
'relation' => 'AND',
array(
'key' => 'color',
'value' => 'red',
'compare' => '=',
),
array(
'key' => 'size',
'value' => 'small',
'compare' => '=',
),
),
),
);
$query = new WP_Query( $args );
```

* * *

### [Permission Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#permission-parameters)

Show posts if user has the appropriate capability

- **`perm`** ( _string_) – User permission.

**Display published and private posts, if the user has the appropriate capability:**

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_status' => array( 'publish', 'private' ),
'perm' => 'readable',
);
$query = new WP_Query( $args );
```

* * *

### [Mime Type Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#mime-type-parameters)

Used with the attachments post type.

- **`post_mime_type`** ( _string/array_) – Allowed mime types.

**Get attachments that are _gif_ images:**

Get gif images and remember that by default the attachment’s post\_status is set to **inherit**.

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'post_type' => 'attachment',
'post_status' => 'inherit',
'post_mime_type' => 'image/gif',
);
$query = new WP_Query( $args );
```

**Get attachments that are not images:**

To exclude certain mime types you first need to get all mime types using [get\_allowed\_mime\_types()](https://developer.wordpress.org/reference/functions/get_allowed_mime_types/) and run a difference between arrays of what you want and the allowed mime types with `[array\_diff()](http://php.net/manual/en/function.array-diff.php)`.

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$unsupported_mimes = array( 'image/jpeg', 'image/gif', 'image/png', 'image/bmp', 'image/tiff', 'image/x-icon' );
$all_mimes = get_allowed_mime_types();
$accepted_mimes = array_diff( $all_mimes, $unsupported_mimes );
$args = array(
'post_type' => 'attachment',
'post_status' => 'inherit',
'post_mime_type' => $accepted_mimes,
);
$query = new WP_Query( $query_args );
```

* * *

### [Caching Parameters](https://developer.wordpress.org/reference/classes/wp_query/\#caching-parameters)

Stop the data retrieved from being added to the cache.

- **`cache_results`** ( _boolean_) – Post information cache.
- **`update_post_meta_cache`** ( _boolean_) – Post meta information cache.
- **`update_post_term_cache`** ( _boolean_) – Post term information cache.

**Show Posts without adding post information to the cache**

Display 50 posts, but don’t add post information to the cache:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'posts_per_page' => 50,
'cache_results' => false
);
$query = new WP_Query( $args );
```

**Show Posts without adding post meta information to the cache**

Display 50 posts, but don’t add post meta information to the cache:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'posts_per_page' => 50,
'update_post_meta_cache' => false
);
$query = new WP_Query( $args );
```

**Show Posts without adding post term information to the cache**

Display 50 posts, but don’t add post term information to the cache:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
$args = array(
'posts_per_page' => 50,
'update_post_term_cache' => false
);
$query = new WP_Query( $args );
```

In general usage you should not need to use these, adding to the cache is the right thing to do, however they may be useful in specific circumstances. An example of such circumstances might be when using a [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) to retrieve a list of post titles and URLs to be displayed, but in which no other information about the post will be used and the taxonomy and meta data won’t be needed. By not loading this information, you can save time from the extra unnecessary SQL queries.

**Note**: If a persistent object cache backend (such as memcached) is used, these flags are set to false by default since there is no need to update the cache every page load when a persistent cache exists.

* * *

### [Return Fields Parameter](https://developer.wordpress.org/reference/classes/wp_query/\#return-fields-parameter)

Set return values.

- **`fields`** ( _string_) – Which fields to return. There are three options:

  - **`'all'`** – Return all fields (default).
  - **`'ids'`** – Return an array of post IDs.
  - **`'id=>parent'`** – Return an array of stdClass objects with ID and post\_parent properties.

Passing anything else will return all fields (default) – an array of post objects.

## [Methods](https://developer.wordpress.org/reference/classes/wp_query/\#methods)

| Name | Description |
| --- | --- |
| [WP\_Query::\_\_call](https://developer.wordpress.org/reference/classes/wp_query/__call/) | Makes private/protected methods readable for backward compatibility. |
| [WP\_Query::\_\_construct](https://developer.wordpress.org/reference/classes/wp_query/__construct/) | Constructor. |
| [WP\_Query::\_\_get](https://developer.wordpress.org/reference/classes/wp_query/__get/) | Makes private properties readable for backward compatibility. |
| [WP\_Query::\_\_isset](https://developer.wordpress.org/reference/classes/wp_query/__isset/) | Makes private properties checkable for backward compatibility. |
| [WP\_Query::fill\_query\_vars](https://developer.wordpress.org/reference/classes/wp_query/fill_query_vars/) | Fills in the query variables, which do not exist within the parameter. |
| [WP\_Query::generate\_cache\_key](https://developer.wordpress.org/reference/classes/wp_query/generate_cache_key/) | Generates cache key. |
| [WP\_Query::generate\_postdata](https://developer.wordpress.org/reference/classes/wp_query/generate_postdata/) | Generates post data. |
| [WP\_Query::get](https://developer.wordpress.org/reference/classes/wp_query/get/) | Retrieves the value of a query variable. |
| [WP\_Query::get\_posts](https://developer.wordpress.org/reference/classes/wp_query/get_posts/) | Retrieves an array of posts based on query variables. |
| [WP\_Query::get\_queried\_object](https://developer.wordpress.org/reference/classes/wp_query/get_queried_object/) | Retrieves the currently queried object. |
| [WP\_Query::get\_queried\_object\_id](https://developer.wordpress.org/reference/classes/wp_query/get_queried_object_id/) | Retrieves the ID of the currently queried object. |
| [WP\_Query::get\_search\_stopwords](https://developer.wordpress.org/reference/classes/wp_query/get_search_stopwords/) | Retrieves stopwords used when parsing search terms. |
| [WP\_Query::have\_comments](https://developer.wordpress.org/reference/classes/wp_query/have_comments/) | Determines whether there are more comments available. |
| [WP\_Query::have\_posts](https://developer.wordpress.org/reference/classes/wp_query/have_posts/) | Determines whether there are more posts available in the loop. |
| [WP\_Query::init](https://developer.wordpress.org/reference/classes/wp_query/init/) | Initiates object properties and sets default values. |
| [WP\_Query::init\_query\_flags](https://developer.wordpress.org/reference/classes/wp_query/init_query_flags/) | Resets query flags to false. |
| [WP\_Query::is\_404](https://developer.wordpress.org/reference/classes/wp_query/is_404/) | Determines whether the query is a 404 (returns no results). |
| [WP\_Query::is\_archive](https://developer.wordpress.org/reference/classes/wp_query/is_archive/) | Determines whether the query is for an existing archive page. |
| [WP\_Query::is\_attachment](https://developer.wordpress.org/reference/classes/wp_query/is_attachment/) | Determines whether the query is for an existing attachment page. |
| [WP\_Query::is\_author](https://developer.wordpress.org/reference/classes/wp_query/is_author/) | Determines whether the query is for an existing author archive page. |
| [WP\_Query::is\_category](https://developer.wordpress.org/reference/classes/wp_query/is_category/) | Determines whether the query is for an existing category archive page. |
| [WP\_Query::is\_comment\_feed](https://developer.wordpress.org/reference/classes/wp_query/is_comment_feed/) | Determines whether the query is for a comments feed. |
| [WP\_Query::is\_comments\_popup](https://developer.wordpress.org/reference/classes/wp_query/is_comments_popup/) | Determines whether the current URL is within the comments popup window. — deprecated |
| [WP\_Query::is\_date](https://developer.wordpress.org/reference/classes/wp_query/is_date/) | Determines whether the query is for an existing date archive. |
| [WP\_Query::is\_day](https://developer.wordpress.org/reference/classes/wp_query/is_day/) | Determines whether the query is for an existing day archive. |
| [WP\_Query::is\_embed](https://developer.wordpress.org/reference/classes/wp_query/is_embed/) | Determines whether the query is for an embedded post. |
| [WP\_Query::is\_favicon](https://developer.wordpress.org/reference/classes/wp_query/is_favicon/) | Determines whether the query is for the favicon.ico file. |
| [WP\_Query::is\_feed](https://developer.wordpress.org/reference/classes/wp_query/is_feed/) | Determines whether the query is for a feed. |
| [WP\_Query::is\_front\_page](https://developer.wordpress.org/reference/classes/wp_query/is_front_page/) | Determines whether the query is for the front page of the site. |
| [WP\_Query::is\_home](https://developer.wordpress.org/reference/classes/wp_query/is_home/) | Determines whether the query is for the blog homepage. |
| [WP\_Query::is\_main\_query](https://developer.wordpress.org/reference/classes/wp_query/is_main_query/) | Determines whether the query is the main query. |
| [WP\_Query::is\_month](https://developer.wordpress.org/reference/classes/wp_query/is_month/) | Determines whether the query is for an existing month archive. |
| [WP\_Query::is\_page](https://developer.wordpress.org/reference/classes/wp_query/is_page/) | Determines whether the query is for an existing single page. |
| [WP\_Query::is\_paged](https://developer.wordpress.org/reference/classes/wp_query/is_paged/) | Determines whether the query is for a paged result and not for the first page. |
| [WP\_Query::is\_post\_type\_archive](https://developer.wordpress.org/reference/classes/wp_query/is_post_type_archive/) | Determines whether the query is for an existing post type archive page. |
| [WP\_Query::is\_preview](https://developer.wordpress.org/reference/classes/wp_query/is_preview/) | Determines whether the query is for a post or page preview. |
| [WP\_Query::is\_privacy\_policy](https://developer.wordpress.org/reference/classes/wp_query/is_privacy_policy/) | Determines whether the query is for the Privacy Policy page. |
| [WP\_Query::is\_robots](https://developer.wordpress.org/reference/classes/wp_query/is_robots/) | Determines whether the query is for the robots.txt file. |
| [WP\_Query::is\_search](https://developer.wordpress.org/reference/classes/wp_query/is_search/) | Determines whether the query is for a search. |
| [WP\_Query::is\_single](https://developer.wordpress.org/reference/classes/wp_query/is_single/) | Determines whether the query is for an existing single post. |
| [WP\_Query::is\_singular](https://developer.wordpress.org/reference/classes/wp_query/is_singular/) | Determines whether the query is for an existing single post of any post type (post, attachment, page, custom post types). |
| [WP\_Query::is\_tag](https://developer.wordpress.org/reference/classes/wp_query/is_tag/) | Determines whether the query is for an existing tag archive page. |
| [WP\_Query::is\_tax](https://developer.wordpress.org/reference/classes/wp_query/is_tax/) | Determines whether the query is for an existing custom taxonomy archive page. |
| [WP\_Query::is\_time](https://developer.wordpress.org/reference/classes/wp_query/is_time/) | Determines whether the query is for a specific time. |
| [WP\_Query::is\_trackback](https://developer.wordpress.org/reference/classes/wp_query/is_trackback/) | Determines whether the query is for a trackback endpoint call. |
| [WP\_Query::is\_year](https://developer.wordpress.org/reference/classes/wp_query/is_year/) | Determines whether the query is for an existing year archive. |
| [WP\_Query::lazyload\_comment\_meta](https://developer.wordpress.org/reference/classes/wp_query/lazyload_comment_meta/) | Lazyloads comment meta for comments in the loop. — deprecated |
| [WP\_Query::lazyload\_term\_meta](https://developer.wordpress.org/reference/classes/wp_query/lazyload_term_meta/) | Lazyloads term meta for posts in the loop. — deprecated |
| [WP\_Query::next\_comment](https://developer.wordpress.org/reference/classes/wp_query/next_comment/) | Iterates current comment index and returns [WP\_Comment](https://developer.wordpress.org/reference/classes/wp_comment/) object. |
| [WP\_Query::next\_post](https://developer.wordpress.org/reference/classes/wp_query/next_post/) | Sets up the next post and iterate current post index. |
| [WP\_Query::parse\_order](https://developer.wordpress.org/reference/classes/wp_query/parse_order/) | Parse an ‘order’ query variable and cast it to ASC or DESC as necessary. |
| [WP\_Query::parse\_orderby](https://developer.wordpress.org/reference/classes/wp_query/parse_orderby/) | Converts the given orderby alias (if allowed) to a properly-prefixed value. |
| [WP\_Query::parse\_query](https://developer.wordpress.org/reference/classes/wp_query/parse_query/) | Parses a query string and sets query type booleans. |
| [WP\_Query::parse\_query\_vars](https://developer.wordpress.org/reference/classes/wp_query/parse_query_vars/) | Reparses the query vars. |
| [WP\_Query::parse\_search](https://developer.wordpress.org/reference/classes/wp_query/parse_search/) | Generates SQL for the WHERE clause based on passed search terms. |
| [WP\_Query::parse\_search\_order](https://developer.wordpress.org/reference/classes/wp_query/parse_search_order/) | Generates SQL for the ORDER BY condition based on passed search terms. |
| [WP\_Query::parse\_search\_terms](https://developer.wordpress.org/reference/classes/wp_query/parse_search_terms/) | Checks if the terms are suitable for searching. |
| [WP\_Query::parse\_tax\_query](https://developer.wordpress.org/reference/classes/wp_query/parse_tax_query/) | Parses various taxonomy related query vars. |
| [WP\_Query::query](https://developer.wordpress.org/reference/classes/wp_query/query/) | Sets up the WordPress query by parsing query string. |
| [WP\_Query::reset\_postdata](https://developer.wordpress.org/reference/classes/wp_query/reset_postdata/) | After looping through a nested query, this function restores the $post global to the current post in this query. |
| [WP\_Query::rewind\_comments](https://developer.wordpress.org/reference/classes/wp_query/rewind_comments/) | Rewinds the comments, resets the comment index and comment to first. |
| [WP\_Query::rewind\_posts](https://developer.wordpress.org/reference/classes/wp_query/rewind_posts/) | Rewinds the posts and resets post index. |
| [WP\_Query::set](https://developer.wordpress.org/reference/classes/wp_query/set/) | Sets the value of a query variable. |
| [WP\_Query::set\_404](https://developer.wordpress.org/reference/classes/wp_query/set_404/) | Sets the 404 property and saves whether query is feed. |
| [WP\_Query::set\_found\_posts](https://developer.wordpress.org/reference/classes/wp_query/set_found_posts/) | Sets up the amount of found posts and the number of pages (if limit clause was used) for the current query. |
| [WP\_Query::setup\_postdata](https://developer.wordpress.org/reference/classes/wp_query/setup_postdata/) | Sets up global post data. |
| [WP\_Query::the\_comment](https://developer.wordpress.org/reference/classes/wp_query/the_comment/) | Sets up the current comment. |
| [WP\_Query::the\_post](https://developer.wordpress.org/reference/classes/wp_query/the_post/) | Sets up the current post. |

## [Source](https://developer.wordpress.org/reference/classes/wp_query/\#source)

`wp-includes/class-wp-query.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
class WP_Query {

	/**
	 * Query vars set by the user.
	 *
	 * @since 1.5.0
	 * @var array
	 */
	public $query;

	/**
	 * Query vars, after parsing.
	 *
	 * @since 1.5.0
	 * @var array
	 */
	public $query_vars = array();

	/**
	 * Taxonomy query, as passed to get_tax_sql().
	 *
	 * @since 3.1.0
	 * @var WP_Tax_Query|null A taxonomy query instance.
	 */
	public $tax_query;

	/**
	 * Metadata query container.
	 *
	 * @since 3.2.0
	 * @var WP_Meta_Query A meta query instance.
	 */
	public $meta_query = false;

	/**
	 * Date query container.
	 *
	 * @since 3.7.0
	 * @var WP_Date_Query A date query instance.
	 */
	public $date_query = false;

	/**
	 * Holds the data for a single object that is queried.
	 *
	 * Holds the contents of a post, page, category, attachment.
	 *
	 * @since 1.5.0
	 * @var WP_Term|WP_Post_Type|WP_Post|WP_User|null
	 */
	public $queried_object;

	/**
	 * The ID of the queried object.
	 *
	 * @since 1.5.0
	 * @var int
	 */
	public $queried_object_id;

	/**
	 * SQL for the database query.
	 *
	 * @since 2.0.1
	 * @var string
	 */
	public $request;

	/**
	 * Array of post objects or post IDs.
	 *
	 * @since 1.5.0
	 * @var WP_Post[]|int[]
	 */
	public $posts;

	/**
	 * The number of posts for the current query.
	 *
	 * @since 1.5.0
	 * @var int
	 */
	public $post_count = 0;

	/**
	 * Index of the current item in the loop.
	 *
	 * @since 1.5.0
	 * @var int
	 */
	public $current_post = -1;

	/**
	 * Whether the caller is before the loop.
	 *
	 * @since 6.3.0
	 * @var bool
	 */
	public $before_loop = true;

	/**
	 * Whether the loop has started and the caller is in the loop.
	 *
	 * @since 2.0.0
	 * @var bool
	 */
	public $in_the_loop = false;

	/**
	 * The current post.
	 *
	 * This property does not get populated when the `fields` argument is set to
	 * `ids` or `id=>parent`.
	 *
	 * @since 1.5.0
	 * @var WP_Post|null
	 */
	public $post;

	/**
	 * The list of comments for current post.
	 *
	 * @since 2.2.0
	 * @var WP_Comment[]
	 */
	public $comments;

	/**
	 * The number of comments for the posts.
	 *
	 * @since 2.2.0
	 * @var int
	 */
	public $comment_count = 0;

	/**
	 * The index of the comment in the comment loop.
	 *
	 * @since 2.2.0
	 * @var int
	 */
	public $current_comment = -1;

	/**
	 * Current comment object.
	 *
	 * @since 2.2.0
	 * @var WP_Comment
	 */
	public $comment;

	/**
	 * The number of found posts for the current query.
	 *
	 * If limit clause was not used, equals $post_count.
	 *
	 * @since 2.1.0
	 * @var int
	 */
	public $found_posts = 0;

	/**
	 * The number of pages.
	 *
	 * @since 2.1.0
	 * @var int
	 */
	public $max_num_pages = 0;

	/**
	 * The number of comment pages.
	 *
	 * @since 2.7.0
	 * @var int
	 */
	public $max_num_comment_pages = 0;

	/**
	 * Signifies whether the current query is for a single post.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_single = false;

	/**
	 * Signifies whether the current query is for a preview.
	 *
	 * @since 2.0.0
	 * @var bool
	 */
	public $is_preview = false;

	/**
	 * Signifies whether the current query is for a page.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_page = false;

	/**
	 * Signifies whether the current query is for an archive.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_archive = false;

	/**
	 * Signifies whether the current query is for a date archive.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_date = false;

	/**
	 * Signifies whether the current query is for a year archive.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_year = false;

	/**
	 * Signifies whether the current query is for a month archive.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_month = false;

	/**
	 * Signifies whether the current query is for a day archive.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_day = false;

	/**
	 * Signifies whether the current query is for a specific time.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_time = false;

	/**
	 * Signifies whether the current query is for an author archive.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_author = false;

	/**
	 * Signifies whether the current query is for a category archive.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_category = false;

	/**
	 * Signifies whether the current query is for a tag archive.
	 *
	 * @since 2.3.0
	 * @var bool
	 */
	public $is_tag = false;

	/**
	 * Signifies whether the current query is for a taxonomy archive.
	 *
	 * @since 2.5.0
	 * @var bool
	 */
	public $is_tax = false;

	/**
	 * Signifies whether the current query is for a search.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_search = false;

	/**
	 * Signifies whether the current query is for a feed.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_feed = false;

	/**
	 * Signifies whether the current query is for a comment feed.
	 *
	 * @since 2.2.0
	 * @var bool
	 */
	public $is_comment_feed = false;

	/**
	 * Signifies whether the current query is for trackback endpoint call.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_trackback = false;

	/**
	 * Signifies whether the current query is for the site homepage.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_home = false;

	/**
	 * Signifies whether the current query is for the Privacy Policy page.
	 *
	 * @since 5.2.0
	 * @var bool
	 */
	public $is_privacy_policy = false;

	/**
	 * Signifies whether the current query couldn't find anything.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_404 = false;

	/**
	 * Signifies whether the current query is for an embed.
	 *
	 * @since 4.4.0
	 * @var bool
	 */
	public $is_embed = false;

	/**
	 * Signifies whether the current query is for a paged result and not for the first page.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_paged = false;

	/**
	 * Signifies whether the current query is for an administrative interface page.
	 *
	 * @since 1.5.0
	 * @var bool
	 */
	public $is_admin = false;

	/**
	 * Signifies whether the current query is for an attachment page.
	 *
	 * @since 2.0.0
	 * @var bool
	 */
	public $is_attachment = false;

	/**
	 * Signifies whether the current query is for an existing single post of any post type
	 * (post, attachment, page, custom post types).
	 *
	 * @since 2.1.0
	 * @var bool
	 */
	public $is_singular = false;

	/**
	 * Signifies whether the current query is for the robots.txt file.
	 *
	 * @since 2.1.0
	 * @var bool
	 */
	public $is_robots = false;

	/**
	 * Signifies whether the current query is for the favicon.ico file.
	 *
	 * @since 5.4.0
	 * @var bool
	 */
	public $is_favicon = false;

	/**
	 * Signifies whether the current query is for the page_for_posts page.
	 *
	 * Basically, the homepage if the option isn't set for the static homepage.
	 *
	 * @since 2.1.0
	 * @var bool
	 */
	public $is_posts_page = false;

	/**
	 * Signifies whether the current query is for a post type archive.
	 *
	 * @since 3.1.0
	 * @var bool
	 */
	public $is_post_type_archive = false;

	/**
	 * Stores the ->query_vars state like md5(serialize( $this->query_vars ) ) so we know
	 * whether we have to re-parse because something has changed
	 *
	 * @since 3.1.0
	 * @var bool|string
	 */
	private $query_vars_hash = false;

	/**
	 * Whether query vars have changed since the initial parse_query() call. Used to catch modifications to query vars made
	 * via pre_get_posts hooks.
	 *
	 * @since 3.1.1
	 * @var bool
	 */
	private $query_vars_changed = true;

	/**
	 * Set if post thumbnails are cached
	 *
	 * @since 3.2.0
	 * @var bool
	 */
	public $thumbnails_cached = false;

	/**
	 * Controls whether an attachment query should include filenames or not.
	 *
	 * @since 6.0.3
	 * @var bool
	 */
	protected $allow_query_attachment_by_filename = false;

	/**
	 * Cached list of search stopwords.
	 *
	 * @since 3.7.0
	 * @var array
	 */
	private $stopwords;

	private $compat_fields = array( 'query_vars_hash', 'query_vars_changed' );

	private $compat_methods = array( 'init_query_flags', 'parse_tax_query' );

	/**
	 * The cache key generated by the query.
	 *
	 * The cache key is generated by the method ::generate_cache_key() after the
	 * query has been normalized.
	 *
	 * @since 6.8.0
	 * @var string
	 */
	private $query_cache_key = '';

	/**
	 * Resets query flags to false.
	 *
	 * The query flags are what page info WordPress was able to figure out.
	 *
	 * @since 2.0.0
	 */
	private function init_query_flags() {
		$this->is_single            = false;
		$this->is_preview           = false;
		$this->is_page              = false;
		$this->is_archive           = false;
		$this->is_date              = false;
		$this->is_year              = false;
		$this->is_month             = false;
		$this->is_day               = false;
		$this->is_time              = false;
		$this->is_author            = false;
		$this->is_category          = false;
		$this->is_tag               = false;
		$this->is_tax               = false;
		$this->is_search            = false;
		$this->is_feed              = false;
		$this->is_comment_feed      = false;
		$this->is_trackback         = false;
		$this->is_home              = false;
		$this->is_privacy_policy    = false;
		$this->is_404               = false;
		$this->is_paged             = false;
		$this->is_admin             = false;
		$this->is_attachment        = false;
		$this->is_singular          = false;
		$this->is_robots            = false;
		$this->is_favicon           = false;
		$this->is_posts_page        = false;
		$this->is_post_type_archive = false;
	}

	/**
	 * Initiates object properties and sets default values.
	 *
	 * @since 1.5.0
	 */
	public function init() {
		unset( $this->posts );
		unset( $this->query );
		$this->query_vars = array();
		unset( $this->queried_object );
		unset( $this->queried_object_id );
		$this->post_count   = 0;
		$this->current_post = -1;
		$this->in_the_loop  = false;
		$this->before_loop  = true;
		unset( $this->request );
		unset( $this->post );
		unset( $this->comments );
		unset( $this->comment );
		$this->comment_count         = 0;
		$this->current_comment       = -1;
		$this->found_posts           = 0;
		$this->max_num_pages         = 0;
		$this->max_num_comment_pages = 0;

		$this->init_query_flags();
	}

	/**
	 * Reparses the query vars.
	 *
	 * @since 1.5.0
	 */
	public function parse_query_vars() {
		$this->parse_query();
	}

	/**
	 * Fills in the query variables, which do not exist within the parameter.
	 *
	 * @since 2.1.0
	 * @since 4.5.0 Removed the `comments_popup` public query variable.
	 *
	 * @param array $query_vars Defined query variables.
	 * @return array Complete query variables with undefined ones filled in empty.
	 */
	public function fill_query_vars( $query_vars ) {
		$keys = array(
			'error',
			'm',
			'p',
			'post_parent',
			'subpost',
			'subpost_id',
			'attachment',
			'attachment_id',
			'name',
			'pagename',
			'page_id',
			'second',
			'minute',
			'hour',
			'day',
			'monthnum',
			'year',
			'w',
			'category_name',
			'tag',
			'cat',
			'tag_id',
			'author',
			'author_name',
			'feed',
			'tb',
			'paged',
			'meta_key',
			'meta_value',
			'preview',
			's',
			'sentence',
			'title',
			'fields',
			'menu_order',
			'embed',
		);

		foreach ( $keys as $key ) {
			if ( ! isset( $query_vars[ $key ] ) ) {
				$query_vars[ $key ] = '';
			}
		}

		$array_keys = array(
			'category__in',
			'category__not_in',
			'category__and',
			'post__in',
			'post__not_in',
			'post_name__in',
			'tag__in',
			'tag__not_in',
			'tag__and',
			'tag_slug__in',
			'tag_slug__and',
			'post_parent__in',
			'post_parent__not_in',
			'author__in',
			'author__not_in',
			'search_columns',
		);

		foreach ( $array_keys as $key ) {
			if ( ! isset( $query_vars[ $key ] ) ) {
				$query_vars[ $key ] = array();
			}
		}

		return $query_vars;
	}

	/**
	 * Parses a query string and sets query type booleans.
	 *
	 * @since 1.5.0
	 * @since 4.2.0 Introduced the ability to order by specific clauses of a `$meta_query`, by passing the clause's
	 *              array key to `$orderby`.
	 * @since 4.4.0 Introduced `$post_name__in` and `$title` parameters. `$s` was updated to support excluded
	 *              search terms, by prepending a hyphen.
	 * @since 4.5.0 Removed the `$comments_popup` parameter.
	 *              Introduced the `$comment_status` and `$ping_status` parameters.
	 *              Introduced `RAND(x)` syntax for `$orderby`, which allows an integer seed value to random sorts.
	 * @since 4.6.0 Added 'post_name__in' support for `$orderby`. Introduced the `$lazy_load_term_meta` argument.
	 * @since 4.9.0 Introduced the `$comment_count` parameter.
	 * @since 5.1.0 Introduced the `$meta_compare_key` parameter.
	 * @since 5.3.0 Introduced the `$meta_type_key` parameter.
	 * @since 6.1.0 Introduced the `$update_menu_item_cache` parameter.
	 * @since 6.2.0 Introduced the `$search_columns` parameter.
	 *
	 * @param string|array $query {
	 *     Optional. Array or string of Query parameters.
	 *
	 *     @type int             $attachment_id          Attachment post ID. Used for 'attachment' post_type.
	 *     @type int|string      $author                 Author ID, or comma-separated list of IDs.
	 *     @type string          $author_name            User 'user_nicename'.
	 *     @type int[]           $author__in             An array of author IDs to query from.
	 *     @type int[]           $author__not_in         An array of author IDs not to query from.
	 *     @type bool            $cache_results          Whether to cache post information. Default true.
	 *     @type int|string      $cat                    Category ID or comma-separated list of IDs (this or any children).
	 *     @type int[]           $category__and          An array of category IDs (AND in).
	 *     @type int[]           $category__in           An array of category IDs (OR in, no children).
	 *     @type int[]           $category__not_in       An array of category IDs (NOT in).
	 *     @type string          $category_name          Use category slug (not name, this or any children).
	 *     @type array|int       $comment_count          Filter results by comment count. Provide an integer to match
	 *                                                   comment count exactly. Provide an array with integer 'value'
	 *                                                   and 'compare' operator ('=', '!=', '>', '>=', '<', '<=' ) to
	 *                                                   compare against comment_count in a specific way.
	 *     @type string          $comment_status         Comment status.
	 *     @type int             $comments_per_page      The number of comments to return per page.
	 *                                                   Default 'comments_per_page' option.
	 *     @type array           $date_query             An associative array of WP_Date_Query arguments.
	 *                                                   See WP_Date_Query::__construct().
	 *     @type int             $day                    Day of the month. Default empty. Accepts numbers 1-31.
	 *     @type bool            $exact                  Whether to search by exact keyword. Default false.
	 *     @type string          $fields                 Post fields to query for. Accepts:
	 *                                                   - '' Returns an array of complete post objects (`WP_Post[]`).
	 *                                                   - 'ids' Returns an array of post IDs (`int[]`).
	 *                                                   - 'id=>parent' Returns an associative array of parent post IDs,
	 *                                                     keyed by post ID (`int[]`).
	 *                                                   Default ''.
	 *     @type int             $hour                   Hour of the day. Default empty. Accepts numbers 0-23.
	 *     @type int|bool        $ignore_sticky_posts    Whether to ignore sticky posts or not. Setting this to false
	 *                                                   excludes stickies from 'post__in'. Accepts 1|true, 0|false.
	 *                                                   Default false.
	 *     @type int             $m                      Combination YearMonth. Accepts any four-digit year and month
	 *                                                   numbers 01-12. Default empty.
	 *     @type string|string[] $meta_key               Meta key or keys to filter by.
	 *     @type string|string[] $meta_value             Meta value or values to filter by.
	 *     @type string          $meta_compare           MySQL operator used for comparing the meta value.
	 *                                                   See WP_Meta_Query::__construct() for accepted values and default value.
	 *     @type string          $meta_compare_key       MySQL operator used for comparing the meta key.
	 *                                                   See WP_Meta_Query::__construct() for accepted values and default value.
	 *     @type string          $meta_type              MySQL data type that the meta_value column will be CAST to for comparisons.
	 *                                                   See WP_Meta_Query::__construct() for accepted values and default value.
	 *     @type string          $meta_type_key          MySQL data type that the meta_key column will be CAST to for comparisons.
	 *                                                   See WP_Meta_Query::__construct() for accepted values and default value.
	 *     @type array           $meta_query             An associative array of WP_Meta_Query arguments.
	 *                                                   See WP_Meta_Query::__construct() for accepted values.
	 *     @type int             $menu_order             The menu order of the posts.
	 *     @type int             $minute                 Minute of the hour. Default empty. Accepts numbers 0-59.
	 *     @type int             $monthnum               The two-digit month. Default empty. Accepts numbers 1-12.
	 *     @type string          $name                   Post slug.
	 *     @type bool            $nopaging               Show all posts (true) or paginate (false). Default false.
	 *     @type bool            $no_found_rows          Whether to skip counting the total rows found. Enabling can improve
	 *                                                   performance. Default false.
	 *     @type int             $offset                 The number of posts to offset before retrieval.
	 *     @type string          $order                  Designates ascending or descending order of posts. Default 'DESC'.
	 *                                                   Accepts 'ASC', 'DESC'.
	 *     @type string|array    $orderby                Sort retrieved posts by parameter. One or more options may be passed.
	 *                                                   To use 'meta_value', or 'meta_value_num', 'meta_key=keyname' must be
	 *                                                   also be defined. To sort by a specific `$meta_query` clause, use that
	 *                                                   clause's array key. Accepts:
	 *                                                   - 'none'
	 *                                                   - 'name'
	 *                                                   - 'author'
	 *                                                   - 'date'
	 *                                                   - 'title'
	 *                                                   - 'modified'
	 *                                                   - 'menu_order'
	 *                                                   - 'parent'
	 *                                                   - 'ID'
	 *                                                   - 'rand'
	 *                                                   - 'relevance'
	 *                                                   - 'RAND(x)' (where 'x' is an integer seed value)
	 *                                                   - 'comment_count'
	 *                                                   - 'meta_value'
	 *                                                   - 'meta_value_num'
	 *                                                   - 'post__in'
	 *                                                   - 'post_name__in'
	 *                                                   - 'post_parent__in'
	 *                                                   - The array keys of `$meta_query`.
	 *                                                   Default is 'date', except when a search is being performed, when
	 *                                                   the default is 'relevance'.
	 *     @type int             $p                      Post ID.
	 *     @type int             $page                   Show the number of posts that would show up on page X of a
	 *                                                   static front page.
	 *     @type int             $paged                  The number of the current page.
	 *     @type int             $page_id                Page ID.
	 *     @type string          $pagename               Page slug.
	 *     @type string          $perm                   Show posts if user has the appropriate capability.
	 *     @type string          $ping_status            Ping status.
	 *     @type int[]           $post__in               An array of post IDs to retrieve, sticky posts will be included.
	 *     @type int[]           $post__not_in           An array of post IDs not to retrieve. Note: a string of comma-
	 *                                                   separated IDs will NOT work.
	 *     @type string          $post_mime_type         The mime type of the post. Used for 'attachment' post_type.
	 *     @type string[]        $post_name__in          An array of post slugs that results must match.
	 *     @type int             $post_parent            Page ID to retrieve child pages for. Use 0 to only retrieve
	 *                                                   top-level pages.
	 *     @type int[]           $post_parent__in        An array containing parent page IDs to query child pages from.
	 *     @type int[]           $post_parent__not_in    An array containing parent page IDs not to query child pages from.
	 *     @type string|string[] $post_type              A post type slug (string) or array of post type slugs.
	 *                                                   Default 'any' if using 'tax_query'.
	 *     @type string|string[] $post_status            A post status (string) or array of post statuses.
	 *     @type int             $posts_per_page         The number of posts to query for. Use -1 to request all posts.
	 *     @type int             $posts_per_archive_page The number of posts to query for by archive page. Overrides
	 *                                                   'posts_per_page' when is_archive(), or is_search() are true.
	 *     @type string          $s                      Search keyword(s). Prepending a term with a hyphen will
	 *                                                   exclude posts matching that term. Eg, 'pillow -sofa' will
	 *                                                   return posts containing 'pillow' but not 'sofa'. The
	 *                                                   character used for exclusion can be modified using the
	 *                                                   the 'wp_query_search_exclusion_prefix' filter.
	 *     @type string[]        $search_columns         Array of column names to be searched. Accepts 'post_title',
	 *                                                   'post_excerpt' and 'post_content'. Default empty array.
	 *     @type int             $second                 Second of the minute. Default empty. Accepts numbers 0-59.
	 *     @type bool            $sentence               Whether to search by phrase. Default false.
	 *     @type bool            $suppress_filters       Whether to suppress filters. Default false.
	 *     @type string          $tag                    Tag slug. Comma-separated (either), Plus-separated (all).
	 *     @type int[]           $tag__and               An array of tag IDs (AND in).
	 *     @type int[]           $tag__in                An array of tag IDs (OR in).
	 *     @type int[]           $tag__not_in            An array of tag IDs (NOT in).
	 *     @type int             $tag_id                 Tag id or comma-separated list of IDs.
	 *     @type string[]        $tag_slug__and          An array of tag slugs (AND in).
	 *     @type string[]        $tag_slug__in           An array of tag slugs (OR in). unless 'ignore_sticky_posts' is
	 *                                                   true. Note: a string of comma-separated IDs will NOT work.
	 *     @type array           $tax_query              An associative array of WP_Tax_Query arguments.
	 *                                                   See WP_Tax_Query::__construct().
	 *     @type string          $title                  Post title.
	 *     @type bool            $update_post_meta_cache Whether to update the post meta cache. Default true.
	 *     @type bool            $update_post_term_cache Whether to update the post term cache. Default true.
	 *     @type bool            $update_menu_item_cache Whether to update the menu item cache. Default false.
	 *     @type bool            $lazy_load_term_meta    Whether to lazy-load term meta. Setting to false will
	 *                                                   disable cache priming for term meta, so that each
	 *                                                   get_term_meta() call will hit the database.
	 *                                                   Defaults to the value of `$update_post_term_cache`.
	 *     @type int             $w                      The week number of the year. Default empty. Accepts numbers 0-53.
	 *     @type int             $year                   The four-digit year. Default empty. Accepts any four-digit year.
	 * }
	 */
	public function parse_query( $query = '' ) {
		if ( ! empty( $query ) ) {
			$this->init();
			$this->query      = wp_parse_args( $query );
			$this->query_vars = $this->query;
		} elseif ( ! isset( $this->query ) ) {
			$this->query = $this->query_vars;
		}

		$this->query_vars         = $this->fill_query_vars( $this->query_vars );
		$qv                       = &$this->query_vars;
		$this->query_vars_changed = true;

		if ( ! empty( $qv['robots'] ) ) {
			$this->is_robots = true;
		} elseif ( ! empty( $qv['favicon'] ) ) {
			$this->is_favicon = true;
		}

		if ( ! is_scalar( $qv['p'] ) || (int) $qv['p'] < 0 ) {
			$qv['p']     = 0;
			$qv['error'] = '404';
		} else {
			$qv['p'] = (int) $qv['p'];
		}

		$qv['page_id']  = is_scalar( $qv['page_id'] ) ? absint( $qv['page_id'] ) : 0;
		$qv['year']     = is_scalar( $qv['year'] ) ? absint( $qv['year'] ) : 0;
		$qv['monthnum'] = is_scalar( $qv['monthnum'] ) ? absint( $qv['monthnum'] ) : 0;
		$qv['day']      = is_scalar( $qv['day'] ) ? absint( $qv['day'] ) : 0;
		$qv['w']        = is_scalar( $qv['w'] ) ? absint( $qv['w'] ) : 0;
		$qv['m']        = is_scalar( $qv['m'] ) ? preg_replace( '|[^0-9]|', '', $qv['m'] ) : '';
		$qv['paged']    = is_scalar( $qv['paged'] ) ? absint( $qv['paged'] ) : 0;
		$qv['cat']      = preg_replace( '|[^0-9,-]|', '', $qv['cat'] ); // Array or comma-separated list of positive or negative integers.
		$qv['author']   = is_scalar( $qv['author'] ) ? preg_replace( '|[^0-9,-]|', '', $qv['author'] ) : ''; // Comma-separated list of positive or negative integers.
		$qv['pagename'] = is_scalar( $qv['pagename'] ) ? trim( $qv['pagename'] ) : '';
		$qv['name']     = is_scalar( $qv['name'] ) ? trim( $qv['name'] ) : '';
		$qv['title']    = is_scalar( $qv['title'] ) ? trim( $qv['title'] ) : '';

		if ( is_scalar( $qv['hour'] ) && '' !== $qv['hour'] ) {
			$qv['hour'] = absint( $qv['hour'] );
		} else {
			$qv['hour'] = '';
		}

		if ( is_scalar( $qv['minute'] ) && '' !== $qv['minute'] ) {
			$qv['minute'] = absint( $qv['minute'] );
		} else {
			$qv['minute'] = '';
		}

		if ( is_scalar( $qv['second'] ) && '' !== $qv['second'] ) {
			$qv['second'] = absint( $qv['second'] );
		} else {
			$qv['second'] = '';
		}

		if ( is_scalar( $qv['menu_order'] ) && '' !== $qv['menu_order'] ) {
			$qv['menu_order'] = absint( $qv['menu_order'] );
		} else {
			$qv['menu_order'] = '';
		}

		// Fairly large, potentially too large, upper bound for search string lengths.
		if ( ! is_scalar( $qv['s'] ) || ( ! empty( $qv['s'] ) && strlen( $qv['s'] ) > 1600 ) ) {
			$qv['s'] = '';
		}

		// Compat. Map subpost to attachment.
		if ( is_scalar( $qv['subpost'] ) && '' != $qv['subpost'] ) {
			$qv['attachment'] = $qv['subpost'];
		}
		if ( is_scalar( $qv['subpost_id'] ) && '' != $qv['subpost_id'] ) {
			$qv['attachment_id'] = $qv['subpost_id'];
		}

		$qv['attachment_id'] = is_scalar( $qv['attachment_id'] ) ? absint( $qv['attachment_id'] ) : 0;

		if ( ( '' !== $qv['attachment'] ) || ! empty( $qv['attachment_id'] ) ) {
			$this->is_single     = true;
			$this->is_attachment = true;
		} elseif ( '' !== $qv['name'] ) {
			$this->is_single = true;
		} elseif ( $qv['p'] ) {
			$this->is_single = true;
		} elseif ( '' !== $qv['pagename'] || ! empty( $qv['page_id'] ) ) {
			$this->is_page   = true;
			$this->is_single = false;
		} else {
			// Look for archive queries. Dates, categories, authors, search, post type archives.

			if ( isset( $this->query['s'] ) ) {
				$this->is_search = true;
			}

			if ( '' !== $qv['second'] ) {
				$this->is_time = true;
				$this->is_date = true;
			}

			if ( '' !== $qv['minute'] ) {
				$this->is_time = true;
				$this->is_date = true;
			}

			if ( '' !== $qv['hour'] ) {
				$this->is_time = true;
				$this->is_date = true;
			}

			if ( $qv['day'] ) {
				if ( ! $this->is_date ) {
					$date = sprintf( '%04d-%02d-%02d', $qv['year'], $qv['monthnum'], $qv['day'] );
					if ( $qv['monthnum'] && $qv['year'] && ! wp_checkdate( $qv['monthnum'], $qv['day'], $qv['year'], $date ) ) {
						$qv['error'] = '404';
					} else {
						$this->is_day  = true;
						$this->is_date = true;
					}
				}
			}

			if ( $qv['monthnum'] ) {
				if ( ! $this->is_date ) {
					if ( 12 < $qv['monthnum'] ) {
						$qv['error'] = '404';
					} else {
						$this->is_month = true;
						$this->is_date  = true;
					}
				}
			}

			if ( $qv['year'] ) {
				if ( ! $this->is_date ) {
					$this->is_year = true;
					$this->is_date = true;
				}
			}

			if ( $qv['m'] ) {
				$this->is_date = true;
				if ( strlen( $qv['m'] ) > 9 ) {
					$this->is_time = true;
				} elseif ( strlen( $qv['m'] ) > 7 ) {
					$this->is_day = true;
				} elseif ( strlen( $qv['m'] ) > 5 ) {
					$this->is_month = true;
				} else {
					$this->is_year = true;
				}
			}

			if ( $qv['w'] ) {
				$this->is_date = true;
			}

			$this->query_vars_hash = false;
			$this->parse_tax_query( $qv );

			foreach ( $this->tax_query->queries as $tax_query ) {
				if ( ! is_array( $tax_query ) ) {
					continue;
				}

				if ( isset( $tax_query['operator'] ) && 'NOT IN' !== $tax_query['operator'] ) {
					switch ( $tax_query['taxonomy'] ) {
						case 'category':
							$this->is_category = true;
							break;
						case 'post_tag':
							$this->is_tag = true;
							break;
						default:
							$this->is_tax = true;
					}
				}
			}
			unset( $tax_query );

			if ( empty( $qv['author'] ) || ( '0' == $qv['author'] ) ) {
				$this->is_author = false;
			} else {
				$this->is_author = true;
			}

			if ( '' !== $qv['author_name'] ) {
				$this->is_author = true;
			}

			if ( ! empty( $qv['post_type'] ) && ! is_array( $qv['post_type'] ) ) {
				$post_type_obj = get_post_type_object( $qv['post_type'] );
				if ( ! empty( $post_type_obj->has_archive ) ) {
					$this->is_post_type_archive = true;
				}
			}

			if ( $this->is_post_type_archive || $this->is_date || $this->is_author || $this->is_category || $this->is_tag || $this->is_tax ) {
				$this->is_archive = true;
			}
		}

		if ( '' != $qv['feed'] ) {
			$this->is_feed = true;
		}

		if ( '' != $qv['embed'] ) {
			$this->is_embed = true;
		}

		if ( '' != $qv['tb'] ) {
			$this->is_trackback = true;
		}

		if ( '' != $qv['paged'] && ( (int) $qv['paged'] > 1 ) ) {
			$this->is_paged = true;
		}

		// If we're previewing inside the write screen.
		if ( '' != $qv['preview'] ) {
			$this->is_preview = true;
		}

		if ( is_admin() ) {
			$this->is_admin = true;
		}

		if ( str_contains( $qv['feed'], 'comments-' ) ) {
			$qv['feed']         = str_replace( 'comments-', '', $qv['feed'] );
			$qv['withcomments'] = 1;
		}

		$this->is_singular = $this->is_single || $this->is_page || $this->is_attachment;

		if ( $this->is_feed && ( ! empty( $qv['withcomments'] ) || ( empty( $qv['withoutcomments'] ) && $this->is_singular ) ) ) {
			$this->is_comment_feed = true;
		}

		if ( ! ( $this->is_singular || $this->is_archive || $this->is_search || $this->is_feed
				|| ( wp_is_serving_rest_request() && $this->is_main_query() )
				|| $this->is_trackback || $this->is_404 || $this->is_admin || $this->is_robots || $this->is_favicon ) ) {
			$this->is_home = true;
		}

		// Correct `is_*` for 'page_on_front' and 'page_for_posts'.
		if ( $this->is_home && 'page' === get_option( 'show_on_front' ) && get_option( 'page_on_front' ) ) {
			$_query = wp_parse_args( $this->query );
			// 'pagename' can be set and empty depending on matched rewrite rules. Ignore an empty 'pagename'.
			if ( isset( $_query['pagename'] ) && '' === $_query['pagename'] ) {
				unset( $_query['pagename'] );
			}

			unset( $_query['embed'] );

			if ( empty( $_query ) || ! array_diff( array_keys( $_query ), array( 'preview', 'page', 'paged', 'cpage' ) ) ) {
				$this->is_page = true;
				$this->is_home = false;
				$qv['page_id'] = get_option( 'page_on_front' );
				// Correct <!--nextpage--> for 'page_on_front'.
				if ( ! empty( $qv['paged'] ) ) {
					$qv['page'] = $qv['paged'];
					unset( $qv['paged'] );
				}
			}
		}

		if ( '' !== $qv['pagename'] ) {
			$this->queried_object = get_page_by_path( $qv['pagename'] );

			if ( $this->queried_object && 'attachment' === $this->queried_object->post_type ) {
				if ( preg_match( '/^[^%]*%(?:postname)%/', get_option( 'permalink_structure' ) ) ) {
					// See if we also have a post with the same slug.
					$post = get_page_by_path( $qv['pagename'], OBJECT, 'post' );
					if ( $post ) {
						$this->queried_object = $post;
						$this->is_page        = false;
						$this->is_single      = true;
					}
				}
			}

			if ( ! empty( $this->queried_object ) ) {
				$this->queried_object_id = (int) $this->queried_object->ID;
			} else {
				unset( $this->queried_object );
			}

			if ( 'page' === get_option( 'show_on_front' ) && isset( $this->queried_object_id ) && get_option( 'page_for_posts' ) == $this->queried_object_id ) {
				$this->is_page       = false;
				$this->is_home       = true;
				$this->is_posts_page = true;
			}

			if ( isset( $this->queried_object_id ) && get_option( 'wp_page_for_privacy_policy' ) == $this->queried_object_id ) {
				$this->is_privacy_policy = true;
			}
		}

		if ( $qv['page_id'] ) {
			if ( 'page' === get_option( 'show_on_front' ) && get_option( 'page_for_posts' ) == $qv['page_id'] ) {
				$this->is_page       = false;
				$this->is_home       = true;
				$this->is_posts_page = true;
			}

			if ( get_option( 'wp_page_for_privacy_policy' ) == $qv['page_id'] ) {
				$this->is_privacy_policy = true;
			}
		}

		if ( ! empty( $qv['post_type'] ) ) {
			if ( is_array( $qv['post_type'] ) ) {
				$qv['post_type'] = array_map( 'sanitize_key', array_unique( $qv['post_type'] ) );
				sort( $qv['post_type'] );
			} else {
				$qv['post_type'] = sanitize_key( $qv['post_type'] );
			}
		}

		if ( ! empty( $qv['post_status'] ) ) {
			if ( is_array( $qv['post_status'] ) ) {
				$qv['post_status'] = array_map( 'sanitize_key', array_unique( $qv['post_status'] ) );
				sort( $qv['post_status'] );
			} else {
				$qv['post_status'] = preg_replace( '|[^a-z0-9_,-]|', '', $qv['post_status'] );
			}
		}

		if ( $this->is_posts_page && ( ! isset( $qv['withcomments'] ) || ! $qv['withcomments'] ) ) {
			$this->is_comment_feed = false;
		}

		$this->is_singular = $this->is_single || $this->is_page || $this->is_attachment;
		// Done correcting `is_*` for 'page_on_front' and 'page_for_posts'.

		if ( '404' == $qv['error'] ) {
			$this->set_404();
		}

		$this->is_embed = $this->is_embed && ( $this->is_singular || $this->is_404 );

		$this->query_vars_hash    = md5( serialize( $this->query_vars ) );
		$this->query_vars_changed = false;

		/**
		 * Fires after the main query vars have been parsed.
		 *
		 * @since 1.5.0
		 *
		 * @param WP_Query $query The WP_Query instance (passed by reference).
		 */
		do_action_ref_array( 'parse_query', array( &$this ) );
	}

	/**
	 * Parses various taxonomy related query vars.
	 *
	 * For BC, this method is not marked as protected. See [28987].
	 *
	 * @since 3.1.0
	 *
	 * @param array $q The query variables. Passed by reference.
	 */
	public function parse_tax_query( &$q ) {
		if ( ! empty( $q['tax_query'] ) && is_array( $q['tax_query'] ) ) {
			$tax_query = $q['tax_query'];
		} else {
			$tax_query = array();
		}

		if ( ! empty( $q['taxonomy'] ) && ! empty( $q['term'] ) ) {
			$tax_query[] = array(
				'taxonomy' => $q['taxonomy'],
				'terms'    => array( $q['term'] ),
				'field'    => 'slug',
			);
		}

		foreach ( get_taxonomies( array(), 'objects' ) as $taxonomy => $t ) {
			if ( 'post_tag' === $taxonomy ) {
				continue; // Handled further down in the $q['tag'] block.
			}

			if ( $t->query_var && ! empty( $q[ $t->query_var ] ) ) {
				$tax_query_defaults = array(
					'taxonomy' => $taxonomy,
					'field'    => 'slug',
				);

				if ( ! empty( $t->rewrite['hierarchical'] ) ) {
					$q[ $t->query_var ] = wp_basename( $q[ $t->query_var ] );
				}

				$term = $q[ $t->query_var ];

				if ( ! is_array( $term ) ) {
					$term = explode( ',', $term );
					$term = array_map( 'trim', $term );
				}
				sort( $term );
				$term = implode( ',', $term );

				if ( str_contains( $term, '+' ) ) {
					$terms = preg_split( '/[+]+/', $term );
					foreach ( $terms as $term ) {
						$tax_query[] = array_merge(
							$tax_query_defaults,
							array(
								'terms' => array( $term ),
							)
						);
					}
				} else {
					$tax_query[] = array_merge(
						$tax_query_defaults,
						array(
							'terms' => preg_split( '/[,]+/', $term ),
						)
					);
				}
			}
		}

		// If query string 'cat' is an array, implode it.
		if ( is_array( $q['cat'] ) ) {
			$q['cat'] = implode( ',', $q['cat'] );
		}

		// Category stuff.

		if ( ! empty( $q['cat'] ) && ! $this->is_singular ) {
			$cat_in     = array();
			$cat_not_in = array();

			$cat_array = preg_split( '/[,\s]+/', urldecode( $q['cat'] ) );
			$cat_array = array_map( 'intval', $cat_array );
			sort( $cat_array );
			$q['cat'] = implode( ',', $cat_array );

			foreach ( $cat_array as $cat ) {
				if ( $cat > 0 ) {
					$cat_in[] = $cat;
				} elseif ( $cat < 0 ) {
					$cat_not_in[] = abs( $cat );
				}
			}

			if ( ! empty( $cat_in ) ) {
				$tax_query[] = array(
					'taxonomy'         => 'category',
					'terms'            => $cat_in,
					'field'            => 'term_id',
					'include_children' => true,
				);
			}

			if ( ! empty( $cat_not_in ) ) {
				$tax_query[] = array(
					'taxonomy'         => 'category',
					'terms'            => $cat_not_in,
					'field'            => 'term_id',
					'operator'         => 'NOT IN',
					'include_children' => true,
				);
			}
			unset( $cat_array, $cat_in, $cat_not_in );
		}

		if ( ! empty( $q['category__and'] ) && 1 === count( (array) $q['category__and'] ) ) {
			$q['category__and'] = (array) $q['category__and'];
			if ( ! isset( $q['category__in'] ) ) {
				$q['category__in'] = array();
			}
			$q['category__in'][] = absint( reset( $q['category__and'] ) );
			unset( $q['category__and'] );
		}

		if ( ! empty( $q['category__in'] ) ) {
			$q['category__in'] = array_map( 'absint', array_unique( (array) $q['category__in'] ) );
			sort( $q['category__in'] );
			$tax_query[] = array(
				'taxonomy'         => 'category',
				'terms'            => $q['category__in'],
				'field'            => 'term_id',
				'include_children' => false,
			);
		}

		if ( ! empty( $q['category__not_in'] ) ) {
			$q['category__not_in'] = array_map( 'absint', array_unique( (array) $q['category__not_in'] ) );
			sort( $q['category__not_in'] );
			$tax_query[] = array(
				'taxonomy'         => 'category',
				'terms'            => $q['category__not_in'],
				'operator'         => 'NOT IN',
				'include_children' => false,
			);
		}

		if ( ! empty( $q['category__and'] ) ) {
			$q['category__and'] = array_map( 'absint', array_unique( (array) $q['category__and'] ) );
			sort( $q['category__and'] );
			$tax_query[] = array(
				'taxonomy'         => 'category',
				'terms'            => $q['category__and'],
				'field'            => 'term_id',
				'operator'         => 'AND',
				'include_children' => false,
			);
		}

		// If query string 'tag' is array, implode it.
		if ( is_array( $q['tag'] ) ) {
			$q['tag'] = implode( ',', $q['tag'] );
		}

		// Tag stuff.

		if ( '' !== $q['tag'] && ! $this->is_singular && $this->query_vars_changed ) {
			if ( str_contains( $q['tag'], ',' ) ) {
				// @todo Handle normalizing `tag` query string.
				$tags = preg_split( '/[,\r\n\t ]+/', $q['tag'] );
				foreach ( (array) $tags as $tag ) {
					$tag                 = sanitize_term_field( 'slug', $tag, 0, 'post_tag', 'db' );
					$q['tag_slug__in'][] = $tag;
					sort( $q['tag_slug__in'] );
				}
			} elseif ( preg_match( '/[+\r\n\t ]+/', $q['tag'] ) || ! empty( $q['cat'] ) ) {
				$tags = preg_split( '/[+\r\n\t ]+/', $q['tag'] );
				foreach ( (array) $tags as $tag ) {
					$tag                  = sanitize_term_field( 'slug', $tag, 0, 'post_tag', 'db' );
					$q['tag_slug__and'][] = $tag;
				}
			} else {
				$q['tag']            = sanitize_term_field( 'slug', $q['tag'], 0, 'post_tag', 'db' );
				$q['tag_slug__in'][] = $q['tag'];
				sort( $q['tag_slug__in'] );
			}
		}

		if ( ! empty( $q['tag_id'] ) ) {
			$q['tag_id'] = absint( $q['tag_id'] );
			$tax_query[] = array(
				'taxonomy' => 'post_tag',
				'terms'    => $q['tag_id'],
			);
		}

		if ( ! empty( $q['tag__in'] ) ) {
			$q['tag__in'] = array_map( 'absint', array_unique( (array) $q['tag__in'] ) );
			sort( $q['tag__in'] );
			$tax_query[] = array(
				'taxonomy' => 'post_tag',
				'terms'    => $q['tag__in'],
			);
		}

		if ( ! empty( $q['tag__not_in'] ) ) {
			$q['tag__not_in'] = array_map( 'absint', array_unique( (array) $q['tag__not_in'] ) );
			sort( $q['tag__not_in'] );
			$tax_query[] = array(
				'taxonomy' => 'post_tag',
				'terms'    => $q['tag__not_in'],
				'operator' => 'NOT IN',
			);
		}

		if ( ! empty( $q['tag__and'] ) ) {
			$q['tag__and'] = array_map( 'absint', array_unique( (array) $q['tag__and'] ) );
			sort( $q['tag__and'] );
			$tax_query[] = array(
				'taxonomy' => 'post_tag',
				'terms'    => $q['tag__and'],
				'operator' => 'AND',
			);
		}

		if ( ! empty( $q['tag_slug__in'] ) ) {
			$q['tag_slug__in'] = array_map( 'sanitize_title_for_query', array_unique( (array) $q['tag_slug__in'] ) );
			sort( $q['tag_slug__in'] );
			$tax_query[] = array(
				'taxonomy' => 'post_tag',
				'terms'    => $q['tag_slug__in'],
				'field'    => 'slug',
			);
		}

		if ( ! empty( $q['tag_slug__and'] ) ) {
			$q['tag_slug__and'] = array_map( 'sanitize_title_for_query', array_unique( (array) $q['tag_slug__and'] ) );
			sort( $q['tag_slug__and'] );
			$tax_query[] = array(
				'taxonomy' => 'post_tag',
				'terms'    => $q['tag_slug__and'],
				'field'    => 'slug',
				'operator' => 'AND',
			);
		}

		$this->tax_query = new WP_Tax_Query( $tax_query );

		/**
		 * Fires after taxonomy-related query vars have been parsed.
		 *
		 * @since 3.7.0
		 *
		 * @param WP_Query $query The WP_Query instance.
		 */
		do_action( 'parse_tax_query', $this );
	}

	/**
	 * Generates SQL for the WHERE clause based on passed search terms.
	 *
	 * @since 3.7.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @param array $q Query variables.
	 * @return string WHERE clause.
	 */
	protected function parse_search( &$q ) {
		global $wpdb;

		$search = '';

		// Added slashes screw with quote grouping when done early, so done later.
		$q['s'] = stripslashes( $q['s'] );
		if ( empty( $_GET['s'] ) && $this->is_main_query() ) {
			$q['s'] = urldecode( $q['s'] );
		}
		// There are no line breaks in <input /> fields.
		$q['s']                  = str_replace( array( "\r", "\n" ), '', $q['s'] );
		$q['search_terms_count'] = 1;
		if ( ! empty( $q['sentence'] ) ) {
			$q['search_terms'] = array( $q['s'] );
		} else {
			if ( preg_match_all( '/".*?("|$)|((?<=[\t ",+])|^)[^\t ",+]+/', $q['s'], $matches ) ) {
				$q['search_terms_count'] = count( $matches[0] );
				$q['search_terms']       = $this->parse_search_terms( $matches[0] );
				// If the search string has only short terms or stopwords, or is 10+ terms long, match it as sentence.
				if ( empty( $q['search_terms'] ) || count( $q['search_terms'] ) > 9 ) {
					$q['search_terms'] = array( $q['s'] );
				}
			} else {
				$q['search_terms'] = array( $q['s'] );
			}
		}

		$n                         = ! empty( $q['exact'] ) ? '' : '%';
		$searchand                 = '';
		$q['search_orderby_title'] = array();

		$default_search_columns = array( 'post_title', 'post_excerpt', 'post_content' );
		$search_columns         = ! empty( $q['search_columns'] ) ? $q['search_columns'] : $default_search_columns;
		if ( ! is_array( $search_columns ) ) {
			$search_columns = array( $search_columns );
		}

		/**
		 * Filters the columns to search in a WP_Query search.
		 *
		 * The supported columns are `post_title`, `post_excerpt` and `post_content`.
		 * They are all included by default.
		 *
		 * @since 6.2.0
		 *
		 * @param string[] $search_columns Array of column names to be searched.
		 * @param string   $search         Text being searched.
		 * @param WP_Query $query          The current WP_Query instance.
		 */
		$search_columns = (array) apply_filters( 'post_search_columns', $search_columns, $q['s'], $this );

		// Use only supported search columns.
		$search_columns = array_intersect( $search_columns, $default_search_columns );
		if ( empty( $search_columns ) ) {
			$search_columns = $default_search_columns;
		}

		/**
		 * Filters the prefix that indicates that a search term should be excluded from results.
		 *
		 * @since 4.7.0
		 *
		 * @param string $exclusion_prefix The prefix. Default '-'. Returning
		 *                                 an empty value disables exclusions.
		 */
		$exclusion_prefix = apply_filters( 'wp_query_search_exclusion_prefix', '-' );

		foreach ( $q['search_terms'] as $term ) {
			// If there is an $exclusion_prefix, terms prefixed with it should be excluded.
			$exclude = $exclusion_prefix && str_starts_with( $term, $exclusion_prefix );
			if ( $exclude ) {
				$like_op  = 'NOT LIKE';
				$andor_op = 'AND';
				$term     = substr( $term, 1 );
			} else {
				$like_op  = 'LIKE';
				$andor_op = 'OR';
			}

			if ( $n && ! $exclude ) {
				$like                        = '%' . $wpdb->esc_like( $term ) . '%';
				$q['search_orderby_title'][] = $wpdb->prepare( "{$wpdb->posts}.post_title LIKE %s", $like );
			}

			$like = $n . $wpdb->esc_like( $term ) . $n;

			$search_columns_parts = array();
			foreach ( $search_columns as $search_column ) {
				$search_columns_parts[ $search_column ] = $wpdb->prepare( "({$wpdb->posts}.$search_column $like_op %s)", $like );
			}

			if ( ! empty( $this->allow_query_attachment_by_filename ) ) {
				$search_columns_parts['attachment'] = $wpdb->prepare( "(sq1.meta_value $like_op %s)", $like );
			}

			$search .= "$searchand(" . implode( " $andor_op ", $search_columns_parts ) . ')';

			$searchand = ' AND ';
		}

		if ( ! empty( $search ) ) {
			$search = " AND ({$search}) ";
			if ( ! is_user_logged_in() ) {
				$search .= " AND ({$wpdb->posts}.post_password = '') ";
			}
		}

		return $search;
	}

	/**
	 * Checks if the terms are suitable for searching.
	 *
	 * Uses an array of stopwords (terms) that are excluded from the separate
	 * term matching when searching for posts. The list of English stopwords is
	 * the approximate search engines list, and is translatable.
	 *
	 * @since 3.7.0
	 *
	 * @param string[] $terms Array of terms to check.
	 * @return string[] Terms that are not stopwords.
	 */
	protected function parse_search_terms( $terms ) {
		$strtolower = function_exists( 'mb_strtolower' ) ? 'mb_strtolower' : 'strtolower';
		$checked    = array();

		$stopwords = $this->get_search_stopwords();

		foreach ( $terms as $term ) {
			// Keep before/after spaces when term is for exact match.
			if ( preg_match( '/^".+"$/', $term ) ) {
				$term = trim( $term, "\"'" );
			} else {
				$term = trim( $term, "\"' " );
			}

			// Avoid single A-Z and single dashes.
			if ( ! $term || ( 1 === strlen( $term ) && preg_match( '/^[a-z\-]$/i', $term ) ) ) {
				continue;
			}

			if ( in_array( call_user_func( $strtolower, $term ), $stopwords, true ) ) {
				continue;
			}

			$checked[] = $term;
		}

		return $checked;
	}

	/**
	 * Retrieves stopwords used when parsing search terms.
	 *
	 * @since 3.7.0
	 *
	 * @return string[] Stopwords.
	 */
	protected function get_search_stopwords() {
		if ( isset( $this->stopwords ) ) {
			return $this->stopwords;
		}

		/*
		 * translators: This is a comma-separated list of very common words that should be excluded from a search,
		 * like a, an, and the. These are usually called "stopwords". You should not simply translate these individual
		 * words into your language. Instead, look for and provide commonly accepted stopwords in your language.
		 */
		$words = explode(
			',',
			_x(
				'about,an,are,as,at,be,by,com,for,from,how,in,is,it,of,on,or,that,the,this,to,was,what,when,where,who,will,with,www',
				'Comma-separated list of search stopwords in your language'
			)
		);

		$stopwords = array();
		foreach ( $words as $word ) {
			$word = trim( $word, "\r\n\t " );
			if ( $word ) {
				$stopwords[] = $word;
			}
		}

		/**
		 * Filters stopwords used when parsing search terms.
		 *
		 * @since 3.7.0
		 *
		 * @param string[] $stopwords Array of stopwords.
		 */
		$this->stopwords = apply_filters( 'wp_search_stopwords', $stopwords );
		return $this->stopwords;
	}

	/**
	 * Generates SQL for the ORDER BY condition based on passed search terms.
	 *
	 * @since 3.7.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @param array $q Query variables.
	 * @return string ORDER BY clause.
	 */
	protected function parse_search_order( &$q ) {
		global $wpdb;

		if ( $q['search_terms_count'] > 1 ) {
			$num_terms = count( $q['search_orderby_title'] );

			// If the search terms contain negative queries, don't bother ordering by sentence matches.
			$like = '';
			if ( ! preg_match( '/(?:\s|^)\-/', $q['s'] ) ) {
				$like = '%' . $wpdb->esc_like( $q['s'] ) . '%';
			}

			$search_orderby = '';

			// Sentence match in 'post_title'.
			if ( $like ) {
				$search_orderby .= $wpdb->prepare( "WHEN {$wpdb->posts}.post_title LIKE %s THEN 1 ", $like );
			}

			/*
			 * Sanity limit, sort as sentence when more than 6 terms
			 * (few searches are longer than 6 terms and most titles are not).
			 */
			if ( $num_terms < 7 ) {
				// All words in title.
				$search_orderby .= 'WHEN ' . implode( ' AND ', $q['search_orderby_title'] ) . ' THEN 2 ';
				// Any word in title, not needed when $num_terms == 1.
				if ( $num_terms > 1 ) {
					$search_orderby .= 'WHEN ' . implode( ' OR ', $q['search_orderby_title'] ) . ' THEN 3 ';
				}
			}

			// Sentence match in 'post_content' and 'post_excerpt'.
			if ( $like ) {
				$search_orderby .= $wpdb->prepare( "WHEN {$wpdb->posts}.post_excerpt LIKE %s THEN 4 ", $like );
				$search_orderby .= $wpdb->prepare( "WHEN {$wpdb->posts}.post_content LIKE %s THEN 5 ", $like );
			}

			if ( $search_orderby ) {
				$search_orderby = '(CASE ' . $search_orderby . 'ELSE 6 END)';
			}
		} else {
			// Single word or sentence search.
			$search_orderby = reset( $q['search_orderby_title'] ) . ' DESC';
		}

		return $search_orderby;
	}

	/**
	 * Converts the given orderby alias (if allowed) to a properly-prefixed value.
	 *
	 * @since 4.0.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @param string $orderby Alias for the field to order by.
	 * @return string|false Table-prefixed value to used in the ORDER clause. False otherwise.
	 */
	protected function parse_orderby( $orderby ) {
		global $wpdb;

		// Used to filter values.
		$allowed_keys = array(
			'post_name',
			'post_author',
			'post_date',
			'post_title',
			'post_modified',
			'post_parent',
			'post_type',
			'name',
			'author',
			'date',
			'title',
			'modified',
			'parent',
			'type',
			'ID',
			'menu_order',
			'comment_count',
			'rand',
			'post__in',
			'post_parent__in',
			'post_name__in',
		);

		$primary_meta_key   = '';
		$primary_meta_query = false;
		$meta_clauses       = $this->meta_query->get_clauses();
		if ( ! empty( $meta_clauses ) ) {
			$primary_meta_query = reset( $meta_clauses );

			if ( ! empty( $primary_meta_query['key'] ) ) {
				$primary_meta_key = $primary_meta_query['key'];
				$allowed_keys[]   = $primary_meta_key;
			}

			$allowed_keys[] = 'meta_value';
			$allowed_keys[] = 'meta_value_num';
			$allowed_keys   = array_merge( $allowed_keys, array_keys( $meta_clauses ) );
		}

		// If RAND() contains a seed value, sanitize and add to allowed keys.
		$rand_with_seed = false;
		if ( preg_match( '/RAND\(([0-9]+)\)/i', $orderby, $matches ) ) {
			$orderby        = sprintf( 'RAND(%s)', (int) $matches[1] );
			$allowed_keys[] = $orderby;
			$rand_with_seed = true;
		}

		if ( ! in_array( $orderby, $allowed_keys, true ) ) {
			return false;
		}

		$orderby_clause = '';

		switch ( $orderby ) {
			case 'post_name':
			case 'post_author':
			case 'post_date':
			case 'post_title':
			case 'post_modified':
			case 'post_parent':
			case 'post_type':
			case 'ID':
			case 'menu_order':
			case 'comment_count':
				$orderby_clause = "{$wpdb->posts}.{$orderby}";
				break;
			case 'rand':
				$orderby_clause = 'RAND()';
				break;
			case $primary_meta_key:
			case 'meta_value':
				if ( ! empty( $primary_meta_query['type'] ) ) {
					$orderby_clause = "CAST({$primary_meta_query['alias']}.meta_value AS {$primary_meta_query['cast']})";
				} else {
					$orderby_clause = "{$primary_meta_query['alias']}.meta_value";
				}
				break;
			case 'meta_value_num':
				$orderby_clause = "{$primary_meta_query['alias']}.meta_value+0";
				break;
			case 'post__in':
				if ( ! empty( $this->query_vars['post__in'] ) ) {
					$orderby_clause = "FIELD({$wpdb->posts}.ID," . implode( ',', array_map( 'absint', $this->query_vars['post__in'] ) ) . ')';
				}
				break;
			case 'post_parent__in':
				if ( ! empty( $this->query_vars['post_parent__in'] ) ) {
					$orderby_clause = "FIELD( {$wpdb->posts}.post_parent," . implode( ', ', array_map( 'absint', $this->query_vars['post_parent__in'] ) ) . ' )';
				}
				break;
			case 'post_name__in':
				if ( ! empty( $this->query_vars['post_name__in'] ) ) {
					$post_name__in        = array_map( 'sanitize_title_for_query', $this->query_vars['post_name__in'] );
					$post_name__in_string = "'" . implode( "','", $post_name__in ) . "'";
					$orderby_clause       = "FIELD( {$wpdb->posts}.post_name," . $post_name__in_string . ' )';
				}
				break;
			default:
				if ( array_key_exists( $orderby, $meta_clauses ) ) {
					// $orderby corresponds to a meta_query clause.
					$meta_clause    = $meta_clauses[ $orderby ];
					$orderby_clause = "CAST({$meta_clause['alias']}.meta_value AS {$meta_clause['cast']})";
				} elseif ( $rand_with_seed ) {
					$orderby_clause = $orderby;
				} else {
					// Default: order by post field.
					$orderby_clause = "{$wpdb->posts}.post_" . sanitize_key( $orderby );
				}

				break;
		}

		return $orderby_clause;
	}

	/**
	 * Parse an 'order' query variable and cast it to ASC or DESC as necessary.
	 *
	 * @since 4.0.0
	 *
	 * @param string $order The 'order' query variable.
	 * @return string The sanitized 'order' query variable.
	 */
	protected function parse_order( $order ) {
		if ( ! is_string( $order ) || empty( $order ) ) {
			return 'DESC';
		}

		if ( 'ASC' === strtoupper( $order ) ) {
			return 'ASC';
		} else {
			return 'DESC';
		}
	}

	/**
	 * Sets the 404 property and saves whether query is feed.
	 *
	 * @since 2.0.0
	 */
	public function set_404() {
		$is_feed = $this->is_feed;

		$this->init_query_flags();
		$this->is_404 = true;

		$this->is_feed = $is_feed;

		/**
		 * Fires after a 404 is triggered.
		 *
		 * @since 5.5.0
		 *
		 * @param WP_Query $query The WP_Query instance (passed by reference).
		 */
		do_action_ref_array( 'set_404', array( $this ) );
	}

	/**
	 * Retrieves the value of a query variable.
	 *
	 * @since 1.5.0
	 * @since 3.9.0 The `$default_value` argument was introduced.
	 *
	 * @param string $query_var     Query variable key.
	 * @param mixed  $default_value Optional. Value to return if the query variable is not set.
	 *                              Default empty string.
	 * @return mixed Contents of the query variable.
	 */
	public function get( $query_var, $default_value = '' ) {
		if ( isset( $this->query_vars[ $query_var ] ) ) {
			return $this->query_vars[ $query_var ];
		}

		return $default_value;
	}

	/**
	 * Sets the value of a query variable.
	 *
	 * @since 1.5.0
	 *
	 * @param string $query_var Query variable key.
	 * @param mixed  $value     Query variable value.
	 */
	public function set( $query_var, $value ) {
		$this->query_vars[ $query_var ] = $value;
	}

	/**
	 * Retrieves an array of posts based on query variables.
	 *
	 * There are a few filters and actions that can be used to modify the post
	 * database query.
	 *
	 * @since 1.5.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @return WP_Post[]|int[] Array of post objects or post IDs.
	 */
	public function get_posts() {
		global $wpdb;

		$this->parse_query();

		/**
		 * Fires after the query variable object is created, but before the actual query is run.
		 *
		 * Note: If using conditional tags, use the method versions within the passed instance
		 * (e.g. $this->is_main_query() instead of is_main_query()). This is because the functions
		 * like is_main_query() test against the global $wp_query instance, not the passed one.
		 *
		 * @since 2.0.0
		 *
		 * @param WP_Query $query The WP_Query instance (passed by reference).
		 */
		do_action_ref_array( 'pre_get_posts', array( &$this ) );

		// Shorthand.
		$q = &$this->query_vars;

		// Fill again in case 'pre_get_posts' unset some vars.
		$q = $this->fill_query_vars( $q );

		/**
		 * Filters whether an attachment query should include filenames or not.
		 *
		 * @since 6.0.3
		 *
		 * @param bool $allow_query_attachment_by_filename Whether or not to include filenames.
		 */
		$this->allow_query_attachment_by_filename = apply_filters( 'wp_allow_query_attachment_by_filename', false );
		remove_all_filters( 'wp_allow_query_attachment_by_filename' );

		// Parse meta query.
		$this->meta_query = new WP_Meta_Query();
		$this->meta_query->parse_query_vars( $q );

		// Set a flag if a 'pre_get_posts' hook changed the query vars.
		$hash = md5( serialize( $this->query_vars ) );
		if ( $hash !== $this->query_vars_hash ) {
			$this->query_vars_changed = true;
			$this->query_vars_hash    = $hash;
		}
		unset( $hash );

		// First let's clear some variables.
		$distinct         = '';
		$whichauthor      = '';
		$whichmimetype    = '';
		$where            = '';
		$limits           = '';
		$join             = '';
		$search           = '';
		$groupby          = '';
		$post_status_join = false;
		$page             = 1;

		if ( isset( $q['caller_get_posts'] ) ) {
			_deprecated_argument(
				'WP_Query',
				'3.1.0',
				sprintf(
					/* translators: 1: caller_get_posts, 2: ignore_sticky_posts */
					__( '%1$s is deprecated. Use %2$s instead.' ),
					'<code>caller_get_posts</code>',
					'<code>ignore_sticky_posts</code>'
				)
			);

			if ( ! isset( $q['ignore_sticky_posts'] ) ) {
				$q['ignore_sticky_posts'] = $q['caller_get_posts'];
			}
		}

		if ( ! isset( $q['ignore_sticky_posts'] ) ) {
			$q['ignore_sticky_posts'] = false;
		}

		if ( ! isset( $q['suppress_filters'] ) ) {
			$q['suppress_filters'] = false;
		}

		if ( ! isset( $q['cache_results'] ) ) {
			$q['cache_results'] = true;
		}

		if ( ! isset( $q['update_post_term_cache'] ) ) {
			$q['update_post_term_cache'] = true;
		}

		if ( ! isset( $q['update_menu_item_cache'] ) ) {
			$q['update_menu_item_cache'] = false;
		}

		if ( ! isset( $q['lazy_load_term_meta'] ) ) {
			$q['lazy_load_term_meta'] = $q['update_post_term_cache'];
		} elseif ( $q['lazy_load_term_meta'] ) { // Lazy loading term meta only works if term caches are primed.
			$q['update_post_term_cache'] = true;
		}

		if ( ! isset( $q['update_post_meta_cache'] ) ) {
			$q['update_post_meta_cache'] = true;
		}

		if ( ! isset( $q['post_type'] ) ) {
			if ( $this->is_search ) {
				$q['post_type'] = 'any';
			} else {
				$q['post_type'] = '';
			}
		}
		$post_type = $q['post_type'];
		if ( empty( $q['posts_per_page'] ) ) {
			$q['posts_per_page'] = get_option( 'posts_per_page' );
		}
		if ( isset( $q['showposts'] ) && $q['showposts'] ) {
			$q['showposts']      = (int) $q['showposts'];
			$q['posts_per_page'] = $q['showposts'];
		}
		if ( ( isset( $q['posts_per_archive_page'] ) && 0 != $q['posts_per_archive_page'] ) && ( $this->is_archive || $this->is_search ) ) {
			$q['posts_per_page'] = $q['posts_per_archive_page'];
		}
		if ( ! isset( $q['nopaging'] ) ) {
			if ( -1 == $q['posts_per_page'] ) {
				$q['nopaging'] = true;
			} else {
				$q['nopaging'] = false;
			}
		}

		if ( $this->is_feed ) {
			// This overrides 'posts_per_page'.
			if ( ! empty( $q['posts_per_rss'] ) ) {
				$q['posts_per_page'] = $q['posts_per_rss'];
			} else {
				$q['posts_per_page'] = get_option( 'posts_per_rss' );
			}
			$q['nopaging'] = false;
		}

		$q['posts_per_page'] = (int) $q['posts_per_page'];
		if ( $q['posts_per_page'] < -1 ) {
			$q['posts_per_page'] = abs( $q['posts_per_page'] );
		} elseif ( 0 === $q['posts_per_page'] ) {
			$q['posts_per_page'] = 1;
		}

		if ( ! isset( $q['comments_per_page'] ) || 0 == $q['comments_per_page'] ) {
			$q['comments_per_page'] = get_option( 'comments_per_page' );
		}

		if ( $this->is_home && ( empty( $this->query ) || 'true' === $q['preview'] ) && ( 'page' === get_option( 'show_on_front' ) ) && get_option( 'page_on_front' ) ) {
			$this->is_page = true;
			$this->is_home = false;
			$q['page_id']  = get_option( 'page_on_front' );
		}

		if ( isset( $q['page'] ) ) {
			$q['page'] = is_scalar( $q['page'] ) ? absint( trim( $q['page'], '/' ) ) : 0;
		}

		// If true, forcibly turns off SQL_CALC_FOUND_ROWS even when limits are present.
		if ( isset( $q['no_found_rows'] ) ) {
			$q['no_found_rows'] = (bool) $q['no_found_rows'];
		} else {
			$q['no_found_rows'] = false;
		}

		switch ( $q['fields'] ) {
			case 'ids':
				$fields = "{$wpdb->posts}.ID";
				break;
			case 'id=>parent':
				$fields = "{$wpdb->posts}.ID, {$wpdb->posts}.post_parent";
				break;
			case '':
				/*
				 * Set the default to 'all'.
				 *
				 * This is used in `WP_Query::the_post` to determine if the
				 * entire post object has been queried.
				 */
				$q['fields'] = 'all';
				// Falls through.
			default:
				$fields = "{$wpdb->posts}.*";
		}

		if ( '' !== $q['menu_order'] ) {
			$where .= " AND {$wpdb->posts}.menu_order = " . $q['menu_order'];
		}
		// The "m" parameter is meant for months but accepts datetimes of varying specificity.
		if ( $q['m'] ) {
			$where .= " AND YEAR({$wpdb->posts}.post_date)=" . substr( $q['m'], 0, 4 );
			if ( strlen( $q['m'] ) > 5 ) {
				$where .= " AND MONTH({$wpdb->posts}.post_date)=" . substr( $q['m'], 4, 2 );
			}
			if ( strlen( $q['m'] ) > 7 ) {
				$where .= " AND DAYOFMONTH({$wpdb->posts}.post_date)=" . substr( $q['m'], 6, 2 );
			}
			if ( strlen( $q['m'] ) > 9 ) {
				$where .= " AND HOUR({$wpdb->posts}.post_date)=" . substr( $q['m'], 8, 2 );
			}
			if ( strlen( $q['m'] ) > 11 ) {
				$where .= " AND MINUTE({$wpdb->posts}.post_date)=" . substr( $q['m'], 10, 2 );
			}
			if ( strlen( $q['m'] ) > 13 ) {
				$where .= " AND SECOND({$wpdb->posts}.post_date)=" . substr( $q['m'], 12, 2 );
			}
		}

		// Handle the other individual date parameters.
		$date_parameters = array();

		if ( '' !== $q['hour'] ) {
			$date_parameters['hour'] = $q['hour'];
		}

		if ( '' !== $q['minute'] ) {
			$date_parameters['minute'] = $q['minute'];
		}

		if ( '' !== $q['second'] ) {
			$date_parameters['second'] = $q['second'];
		}

		if ( $q['year'] ) {
			$date_parameters['year'] = $q['year'];
		}

		if ( $q['monthnum'] ) {
			$date_parameters['monthnum'] = $q['monthnum'];
		}

		if ( $q['w'] ) {
			$date_parameters['week'] = $q['w'];
		}

		if ( $q['day'] ) {
			$date_parameters['day'] = $q['day'];
		}

		if ( $date_parameters ) {
			$date_query = new WP_Date_Query( array( $date_parameters ) );
			$where     .= $date_query->get_sql();
		}
		unset( $date_parameters, $date_query );

		// Handle complex date queries.
		if ( ! empty( $q['date_query'] ) ) {
			$this->date_query = new WP_Date_Query( $q['date_query'] );
			$where           .= $this->date_query->get_sql();
		}

		// If we've got a post_type AND it's not "any" post_type.
		if ( ! empty( $q['post_type'] ) && 'any' !== $q['post_type'] ) {
			foreach ( (array) $q['post_type'] as $_post_type ) {
				$ptype_obj = get_post_type_object( $_post_type );
				if ( ! $ptype_obj || ! $ptype_obj->query_var || empty( $q[ $ptype_obj->query_var ] ) ) {
					continue;
				}

				if ( ! $ptype_obj->hierarchical ) {
					// Non-hierarchical post types can directly use 'name'.
					$q['name'] = $q[ $ptype_obj->query_var ];
				} else {
					// Hierarchical post types will operate through 'pagename'.
					$q['pagename'] = $q[ $ptype_obj->query_var ];
					$q['name']     = '';
				}

				// Only one request for a slug is possible, this is why name & pagename are overwritten above.
				break;
			} // End foreach.
			unset( $ptype_obj );
		}

		if ( '' !== $q['title'] ) {
			$where .= $wpdb->prepare( " AND {$wpdb->posts}.post_title = %s", stripslashes( $q['title'] ) );
		}

		// Parameters related to 'post_name'.
		if ( '' !== $q['name'] ) {
			$q['name'] = sanitize_title_for_query( $q['name'] );
			$where    .= " AND {$wpdb->posts}.post_name = '" . $q['name'] . "'";
		} elseif ( '' !== $q['pagename'] ) {
			if ( isset( $this->queried_object_id ) ) {
				$reqpage = $this->queried_object_id;
			} else {
				if ( 'page' !== $q['post_type'] ) {
					foreach ( (array) $q['post_type'] as $_post_type ) {
						$ptype_obj = get_post_type_object( $_post_type );
						if ( ! $ptype_obj || ! $ptype_obj->hierarchical ) {
							continue;
						}

						$reqpage = get_page_by_path( $q['pagename'], OBJECT, $_post_type );
						if ( $reqpage ) {
							break;
						}
					}
					unset( $ptype_obj );
				} else {
					$reqpage = get_page_by_path( $q['pagename'] );
				}
				if ( ! empty( $reqpage ) ) {
					$reqpage = $reqpage->ID;
				} else {
					$reqpage = 0;
				}
			}

			$page_for_posts = get_option( 'page_for_posts' );
			if ( ( 'page' !== get_option( 'show_on_front' ) ) || empty( $page_for_posts ) || ( $reqpage != $page_for_posts ) ) {
				$q['pagename'] = sanitize_title_for_query( wp_basename( $q['pagename'] ) );
				$q['name']     = $q['pagename'];
				$where        .= " AND ({$wpdb->posts}.ID = '$reqpage')";
				$reqpage_obj   = get_post( $reqpage );
				if ( is_object( $reqpage_obj ) && 'attachment' === $reqpage_obj->post_type ) {
					$this->is_attachment = true;
					$post_type           = 'attachment';
					$q['post_type']      = 'attachment';
					$this->is_page       = true;
					$q['attachment_id']  = $reqpage;
				}
			}
		} elseif ( '' !== $q['attachment'] ) {
			$q['attachment'] = sanitize_title_for_query( wp_basename( $q['attachment'] ) );
			$q['name']       = $q['attachment'];
			$where          .= " AND {$wpdb->posts}.post_name = '" . $q['attachment'] . "'";
		} elseif ( is_array( $q['post_name__in'] ) && ! empty( $q['post_name__in'] ) ) {
			$q['post_name__in'] = array_map( 'sanitize_title_for_query', $q['post_name__in'] );
			// Duplicate array before sorting to allow for the orderby clause.
			$post_name__in_for_where = array_unique( $q['post_name__in'] );
			sort( $post_name__in_for_where );
			$post_name__in = "'" . implode( "','", $post_name__in_for_where ) . "'";
			$where        .= " AND {$wpdb->posts}.post_name IN ($post_name__in)";
		}

		// If an attachment is requested by number, let it supersede any post number.
		if ( $q['attachment_id'] ) {
			$q['p'] = absint( $q['attachment_id'] );
		}

		// If a post number is specified, load that post.
		if ( $q['p'] ) {
			$where .= " AND {$wpdb->posts}.ID = " . $q['p'];
		} elseif ( $q['post__in'] ) {
			// Duplicate array before sorting to allow for the orderby clause.
			$post__in_for_where = $q['post__in'];
			$post__in_for_where = array_unique( array_map( 'absint', $post__in_for_where ) );
			sort( $post__in_for_where );
			$post__in = implode( ',', array_map( 'absint', $post__in_for_where ) );
			$where   .= " AND {$wpdb->posts}.ID IN ($post__in)";
		} elseif ( $q['post__not_in'] ) {
			sort( $q['post__not_in'] );
			$post__not_in = implode( ',', array_map( 'absint', $q['post__not_in'] ) );
			$where       .= " AND {$wpdb->posts}.ID NOT IN ($post__not_in)";
		}

		if ( is_numeric( $q['post_parent'] ) ) {
			$where .= $wpdb->prepare( " AND {$wpdb->posts}.post_parent = %d ", $q['post_parent'] );
		} elseif ( $q['post_parent__in'] ) {
			// Duplicate array before sorting to allow for the orderby clause.
			$post_parent__in_for_where = $q['post_parent__in'];
			$post_parent__in_for_where = array_unique( array_map( 'absint', $post_parent__in_for_where ) );
			sort( $post_parent__in_for_where );
			$post_parent__in = implode( ',', array_map( 'absint', $post_parent__in_for_where ) );
			$where          .= " AND {$wpdb->posts}.post_parent IN ($post_parent__in)";
		} elseif ( $q['post_parent__not_in'] ) {
			sort( $q['post_parent__not_in'] );
			$post_parent__not_in = implode( ',', array_map( 'absint', $q['post_parent__not_in'] ) );
			$where              .= " AND {$wpdb->posts}.post_parent NOT IN ($post_parent__not_in)";
		}

		if ( $q['page_id'] ) {
			if ( ( 'page' !== get_option( 'show_on_front' ) ) || ( get_option( 'page_for_posts' ) != $q['page_id'] ) ) {
				$q['p'] = $q['page_id'];
				$where  = " AND {$wpdb->posts}.ID = " . $q['page_id'];
			}
		}

		// If a search pattern is specified, load the posts that match.
		if ( strlen( $q['s'] ) ) {
			$search = $this->parse_search( $q );
		}

		if ( ! $q['suppress_filters'] ) {
			/**
			 * Filters the search SQL that is used in the WHERE clause of WP_Query.
			 *
			 * @since 3.0.0
			 *
			 * @param string   $search Search SQL for WHERE clause.
			 * @param WP_Query $query  The current WP_Query object.
			 */
			$search = apply_filters_ref_array( 'posts_search', array( $search, &$this ) );
		}

		// Taxonomies.
		if ( ! $this->is_singular ) {
			$this->parse_tax_query( $q );

			$clauses = $this->tax_query->get_sql( $wpdb->posts, 'ID' );

			$join  .= $clauses['join'];
			$where .= $clauses['where'];
		}

		if ( $this->is_tax ) {
			if ( empty( $post_type ) ) {
				// Do a fully inclusive search for currently registered post types of queried taxonomies.
				$post_type  = array();
				$taxonomies = array_keys( $this->tax_query->queried_terms );
				foreach ( get_post_types( array( 'exclude_from_search' => false ) ) as $pt ) {
					$object_taxonomies = 'attachment' === $pt ? get_taxonomies_for_attachments() : get_object_taxonomies( $pt );
					if ( array_intersect( $taxonomies, $object_taxonomies ) ) {
						$post_type[] = $pt;
					}
				}
				if ( ! $post_type ) {
					$post_type = 'any';
				} elseif ( count( $post_type ) === 1 ) {
					$post_type = $post_type[0];
				} else {
					// Sort post types to ensure same cache key generation.
					sort( $post_type );
				}

				$post_status_join = true;
			} elseif ( in_array( 'attachment', (array) $post_type, true ) ) {
				$post_status_join = true;
			}
		}

		/*
		 * Ensure that 'taxonomy', 'term', 'term_id', 'cat', and
		 * 'category_name' vars are set for backward compatibility.
		 */
		if ( ! empty( $this->tax_query->queried_terms ) ) {

			/*
			 * Set 'taxonomy', 'term', and 'term_id' to the
			 * first taxonomy other than 'post_tag' or 'category'.
			 */
			if ( ! isset( $q['taxonomy'] ) ) {
				foreach ( $this->tax_query->queried_terms as $queried_taxonomy => $queried_items ) {
					if ( empty( $queried_items['terms'][0] ) ) {
						continue;
					}

					if ( ! in_array( $queried_taxonomy, array( 'category', 'post_tag' ), true ) ) {
						$q['taxonomy'] = $queried_taxonomy;

						if ( 'slug' === $queried_items['field'] ) {
							$q['term'] = $queried_items['terms'][0];
						} else {
							$q['term_id'] = $queried_items['terms'][0];
						}

						// Take the first one we find.
						break;
					}
				}
			}

			// 'cat', 'category_name', 'tag_id'.
			foreach ( $this->tax_query->queried_terms as $queried_taxonomy => $queried_items ) {
				if ( empty( $queried_items['terms'][0] ) ) {
					continue;
				}

				if ( 'category' === $queried_taxonomy ) {
					$the_cat = get_term_by( $queried_items['field'], $queried_items['terms'][0], 'category' );
					if ( $the_cat ) {
						$this->set( 'cat', $the_cat->term_id );
						$this->set( 'category_name', $the_cat->slug );
					}
					unset( $the_cat );
				}

				if ( 'post_tag' === $queried_taxonomy ) {
					$the_tag = get_term_by( $queried_items['field'], $queried_items['terms'][0], 'post_tag' );
					if ( $the_tag ) {
						$this->set( 'tag_id', $the_tag->term_id );
					}
					unset( $the_tag );
				}
			}
		}

		if ( ! empty( $this->tax_query->queries ) || ! empty( $this->meta_query->queries ) || ! empty( $this->allow_query_attachment_by_filename ) ) {
			$groupby = "{$wpdb->posts}.ID";
		}

		// Author/user stuff.

		if ( ! empty( $q['author'] ) && '0' != $q['author'] ) {
			$q['author'] = addslashes_gpc( '' . urldecode( $q['author'] ) );
			$authors     = array_unique( array_map( 'intval', preg_split( '/[,\s]+/', $q['author'] ) ) );
			sort( $authors );
			foreach ( $authors as $author ) {
				$key         = $author > 0 ? 'author__in' : 'author__not_in';
				$q[ $key ][] = abs( $author );
			}
			$q['author'] = implode( ',', $authors );
		}

		if ( ! empty( $q['author__not_in'] ) ) {
			if ( is_array( $q['author__not_in'] ) ) {
				$q['author__not_in'] = array_unique( array_map( 'absint', $q['author__not_in'] ) );
				sort( $q['author__not_in'] );
			}
			$author__not_in = implode( ',', (array) $q['author__not_in'] );
			$where         .= " AND {$wpdb->posts}.post_author NOT IN ($author__not_in) ";
		} elseif ( ! empty( $q['author__in'] ) ) {
			if ( is_array( $q['author__in'] ) ) {
				$q['author__in'] = array_unique( array_map( 'absint', $q['author__in'] ) );
				sort( $q['author__in'] );
			}
			$author__in = implode( ',', array_map( 'absint', array_unique( (array) $q['author__in'] ) ) );
			$where     .= " AND {$wpdb->posts}.post_author IN ($author__in) ";
		}

		// Author stuff for nice URLs.

		if ( '' !== $q['author_name'] ) {
			if ( str_contains( $q['author_name'], '/' ) ) {
				$q['author_name'] = explode( '/', $q['author_name'] );
				if ( $q['author_name'][ count( $q['author_name'] ) - 1 ] ) {
					$q['author_name'] = $q['author_name'][ count( $q['author_name'] ) - 1 ]; // No trailing slash.
				} else {
					$q['author_name'] = $q['author_name'][ count( $q['author_name'] ) - 2 ]; // There was a trailing slash.
				}
			}
			$q['author_name'] = sanitize_title_for_query( $q['author_name'] );
			$q['author']      = get_user_by( 'slug', $q['author_name'] );
			if ( $q['author'] ) {
				$q['author'] = $q['author']->ID;
			}
			$whichauthor .= " AND ({$wpdb->posts}.post_author = " . absint( $q['author'] ) . ')';
		}

		// Matching by comment count.
		if ( isset( $q['comment_count'] ) ) {
			// Numeric comment count is converted to array format.
			if ( is_numeric( $q['comment_count'] ) ) {
				$q['comment_count'] = array(
					'value' => (int) $q['comment_count'],
				);
			}

			if ( isset( $q['comment_count']['value'] ) ) {
				$q['comment_count'] = array_merge(
					array(
						'compare' => '=',
					),
					$q['comment_count']
				);

				// Fallback for invalid compare operators is '='.
				$compare_operators = array( '=', '!=', '>', '>=', '<', '<=' );
				if ( ! in_array( $q['comment_count']['compare'], $compare_operators, true ) ) {
					$q['comment_count']['compare'] = '=';
				}

				$where .= $wpdb->prepare( " AND {$wpdb->posts}.comment_count {$q['comment_count']['compare']} %d", $q['comment_count']['value'] );
			}
		}

		// MIME-Type stuff for attachment browsing.

		if ( isset( $q['post_mime_type'] ) && '' !== $q['post_mime_type'] ) {
			$whichmimetype = wp_post_mime_type_where( $q['post_mime_type'], $wpdb->posts );
		}
		$where .= $search . $whichauthor . $whichmimetype;

		if ( ! empty( $this->allow_query_attachment_by_filename ) ) {
			$join .= " LEFT JOIN {$wpdb->postmeta} AS sq1 ON ( {$wpdb->posts}.ID = sq1.post_id AND sq1.meta_key = '_wp_attached_file' )";
		}

		if ( ! empty( $this->meta_query->queries ) ) {
			$clauses = $this->meta_query->get_sql( 'post', $wpdb->posts, 'ID', $this );
			$join   .= $clauses['join'];
			$where  .= $clauses['where'];
		}

		$rand = ( isset( $q['orderby'] ) && 'rand' === $q['orderby'] );
		if ( ! isset( $q['order'] ) ) {
			$q['order'] = $rand ? '' : 'DESC';
		} else {
			$q['order'] = $rand ? '' : $this->parse_order( $q['order'] );
		}

		// These values of orderby should ignore the 'order' parameter.
		$force_asc = array( 'post__in', 'post_name__in', 'post_parent__in' );
		if ( isset( $q['orderby'] ) && in_array( $q['orderby'], $force_asc, true ) ) {
			$q['order'] = '';
		}

		// Order by.
		if ( empty( $q['orderby'] ) ) {
			/*
			 * Boolean false or empty array blanks out ORDER BY,
			 * while leaving the value unset or otherwise empty sets the default.
			 */
			if ( isset( $q['orderby'] ) && ( is_array( $q['orderby'] ) || false === $q['orderby'] ) ) {
				$orderby = '';
			} else {
				$orderby = "{$wpdb->posts}.post_date " . $q['order'];
			}
		} elseif ( 'none' === $q['orderby'] ) {
			$orderby = '';
		} else {
			$orderby_array = array();
			if ( is_array( $q['orderby'] ) ) {
				foreach ( $q['orderby'] as $_orderby => $order ) {
					$orderby = addslashes_gpc( urldecode( $_orderby ) );
					$parsed  = $this->parse_orderby( $orderby );

					if ( ! $parsed ) {
						continue;
					}

					$orderby_array[] = $parsed . ' ' . $this->parse_order( $order );
				}
				$orderby = implode( ', ', $orderby_array );

			} else {
				$q['orderby'] = urldecode( $q['orderby'] );
				$q['orderby'] = addslashes_gpc( $q['orderby'] );

				foreach ( explode( ' ', $q['orderby'] ) as $i => $orderby ) {
					$parsed = $this->parse_orderby( $orderby );
					// Only allow certain values for safety.
					if ( ! $parsed ) {
						continue;
					}

					$orderby_array[] = $parsed;
				}
				$orderby = implode( ' ' . $q['order'] . ', ', $orderby_array );

				if ( empty( $orderby ) ) {
					$orderby = "{$wpdb->posts}.post_date " . $q['order'];
				} elseif ( ! empty( $q['order'] ) ) {
					$orderby .= " {$q['order']}";
				}
			}
		}

		// Order search results by relevance only when another "orderby" is not specified in the query.
		if ( ! empty( $q['s'] ) ) {
			$search_orderby = '';
			if ( ! empty( $q['search_orderby_title'] ) && ( empty( $q['orderby'] ) && ! $this->is_feed ) || ( isset( $q['orderby'] ) && 'relevance' === $q['orderby'] ) ) {
				$search_orderby = $this->parse_search_order( $q );
			}

			if ( ! $q['suppress_filters'] ) {
				/**
				 * Filters the ORDER BY used when ordering search results.
				 *
				 * @since 3.7.0
				 *
				 * @param string   $search_orderby The ORDER BY clause.
				 * @param WP_Query $query          The current WP_Query instance.
				 */
				$search_orderby = apply_filters( 'posts_search_orderby', $search_orderby, $this );
			}

			if ( $search_orderby ) {
				$orderby = $orderby ? $search_orderby . ', ' . $orderby : $search_orderby;
			}
		}

		if ( is_array( $post_type ) && count( $post_type ) > 1 ) {
			$post_type_cap = 'multiple_post_type';
		} else {
			if ( is_array( $post_type ) ) {
				$post_type = reset( $post_type );
			}
			$post_type_object = get_post_type_object( $post_type );
			if ( empty( $post_type_object ) ) {
				$post_type_cap = $post_type;
			}
		}

		if ( isset( $q['post_password'] ) ) {
			$where .= $wpdb->prepare( " AND {$wpdb->posts}.post_password = %s", $q['post_password'] );
			if ( empty( $q['perm'] ) ) {
				$q['perm'] = 'readable';
			}
		} elseif ( isset( $q['has_password'] ) ) {
			$where .= sprintf( " AND {$wpdb->posts}.post_password %s ''", $q['has_password'] ? '!=' : '=' );
		}

		if ( ! empty( $q['comment_status'] ) ) {
			$where .= $wpdb->prepare( " AND {$wpdb->posts}.comment_status = %s ", $q['comment_status'] );
		}

		if ( ! empty( $q['ping_status'] ) ) {
			$where .= $wpdb->prepare( " AND {$wpdb->posts}.ping_status = %s ", $q['ping_status'] );
		}

		$skip_post_status = false;
		if ( 'any' === $post_type ) {
			$in_search_post_types = get_post_types( array( 'exclude_from_search' => false ) );
			if ( empty( $in_search_post_types ) ) {
				$post_type_where  = ' AND 1=0 ';
				$skip_post_status = true;
			} else {
				$post_type_where = " AND {$wpdb->posts}.post_type IN ('" . implode( "', '", array_map( 'esc_sql', $in_search_post_types ) ) . "')";
			}
		} elseif ( ! empty( $post_type ) && is_array( $post_type ) ) {
			// Sort post types to ensure same cache key generation.
			sort( $post_type );
			$post_type_where = " AND {$wpdb->posts}.post_type IN ('" . implode( "', '", esc_sql( $post_type ) ) . "')";
		} elseif ( ! empty( $post_type ) ) {
			$post_type_where  = $wpdb->prepare( " AND {$wpdb->posts}.post_type = %s", $post_type );
			$post_type_object = get_post_type_object( $post_type );
		} elseif ( $this->is_attachment ) {
			$post_type_where  = " AND {$wpdb->posts}.post_type = 'attachment'";
			$post_type_object = get_post_type_object( 'attachment' );
		} elseif ( $this->is_page ) {
			$post_type_where  = " AND {$wpdb->posts}.post_type = 'page'";
			$post_type_object = get_post_type_object( 'page' );
		} else {
			$post_type_where  = " AND {$wpdb->posts}.post_type = 'post'";
			$post_type_object = get_post_type_object( 'post' );
		}

		$edit_cap = 'edit_post';
		$read_cap = 'read_post';

		if ( ! empty( $post_type_object ) ) {
			$edit_others_cap  = $post_type_object->cap->edit_others_posts;
			$read_private_cap = $post_type_object->cap->read_private_posts;
		} else {
			$edit_others_cap  = 'edit_others_' . $post_type_cap . 's';
			$read_private_cap = 'read_private_' . $post_type_cap . 's';
		}

		$user_id = get_current_user_id();

		$q_status = array();
		if ( $skip_post_status ) {
			$where .= $post_type_where;
		} elseif ( ! empty( $q['post_status'] ) ) {

			$where .= $post_type_where;

			$statuswheres = array();
			$q_status     = $q['post_status'];
			if ( ! is_array( $q_status ) ) {
				$q_status = explode( ',', $q_status );
			}
			sort( $q_status );
			$r_status = array();
			$p_status = array();
			$e_status = array();
			if ( in_array( 'any', $q_status, true ) ) {
				foreach ( get_post_stati( array( 'exclude_from_search' => true ) ) as $status ) {
					if ( ! in_array( $status, $q_status, true ) ) {
						$e_status[] = "{$wpdb->posts}.post_status <> '$status'";
					}
				}
			} else {
				foreach ( get_post_stati() as $status ) {
					if ( in_array( $status, $q_status, true ) ) {
						if ( 'private' === $status ) {
							$p_status[] = "{$wpdb->posts}.post_status = '$status'";
						} else {
							$r_status[] = "{$wpdb->posts}.post_status = '$status'";
						}
					}
				}
			}

			if ( empty( $q['perm'] ) || 'readable' !== $q['perm'] ) {
				$r_status = array_merge( $r_status, $p_status );
				unset( $p_status );
			}

			if ( ! empty( $e_status ) ) {
				$statuswheres[] = '(' . implode( ' AND ', $e_status ) . ')';
			}
			if ( ! empty( $r_status ) ) {
				if ( ! empty( $q['perm'] ) && 'editable' === $q['perm'] && ! current_user_can( $edit_others_cap ) ) {
					$statuswheres[] = "({$wpdb->posts}.post_author = $user_id " . 'AND (' . implode( ' OR ', $r_status ) . '))';
				} else {
					$statuswheres[] = '(' . implode( ' OR ', $r_status ) . ')';
				}
			}
			if ( ! empty( $p_status ) ) {
				if ( ! empty( $q['perm'] ) && 'readable' === $q['perm'] && ! current_user_can( $read_private_cap ) ) {
					$statuswheres[] = "({$wpdb->posts}.post_author = $user_id " . 'AND (' . implode( ' OR ', $p_status ) . '))';
				} else {
					$statuswheres[] = '(' . implode( ' OR ', $p_status ) . ')';
				}
			}
			if ( $post_status_join ) {
				$join .= " LEFT JOIN {$wpdb->posts} AS p2 ON ({$wpdb->posts}.post_parent = p2.ID) ";
				foreach ( $statuswheres as $index => $statuswhere ) {
					$statuswheres[ $index ] = "($statuswhere OR ({$wpdb->posts}.post_status = 'inherit' AND " . str_replace( $wpdb->posts, 'p2', $statuswhere ) . '))';
				}
			}
			$where_status = implode( ' OR ', $statuswheres );
			if ( ! empty( $where_status ) ) {
				$where .= " AND ($where_status)";
			}
		} elseif ( ! $this->is_singular ) {
			if ( 'any' === $post_type ) {
				$queried_post_types = get_post_types( array( 'exclude_from_search' => false ) );
			} elseif ( is_array( $post_type ) ) {
				$queried_post_types = $post_type;
			} elseif ( ! empty( $post_type ) ) {
				$queried_post_types = array( $post_type );
			} else {
				$queried_post_types = array( 'post' );
			}

			if ( ! empty( $queried_post_types ) ) {
				sort( $queried_post_types );
				$status_type_clauses = array();

				foreach ( $queried_post_types as $queried_post_type ) {

					$queried_post_type_object = get_post_type_object( $queried_post_type );

					$type_where = '(' . $wpdb->prepare( "{$wpdb->posts}.post_type = %s AND (", $queried_post_type );

					// Public statuses.
					$public_statuses = get_post_stati( array( 'public' => true ) );
					$status_clauses  = array();
					foreach ( $public_statuses as $public_status ) {
						$status_clauses[] = "{$wpdb->posts}.post_status = '$public_status'";
					}
					$type_where .= implode( ' OR ', $status_clauses );

					// Add protected states that should show in the admin all list.
					if ( $this->is_admin ) {
						$admin_all_statuses = get_post_stati(
							array(
								'protected'              => true,
								'show_in_admin_all_list' => true,
							)
						);
						foreach ( $admin_all_statuses as $admin_all_status ) {
							$type_where .= " OR {$wpdb->posts}.post_status = '$admin_all_status'";
						}
					}

					// Add private states that are visible to current user.
					if ( is_user_logged_in() && $queried_post_type_object instanceof WP_Post_Type ) {
						$read_private_cap = $queried_post_type_object->cap->read_private_posts;
						$private_statuses = get_post_stati( array( 'private' => true ) );
						foreach ( $private_statuses as $private_status ) {
							$type_where .= current_user_can( $read_private_cap ) ? " \nOR {$wpdb->posts}.post_status = '$private_status'" : " \nOR ({$wpdb->posts}.post_author = $user_id AND {$wpdb->posts}.post_status = '$private_status')";
						}
					}

					$type_where .= '))';

					$status_type_clauses[] = $type_where;
				}

				if ( ! empty( $status_type_clauses ) ) {
					$where .= ' AND (' . implode( ' OR ', $status_type_clauses ) . ')';
				}
			} else {
				$where .= ' AND 1=0 ';
			}
		} else {
			$where .= $post_type_where;
		}

		/*
		 * Apply filters on where and join prior to paging so that any
		 * manipulations to them are reflected in the paging by day queries.
		 */
		if ( ! $q['suppress_filters'] ) {
			/**
			 * Filters the WHERE clause of the query.
			 *
			 * @since 1.5.0
			 *
			 * @param string   $where The WHERE clause of the query.
			 * @param WP_Query $query The WP_Query instance (passed by reference).
			 */
			$where = apply_filters_ref_array( 'posts_where', array( $where, &$this ) );

			/**
			 * Filters the JOIN clause of the query.
			 *
			 * @since 1.5.0
			 *
			 * @param string   $join  The JOIN clause of the query.
			 * @param WP_Query $query The WP_Query instance (passed by reference).
			 */
			$join = apply_filters_ref_array( 'posts_join', array( $join, &$this ) );
		}

		// Paging.
		if ( empty( $q['nopaging'] ) && ! $this->is_singular ) {
			$page = absint( $q['paged'] );
			if ( ! $page ) {
				$page = 1;
			}

			// If 'offset' is provided, it takes precedence over 'paged'.
			if ( isset( $q['offset'] ) && is_numeric( $q['offset'] ) ) {
				$q['offset'] = absint( $q['offset'] );
				$pgstrt      = $q['offset'] . ', ';
			} else {
				$pgstrt = absint( ( $page - 1 ) * $q['posts_per_page'] ) . ', ';
			}
			$limits = 'LIMIT ' . $pgstrt . $q['posts_per_page'];
		}

		// Comments feeds.
		if ( $this->is_comment_feed && ! $this->is_singular ) {
			if ( $this->is_archive || $this->is_search ) {
				$cjoin    = "JOIN {$wpdb->posts} ON ( {$wpdb->comments}.comment_post_ID = {$wpdb->posts}.ID ) $join ";
				$cwhere   = "WHERE comment_approved = '1' $where";
				$cgroupby = "{$wpdb->comments}.comment_id";
			} else { // Other non-singular, e.g. front.
				$cjoin    = "JOIN {$wpdb->posts} ON ( {$wpdb->comments}.comment_post_ID = {$wpdb->posts}.ID )";
				$cwhere   = "WHERE ( post_status = 'publish' OR ( post_status = 'inherit' AND post_type = 'attachment' ) ) AND comment_approved = '1'";
				$cgroupby = '';
			}

			if ( ! $q['suppress_filters'] ) {
				/**
				 * Filters the JOIN clause of the comments feed query before sending.
				 *
				 * @since 2.2.0
				 *
				 * @param string   $cjoin The JOIN clause of the query.
				 * @param WP_Query $query The WP_Query instance (passed by reference).
				 */
				$cjoin = apply_filters_ref_array( 'comment_feed_join', array( $cjoin, &$this ) );

				/**
				 * Filters the WHERE clause of the comments feed query before sending.
				 *
				 * @since 2.2.0
				 *
				 * @param string   $cwhere The WHERE clause of the query.
				 * @param WP_Query $query  The WP_Query instance (passed by reference).
				 */
				$cwhere = apply_filters_ref_array( 'comment_feed_where', array( $cwhere, &$this ) );

				/**
				 * Filters the GROUP BY clause of the comments feed query before sending.
				 *
				 * @since 2.2.0
				 *
				 * @param string   $cgroupby The GROUP BY clause of the query.
				 * @param WP_Query $query    The WP_Query instance (passed by reference).
				 */
				$cgroupby = apply_filters_ref_array( 'comment_feed_groupby', array( $cgroupby, &$this ) );

				/**
				 * Filters the ORDER BY clause of the comments feed query before sending.
				 *
				 * @since 2.8.0
				 *
				 * @param string   $corderby The ORDER BY clause of the query.
				 * @param WP_Query $query    The WP_Query instance (passed by reference).
				 */
				$corderby = apply_filters_ref_array( 'comment_feed_orderby', array( 'comment_date_gmt DESC', &$this ) );

				/**
				 * Filters the LIMIT clause of the comments feed query before sending.
				 *
				 * @since 2.8.0
				 *
				 * @param string   $climits The JOIN clause of the query.
				 * @param WP_Query $query   The WP_Query instance (passed by reference).
				 */
				$climits = apply_filters_ref_array( 'comment_feed_limits', array( 'LIMIT ' . get_option( 'posts_per_rss' ), &$this ) );
			}

			$cgroupby = ( ! empty( $cgroupby ) ) ? 'GROUP BY ' . $cgroupby : '';
			$corderby = ( ! empty( $corderby ) ) ? 'ORDER BY ' . $corderby : '';
			$climits  = ( ! empty( $climits ) ) ? $climits : '';

			$comments_request = "SELECT $distinct {$wpdb->comments}.comment_ID FROM {$wpdb->comments} $cjoin $cwhere $cgroupby $corderby $climits";

			$key          = md5( $comments_request );
			$last_changed = wp_cache_get_last_changed( 'comment' ) . ':' . wp_cache_get_last_changed( 'posts' );

			$cache_key   = "comment_feed:$key:$last_changed";
			$comment_ids = wp_cache_get( $cache_key, 'comment-queries' );
			if ( false === $comment_ids ) {
				$comment_ids = $wpdb->get_col( $comments_request );
				wp_cache_add( $cache_key, $comment_ids, 'comment-queries' );
			}
			_prime_comment_caches( $comment_ids );

			// Convert to WP_Comment.
			/** @var WP_Comment[] */
			$this->comments      = array_map( 'get_comment', $comment_ids );
			$this->comment_count = count( $this->comments );

			$post_ids = array();

			foreach ( $this->comments as $comment ) {
				$post_ids[] = (int) $comment->comment_post_ID;
			}

			$post_ids = implode( ',', $post_ids );
			$join     = '';
			if ( $post_ids ) {
				$where = "AND {$wpdb->posts}.ID IN ($post_ids) ";
			} else {
				$where = 'AND 0';
			}
		}

		$pieces = array( 'where', 'groupby', 'join', 'orderby', 'distinct', 'fields', 'limits' );

		/*
		 * Apply post-paging filters on where and join. Only plugins that
		 * manipulate paging queries should use these hooks.
		 */
		if ( ! $q['suppress_filters'] ) {
			/**
			 * Filters the WHERE clause of the query.
			 *
			 * Specifically for manipulating paging queries.
			 *
			 * @since 1.5.0
			 *
			 * @param string   $where The WHERE clause of the query.
			 * @param WP_Query $query The WP_Query instance (passed by reference).
			 */
			$where = apply_filters_ref_array( 'posts_where_paged', array( $where, &$this ) );

			/**
			 * Filters the GROUP BY clause of the query.
			 *
			 * @since 2.0.0
			 *
			 * @param string   $groupby The GROUP BY clause of the query.
			 * @param WP_Query $query   The WP_Query instance (passed by reference).
			 */
			$groupby = apply_filters_ref_array( 'posts_groupby', array( $groupby, &$this ) );

			/**
			 * Filters the JOIN clause of the query.
			 *
			 * Specifically for manipulating paging queries.
			 *
			 * @since 1.5.0
			 *
			 * @param string   $join  The JOIN clause of the query.
			 * @param WP_Query $query The WP_Query instance (passed by reference).
			 */
			$join = apply_filters_ref_array( 'posts_join_paged', array( $join, &$this ) );

			/**
			 * Filters the ORDER BY clause of the query.
			 *
			 * @since 1.5.1
			 *
			 * @param string   $orderby The ORDER BY clause of the query.
			 * @param WP_Query $query   The WP_Query instance (passed by reference).
			 */
			$orderby = apply_filters_ref_array( 'posts_orderby', array( $orderby, &$this ) );

			/**
			 * Filters the DISTINCT clause of the query.
			 *
			 * @since 2.1.0
			 *
			 * @param string   $distinct The DISTINCT clause of the query.
			 * @param WP_Query $query    The WP_Query instance (passed by reference).
			 */
			$distinct = apply_filters_ref_array( 'posts_distinct', array( $distinct, &$this ) );

			/**
			 * Filters the LIMIT clause of the query.
			 *
			 * @since 2.1.0
			 *
			 * @param string   $limits The LIMIT clause of the query.
			 * @param WP_Query $query  The WP_Query instance (passed by reference).
			 */
			$limits = apply_filters_ref_array( 'post_limits', array( $limits, &$this ) );

			/**
			 * Filters the SELECT clause of the query.
			 *
			 * @since 2.1.0
			 *
			 * @param string   $fields The SELECT clause of the query.
			 * @param WP_Query $query  The WP_Query instance (passed by reference).
			 */
			$fields = apply_filters_ref_array( 'posts_fields', array( $fields, &$this ) );

			/**
			 * Filters all query clauses at once, for convenience.
			 *
			 * Covers the WHERE, GROUP BY, JOIN, ORDER BY, DISTINCT,
			 * fields (SELECT), and LIMIT clauses.
			 *
			 * @since 3.1.0
			 *
			 * @param string[] $clauses {
			 *     Associative array of the clauses for the query.
			 *
			 *     @type string $where    The WHERE clause of the query.
			 *     @type string $groupby  The GROUP BY clause of the query.
			 *     @type string $join     The JOIN clause of the query.
			 *     @type string $orderby  The ORDER BY clause of the query.
			 *     @type string $distinct The DISTINCT clause of the query.
			 *     @type string $fields   The SELECT clause of the query.
			 *     @type string $limits   The LIMIT clause of the query.
			 * }
			 * @param WP_Query $query   The WP_Query instance (passed by reference).
			 */
			$clauses = (array) apply_filters_ref_array( 'posts_clauses', array( compact( $pieces ), &$this ) );

			$where    = isset( $clauses['where'] ) ? $clauses['where'] : '';
			$groupby  = isset( $clauses['groupby'] ) ? $clauses['groupby'] : '';
			$join     = isset( $clauses['join'] ) ? $clauses['join'] : '';
			$orderby  = isset( $clauses['orderby'] ) ? $clauses['orderby'] : '';
			$distinct = isset( $clauses['distinct'] ) ? $clauses['distinct'] : '';
			$fields   = isset( $clauses['fields'] ) ? $clauses['fields'] : '';
			$limits   = isset( $clauses['limits'] ) ? $clauses['limits'] : '';
		}

		/**
		 * Fires to announce the query's current selection parameters.
		 *
		 * For use by caching plugins.
		 *
		 * @since 2.3.0
		 *
		 * @param string $selection The assembled selection query.
		 */
		do_action( 'posts_selection', $where . $groupby . $orderby . $limits . $join );

		/*
		 * Filters again for the benefit of caching plugins.
		 * Regular plugins should use the hooks above.
		 */
		if ( ! $q['suppress_filters'] ) {
			/**
			 * Filters the WHERE clause of the query.
			 *
			 * For use by caching plugins.
			 *
			 * @since 2.5.0
			 *
			 * @param string   $where The WHERE clause of the query.
			 * @param WP_Query $query The WP_Query instance (passed by reference).
			 */
			$where = apply_filters_ref_array( 'posts_where_request', array( $where, &$this ) );

			/**
			 * Filters the GROUP BY clause of the query.
			 *
			 * For use by caching plugins.
			 *
			 * @since 2.5.0
			 *
			 * @param string   $groupby The GROUP BY clause of the query.
			 * @param WP_Query $query   The WP_Query instance (passed by reference).
			 */
			$groupby = apply_filters_ref_array( 'posts_groupby_request', array( $groupby, &$this ) );

			/**
			 * Filters the JOIN clause of the query.
			 *
			 * For use by caching plugins.
			 *
			 * @since 2.5.0
			 *
			 * @param string   $join  The JOIN clause of the query.
			 * @param WP_Query $query The WP_Query instance (passed by reference).
			 */
			$join = apply_filters_ref_array( 'posts_join_request', array( $join, &$this ) );

			/**
			 * Filters the ORDER BY clause of the query.
			 *
			 * For use by caching plugins.
			 *
			 * @since 2.5.0
			 *
			 * @param string   $orderby The ORDER BY clause of the query.
			 * @param WP_Query $query   The WP_Query instance (passed by reference).
			 */
			$orderby = apply_filters_ref_array( 'posts_orderby_request', array( $orderby, &$this ) );

			/**
			 * Filters the DISTINCT clause of the query.
			 *
			 * For use by caching plugins.
			 *
			 * @since 2.5.0
			 *
			 * @param string   $distinct The DISTINCT clause of the query.
			 * @param WP_Query $query    The WP_Query instance (passed by reference).
			 */
			$distinct = apply_filters_ref_array( 'posts_distinct_request', array( $distinct, &$this ) );

			/**
			 * Filters the SELECT clause of the query.
			 *
			 * For use by caching plugins.
			 *
			 * @since 2.5.0
			 *
			 * @param string   $fields The SELECT clause of the query.
			 * @param WP_Query $query  The WP_Query instance (passed by reference).
			 */
			$fields = apply_filters_ref_array( 'posts_fields_request', array( $fields, &$this ) );

			/**
			 * Filters the LIMIT clause of the query.
			 *
			 * For use by caching plugins.
			 *
			 * @since 2.5.0
			 *
			 * @param string   $limits The LIMIT clause of the query.
			 * @param WP_Query $query  The WP_Query instance (passed by reference).
			 */
			$limits = apply_filters_ref_array( 'post_limits_request', array( $limits, &$this ) );

			/**
			 * Filters all query clauses at once, for convenience.
			 *
			 * For use by caching plugins.
			 *
			 * Covers the WHERE, GROUP BY, JOIN, ORDER BY, DISTINCT,
			 * fields (SELECT), and LIMIT clauses.
			 *
			 * @since 3.1.0
			 *
			 * @param string[] $clauses {
			 *     Associative array of the clauses for the query.
			 *
			 *     @type string $where    The WHERE clause of the query.
			 *     @type string $groupby  The GROUP BY clause of the query.
			 *     @type string $join     The JOIN clause of the query.
			 *     @type string $orderby  The ORDER BY clause of the query.
			 *     @type string $distinct The DISTINCT clause of the query.
			 *     @type string $fields   The SELECT clause of the query.
			 *     @type string $limits   The LIMIT clause of the query.
			 * }
			 * @param WP_Query $query  The WP_Query instance (passed by reference).
			 */
			$clauses = (array) apply_filters_ref_array( 'posts_clauses_request', array( compact( $pieces ), &$this ) );

			$where    = isset( $clauses['where'] ) ? $clauses['where'] : '';
			$groupby  = isset( $clauses['groupby'] ) ? $clauses['groupby'] : '';
			$join     = isset( $clauses['join'] ) ? $clauses['join'] : '';
			$orderby  = isset( $clauses['orderby'] ) ? $clauses['orderby'] : '';
			$distinct = isset( $clauses['distinct'] ) ? $clauses['distinct'] : '';
			$fields   = isset( $clauses['fields'] ) ? $clauses['fields'] : '';
			$limits   = isset( $clauses['limits'] ) ? $clauses['limits'] : '';
		}

		if ( ! empty( $groupby ) ) {
			$groupby = 'GROUP BY ' . $groupby;
		}
		if ( ! empty( $orderby ) ) {
			$orderby = 'ORDER BY ' . $orderby;
		}

		$found_rows = '';
		if ( ! $q['no_found_rows'] && ! empty( $limits ) ) {
			$found_rows = 'SQL_CALC_FOUND_ROWS';
		}

		/*
		 * Beginning of the string is on a new line to prevent leading whitespace.
		 *
		 * The additional indentation of subsequent lines is to ensure the SQL
		 * queries are identical to those generated when splitting queries. This
		 * improves caching of the query by ensuring the same cache key is
		 * generated for the same database queries functionally.
		 *
		 * See https://core.trac.wordpress.org/ticket/56841.
		 * See https://github.com/WordPress/wordpress-develop/pull/6393#issuecomment-2088217429
		 */
		$old_request =
			"SELECT $found_rows $distinct $fields
					 FROM {$wpdb->posts} $join
					 WHERE 1=1 $where
					 $groupby
					 $orderby
					 $limits";

		$this->request = $old_request;

		if ( ! $q['suppress_filters'] ) {
			/**
			 * Filters the completed SQL query before sending.
			 *
			 * @since 2.0.0
			 *
			 * @param string   $request The complete SQL query.
			 * @param WP_Query $query   The WP_Query instance (passed by reference).
			 */
			$this->request = apply_filters_ref_array( 'posts_request', array( $this->request, &$this ) );
		}

		/**
		 * Filters the posts array before the query takes place.
		 *
		 * Return a non-null value to bypass WordPress' default post queries.
		 *
		 * Filtering functions that require pagination information are encouraged to set
		 * the `found_posts` and `max_num_pages` properties of the WP_Query object,
		 * passed to the filter by reference. If WP_Query does not perform a database
		 * query, it will not have enough information to generate these values itself.
		 *
		 * @since 4.6.0
		 *
		 * @param WP_Post[]|int[]|null $posts Return an array of post data to short-circuit WP's query,
		 *                                    or null to allow WP to run its normal queries.
		 * @param WP_Query             $query The WP_Query instance (passed by reference).
		 */
		$this->posts = apply_filters_ref_array( 'posts_pre_query', array( null, &$this ) );

		/*
		 * Ensure the ID database query is able to be cached.
		 *
		 * Random queries are expected to have unpredictable results and
		 * cannot be cached. Note the space before `RAND` in the string
		 * search, that to ensure against a collision with another
		 * function.
		 *
		 * If `$fields` has been modified by the `posts_fields`,
		 * `posts_fields_request`, `post_clauses` or `posts_clauses_request`
		 * filters, then caching is disabled to prevent caching collisions.
		 */
		$id_query_is_cacheable = ! str_contains( strtoupper( $orderby ), ' RAND(' );

		$cacheable_field_values = array(
			"{$wpdb->posts}.*",
			"{$wpdb->posts}.ID, {$wpdb->posts}.post_parent",
			"{$wpdb->posts}.ID",
		);

		if ( ! in_array( $fields, $cacheable_field_values, true ) ) {
			$id_query_is_cacheable = false;
		}

		if ( $q['cache_results'] && $id_query_is_cacheable ) {
			$new_request = str_replace( $fields, "{$wpdb->posts}.*", $this->request );
			$cache_key   = $this->generate_cache_key( $q, $new_request );

			$cache_found = false;
			if ( null === $this->posts ) {
				$cached_results = wp_cache_get( $cache_key, 'post-queries', false, $cache_found );

				if ( $cached_results ) {
					/** @var int[] */
					$post_ids = array_map( 'intval', $cached_results['posts'] );

					$this->post_count    = count( $post_ids );
					$this->found_posts   = $cached_results['found_posts'];
					$this->max_num_pages = $cached_results['max_num_pages'];

					if ( 'ids' === $q['fields'] ) {
						$this->posts = $post_ids;

						return $this->posts;
					} elseif ( 'id=>parent' === $q['fields'] ) {
						_prime_post_parent_id_caches( $post_ids );

						$post_parent_cache_keys = array();
						foreach ( $post_ids as $post_id ) {
							$post_parent_cache_keys[] = 'post_parent:' . (string) $post_id;
						}

						/** @var int[] */
						$post_parents = wp_cache_get_multiple( $post_parent_cache_keys, 'posts' );

						foreach ( $post_parents as $cache_key => $post_parent ) {
							$obj              = new stdClass();
							$obj->ID          = (int) str_replace( 'post_parent:', '', $cache_key );
							$obj->post_parent = (int) $post_parent;

							$this->posts[] = $obj;
						}

						return $post_parents;
					} else {
						_prime_post_caches( $post_ids, $q['update_post_term_cache'], $q['update_post_meta_cache'] );
						/** @var WP_Post[] */
						$this->posts = array_map( 'get_post', $post_ids );
					}
				}
			}
		}

		if ( 'ids' === $q['fields'] ) {
			if ( null === $this->posts ) {
				$this->posts = $wpdb->get_col( $this->request );
			}

			/** @var int[] */
			$this->posts      = array_map( 'intval', $this->posts );
			$this->post_count = count( $this->posts );
			$this->set_found_posts( $q, $limits );

			if ( $q['cache_results'] && $id_query_is_cacheable ) {
				$cache_value = array(
					'posts'         => $this->posts,
					'found_posts'   => $this->found_posts,
					'max_num_pages' => $this->max_num_pages,
				);

				wp_cache_set( $cache_key, $cache_value, 'post-queries' );
			}

			return $this->posts;
		}

		if ( 'id=>parent' === $q['fields'] ) {
			if ( null === $this->posts ) {
				$this->posts = $wpdb->get_results( $this->request );
			}

			$this->post_count = count( $this->posts );
			$this->set_found_posts( $q, $limits );

			/** @var int[] */
			$post_parents       = array();
			$post_ids           = array();
			$post_parents_cache = array();

			foreach ( $this->posts as $key => $post ) {
				$this->posts[ $key ]->ID          = (int) $post->ID;
				$this->posts[ $key ]->post_parent = (int) $post->post_parent;

				$post_parents[ (int) $post->ID ] = (int) $post->post_parent;
				$post_ids[]                      = (int) $post->ID;

				$post_parents_cache[ 'post_parent:' . (string) $post->ID ] = (int) $post->post_parent;
			}
			// Prime post parent caches, so that on second run, there is not another database query.
			wp_cache_add_multiple( $post_parents_cache, 'posts' );

			if ( $q['cache_results'] && $id_query_is_cacheable ) {
				$cache_value = array(
					'posts'         => $post_ids,
					'found_posts'   => $this->found_posts,
					'max_num_pages' => $this->max_num_pages,
				);

				wp_cache_set( $cache_key, $cache_value, 'post-queries' );
			}

			return $post_parents;
		}

		$is_unfiltered_query = $old_request === $this->request && "{$wpdb->posts}.*" === $fields;

		if ( null === $this->posts ) {
			$split_the_query = (
				$is_unfiltered_query
				&& (
					wp_using_ext_object_cache()
					|| ( ! empty( $limits ) && $q['posts_per_page'] < 500 )
				)
			);

			/**
			 * Filters whether to split the query.
			 *
			 * Splitting the query will cause it to fetch just the IDs of the found posts
			 * (and then individually fetch each post by ID), rather than fetching every
			 * complete row at once. One massive result vs. many small results.
			 *
			 * @since 3.4.0
			 * @since 6.6.0 Added the `$old_request` and `$clauses` parameters.
			 *
			 * @param bool     $split_the_query Whether or not to split the query.
			 * @param WP_Query $query           The WP_Query instance.
			 * @param string   $old_request     The complete SQL query before filtering.
			 * @param string[] $clauses {
			 *     Associative array of the clauses for the query.
			 *
			 *     @type string $where    The WHERE clause of the query.
			 *     @type string $groupby  The GROUP BY clause of the query.
			 *     @type string $join     The JOIN clause of the query.
			 *     @type string $orderby  The ORDER BY clause of the query.
			 *     @type string $distinct The DISTINCT clause of the query.
			 *     @type string $fields   The SELECT clause of the query.
			 *     @type string $limits   The LIMIT clause of the query.
			 * }
			 */
			$split_the_query = apply_filters( 'split_the_query', $split_the_query, $this, $old_request, compact( $pieces ) );

			if ( $split_the_query ) {
				// First get the IDs and then fill in the objects.

				// Beginning of the string is on a new line to prevent leading whitespace. See https://core.trac.wordpress.org/ticket/56841.
				$this->request =
					"SELECT $found_rows $distinct {$wpdb->posts}.ID
					 FROM {$wpdb->posts} $join
					 WHERE 1=1 $where
					 $groupby
					 $orderby
					 $limits";

				/**
				 * Filters the Post IDs SQL request before sending.
				 *
				 * @since 3.4.0
				 *
				 * @param string   $request The post ID request.
				 * @param WP_Query $query   The WP_Query instance.
				 */
				$this->request = apply_filters( 'posts_request_ids', $this->request, $this );

				$post_ids = $wpdb->get_col( $this->request );

				if ( $post_ids ) {
					$this->posts = $post_ids;
					$this->set_found_posts( $q, $limits );
					_prime_post_caches( $post_ids, $q['update_post_term_cache'], $q['update_post_meta_cache'] );
				} else {
					$this->posts = array();
				}
			} else {
				$this->posts = $wpdb->get_results( $this->request );
				$this->set_found_posts( $q, $limits );
			}
		}

		// Convert to WP_Post objects.
		if ( $this->posts ) {
			/** @var WP_Post[] */
			$this->posts = array_map( 'get_post', $this->posts );
		}

		$unfiltered_posts = $this->posts;

		if ( $q['cache_results'] && $id_query_is_cacheable && ! $cache_found ) {
			$post_ids = wp_list_pluck( $this->posts, 'ID' );

			$cache_value = array(
				'posts'         => $post_ids,
				'found_posts'   => $this->found_posts,
				'max_num_pages' => $this->max_num_pages,
			);

			wp_cache_set( $cache_key, $cache_value, 'post-queries' );
		}

		if ( ! $q['suppress_filters'] ) {
			/**
			 * Filters the raw post results array, prior to status checks.
			 *
			 * @since 2.3.0
			 *
			 * @param WP_Post[] $posts Array of post objects.
			 * @param WP_Query  $query The WP_Query instance (passed by reference).
			 */
			$this->posts = apply_filters_ref_array( 'posts_results', array( $this->posts, &$this ) );
		}

		if ( ! empty( $this->posts ) && $this->is_comment_feed && $this->is_singular ) {
			/** This filter is documented in wp-includes/query.php */
			$cjoin = apply_filters_ref_array( 'comment_feed_join', array( '', &$this ) );

			/** This filter is documented in wp-includes/query.php */
			$cwhere = apply_filters_ref_array( 'comment_feed_where', array( "WHERE comment_post_ID = '{$this->posts[0]->ID}' AND comment_approved = '1'", &$this ) );

			/** This filter is documented in wp-includes/query.php */
			$cgroupby = apply_filters_ref_array( 'comment_feed_groupby', array( '', &$this ) );
			$cgroupby = ( ! empty( $cgroupby ) ) ? 'GROUP BY ' . $cgroupby : '';

			/** This filter is documented in wp-includes/query.php */
			$corderby = apply_filters_ref_array( 'comment_feed_orderby', array( 'comment_date_gmt DESC', &$this ) );
			$corderby = ( ! empty( $corderby ) ) ? 'ORDER BY ' . $corderby : '';

			/** This filter is documented in wp-includes/query.php */
			$climits = apply_filters_ref_array( 'comment_feed_limits', array( 'LIMIT ' . get_option( 'posts_per_rss' ), &$this ) );

			$comments_request = "SELECT {$wpdb->comments}.comment_ID FROM {$wpdb->comments} $cjoin $cwhere $cgroupby $corderby $climits";

			$comment_key          = md5( $comments_request );
			$comment_last_changed = wp_cache_get_last_changed( 'comment' );

			$comment_cache_key = "comment_feed:$comment_key:$comment_last_changed";
			$comment_ids       = wp_cache_get( $comment_cache_key, 'comment-queries' );
			if ( false === $comment_ids ) {
				$comment_ids = $wpdb->get_col( $comments_request );
				wp_cache_add( $comment_cache_key, $comment_ids, 'comment-queries' );
			}
			_prime_comment_caches( $comment_ids );

			// Convert to WP_Comment.
			/** @var WP_Comment[] */
			$this->comments      = array_map( 'get_comment', $comment_ids );
			$this->comment_count = count( $this->comments );
		}

		// Check post status to determine if post should be displayed.
		if ( ! empty( $this->posts ) && ( $this->is_single || $this->is_page ) ) {
			$status = get_post_status( $this->posts[0] );

			if ( 'attachment' === $this->posts[0]->post_type && 0 === (int) $this->posts[0]->post_parent ) {
				$this->is_page       = false;
				$this->is_single     = true;
				$this->is_attachment = true;
			}

			// If the post_status was specifically requested, let it pass through.
			if ( ! in_array( $status, $q_status, true ) ) {
				$post_status_obj = get_post_status_object( $status );

				if ( $post_status_obj && ! $post_status_obj->public ) {
					if ( ! is_user_logged_in() ) {
						// User must be logged in to view unpublished posts.
						$this->posts = array();
					} else {
						if ( $post_status_obj->protected ) {
							// User must have edit permissions on the draft to preview.
							if ( ! current_user_can( $edit_cap, $this->posts[0]->ID ) ) {
								$this->posts = array();
							} else {
								$this->is_preview = true;
								if ( 'future' !== $status ) {
									$this->posts[0]->post_date = current_time( 'mysql' );
								}
							}
						} elseif ( $post_status_obj->private ) {
							if ( ! current_user_can( $read_cap, $this->posts[0]->ID ) ) {
								$this->posts = array();
							}
						} else {
							$this->posts = array();
						}
					}
				} elseif ( ! $post_status_obj ) {
					// Post status is not registered, assume it's not public.
					if ( ! current_user_can( $edit_cap, $this->posts[0]->ID ) ) {
						$this->posts = array();
					}
				}
			}

			if ( $this->is_preview && $this->posts && current_user_can( $edit_cap, $this->posts[0]->ID ) ) {
				/**
				 * Filters the single post for preview mode.
				 *
				 * @since 2.7.0
				 *
				 * @param WP_Post  $post_preview  The Post object.
				 * @param WP_Query $query         The WP_Query instance (passed by reference).
				 */
				$this->posts[0] = get_post( apply_filters_ref_array( 'the_preview', array( $this->posts[0], &$this ) ) );
			}
		}

		// Put sticky posts at the top of the posts array.
		$sticky_posts = get_option( 'sticky_posts' );
		if ( $this->is_home && $page <= 1 && is_array( $sticky_posts ) && ! empty( $sticky_posts ) && ! $q['ignore_sticky_posts'] ) {
			$num_posts     = count( $this->posts );
			$sticky_offset = 0;
			// Loop over posts and relocate stickies to the front.
			for ( $i = 0; $i < $num_posts; $i++ ) {
				if ( in_array( $this->posts[ $i ]->ID, $sticky_posts, true ) ) {
					$sticky_post = $this->posts[ $i ];
					// Remove sticky from current position.
					array_splice( $this->posts, $i, 1 );
					// Move to front, after other stickies.
					array_splice( $this->posts, $sticky_offset, 0, array( $sticky_post ) );
					// Increment the sticky offset. The next sticky will be placed at this offset.
					++$sticky_offset;
					// Remove post from sticky posts array.
					$offset = array_search( $sticky_post->ID, $sticky_posts, true );
					unset( $sticky_posts[ $offset ] );
				}
			}

			// If any posts have been excluded specifically, Ignore those that are sticky.
			if ( ! empty( $sticky_posts ) && ! empty( $q['post__not_in'] ) ) {
				$sticky_posts = array_diff( $sticky_posts, $q['post__not_in'] );
			}

			// Fetch sticky posts that weren't in the query results.
			if ( ! empty( $sticky_posts ) ) {
				$stickies = get_posts(
					array(
						'post__in'               => $sticky_posts,
						'post_type'              => $post_type,
						'post_status'            => 'publish',
						'posts_per_page'         => count( $sticky_posts ),
						'suppress_filters'       => $q['suppress_filters'],
						'cache_results'          => $q['cache_results'],
						'update_post_meta_cache' => $q['update_post_meta_cache'],
						'update_post_term_cache' => $q['update_post_term_cache'],
						'lazy_load_term_meta'    => $q['lazy_load_term_meta'],
					)
				);

				foreach ( $stickies as $sticky_post ) {
					array_splice( $this->posts, $sticky_offset, 0, array( $sticky_post ) );
					++$sticky_offset;
				}
			}
		}

		if ( ! $q['suppress_filters'] ) {
			/**
			 * Filters the array of retrieved posts after they've been fetched and
			 * internally processed.
			 *
			 * @since 1.5.0
			 *
			 * @param WP_Post[] $posts Array of post objects.
			 * @param WP_Query  $query The WP_Query instance (passed by reference).
			 */
			$this->posts = apply_filters_ref_array( 'the_posts', array( $this->posts, &$this ) );
		}

		/*
		 * Ensure that any posts added/modified via one of the filters above are
		 * of the type WP_Post and are filtered.
		 */
		if ( $this->posts ) {
			$this->post_count = count( $this->posts );

			/** @var WP_Post[] */
			$this->posts = array_map( 'get_post', $this->posts );

			if ( $q['cache_results'] ) {
				if ( $is_unfiltered_query && $unfiltered_posts === $this->posts ) {
					update_post_caches( $this->posts, $post_type, $q['update_post_term_cache'], $q['update_post_meta_cache'] );
				} else {
					$post_ids = wp_list_pluck( $this->posts, 'ID' );
					_prime_post_caches( $post_ids, $q['update_post_term_cache'], $q['update_post_meta_cache'] );
				}
			}

			/** @var WP_Post */
			$this->post = reset( $this->posts );
		} else {
			$this->post_count = 0;
			$this->posts      = array();
		}

		if ( ! empty( $this->posts ) && $q['update_menu_item_cache'] ) {
			update_menu_item_cache( $this->posts );
		}

		if ( $q['lazy_load_term_meta'] ) {
			wp_queue_posts_for_term_meta_lazyload( $this->posts );
		}

		return $this->posts;
	}

	/**
	 * Sets up the amount of found posts and the number of pages (if limit clause was used)
	 * for the current query.
	 *
	 * @since 3.5.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @param array  $q      Query variables.
	 * @param string $limits LIMIT clauses of the query.
	 */
	private function set_found_posts( $q, $limits ) {
		global $wpdb;

		/*
		 * Bail if posts is an empty array. Continue if posts is an empty string,
		 * null, or false to accommodate caching plugins that fill posts later.
		 */
		if ( $q['no_found_rows'] || ( is_array( $this->posts ) && ! $this->posts ) ) {
			return;
		}

		if ( ! empty( $limits ) ) {
			/**
			 * Filters the query to run for retrieving the found posts.
			 *
			 * @since 2.1.0
			 *
			 * @param string   $found_posts_query The query to run to find the found posts.
			 * @param WP_Query $query             The WP_Query instance (passed by reference).
			 */
			$found_posts_query = apply_filters_ref_array( 'found_posts_query', array( 'SELECT FOUND_ROWS()', &$this ) );

			$this->found_posts = (int) $wpdb->get_var( $found_posts_query );
		} else {
			if ( is_array( $this->posts ) ) {
				$this->found_posts = count( $this->posts );
			} else {
				if ( null === $this->posts ) {
					$this->found_posts = 0;
				} else {
					$this->found_posts = 1;
				}
			}
		}

		/**
		 * Filters the number of found posts for the query.
		 *
		 * @since 2.1.0
		 *
		 * @param int      $found_posts The number of posts found.
		 * @param WP_Query $query       The WP_Query instance (passed by reference).
		 */
		$this->found_posts = (int) apply_filters_ref_array( 'found_posts', array( $this->found_posts, &$this ) );

		if ( ! empty( $limits ) ) {
			$this->max_num_pages = (int) ceil( $this->found_posts / $q['posts_per_page'] );
		}
	}

	/**
	 * Sets up the next post and iterate current post index.
	 *
	 * @since 1.5.0
	 *
	 * @return WP_Post Next post.
	 */
	public function next_post() {

		++$this->current_post;

		/** @var WP_Post */
		$this->post = $this->posts[ $this->current_post ];
		return $this->post;
	}

	/**
	 * Sets up the current post.
	 *
	 * Retrieves the next post, sets up the post, sets the 'in the loop'
	 * property to true.
	 *
	 * @since 1.5.0
	 *
	 * @global WP_Post $post Global post object.
	 */
	public function the_post() {
		global $post;

		if ( ! $this->in_the_loop ) {
			if ( 'all' === $this->query_vars['fields'] ) {
				// Full post objects queried.
				$post_objects = $this->posts;
			} else {
				if ( 'ids' === $this->query_vars['fields'] ) {
					// Post IDs queried.
					$post_ids = $this->posts;
				} else {
					// Only partial objects queried, need to prime the cache for the loop.
					$post_ids = array_reduce(
						$this->posts,
						function ( $carry, $post ) {
							if ( isset( $post->ID ) ) {
								$carry[] = $post->ID;
							}

							return $carry;
						},
						array()
					);
				}
				_prime_post_caches( $post_ids, $this->query_vars['update_post_term_cache'], $this->query_vars['update_post_meta_cache'] );
				$post_objects = array_map( 'get_post', $post_ids );
			}
			update_post_author_caches( $post_objects );
		}

		$this->in_the_loop = true;
		$this->before_loop = false;

		if ( -1 === $this->current_post ) { // Loop has just started.
			/**
			 * Fires once the loop is started.
			 *
			 * @since 2.0.0
			 *
			 * @param WP_Query $query The WP_Query instance (passed by reference).
			 */
			do_action_ref_array( 'loop_start', array( &$this ) );
		}

		$post = $this->next_post();

		// Ensure a full post object is available.
		if ( 'all' !== $this->query_vars['fields'] ) {
			if ( 'ids' === $this->query_vars['fields'] ) {
				// Post IDs queried.
				$post = get_post( $post );
			} elseif ( isset( $post->ID ) ) {
				/*
				 * Partial objecct queried.
				 *
				 * The post object was queried with a partial set of
				 * fields, populate the entire object for the loop.
				 */
				$post = get_post( $post->ID );
			}
		}

		// Set up the global post object for the loop.
		$this->setup_postdata( $post );
	}

	/**
	 * Determines whether there are more posts available in the loop.
	 *
	 * Calls the 'loop_end' action when the loop is complete.
	 *
	 * @since 1.5.0
	 *
	 * @return bool True if posts are available, false if end of the loop.
	 */
	public function have_posts() {
		if ( $this->current_post + 1 < $this->post_count ) {
			return true;
		} elseif ( $this->current_post + 1 === $this->post_count && $this->post_count > 0 ) {
			/**
			 * Fires once the loop has ended.
			 *
			 * @since 2.0.0
			 *
			 * @param WP_Query $query The WP_Query instance (passed by reference).
			 */
			do_action_ref_array( 'loop_end', array( &$this ) );

			// Do some cleaning up after the loop.
			$this->rewind_posts();
		} elseif ( 0 === $this->post_count ) {
			$this->before_loop = false;

			/**
			 * Fires if no results are found in a post query.
			 *
			 * @since 4.9.0
			 *
			 * @param WP_Query $query The WP_Query instance.
			 */
			do_action( 'loop_no_results', $this );
		}

		$this->in_the_loop = false;
		return false;
	}

	/**
	 * Rewinds the posts and resets post index.
	 *
	 * @since 1.5.0
	 */
	public function rewind_posts() {
		$this->current_post = -1;
		if ( $this->post_count > 0 ) {
			$this->post = $this->posts[0];
		}
	}

	/**
	 * Iterates current comment index and returns WP_Comment object.
	 *
	 * @since 2.2.0
	 *
	 * @return WP_Comment Comment object.
	 */
	public function next_comment() {
		++$this->current_comment;

		/** @var WP_Comment */
		$this->comment = $this->comments[ $this->current_comment ];
		return $this->comment;
	}

	/**
	 * Sets up the current comment.
	 *
	 * @since 2.2.0
	 *
	 * @global WP_Comment $comment Global comment object.
	 */
	public function the_comment() {
		global $comment;

		$comment = $this->next_comment();

		if ( 0 === $this->current_comment ) {
			/**
			 * Fires once the comment loop is started.
			 *
			 * @since 2.2.0
			 */
			do_action( 'comment_loop_start' );
		}
	}

	/**
	 * Determines whether there are more comments available.
	 *
	 * Automatically rewinds comments when finished.
	 *
	 * @since 2.2.0
	 *
	 * @return bool True if comments are available, false if no more comments.
	 */
	public function have_comments() {
		if ( $this->current_comment + 1 < $this->comment_count ) {
			return true;
		} elseif ( $this->current_comment + 1 === $this->comment_count ) {
			$this->rewind_comments();
		}

		return false;
	}

	/**
	 * Rewinds the comments, resets the comment index and comment to first.
	 *
	 * @since 2.2.0
	 */
	public function rewind_comments() {
		$this->current_comment = -1;
		if ( $this->comment_count > 0 ) {
			$this->comment = $this->comments[0];
		}
	}

	/**
	 * Sets up the WordPress query by parsing query string.
	 *
	 * @since 1.5.0
	 *
	 * @see WP_Query::parse_query() for all available arguments.
	 *
	 * @param string|array $query URL query string or array of query arguments.
	 * @return WP_Post[]|int[] Array of post objects or post IDs.
	 */
	public function query( $query ) {
		$this->init();
		$this->query      = wp_parse_args( $query );
		$this->query_vars = $this->query;
		return $this->get_posts();
	}

	/**
	 * Retrieves the currently queried object.
	 *
	 * If queried object is not set, then the queried object will be set from
	 * the category, tag, taxonomy, posts page, single post, page, or author
	 * query variable. After it is set up, it will be returned.
	 *
	 * @since 1.5.0
	 *
	 * @return WP_Term|WP_Post_Type|WP_Post|WP_User|null The queried object.
	 */
	public function get_queried_object() {
		if ( isset( $this->queried_object ) ) {
			return $this->queried_object;
		}

		$this->queried_object    = null;
		$this->queried_object_id = null;

		if ( $this->is_category || $this->is_tag || $this->is_tax ) {
			if ( $this->is_category ) {
				$cat           = $this->get( 'cat' );
				$category_name = $this->get( 'category_name' );

				if ( $cat ) {
					$term = get_term( $cat, 'category' );
				} elseif ( $category_name ) {
					$term = get_term_by( 'slug', $category_name, 'category' );
				}
			} elseif ( $this->is_tag ) {
				$tag_id = $this->get( 'tag_id' );
				$tag    = $this->get( 'tag' );

				if ( $tag_id ) {
					$term = get_term( $tag_id, 'post_tag' );
				} elseif ( $tag ) {
					$term = get_term_by( 'slug', $tag, 'post_tag' );
				}
			} else {
				// For other tax queries, grab the first term from the first clause.
				if ( ! empty( $this->tax_query->queried_terms ) ) {
					$queried_taxonomies = array_keys( $this->tax_query->queried_terms );
					$matched_taxonomy   = reset( $queried_taxonomies );
					$query              = $this->tax_query->queried_terms[ $matched_taxonomy ];

					if ( ! empty( $query['terms'] ) ) {
						if ( 'term_id' === $query['field'] ) {
							$term = get_term( reset( $query['terms'] ), $matched_taxonomy );
						} else {
							$term = get_term_by( $query['field'], reset( $query['terms'] ), $matched_taxonomy );
						}
					}
				}
			}

			if ( ! empty( $term ) && ! is_wp_error( $term ) ) {
				$this->queried_object    = $term;
				$this->queried_object_id = (int) $term->term_id;

				if ( $this->is_category && 'category' === $this->queried_object->taxonomy ) {
					_make_cat_compat( $this->queried_object );
				}
			}
		} elseif ( $this->is_post_type_archive ) {
			$post_type = $this->get( 'post_type' );

			if ( is_array( $post_type ) ) {
				$post_type = reset( $post_type );
			}

			$this->queried_object = get_post_type_object( $post_type );
		} elseif ( $this->is_posts_page ) {
			$page_for_posts = get_option( 'page_for_posts' );

			$this->queried_object    = get_post( $page_for_posts );
			$this->queried_object_id = (int) $this->queried_object->ID;
		} elseif ( $this->is_singular && ! empty( $this->post ) ) {
			$this->queried_object    = $this->post;
			$this->queried_object_id = (int) $this->post->ID;
		} elseif ( $this->is_author ) {
			$author      = (int) $this->get( 'author' );
			$author_name = $this->get( 'author_name' );

			if ( $author ) {
				$this->queried_object_id = $author;
			} elseif ( $author_name ) {
				$user = get_user_by( 'slug', $author_name );

				if ( $user ) {
					$this->queried_object_id = $user->ID;
				}
			}

			$this->queried_object = get_userdata( $this->queried_object_id );
		}

		return $this->queried_object;
	}

	/**
	 * Retrieves the ID of the currently queried object.
	 *
	 * @since 1.5.0
	 *
	 * @return int
	 */
	public function get_queried_object_id() {
		$this->get_queried_object();

		if ( isset( $this->queried_object_id ) ) {
			return $this->queried_object_id;
		}

		return 0;
	}

	/**
	 * Constructor.
	 *
	 * Sets up the WordPress query, if parameter is not empty.
	 *
	 * @since 1.5.0
	 *
	 * @see WP_Query::parse_query() for all available arguments.
	 *
	 * @param string|array $query URL query string or array of vars.
	 */
	public function __construct( $query = '' ) {
		if ( ! empty( $query ) ) {
			$this->query( $query );
		}
	}

	/**
	 * Makes private properties readable for backward compatibility.
	 *
	 * @since 4.0.0
	 *
	 * @param string $name Property to get.
	 * @return mixed Property.
	 */
	public function __get( $name ) {
		if ( in_array( $name, $this->compat_fields, true ) ) {
			return $this->$name;
		}
	}

	/**
	 * Makes private properties checkable for backward compatibility.
	 *
	 * @since 4.0.0
	 *
	 * @param string $name Property to check if set.
	 * @return bool Whether the property is set.
	 */
	public function __isset( $name ) {
		if ( in_array( $name, $this->compat_fields, true ) ) {
			return isset( $this->$name );
		}

		return false;
	}

	/**
	 * Makes private/protected methods readable for backward compatibility.
	 *
	 * @since 4.0.0
	 *
	 * @param string $name      Method to call.
	 * @param array  $arguments Arguments to pass when calling.
	 * @return mixed|false Return value of the callback, false otherwise.
	 */
	public function __call( $name, $arguments ) {
		if ( in_array( $name, $this->compat_methods, true ) ) {
			return $this->$name( ...$arguments );
		}
		return false;
	}

	/**
	 * Determines whether the query is for an existing archive page.
	 *
	 * Archive pages include category, tag, author, date, custom post type,
	 * and custom taxonomy based archives.
	 *
	 * @since 3.1.0
	 *
	 * @see WP_Query::is_category()
	 * @see WP_Query::is_tag()
	 * @see WP_Query::is_author()
	 * @see WP_Query::is_date()
	 * @see WP_Query::is_post_type_archive()
	 * @see WP_Query::is_tax()
	 *
	 * @return bool Whether the query is for an existing archive page.
	 */
	public function is_archive() {
		return (bool) $this->is_archive;
	}

	/**
	 * Determines whether the query is for an existing post type archive page.
	 *
	 * @since 3.1.0
	 *
	 * @param string|string[] $post_types Optional. Post type or array of posts types
	 *                                    to check against. Default empty.
	 * @return bool Whether the query is for an existing post type archive page.
	 */
	public function is_post_type_archive( $post_types = '' ) {
		if ( empty( $post_types ) || ! $this->is_post_type_archive ) {
			return (bool) $this->is_post_type_archive;
		}

		$post_type = $this->get( 'post_type' );
		if ( is_array( $post_type ) ) {
			$post_type = reset( $post_type );
		}
		$post_type_object = get_post_type_object( $post_type );

		if ( ! $post_type_object ) {
			return false;
		}

		return in_array( $post_type_object->name, (array) $post_types, true );
	}

	/**
	 * Determines whether the query is for an existing attachment page.
	 *
	 * @since 3.1.0
	 *
	 * @param int|string|int[]|string[] $attachment Optional. Attachment ID, title, slug, or array of such
	 *                                              to check against. Default empty.
	 * @return bool Whether the query is for an existing attachment page.
	 */
	public function is_attachment( $attachment = '' ) {
		if ( ! $this->is_attachment ) {
			return false;
		}

		if ( empty( $attachment ) ) {
			return true;
		}

		$attachment = array_map( 'strval', (array) $attachment );

		$post_obj = $this->get_queried_object();
		if ( ! $post_obj ) {
			return false;
		}

		if ( in_array( (string) $post_obj->ID, $attachment, true ) ) {
			return true;
		} elseif ( in_array( $post_obj->post_title, $attachment, true ) ) {
			return true;
		} elseif ( in_array( $post_obj->post_name, $attachment, true ) ) {
			return true;
		}
		return false;
	}

	/**
	 * Determines whether the query is for an existing author archive page.
	 *
	 * If the $author parameter is specified, this function will additionally
	 * check if the query is for one of the authors specified.
	 *
	 * @since 3.1.0
	 *
	 * @param int|string|int[]|string[] $author Optional. User ID, nickname, nicename, or array of such
	 *                                          to check against. Default empty.
	 * @return bool Whether the query is for an existing author archive page.
	 */
	public function is_author( $author = '' ) {
		if ( ! $this->is_author ) {
			return false;
		}

		if ( empty( $author ) ) {
			return true;
		}

		$author_obj = $this->get_queried_object();
		if ( ! $author_obj ) {
			return false;
		}

		$author = array_map( 'strval', (array) $author );

		if ( in_array( (string) $author_obj->ID, $author, true ) ) {
			return true;
		} elseif ( in_array( $author_obj->nickname, $author, true ) ) {
			return true;
		} elseif ( in_array( $author_obj->user_nicename, $author, true ) ) {
			return true;
		}

		return false;
	}

	/**
	 * Determines whether the query is for an existing category archive page.
	 *
	 * If the $category parameter is specified, this function will additionally
	 * check if the query is for one of the categories specified.
	 *
	 * @since 3.1.0
	 *
	 * @param int|string|int[]|string[] $category Optional. Category ID, name, slug, or array of such
	 *                                            to check against. Default empty.
	 * @return bool Whether the query is for an existing category archive page.
	 */
	public function is_category( $category = '' ) {
		if ( ! $this->is_category ) {
			return false;
		}

		if ( empty( $category ) ) {
			return true;
		}

		$cat_obj = $this->get_queried_object();
		if ( ! $cat_obj ) {
			return false;
		}

		$category = array_map( 'strval', (array) $category );

		if ( in_array( (string) $cat_obj->term_id, $category, true ) ) {
			return true;
		} elseif ( in_array( $cat_obj->name, $category, true ) ) {
			return true;
		} elseif ( in_array( $cat_obj->slug, $category, true ) ) {
			return true;
		}

		return false;
	}

	/**
	 * Determines whether the query is for an existing tag archive page.
	 *
	 * If the $tag parameter is specified, this function will additionally
	 * check if the query is for one of the tags specified.
	 *
	 * @since 3.1.0
	 *
	 * @param int|string|int[]|string[] $tag Optional. Tag ID, name, slug, or array of such
	 *                                       to check against. Default empty.
	 * @return bool Whether the query is for an existing tag archive page.
	 */
	public function is_tag( $tag = '' ) {
		if ( ! $this->is_tag ) {
			return false;
		}

		if ( empty( $tag ) ) {
			return true;
		}

		$tag_obj = $this->get_queried_object();
		if ( ! $tag_obj ) {
			return false;
		}

		$tag = array_map( 'strval', (array) $tag );

		if ( in_array( (string) $tag_obj->term_id, $tag, true ) ) {
			return true;
		} elseif ( in_array( $tag_obj->name, $tag, true ) ) {
			return true;
		} elseif ( in_array( $tag_obj->slug, $tag, true ) ) {
			return true;
		}

		return false;
	}

	/**
	 * Determines whether the query is for an existing custom taxonomy archive page.
	 *
	 * If the $taxonomy parameter is specified, this function will additionally
	 * check if the query is for that specific $taxonomy.
	 *
	 * If the $term parameter is specified in addition to the $taxonomy parameter,
	 * this function will additionally check if the query is for one of the terms
	 * specified.
	 *
	 * @since 3.1.0
	 *
	 * @global WP_Taxonomy[] $wp_taxonomies Registered taxonomies.
	 *
	 * @param string|string[]           $taxonomy Optional. Taxonomy slug or slugs to check against.
	 *                                            Default empty.
	 * @param int|string|int[]|string[] $term     Optional. Term ID, name, slug, or array of such
	 *                                            to check against. Default empty.
	 * @return bool Whether the query is for an existing custom taxonomy archive page.
	 *              True for custom taxonomy archive pages, false for built-in taxonomies
	 *              (category and tag archives).
	 */
	public function is_tax( $taxonomy = '', $term = '' ) {
		global $wp_taxonomies;

		if ( ! $this->is_tax ) {
			return false;
		}

		if ( empty( $taxonomy ) ) {
			return true;
		}

		$queried_object = $this->get_queried_object();
		$tax_array      = array_intersect( array_keys( $wp_taxonomies ), (array) $taxonomy );
		$term_array     = (array) $term;

		// Check that the taxonomy matches.
		if ( ! ( isset( $queried_object->taxonomy ) && count( $tax_array ) && in_array( $queried_object->taxonomy, $tax_array, true ) ) ) {
			return false;
		}

		// Only a taxonomy provided.
		if ( empty( $term ) ) {
			return true;
		}

		return isset( $queried_object->term_id ) &&
			count(
				array_intersect(
					array( $queried_object->term_id, $queried_object->name, $queried_object->slug ),
					$term_array
				)
			);
	}

	/**
	 * Determines whether the current URL is within the comments popup window.
	 *
	 * @since 3.1.0
	 * @deprecated 4.5.0
	 *
	 * @return false Always returns false.
	 */
	public function is_comments_popup() {
		_deprecated_function( __FUNCTION__, '4.5.0' );

		return false;
	}

	/**
	 * Determines whether the query is for an existing date archive.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for an existing date archive.
	 */
	public function is_date() {
		return (bool) $this->is_date;
	}

	/**
	 * Determines whether the query is for an existing day archive.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for an existing day archive.
	 */
	public function is_day() {
		return (bool) $this->is_day;
	}

	/**
	 * Determines whether the query is for a feed.
	 *
	 * @since 3.1.0
	 *
	 * @param string|string[] $feeds Optional. Feed type or array of feed types
	 *                                         to check against. Default empty.
	 * @return bool Whether the query is for a feed.
	 */
	public function is_feed( $feeds = '' ) {
		if ( empty( $feeds ) || ! $this->is_feed ) {
			return (bool) $this->is_feed;
		}

		$qv = $this->get( 'feed' );
		if ( 'feed' === $qv ) {
			$qv = get_default_feed();
		}

		return in_array( $qv, (array) $feeds, true );
	}

	/**
	 * Determines whether the query is for a comments feed.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for a comments feed.
	 */
	public function is_comment_feed() {
		return (bool) $this->is_comment_feed;
	}

	/**
	 * Determines whether the query is for the front page of the site.
	 *
	 * This is for what is displayed at your site's main URL.
	 *
	 * Depends on the site's "Front page displays" Reading Settings 'show_on_front' and 'page_on_front'.
	 *
	 * If you set a static page for the front page of your site, this function will return
	 * true when viewing that page.
	 *
	 * Otherwise the same as WP_Query::is_home().
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for the front page of the site.
	 */
	public function is_front_page() {
		// Most likely case.
		if ( 'posts' === get_option( 'show_on_front' ) && $this->is_home() ) {
			return true;
		} elseif ( 'page' === get_option( 'show_on_front' ) && get_option( 'page_on_front' )
			&& $this->is_page( get_option( 'page_on_front' ) )
		) {
			return true;
		} else {
			return false;
		}
	}

	/**
	 * Determines whether the query is for the blog homepage.
	 *
	 * This is the page which shows the time based blog content of your site.
	 *
	 * Depends on the site's "Front page displays" Reading Settings 'show_on_front' and 'page_for_posts'.
	 *
	 * If you set a static page for the front page of your site, this function will return
	 * true only on the page you set as the "Posts page".
	 *
	 * @since 3.1.0
	 *
	 * @see WP_Query::is_front_page()
	 *
	 * @return bool Whether the query is for the blog homepage.
	 */
	public function is_home() {
		return (bool) $this->is_home;
	}

	/**
	 * Determines whether the query is for the Privacy Policy page.
	 *
	 * This is the page which shows the Privacy Policy content of your site.
	 *
	 * Depends on the site's "Change your Privacy Policy page" Privacy Settings 'wp_page_for_privacy_policy'.
	 *
	 * This function will return true only on the page you set as the "Privacy Policy page".
	 *
	 * @since 5.2.0
	 *
	 * @return bool Whether the query is for the Privacy Policy page.
	 */
	public function is_privacy_policy() {
		if ( get_option( 'wp_page_for_privacy_policy' )
			&& $this->is_page( get_option( 'wp_page_for_privacy_policy' ) )
		) {
			return true;
		} else {
			return false;
		}
	}

	/**
	 * Determines whether the query is for an existing month archive.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for an existing month archive.
	 */
	public function is_month() {
		return (bool) $this->is_month;
	}

	/**
	 * Determines whether the query is for an existing single page.
	 *
	 * If the $page parameter is specified, this function will additionally
	 * check if the query is for one of the pages specified.
	 *
	 * @since 3.1.0
	 *
	 * @see WP_Query::is_single()
	 * @see WP_Query::is_singular()
	 *
	 * @param int|string|int[]|string[] $page Optional. Page ID, title, slug, path, or array of such
	 *                                        to check against. Default empty.
	 * @return bool Whether the query is for an existing single page.
	 */
	public function is_page( $page = '' ) {
		if ( ! $this->is_page ) {
			return false;
		}

		if ( empty( $page ) ) {
			return true;
		}

		$page_obj = $this->get_queried_object();
		if ( ! $page_obj ) {
			return false;
		}

		$page = array_map( 'strval', (array) $page );

		if ( in_array( (string) $page_obj->ID, $page, true ) ) {
			return true;
		} elseif ( in_array( $page_obj->post_title, $page, true ) ) {
			return true;
		} elseif ( in_array( $page_obj->post_name, $page, true ) ) {
			return true;
		} else {
			foreach ( $page as $pagepath ) {
				if ( ! strpos( $pagepath, '/' ) ) {
					continue;
				}

				$pagepath_obj = get_page_by_path( $pagepath );

				if ( $pagepath_obj && ( $pagepath_obj->ID === $page_obj->ID ) ) {
					return true;
				}
			}
		}

		return false;
	}

	/**
	 * Determines whether the query is for a paged result and not for the first page.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for a paged result.
	 */
	public function is_paged() {
		return (bool) $this->is_paged;
	}

	/**
	 * Determines whether the query is for a post or page preview.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for a post or page preview.
	 */
	public function is_preview() {
		return (bool) $this->is_preview;
	}

	/**
	 * Determines whether the query is for the robots.txt file.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for the robots.txt file.
	 */
	public function is_robots() {
		return (bool) $this->is_robots;
	}

	/**
	 * Determines whether the query is for the favicon.ico file.
	 *
	 * @since 5.4.0
	 *
	 * @return bool Whether the query is for the favicon.ico file.
	 */
	public function is_favicon() {
		return (bool) $this->is_favicon;
	}

	/**
	 * Determines whether the query is for a search.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for a search.
	 */
	public function is_search() {
		return (bool) $this->is_search;
	}

	/**
	 * Determines whether the query is for an existing single post.
	 *
	 * Works for any post type excluding pages.
	 *
	 * If the $post parameter is specified, this function will additionally
	 * check if the query is for one of the Posts specified.
	 *
	 * @since 3.1.0
	 *
	 * @see WP_Query::is_page()
	 * @see WP_Query::is_singular()
	 *
	 * @param int|string|int[]|string[] $post Optional. Post ID, title, slug, path, or array of such
	 *                                        to check against. Default empty.
	 * @return bool Whether the query is for an existing single post.
	 */
	public function is_single( $post = '' ) {
		if ( ! $this->is_single ) {
			return false;
		}

		if ( empty( $post ) ) {
			return true;
		}

		$post_obj = $this->get_queried_object();
		if ( ! $post_obj ) {
			return false;
		}

		$post = array_map( 'strval', (array) $post );

		if ( in_array( (string) $post_obj->ID, $post, true ) ) {
			return true;
		} elseif ( in_array( $post_obj->post_title, $post, true ) ) {
			return true;
		} elseif ( in_array( $post_obj->post_name, $post, true ) ) {
			return true;
		} else {
			foreach ( $post as $postpath ) {
				if ( ! strpos( $postpath, '/' ) ) {
					continue;
				}

				$postpath_obj = get_page_by_path( $postpath, OBJECT, $post_obj->post_type );

				if ( $postpath_obj && ( $postpath_obj->ID === $post_obj->ID ) ) {
					return true;
				}
			}
		}
		return false;
	}

	/**
	 * Determines whether the query is for an existing single post of any post type
	 * (post, attachment, page, custom post types).
	 *
	 * If the $post_types parameter is specified, this function will additionally
	 * check if the query is for one of the Posts Types specified.
	 *
	 * @since 3.1.0
	 *
	 * @see WP_Query::is_page()
	 * @see WP_Query::is_single()
	 *
	 * @param string|string[] $post_types Optional. Post type or array of post types
	 *                                    to check against. Default empty.
	 * @return bool Whether the query is for an existing single post
	 *              or any of the given post types.
	 */
	public function is_singular( $post_types = '' ) {
		if ( empty( $post_types ) || ! $this->is_singular ) {
			return (bool) $this->is_singular;
		}

		$post_obj = $this->get_queried_object();
		if ( ! $post_obj ) {
			return false;
		}

		return in_array( $post_obj->post_type, (array) $post_types, true );
	}

	/**
	 * Determines whether the query is for a specific time.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for a specific time.
	 */
	public function is_time() {
		return (bool) $this->is_time;
	}

	/**
	 * Determines whether the query is for a trackback endpoint call.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for a trackback endpoint call.
	 */
	public function is_trackback() {
		return (bool) $this->is_trackback;
	}

	/**
	 * Determines whether the query is for an existing year archive.
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is for an existing year archive.
	 */
	public function is_year() {
		return (bool) $this->is_year;
	}

	/**
	 * Determines whether the query is a 404 (returns no results).
	 *
	 * @since 3.1.0
	 *
	 * @return bool Whether the query is a 404 error.
	 */
	public function is_404() {
		return (bool) $this->is_404;
	}

	/**
	 * Determines whether the query is for an embedded post.
	 *
	 * @since 4.4.0
	 *
	 * @return bool Whether the query is for an embedded post.
	 */
	public function is_embed() {
		return (bool) $this->is_embed;
	}

	/**
	 * Determines whether the query is the main query.
	 *
	 * @since 3.3.0
	 *
	 * @global WP_Query $wp_the_query WordPress Query object.
	 *
	 * @return bool Whether the query is the main query.
	 */
	public function is_main_query() {
		global $wp_the_query;
		return $wp_the_query === $this;
	}

	/**
	 * Sets up global post data.
	 *
	 * @since 4.1.0
	 * @since 4.4.0 Added the ability to pass a post ID to `$post`.
	 *
	 * @global int     $id
	 * @global WP_User $authordata
	 * @global string  $currentday
	 * @global string  $currentmonth
	 * @global int     $page
	 * @global array   $pages
	 * @global int     $multipage
	 * @global int     $more
	 * @global int     $numpages
	 *
	 * @param WP_Post|object|int $post WP_Post instance or Post ID/object.
	 * @return true True when finished.
	 */
	public function setup_postdata( $post ) {
		global $id, $authordata, $currentday, $currentmonth, $page, $pages, $multipage, $more, $numpages;

		if ( ! ( $post instanceof WP_Post ) ) {
			$post = get_post( $post );
		}

		if ( ! $post ) {
			return;
		}

		$elements = $this->generate_postdata( $post );
		if ( false === $elements ) {
			return;
		}

		$id           = $elements['id'];
		$authordata   = $elements['authordata'];
		$currentday   = $elements['currentday'];
		$currentmonth = $elements['currentmonth'];
		$page         = $elements['page'];
		$pages        = $elements['pages'];
		$multipage    = $elements['multipage'];
		$more         = $elements['more'];
		$numpages     = $elements['numpages'];

		/**
		 * Fires once the post data has been set up.
		 *
		 * @since 2.8.0
		 * @since 4.1.0 Introduced `$query` parameter.
		 *
		 * @param WP_Post  $post  The Post object (passed by reference).
		 * @param WP_Query $query The current Query object (passed by reference).
		 */
		do_action_ref_array( 'the_post', array( &$post, &$this ) );

		return true;
	}

	/**
	 * Generates post data.
	 *
	 * @since 5.2.0
	 *
	 * @param WP_Post|object|int $post WP_Post instance or Post ID/object.
	 * @return array|false Elements of post or false on failure.
	 */
	public function generate_postdata( $post ) {

		if ( ! ( $post instanceof WP_Post ) ) {
			$post = get_post( $post );
		}

		if ( ! $post ) {
			return false;
		}

		$id = (int) $post->ID;

		$authordata = get_userdata( $post->post_author );

		$currentday   = false;
		$currentmonth = false;

		$post_date = $post->post_date;
		if ( ! empty( $post_date ) && '0000-00-00 00:00:00' !== $post_date ) {
			// Avoid using mysql2date for performance reasons.
			$currentmonth = substr( $post_date, 5, 2 );
			$day          = substr( $post_date, 8, 2 );
			$year         = substr( $post_date, 2, 2 );

			$currentday = sprintf( '%s.%s.%s', $day, $currentmonth, $year );
		}

		$numpages  = 1;
		$multipage = 0;
		$page      = $this->get( 'page' );
		if ( ! $page ) {
			$page = 1;
		}

		/*
		 * Force full post content when viewing the permalink for the $post,
		 * or when on an RSS feed. Otherwise respect the 'more' tag.
		 */
		if ( get_queried_object_id() === $post->ID && ( $this->is_page() || $this->is_single() ) ) {
			$more = 1;
		} elseif ( $this->is_feed() ) {
			$more = 1;
		} else {
			$more = 0;
		}

		$content = $post->post_content;
		if ( str_contains( $content, '<!--nextpage-->' ) ) {
			$content = str_replace( "\n<!--nextpage-->\n", '<!--nextpage-->', $content );
			$content = str_replace( "\n<!--nextpage-->", '<!--nextpage-->', $content );
			$content = str_replace( "<!--nextpage-->\n", '<!--nextpage-->', $content );

			// Remove the nextpage block delimiters, to avoid invalid block structures in the split content.
			$content = str_replace( '<!-- wp:nextpage -->', '', $content );
			$content = str_replace( '<!-- /wp:nextpage -->', '', $content );

			// Ignore nextpage at the beginning of the content.
			if ( str_starts_with( $content, '<!--nextpage-->' ) ) {
				$content = substr( $content, 15 );
			}

			$pages = explode( '<!--nextpage-->', $content );
		} else {
			$pages = array( $post->post_content );
		}

		/**
		 * Filters the "pages" derived from splitting the post content.
		 *
		 * "Pages" are determined by splitting the post content based on the presence
		 * of `<!-- nextpage -->` tags.
		 *
		 * @since 4.4.0
		 *
		 * @param string[] $pages Array of "pages" from the post content split by `<!-- nextpage -->` tags.
		 * @param WP_Post  $post  Current post object.
		 */
		$pages = apply_filters( 'content_pagination', $pages, $post );

		$numpages = count( $pages );

		if ( $numpages > 1 ) {
			if ( $page > 1 ) {
				$more = 1;
			}
			$multipage = 1;
		} else {
			$multipage = 0;
		}

		$elements = compact( 'id', 'authordata', 'currentday', 'currentmonth', 'page', 'pages', 'multipage', 'more', 'numpages' );

		return $elements;
	}

	/**
	 * Generates cache key.
	 *
	 * @since 6.1.0
	 *
	 * @global wpdb $wpdb WordPress database abstraction object.
	 *
	 * @param array  $args Query arguments.
	 * @param string $sql  SQL statement.
	 * @return string Cache key.
	 */
	protected function generate_cache_key( array $args, $sql ) {
		global $wpdb;

		unset(
			$args['cache_results'],
			$args['fields'],
			$args['lazy_load_term_meta'],
			$args['update_post_meta_cache'],
			$args['update_post_term_cache'],
			$args['update_menu_item_cache'],
			$args['suppress_filters']
		);

		if ( empty( $args['post_type'] ) ) {
			if ( $this->is_attachment ) {
				$args['post_type'] = 'attachment';
			} elseif ( $this->is_page ) {
				$args['post_type'] = 'page';
			} else {
				$args['post_type'] = 'post';
			}
		} elseif ( 'any' === $args['post_type'] ) {
			$args['post_type'] = array_values( get_post_types( array( 'exclude_from_search' => false ) ) );
		}
		$args['post_type'] = (array) $args['post_type'];
		// Sort post types to ensure same cache key generation.
		sort( $args['post_type'] );

		/*
		 * Sort arrays that can be used for ordering prior to cache key generation.
		 *
		 * These arrays are sorted in the query generator for the purposes of the
		 * WHERE clause but the arguments are not modified as they can be used for
		 * the orderby clase.
		 *
		 * Their use in the orderby clause will generate a different SQL query so
		 * they can be sorted for the cache key generation.
		 */
		$sortable_arrays_with_int_values = array(
			'post__in',
			'post_parent__in',
		);
		foreach ( $sortable_arrays_with_int_values as $key ) {
			if ( isset( $args[ $key ] ) && is_array( $args[ $key ] ) ) {
				$args[ $key ] = array_unique( array_map( 'absint', $args[ $key ] ) );
				sort( $args[ $key ] );
			}
		}

		// Sort and unique the 'post_name__in' for cache key generation.
		if ( isset( $args['post_name__in'] ) && is_array( $args['post_name__in'] ) ) {
			$args['post_name__in'] = array_unique( $args['post_name__in'] );
			sort( $args['post_name__in'] );
		}

		if ( isset( $args['post_status'] ) ) {
			$args['post_status'] = (array) $args['post_status'];
			// Sort post status to ensure same cache key generation.
			sort( $args['post_status'] );
		}

		// Add a default orderby value of date to ensure same cache key generation.
		if ( ! isset( $q['orderby'] ) ) {
			$args['orderby'] = 'date';
		}

		$placeholder = $wpdb->placeholder_escape();
		array_walk_recursive(
			$args,
			/*
			 * Replace wpdb placeholders with the string used in the database
			 * query to avoid unreachable cache keys. This is necessary because
			 * the placeholder is randomly generated in each request.
			 *
			 * $value is passed by reference to allow it to be modified.
			 * array_walk_recursive() does not return an array.
			 */
			static function ( &$value ) use ( $wpdb, $placeholder ) {
				if ( is_string( $value ) && str_contains( $value, $placeholder ) ) {
					$value = $wpdb->remove_placeholder_escape( $value );
				}
			}
		);

		ksort( $args );

		// Replace wpdb placeholder in the SQL statement used by the cache key.
		$sql = $wpdb->remove_placeholder_escape( $sql );
		$key = md5( serialize( $args ) . $sql );

		$last_changed = wp_cache_get_last_changed( 'posts' );
		if ( ! empty( $this->tax_query->queries ) ) {
			$last_changed .= wp_cache_get_last_changed( 'terms' );
		}

		$this->query_cache_key = "wp_query:$key:$last_changed";
		return $this->query_cache_key;
	}

	/**
	 * After looping through a nested query, this function
	 * restores the $post global to the current post in this query.
	 *
	 * @since 3.7.0
	 *
	 * @global WP_Post $post Global post object.
	 */
	public function reset_postdata() {
		if ( ! empty( $this->post ) ) {
			$GLOBALS['post'] = $this->post;
			$this->setup_postdata( $this->post );
		}
	}

	/**
	 * Lazyloads term meta for posts in the loop.
	 *
	 * @since 4.4.0
	 * @deprecated 4.5.0 See wp_queue_posts_for_term_meta_lazyload().
	 *
	 * @param mixed $check
	 * @param int   $term_id
	 * @return mixed
	 */
	public function lazyload_term_meta( $check, $term_id ) {
		_deprecated_function( __METHOD__, '4.5.0' );
		return $check;
	}

	/**
	 * Lazyloads comment meta for comments in the loop.
	 *
	 * @since 4.4.0
	 * @deprecated 4.5.0 See wp_lazyload_comment_meta().
	 *
	 * @param mixed $check
	 * @param int   $comment_id
	 * @return mixed
	 */
	public function lazyload_comment_meta( $check, $comment_id ) {
		_deprecated_function( __METHOD__, '4.5.0' );
		return $check;
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-query.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-query.php#L19) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-query.php#L19-L5118)

## [Changelog](https://developer.wordpress.org/reference/classes/wp_query/\#changelog)

| Version | Description |
| --- | --- |
| [4.5.0](https://developer.wordpress.org/reference/since/4.5.0/) | Removed the `$comments_popup` property. |
| [1.5.0](https://developer.wordpress.org/reference/since/1.5.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/classes/wp_query/\#user-contributed-notes)

01. [Skip to note 32 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-2378)



    Beware of setting the `'post_status'` to anything other than `'public'`, as it can easily lead to an **information disclosure vulnerability** if you are not careful.



    Normally `WP_Query` applies logic that will ensure that it only returns posts that the current user should be able to view (e.g., `private` posts are excluded from low-privilege users). However, when you supply a value for `'post_status'` this capability-checking logic is effectively disabled. This means that if you pass `'post_status'` as `'private'`, private posts will be returned even if the current user is not even logged in.



    To ensure that the proper capability checks are applied, you must use [the `'perm'` arg](https://developer.wordpress.org/reference/classes/WP_Query/#permission-parameters) as well. It has two possible values: `'readable'` and `'editable'`. Passing this will ensure that only posts are returned that the user is allowed to read or edit, respectively.



    In summary, **always set `'perm' => 'readable'` when passing the `'post_status'` arg, if you are going to be exposing the query results to the user in any way**. And if the posts are going to be modified, pass `'perm' => 'editable'`.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D2378%23feedback-editor-2378)

02. [Skip to note 33 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5502)



    For lazy developers like me. :D


    You don’t need to read the full article. I already covered the most common scenario.





    `wp-includes/class-wp-query.php`
    [Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    <?php
    // WP_Query arguments
    $args = array(
        'post_type'              => array('post'), // use any for any kind of post type, custom post type slug for custom post type
        'post_status'            => array('publish'), // Also support: pending, draft, auto-draft, future, private, inherit, trash, any
        'posts_per_page'         => '5', // use -1 for all post
        'order'                  => 'DESC', // Also support: ASC
        'orderby'                => 'date', // Also support: none, rand, id, title, slug, modified, parent, menu_order, comment_count
        'tax_query'              => array(
            'relation' => 'OR', // Use AND for taking result on both condition true
            array(
                'taxonomy'         => 'category', // taxonomy slug
                'terms'            => array(1, 2), // term ids
                'field'            => 'term_id', // Also support: slug, name, term_taxonomy_id
                'operator'         => 'IN', // Also support: AND, NOT IN, EXISTS, NOT EXISTS
                'include_children' => true,
            ),
            array(
                'taxonomy'         => 'custom-category', // taxonomy slug
                'terms'            => array(1, 2), // term ids
                'field'            => 'term_id', // Also support: slug, name, term_taxonomy_id
                'operator'         => 'IN', // Also support: slug, name, term_taxonomy_id
                'include_children' => true,
            ),
        ),
        'meta_query'             => array(
            'relation' => 'OR', // Use AND for taking result on both condition true
            array(
                'key'     => 'meta-1', // any meta key
                'value'   => 'value-1', // value under that meta
                'compare' => 'LIKE', // Also support: =, !=, >, >=, <, <=, NOT LIKE, IN, NOT IN, BETWEEN, NOT BETWEEN, EXISTS, NOT EXISTS, REGEXP, NOT REGEXP, RLIKE
                'type'    => 'CHAR', // Also support: NUMERIC, BINARY, DATE, DATETIME, DECIMAL, SIGNED, UNSIGNED, TIME
            ),
            array(
                'key'     => 'meta-2', // any meta key
                'value'   => 'value-2', // value under that meta
                'compare' => 'LIKE', // Also support: =, !=, >, >=, <, <=, NOT LIKE, IN, NOT IN, BETWEEN, NOT BETWEEN, EXISTS, NOT EXISTS, REGEXP, NOT REGEXP, RLIKE
                'type'    => 'CHAR', // Also support: NUMERIC, BINARY, DATE, DATETIME, DECIMAL, SIGNED, UNSIGNED, TIME
            ),
        ),
    );

    // The Query
    $query = new WP_Query($args);

    // The Loop
    if ($query->have_posts()) {
        while ($query->have_posts()) {
            $query->the_post();
            // do something
        }
    } else {
        // no posts found
    }

    // Restore original Post Data
    wp_reset_postdata();
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5502%23feedback-editor-5502)

03. [Skip to note 34 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-1713)



    WordPress [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) Generator:



    [https://GenerateWP.com/wp\_query/](https://generatewp.com/wp_query/)





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D1713%23feedback-editor-1713)

04. [Skip to note 35 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-4747)



    When you need to query for posts that have a featured image (post thumbnail) set, you can use the meta\_query parameter like this:





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    $args = array(
        'meta_query' => array(
            array(
             'key' => '_thumbnail_id',
             'compare' => 'EXISTS'
            ),
        ),
    );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D4747%23feedback-editor-4747)

05. [Skip to note 36 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5834)



    When you need to retreive only last n posts, without pagination, it is useful to use undocumented (it is documented only on code) parameter ‘no\_found\_rows’ => true. This will increase performance.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5834%23feedback-editor-5834)

06. [Skip to note 37 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-2218)



    When using the \`fields\` parameter passed to [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/), the Object Cache parameters will be set to \`false\` by WP\_Query:





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    array(
    	...
    	'fields' => 'ids',
    	'cache_results' => false,			// Turned off by default since 'fields' was passed.
    	'update_post_meta_cache' => false, 	// Turned off by default since 'fields' was passed.
    	'update_post_term_cache' => false,	// Turned off by default since 'fields' was passed.
    	...
    );
    ```





    The reason being there’s no objects being returned and thus no objects to cache.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D2218%23feedback-editor-2218)

07. [Skip to note 38 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-2510)



    The documentation states that \` `tax` \` parameter is deprecated since 3.1(not working anymore) in favor of \` `tax_query` \`, but it does not explain how to use \` `tax_query` \` to get all posts that belongs to a taxonomy, regardless of \` `terms` \` value.



    Long story, short. If you want to get all posts from a specific taxonomy, set the \` `operator` \` to \` `EXISTS` \`.





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    $args = array(
        'post_type' => 'post',
        'post_status' => 'publish',
        'tax_query' => array(
            array(
                'taxonomy' => 'custom_taxonomy_slug',
                'operator' => 'EXISTS'
            ),
        ),
    );
    ```





    _Note: make sure to set the `post_type` value and replace the `custom_taxonomy_slug` string, if you copy/paste this snippet._





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D2510%23feedback-editor-2510)

08. [Skip to note 39 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-3377)



    Make sure that when you are setting a `meta_query type` to `DECIMAL`, that you have also set the precision and the scale, for example in your query array





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    'compare' => '>=',
    'type' => 'DECIMAL(5,2)',
    ```





    For more info check the MySQL manual [https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html](https://dev.mysql.com/doc/refman/8.0/en/fixed-point-types.html)





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D3377%23feedback-editor-3377)

09. [Skip to note 40 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-3451)



    If for some reason you’re storing comma separated values and you would like to find out if there is a match, you can use this regular expression.





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    [\
      'key'     => 'item_ids',\
      'value'   => '(:?^|,)(' . $item_id. ')(:?$|,)',\
      'compare' => 'REGEXP',\
    ]
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D3451%23feedback-editor-3451)

10. [Skip to note 41 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5309)



    Order Events by `start` date



    For date format `yyyy-mm-dd hh:mm:ss`





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php

    $args = array(
        'post_type'      => 'event',
        'post_status'    => 'publish',
        'meta_key'       => 'start',
        'meta_type'      => 'DATETIME',
        'orderby'        => 'meta_value',
        'order'          => 'ASC',
    );
    ```





    In this case `orderby` does not require `meta_value_datetime`.





    [Show feedback (1)](https://developer.wordpress.org/reference/classes/wp_query/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5309%23feedback-editor-5309)



- I thank you so much because I was getting crazy trying to order results by a datetime picker by ACF Pro. I was using this ` 'orderby' => 'meta_value_datetime' ` and it would just ignore it and sort by post date instead. I changed it to meta\_value and now it works correctly. My question is: WHY is that so?! ACF Pro stores datetime metas as “Y-m-d H:i” (i.e., for example, “2021-12-11 12:53:00”) so shouldn’t “meta\_value\_datetime” be the correct way? I just don’t understand.



[lupusyon](https://profiles.wordpress.org/lupusyon/) [4 years ago](https://developer.wordpress.org/reference/classes/wp_query/#comment-5535)


11. [Skip to note 42 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-2809)



    If [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) determines that the result will be singular ( `is_singular()` is true), it will ignore the `tax_query` parameter. To modify `tax_query`, use the `posts_clauses` filter to add the required SQL statements.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D2809%23feedback-editor-2809)

12. [Skip to note 43 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-3171)



    To clarify the order and orderby parameters, `orderby` definitely accepts either a string or array (with examples shown) but `order` only accepts strings. Internally, the only values accepted are ‘ASC’ and ‘DESC’ with all other inputs being cast to ‘DESC’ by default.



    To have multiple `order` values, use the array form of `orderby` and do not include an `order` parameter.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D3171%23feedback-editor-3171)

13. [Skip to note 44 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5025)



    [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) is limited to 5 meta query clauses





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5025%23feedback-editor-5025)

14. [Skip to note 45 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5837)



    For post\_types documentation, please highlight the default as being ‘post’ if not set and highlight ‘any’ as the parameter that needs to be passed to retrieve ids for all post types.





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    // Example of the issue and how to fix. Add 'any' to post_type if you have post ids from different post types
    $args = array(
        'post_type'  => 'any', // if any ids that are passed in post__in are not in post_type `post` it will be diregarded.
        'post__in'   => array( 1, 4, 200 )
    );

    $query = new WP_Query( $args );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5837%23feedback-editor-5837)

15. [Skip to note 46 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5873)



    I found an issue with the [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/), In paginated query the post displayed in first page repeats in the second page as well if any of the product from 1st page was skipped based on our conditions for the query. It happens because like if we need 16 products per page and for first page one product(e.g out of stock) was skipped. So, for 1st page it takes 17th product to complete our 16 products list. That’s expected. But now for 2nd page it don’t consider product which it had skipped for the 1st page and returns us 16 products including the 17th product again in the 2nd page results.



    I have tackled this issue, by avoiding pagination and getting specific number of posts from filtered array of ids(unseen products). Like below code.





    `wp-includes/class-wp-query.php`
    [Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    $last_seen       = array_search( get_option( 'ubp_last_seen', 0 ), $all_prod );
    			$unseen_products = array_slice( $all_prod, $last_seen + 1 );

    			$arg = array(
    				'post_type'      => array( 'product', 'product_variation' ),
    				'post__in'       => $unseen_products,
    				'orderby'        => 'post__in',
    				'posts_per_page' => $show_prod,
    				// 'paged'          => $paged,
    				'tax_query'      => array(
    					'relation' => 'OR',
    					array(
    						'taxonomy' => 'product_type',
    						'field'    => 'slug',
    						'terms'    => array( 'simple', 'product_variation' ),
    						'operator' => 'IN',
    					),
    					array(
    						'taxonomy' => 'product_type',
    						'operator' => 'NOT EXISTS',
    					),
    				),
    			);
    			if ( $product_hide_out_of_stock == 'yes' ) {
    				$arg['meta_query'] = array(
    					array(
    						'key'     => '_stock_status',
    						'value'   => 'instock',
    						'compare' => '=',
    					),
    				);
    			}

    			$arg      = apply_filters( 'ubp_loop_frontend_query_args', $arg );
    			$products = new WP_Query( $arg );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5873%23feedback-editor-5873)

16. [Skip to note 47 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5979)



    There’s a gotcha when using the `orderby` argument in combination with a `meta_value`. Whenever you’re using a `meta_value` any posts that don’t have that specific meta value are excluded from the query. E.g. if you’re sorting by a `meta_key` called `color` posts that don’t have that value won’t be included in the query.



    This is [documented behaviour](https://core.trac.wordpress.org/ticket/19653) and usually not a problem when creating posts with meta values from the admin interface because those values are initialised in the database (but set to an empty value). But when you’re creating posts using an automated process (perhaps using some kind of import script) this might be a problem.



    To fix this problem there are two solutions:


    1\. Make sure all posts have the meta value that you’re using for ordering


    2\. Change the SQL query done by WordPress





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5979%23feedback-editor-5979)

17. [Skip to note 48 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-6130)



    In case your query isn’t planned to paginate results, always pass `no_found_rows => true` to [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/).



    Doing so will speed up your query by informing WordPress not to run `SQL_CALC_FOUND_ROWS` on the SQL query. `SQL_CALC_FOUND_ROWS` calculates the total number of rows in your query, which is required to know the total amount of “pages” for pagination.





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    // Skip SQL_CALC_FOUND_ROWS for performance (no pagination).
    $posts = new WP_Query( array(
      'no_found_rows' => true,
    ) );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D6130%23feedback-editor-6130)

18. [Skip to note 49 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-6142)



    One undocumented note about `'operator'` in `'tax_query'`: if you set it to `'AND'` and pass a multiple term ids to `'terms'` – that will only work for same hierarchy level terms (it seems). If you pass it a valid subcategory id and a parent category id combination it will return empty, but if you split that into multiple tax\_query arrays, and use `'relation' => 'AND'` instead it’ll work.



    For example for this setup:

    `cat 1
- subcat 2
cat 3
- subcat 4`

This will work:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
'tax_query' => array(
    array(
        'terms'    => array( 2, 4 ),
        'operator' => 'AND',
    )
)
```

And this:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
'tax_query' => array(
    'relationship' => 'AND',
    array(
        'terms' => 1,
    ),
    array(
        'terms' => 4,
    )
)
```

This will not work:

`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)

```php
'tax_query' => array(
    array(
        'terms'    => array( 1, 4 ),
        'operator' => 'AND',
    )
)
```

[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D6142%23feedback-editor-6142)

19. [Skip to note 50 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-6793)



    `tax_query` will not work in a multisite context when using `switch_to_blog()` unless the taxonomy is registered on **both blogs.** The taxonomy does not need to be used or even applied to a valid post type on the current blog, but it must at least be registered. See: [https://core.trac.wordpress.org/ticket/32526](https://core.trac.wordpress.org/ticket/32526)





    `wp-includes/class-wp-query.php`
    [Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    switch_to_blog( 1 ); // Switch to main site from a subsite.

    $posts = get_posts(
    	array(
    		'post_type'        => 'post',
    		'posts_per_page'   => 10,
    		'post_status'      => 'publish',
    		'tax_query'        => array(
    			array(
    				'taxonomy' => 'my_taxonomy', // Must be registered on BOTH sites.
    				'field'    => 'slug',
    				'terms'    => 'some-term', // The terms are not needed on the subsite.
    			),
    		),
    	)
    );

    // Display posts.

    restore_current_blog();
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D6793%23feedback-editor-6793)

20. [Skip to note 51 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-6806)



    In WordPress 6.2+, within \` [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) \` you can set \`search\_columns\` parameter (not documented at time of writing) to specify the fields to search:





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    $query = new WP_Query( array(
        's'              => 'search term',
        'search_columns' => array( 'post_content', 'post_name', 'post_title' ),
    ) );
    ```







    [Show feedback (2)](https://developer.wordpress.org/reference/classes/wp_query/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D6806%23feedback-editor-6806)



- Thanks for sharing. That’s great to know. Is it possible to add ACF fields here as well or those still have to be done through `meta_query`?



[ashkanahmadi](https://profiles.wordpress.org/ashkanahmadi/) [1 year ago](https://developer.wordpress.org/reference/classes/wp_query/#comment-7100)

- @ashkanahmadi The `search_columns` parameter is limited to those three columns in the `wp_posts` table.



[crstauf](https://profiles.wordpress.org/crstauf/) [1 year ago](https://developer.wordpress.org/reference/classes/wp_query/#comment-7103)


21. [Skip to note 52 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-2315)



    Just a note — if you ever have occasion to use a `NOT EXISTS` clause, this will generate a sub-select in the SQL, which could be a performance problem in high-traffic environments.



    For example:





    `wp-includes/class-wp-query.php`
    [Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    $args = [\
                'post_type' => 'post',\
                'post_status' => 'publish',\
                'posts_per_page' => 1,\
                'tax_query' => [\
                    'relation' => 'OR',\
                    [\
                        'taxonomy' => 'team',\
                        'field' => 'slug',\
                        'terms' => $team_slug,\
                    ],\
    	            [\
    		            'taxonomy' => 'team',\
    		            'field' => 'id',\
    		            'operator' => 'NOT EXISTS',\
    	            ],\
                ],\
                'date_query' => [\
                    [\
                        'before' => $post_date,\
                        'inclusive' => false,\
                    ]\
                ],\
                'ignore_sticky_posts' => 1,\
            ];
    ```





    This is a “previous post” query that tries to match the same ‘team’ taxonomy term of the current post, or a post with no ‘team’ taxonomy term set. We deployed code similar to this on a high-traffic site, and it immediately ran into problems due to the MySQL load. Fortunately, we were able to implement an alternative quickly.



    I would recommend doing load testing in a test environment if you find yourself needing to use `EXISTS` or `NOT EXISTS`.





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D2315%23feedback-editor-2315)

22. [Skip to note 53 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-3334)



    Very handy example how to only order by multiple meta keys (taken from Stack Overflow)





    `wp-includes/class-wp-query.php`
    [Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    $args = array(
        'post_type'  => 'event',
        'meta_query' => array(
            'relation' => 'AND',
            'event_start_date_clause' => array(
                'key'     => '_event_start_date',
                'compare' => 'EXISTS',
            ),
            'event_start_time_clause' => array(
                'key'     => '_event_start_time',
                'compare' => 'EXISTS',
            ),
        ),
        'orderby' => array(
            'event_start_date_clause' => 'ASC',
            'event_start_time_clause' => 'ASC',
        ),
    );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D3334%23feedback-editor-3334)

23. [Skip to note 54 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5474)





    `wp-includes/class-wp-query.php`
    [Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    <?php

    if(is_user_logged_in()){
       $args = array(
        'category_name' => 'Flowers',
        'post_status' => 'draft,publish',
        'posts_per_page' => 3,
       );
    }
    else{
        $args = array(
        'category_name' => 'Flowers',
        'post_status' => 'publish',
        'posts_per_page' => 3,
    );
    }

    $flowerposts = new WP_query($args);

    if($flowerposts->have_posts()):
       while($flowerposts->have_posts()) : $flowerposts->the_post();
       ?>
      <h1><?php the_title(); ?></h1>
      <p><?php the_content(); ?>
      </p>

    <?php

    endwhile;
    endif;

    ?>
    ```





    **Output:**


    User login show 3 recent “Flowers Category” publish & draft posts


    User don’t log in show 3 recent “Flowers Category” publish posts just





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5474%23feedback-editor-5474)

24. [Skip to note 55 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-5759)



    To query posts in a specific taxonomy, the ‘taxonomy’ parameter is **required**.





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    // For example to get WC products in category 254:
    $args = array(
        'tax_query'     => array(
            array(
                'taxonomy'  => 'product_cat', // required
                'terms'     =>  254
            ),
        ),
        'post_type'     => 'product'
    );

    $query = new WP_Query( $args );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D5759%23feedback-editor-5759)

25. [Skip to note 56 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-6349)



    For the function code in the demonstration, the number of articles published today will be obtained, and the articles with the status of public release and top will be counted. Not accurate., If you want to get the number of articles posted today, you need to exclude the topmost articles, please refer to the following code:





    `wp-includes/class-wp-query.php`
    [Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
           function wpdocs_get_articles_count_today() {
                $today = getdate();
                $args = array(
                    'post_type' => 'post',
                    'post_status' => 'publish',
                    //'post__not_in' => get_option( 'sticky_posts' ), // Exclude top articles
                    'date_query' => array( //time
                        array(
                            'year' => $today['year'],
                            'month' => $today['mon'],
                            'day' => $today['mday'],
                        ),
                    ),
                );

                $query = new WP_Query( $args );

                return $query->post_count;
            }
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D6349%23feedback-editor-6349)

26. [Skip to note 57 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-6442)



    _meta\_value\_datetime_ to define order structure is not working at all, see [https://core.trac.wordpress.org/ticket/50081](https://core.trac.wordpress.org/ticket/50081)





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D6442%23feedback-editor-6442)

27. [Skip to note 58 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-6607)



    The standard loop example can be optimized a little. `wp_reset_postdata()` needs to be called only if the `the_post()` method has been used to alter the global `$post` variable.





    `wp-includes/class-wp-query.php`
    [Expand code](https://developer.wordpress.org/reference/classes/wp_query/#)

    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    // The Query.
    $the_query = new WP_Query( $args );

    // The Loop.
    if ( $the_query->have_posts() ) {
    	echo '<ul>';

    	while ( $the_query->have_posts() ) {
    		$the_query->the_post();
    		echo '<li>' . esc_html( get_the_title() ) . '</li>';
    	}

    	echo '</ul>';

    	// Restore original Post Data.
    	wp_reset_postdata();
    } else {
    	esc_html_e( 'Sorry, no posts matched your criteria.' );
    }
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D6607%23feedback-editor-6607)

28. [Skip to note 59 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-6804)



    You can use ‘title’ param to get the posts or any custom post type by title, which was added to WP version 4.4





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    $args = array(
    	'post_type' => 'ANY_POST_TYPE',
    	'title'     => 'Hello' // It seems to be case sensitive, so 'hello' and 'Hello' both are different.
    );
    $posts = new WP_Query( $args );
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D6804%23feedback-editor-6804)

29. [Skip to note 60 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-4283)



    Seems like you can use an array for the `cat` parameter, too.



    See line 1149:





    `wp-includes/class-wp-query.php`
    [Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




    ```php
    // If query string 'cat' is an array, implode it.
    if ( is_array( $q['cat'] ) ) {
    	$q['cat'] = implode( ',', $q['cat'] );
    }
    ```







    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D4283%23feedback-editor-4283)

30. [Skip to note 61 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-3931)



    `WP_Query` doesn’t always generate optimized queries, and by default there might be missing indexes, which can lead to performance issues and slow response.



    For example, In the `wp_postmeta` table, I suggest considering to remove the meta\_value from the index, because it is a largetext type, which cannot be indexed.



    I would recommend that you will try analyzing your database to see if there are missing or redundant indexes. you can use [EverSQL](https://www.eversql.com/) for that. (Disclaimer: I am EverSQL’s co-founder)





    [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D3931%23feedback-editor-3931)

31. [Skip to note 62 content](https://developer.wordpress.org/reference/classes/wp_query/#comment-content-83)



    A great way to learn about `WP_Query` is watching this talk:



    [http://wordpress.tv/2013/03/15/andrew-nacin-wp\_query-wordpress-in-depth/](http://wordpress.tv/2013/03/15/andrew-nacin-wp_query-wordpress-in-depth/)





    [Show feedback (1)](https://developer.wordpress.org/reference/classes/wp_query/#) [Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F%3Freplytocom%3D83%23feedback-editor-83)



- I found some strange behavior with [WP\_Query](https://developer.wordpress.org/reference/classes/wp_query/) and query\_posts when running it in an AJAX call with sort parameters. When I set it to sort by ‘title’ it would attempt to sort by meta\_value with the meta\_key of ‘title’. To fix this, I had to change the orderby value to ‘post\_title’. So this does not work as expected:







`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




```php
$the_query = new WP_Query( 	array( 		'orderby' =&gt; 'title' 		'order'   =&gt; 'ASC' 	) );
```





This does work:





`wp-includes/class-wp-query.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_query/#)




```php
$the_query = new WP_Query( 	array( 		'orderby' =&gt; 'post_title' 		'order'   =&gt; 'ASC' 	) );
```







[Aaron](https://profiles.wordpress.org/amilgrom/) [4 years ago](https://developer.wordpress.org/reference/classes/wp_query/#comment-5481)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_query%2F) before being able to contribute a note or feedback.

Notifications