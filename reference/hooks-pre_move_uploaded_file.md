---
url: https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file
scraped_at: 2025-10-20T03:20:06.151Z
---

[Skip to content](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

pre\_move\_uploaded\_file


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Hooks](https://developer.wordpress.org/reference/hooks/)pre\_move\_uploaded\_file

Search

# apply\_filters( ‘pre\_move\_uploaded\_file’, mixed$move\_new\_file, array$file, string$new\_file, string$type )

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#description)
- [Parameters](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#parameters)
- [Source](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#source)
- [Related](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#related)
- [Changelog](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#wp--skip-link--target)

Filters whether to short-circuit moving the uploaded file after passing all checks.

## [Description](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/\#description)

If a non-null value is returned from the filter, moving the file and any related error reporting will be completely skipped.

## [Parameters](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/\#parameters)

`$move_new_file` mixed

If null (default) move the file after the upload.

`$file` array

Reference to a single element from `$_FILES`.

- `name` string
The original name of the file on the client machine.

- `type` string
The mime type of the file, if the browser provided this information.

- `tmp_name` string
The temporary filename of the file in which the uploaded file was stored on the server.

- `size` int
The size, in bytes, of the uploaded file.

- `error` int
The error code associated with this file upload.


`$new_file` string

Filename of the newly-uploaded file.

`$type` string

Mime type of the newly-uploaded file.

## [Source](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/\#source)

`wp-admin/includes/file.php`
[Copy](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#)

```php
$move_new_file = apply_filters( 'pre_move_uploaded_file', null, $file, $new_file, $type );

```

[View all references](https://developer.wordpress.org/reference/files/wp-admin/includes/file.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-admin/includes/file.php#L1010) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-admin/includes/file.php#L1010-L1010)

## [Related](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/\#related)

| Used by | Description |
| --- | --- |
| [\_wp\_handle\_upload()](https://developer.wordpress.org/reference/functions/_wp_handle_upload/) `wp-admin/includes/file.php` | Handles PHP uploads in WordPress. |

## [Changelog](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/\#changelog)

| Version | Description |
| --- | --- |
| [4.9.0](https://developer.wordpress.org/reference/since/4.9.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/\#user-contributed-notes)

1. [Skip to note 2 content](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#comment-content-6717)



There is an interesting [question](https://wordpress.org/support/topic/purpose-of-pre_move_uploaded_file-hook/) on this filter in the support forum with a rather complicated reply, however, I have to use this for a slightly different problem.



I normally use the function [`media_handle_sideload()`](https://developer.wordpress.org/reference/functions/media_handle_sideload/) to move a file into the wp uploads fodler and save it as a media attachment post, which works quite nicely.



However, recently I had to copy a file (rather than move it), in my plugin extension as the original plugin still needed to have access to the original file location (a temporary folder on the fs), and unfortunately there is no way to get the `media_handle_sideload()` to copy rather than move a file.



This is where this filter comes in handy. The `media_handle_sideload()` makes use of the [`wp_handle_sideload()`](https://developer.wordpress.org/reference/functions/wp_handle_sideload/), which in turns calls the `_wp_handle_upload()` function, within which the `pre_move_uploaded_file` filter is applied.



The filter can be used to switch off the actual moving of the file while retaining all the goodness of validation that the function handles, allowing one to handle the actual file handling, copying it instead of moving it in my case. This is how I used it,





`wp-admin/includes/file.php`
[Expand code](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#)

[Copy](https://developer.wordpress.org/reference/hooks/pre_move_uploaded_file/#)




```php
// first step is to identify the filename and path you want to copy.
$file_arr = array(
   	'name'     => $filename, //something like my-photo.jpg
   	'tmp_name' => $path, //something like /..../wp-content/uploads/cf7-uploads/tmp/my-photo.jpg
);

// next use a unique action handle to identify your file process from others handled by WP core/plugins.
$action = 'wpdocs_file_copy';

// this allows to identify your file action with the filter applied at the start of _wp_handle_upload().
// register your file handling process with an anonymous function.
add_filter( "{$action}_prefilter", function( $file ) {
   	// next we hook the filter to cancel the file move.
   	add_filter( 'pre_move_uploaded_file', function( $move, $file, $new_file ) {

   		// now you copy your file, knowing that the $new_file path has been validated by WP.
   		$move = @copy( $file['tmp_name'], $new_file );

   		if ( false === $move && WP_DEBUG ) {
   			trigger_error( ... ); // handle the error (optional).
   		}

   		return $move; // either false or true, but not null will cancel the file move.
   	}, 10, 3 ); // pre_move filter

   	return $file;
} ); // filter

// now you fire the actually file moving process which will validate the new location of the file on the fs and trigger the above filter.
$new_file_arr = wp_handle_sideload( $file_arr,
   	array(
   		'action'    => $action, // the action defined above.
   		'test_form' => false, // in this case the file I am copying is not coming from the $_FILES submission and so I don't need the extra validation.
   	),
   	current_time( 'mysql' ) // timestamp.
);

if ( isset( $new_file_arr['error'] ) ) { //in case there was an error.
   	// handle the error (optional)
} else {
   	$url      = $new_file_arr['url'];
   	$type     = $new_file_arr['type'];
   	$new_file = $new_file_arr['file'];
}
// you can then go on to create an attachment post and link it to a parent post if need be.
```





Note, the above only copies the file to the `wp-content/uploads/<year>/<month>/` folder structure, but does not actually create an attachment post (required to see your file in the Media section of the dashboard), nor links it to a parent post (eg as a featured/thumbnail image). If you need to see how to do this I suggest you take a look at the process used in the [`media_handle_sideload()`](https://developer.wordpress.org/reference/functions/media_handle_sideload/) function.





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_move_uploaded_file%2F%3Freplytocom%3D6717%23feedback-editor-6717)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fhooks%2Fpre_move_uploaded_file%2F) before being able to contribute a note or feedback.

Notifications