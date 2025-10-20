---
url: https://developer.wordpress.org/plugins/javascript/summary
scraped_at: 2025-10-20T03:14:15.276Z
---

[Skip to content](https://developer.wordpress.org/plugins/javascript/summary/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Summary


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[JavaScript](https://developer.wordpress.org/plugins/javascript/)Summary

Search

# Summary

## In this article

Table of Contents

- [PHP](https://developer.wordpress.org/plugins/javascript/summary/#php)
- [jQuery](https://developer.wordpress.org/plugins/javascript/summary/#jquery)
- [More Information](https://developer.wordpress.org/plugins/javascript/summary/#more-information)

[↑ Back to top](https://developer.wordpress.org/plugins/javascript/summary/#wp--skip-link--target)

Here are all the example code snippets from the preceding discussion, assembled into two complete code pages: one for jQuery and the other for PHP.

## [PHP](https://developer.wordpress.org/plugins/javascript/summary/\#php)

This code resides on one of your plugin pages.

``
[Expand code](https://developer.wordpress.org/plugins/javascript/summary/#)

[Copy](https://developer.wordpress.org/plugins/javascript/summary/#)

```php
add_action( 'admin_enqueue_scripts', 'my_enqueue' );
function my_enqueue( $hook ) {
   if ( 'myplugin_settings.php' !== $hook ) {
      return;
   }

   wp_enqueue_script(
      'ajax-script',
      plugins_url( '/js/myjquery.js', __FILE__ ),
      array( 'jquery' ),
      '1.0.0',
      true
   );

   $title_nonce = wp_create_nonce( 'title_example' );
   wp_localize_script(
      'ajax-script',
      'my_ajax_obj',
      array(
         'ajax_url' => admin_url( 'admin-ajax.php' ),
         'nonce'    => $title_nonce,
      )
   );
}

add_action( 'wp_ajax_my_tag_count', 'my_ajax_handler' );
function my_ajax_handler() {
   check_ajax_referer( 'title_example' );

   $title = wp_unslash( $_POST['title'] );

   update_user_meta( get_current_user_id(), 'title_preference', $title );

   $args = array(
      'tag' => $title,
   );

   $the_query = new WP_Query( $args );

   echo esc_html( $title ) . ' (' . $the_query->post_count . ') ';

   wp_die(); // all ajax handlers should die when finished
}
```

## [jQuery](https://developer.wordpress.org/plugins/javascript/summary/\#jquery)

This code is in the file `js/myjquery.js` below your plugin folder.

``
[Expand code](https://developer.wordpress.org/plugins/javascript/summary/#)

[Copy](https://developer.wordpress.org/plugins/javascript/summary/#)

```javascript
jQuery(document).ready(function($) { 	   //wrapper
	$(".pref").change(function() { 		   //event
		var this2 = this; 		           //use in callback
		$.post(my_ajax_obj.ajax_url, { 	   //POST request
	       _ajax_nonce: my_ajax_obj.nonce, //nonce
			action: "my_tag_count",        //action
	  		title: this.value 	           //data
  		}, function(data) {		           //callback
			this2.nextSibling.remove();    //remove the current title
			$(this2).after(data); 	       //insert server response
		});
	});
});
```

And after storing the preference, the resulting post count is added to the selected title.

## [More Information](https://developer.wordpress.org/plugins/javascript/summary/\#more-information)

- [How To Use AJAX In WordPress](http://wp.smashingmagazine.com/2011/10/18/how-to-use-ajax-in-wordpress/ "External Site")
- [AJAX for WordPress](http://www.glennmessersmith.com/pages/wpajax.html "External Site")

First published

December 1, 2014

Last updated

November 17, 2022

[PreviousServer Side PHP and EnqueuingPrevious: Server Side PHP and Enqueuing](https://developer.wordpress.org/plugins/javascript/enqueuing/)

[NextCronNext: Cron](https://developer.wordpress.org/plugins/cron/)

Notifications