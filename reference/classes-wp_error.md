---
url: https://developer.wordpress.org/reference/classes/wp_error
scraped_at: 2025-10-20T03:40:29.165Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/reference/classes/wp_error/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

WP\_Error


[Home](https://developer.wordpress.org/)[Reference](https://developer.wordpress.org/reference/)[Classes](https://developer.wordpress.org/reference/classes/)WP\_Error

Search

# class WP\_Error {}

## In this article

Table of Contents

- [Description](https://developer.wordpress.org/reference/classes/wp_error/#description)
- [More Information](https://developer.wordpress.org/reference/classes/wp_error/#more-information)
  - [Error Codes](https://developer.wordpress.org/reference/classes/wp_error/#error-codes)
- [Properties](https://developer.wordpress.org/reference/classes/wp_error/#properties)
  - [Related](https://developer.wordpress.org/reference/classes/wp_error/#related)
- [Methods](https://developer.wordpress.org/reference/classes/wp_error/#methods)
- [Source](https://developer.wordpress.org/reference/classes/wp_error/#source)
- [Changelog](https://developer.wordpress.org/reference/classes/wp_error/#changelog)
- [User Contributed Notes](https://developer.wordpress.org/reference/classes/wp_error/#user-contributed-notes)

[↑ Back to top](https://developer.wordpress.org/reference/classes/wp_error/#wp--skip-link--target)

WordPress Error class.

## [Description](https://developer.wordpress.org/reference/classes/wp_error/\#description)

Container for checking for WordPress errors and error messages. Return [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) and use [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/) to check if this class is returned. Many core WordPress functions pass this class in the event of an error and if not handled properly will result in code errors.

## [More Information](https://developer.wordpress.org/reference/classes/wp_error/\#more-information)

`[WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)` is a class that makes error handling within plugins and WordPress itself much easier.

Instances of `[WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)` store error codes and messages representing one or more errors, and whether or not a variable is an instance of `[WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/)` can be determined using the `[is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/ "Function Reference/is wp error")` function.

### [Error Codes](https://developer.wordpress.org/reference/classes/wp_error/\#error-codes)

Error codes are slugs that are used to identify each error. They are mostly useful when a piece of code can produce several different errors, and you want to handle each of those errors differently.

The error codes used in WordPress are not integers, but strings, with any spaces between words replaced with underscores (example: `an_error_code`). The error codes used in WordPress are usually based on the error message associated with that code.

## [Properties](https://developer.wordpress.org/reference/classes/wp_error/\#properties)

Please refer source code for the complete lists of properties. Below description may cover some of them.

`$errors`Array containing the list of errors.`$error_data`Array containing the list of data for error codes.

### [Related](https://developer.wordpress.org/reference/classes/wp_error/\#related)

- see [is\_wp\_error()](https://developer.wordpress.org/reference/functions/is_wp_error/ "Function Reference/is wp error") for more information on trapping for errors (particularly useful when faced with the dreaded ‘Catchable fatal error: Object of class [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) could not be converted to string’)

## [Methods](https://developer.wordpress.org/reference/classes/wp_error/\#methods)

| Name | Description |
| --- | --- |
| [WP\_Error::\_\_construct](https://developer.wordpress.org/reference/classes/wp_error/__construct/) | Initializes the error. |
| [WP\_Error::add](https://developer.wordpress.org/reference/classes/wp_error/add/) | Adds an error or appends an additional message to an existing error. |
| [WP\_Error::add\_data](https://developer.wordpress.org/reference/classes/wp_error/add_data/) | Adds data to an error with the given code. |
| [WP\_Error::copy\_errors](https://developer.wordpress.org/reference/classes/wp_error/copy_errors/) | Copies errors from one [WP\_Error](https://developer.wordpress.org/reference/classes/wp_error/) instance to another. |
| [WP\_Error::export\_to](https://developer.wordpress.org/reference/classes/wp_error/export_to/) | Exports the errors in this object into the given one. |
| [WP\_Error::get\_all\_error\_data](https://developer.wordpress.org/reference/classes/wp_error/get_all_error_data/) | Retrieves all error data for an error code in the order in which the data was added. |
| [WP\_Error::get\_error\_code](https://developer.wordpress.org/reference/classes/wp_error/get_error_code/) | Retrieves the first error code available. |
| [WP\_Error::get\_error\_codes](https://developer.wordpress.org/reference/classes/wp_error/get_error_codes/) | Retrieves all error codes. |
| [WP\_Error::get\_error\_data](https://developer.wordpress.org/reference/classes/wp_error/get_error_data/) | Retrieves the most recently added error data for an error code. |
| [WP\_Error::get\_error\_message](https://developer.wordpress.org/reference/classes/wp_error/get_error_message/) | Gets a single error message. |
| [WP\_Error::get\_error\_messages](https://developer.wordpress.org/reference/classes/wp_error/get_error_messages/) | Retrieves all error messages, or the error messages for the given error code. |
| [WP\_Error::has\_errors](https://developer.wordpress.org/reference/classes/wp_error/has_errors/) | Verifies if the instance contains errors. |
| [WP\_Error::merge\_from](https://developer.wordpress.org/reference/classes/wp_error/merge_from/) | Merges the errors in the given error object into this one. |
| [WP\_Error::remove](https://developer.wordpress.org/reference/classes/wp_error/remove/) | Removes the specified error. |

## [Source](https://developer.wordpress.org/reference/classes/wp_error/\#source)

`wp-includes/class-wp-error.php`
[Expand code](https://developer.wordpress.org/reference/classes/wp_error/#)

[Copy](https://developer.wordpress.org/reference/classes/wp_error/#)

```php
class WP_Error {
	/**
	 * Stores the list of errors.
	 *
	 * @since 2.1.0
	 * @var array
	 */
	public $errors = array();

	/**
	 * Stores the most recently added data for each error code.
	 *
	 * @since 2.1.0
	 * @var array
	 */
	public $error_data = array();

	/**
	 * Stores previously added data added for error codes, oldest-to-newest by code.
	 *
	 * @since 5.6.0
	 * @var array[]
	 */
	protected $additional_data = array();

	/**
	 * Initializes the error.
	 *
	 * If `$code` is empty, the other parameters will be ignored.
	 * When `$code` is not empty, `$message` will be used even if
	 * it is empty. The `$data` parameter will be used only if it
	 * is not empty.
	 *
	 * Though the class is constructed with a single error code and
	 * message, multiple codes can be added using the `add()` method.
	 *
	 * @since 2.1.0
	 *
	 * @param string|int $code    Error code.
	 * @param string     $message Error message.
	 * @param mixed      $data    Optional. Error data. Default empty string.
	 */
	public function __construct( $code = '', $message = '', $data = '' ) {
		if ( empty( $code ) ) {
			return;
		}

		$this->add( $code, $message, $data );
	}

	/**
	 * Retrieves all error codes.
	 *
	 * @since 2.1.0
	 *
	 * @return array List of error codes, if available.
	 */
	public function get_error_codes() {
		if ( ! $this->has_errors() ) {
			return array();
		}

		return array_keys( $this->errors );
	}

	/**
	 * Retrieves the first error code available.
	 *
	 * @since 2.1.0
	 *
	 * @return string|int Empty string, if no error codes.
	 */
	public function get_error_code() {
		$codes = $this->get_error_codes();

		if ( empty( $codes ) ) {
			return '';
		}

		return $codes[0];
	}

	/**
	 * Retrieves all error messages, or the error messages for the given error code.
	 *
	 * @since 2.1.0
	 *
	 * @param string|int $code Optional. Error code to retrieve the messages for.
	 *                         Default empty string.
	 * @return string[] Error strings on success, or empty array if there are none.
	 */
	public function get_error_messages( $code = '' ) {
		// Return all messages if no code specified.
		if ( empty( $code ) ) {
			$all_messages = array();
			foreach ( (array) $this->errors as $code => $messages ) {
				$all_messages = array_merge( $all_messages, $messages );
			}

			return $all_messages;
		}

		if ( isset( $this->errors[ $code ] ) ) {
			return $this->errors[ $code ];
		} else {
			return array();
		}
	}

	/**
	 * Gets a single error message.
	 *
	 * This will get the first message available for the code. If no code is
	 * given then the first code available will be used.
	 *
	 * @since 2.1.0
	 *
	 * @param string|int $code Optional. Error code to retrieve the message for.
	 *                         Default empty string.
	 * @return string The error message.
	 */
	public function get_error_message( $code = '' ) {
		if ( empty( $code ) ) {
			$code = $this->get_error_code();
		}
		$messages = $this->get_error_messages( $code );
		if ( empty( $messages ) ) {
			return '';
		}
		return $messages[0];
	}

	/**
	 * Retrieves the most recently added error data for an error code.
	 *
	 * @since 2.1.0
	 *
	 * @param string|int $code Optional. Error code. Default empty string.
	 * @return mixed Error data, if it exists.
	 */
	public function get_error_data( $code = '' ) {
		if ( empty( $code ) ) {
			$code = $this->get_error_code();
		}

		if ( isset( $this->error_data[ $code ] ) ) {
			return $this->error_data[ $code ];
		}
	}

	/**
	 * Verifies if the instance contains errors.
	 *
	 * @since 5.1.0
	 *
	 * @return bool If the instance contains errors.
	 */
	public function has_errors() {
		if ( ! empty( $this->errors ) ) {
			return true;
		}
		return false;
	}

	/**
	 * Adds an error or appends an additional message to an existing error.
	 *
	 * @since 2.1.0
	 *
	 * @param string|int $code    Error code.
	 * @param string     $message Error message.
	 * @param mixed      $data    Optional. Error data. Default empty string.
	 */
	public function add( $code, $message, $data = '' ) {
		$this->errors[ $code ][] = $message;

		if ( ! empty( $data ) ) {
			$this->add_data( $data, $code );
		}

		/**
		 * Fires when an error is added to a WP_Error object.
		 *
		 * @since 5.6.0
		 *
		 * @param string|int $code     Error code.
		 * @param string     $message  Error message.
		 * @param mixed      $data     Error data. Might be empty.
		 * @param WP_Error   $wp_error The WP_Error object.
		 */
		do_action( 'wp_error_added', $code, $message, $data, $this );
	}

	/**
	 * Adds data to an error with the given code.
	 *
	 * @since 2.1.0
	 * @since 5.6.0 Errors can now contain more than one item of error data. WP_Error::$additional_data.
	 *
	 * @param mixed      $data Error data.
	 * @param string|int $code Error code.
	 */
	public function add_data( $data, $code = '' ) {
		if ( empty( $code ) ) {
			$code = $this->get_error_code();
		}

		if ( isset( $this->error_data[ $code ] ) ) {
			$this->additional_data[ $code ][] = $this->error_data[ $code ];
		}

		$this->error_data[ $code ] = $data;
	}

	/**
	 * Retrieves all error data for an error code in the order in which the data was added.
	 *
	 * @since 5.6.0
	 *
	 * @param string|int $code Error code.
	 * @return mixed[] Array of error data, if it exists.
	 */
	public function get_all_error_data( $code = '' ) {
		if ( empty( $code ) ) {
			$code = $this->get_error_code();
		}

		$data = array();

		if ( isset( $this->additional_data[ $code ] ) ) {
			$data = $this->additional_data[ $code ];
		}

		if ( isset( $this->error_data[ $code ] ) ) {
			$data[] = $this->error_data[ $code ];
		}

		return $data;
	}

	/**
	 * Removes the specified error.
	 *
	 * This function removes all error messages associated with the specified
	 * error code, along with any error data for that code.
	 *
	 * @since 4.1.0
	 *
	 * @param string|int $code Error code.
	 */
	public function remove( $code ) {
		unset( $this->errors[ $code ] );
		unset( $this->error_data[ $code ] );
		unset( $this->additional_data[ $code ] );
	}

	/**
	 * Merges the errors in the given error object into this one.
	 *
	 * @since 5.6.0
	 *
	 * @param WP_Error $error Error object to merge.
	 */
	public function merge_from( WP_Error $error ) {
		static::copy_errors( $error, $this );
	}

	/**
	 * Exports the errors in this object into the given one.
	 *
	 * @since 5.6.0
	 *
	 * @param WP_Error $error Error object to export into.
	 */
	public function export_to( WP_Error $error ) {
		static::copy_errors( $this, $error );
	}

	/**
	 * Copies errors from one WP_Error instance to another.
	 *
	 * @since 5.6.0
	 *
	 * @param WP_Error $from The WP_Error to copy from.
	 * @param WP_Error $to   The WP_Error to copy to.
	 */
	protected static function copy_errors( WP_Error $from, WP_Error $to ) {
		foreach ( $from->get_error_codes() as $code ) {
			foreach ( $from->get_error_messages( $code ) as $error_message ) {
				$to->add( $code, $error_message );
			}

			foreach ( $from->get_all_error_data( $code ) as $data ) {
				$to->add_data( $data, $code );
			}
		}
	}
}

```

[View all references](https://developer.wordpress.org/reference/files/wp-includes/class-wp-error.php/) [View on Trac](https://core.trac.wordpress.org/browser/tags/6.8.3/src/wp-includes/class-wp-error.php#L19) [View on GitHub](https://github.com/WordPress/wordpress-develop/blob/6.8.3/src/wp-includes/class-wp-error.php#L19-L316)

## [Changelog](https://developer.wordpress.org/reference/classes/wp_error/\#changelog)

| Version | Description |
| --- | --- |
| [2.1.0](https://developer.wordpress.org/reference/since/2.1.0/) | Introduced. |

## [User Contributed Notes](https://developer.wordpress.org/reference/classes/wp_error/\#user-contributed-notes)

1. [Skip to note 4 content](https://developer.wordpress.org/reference/classes/wp_error/#comment-content-1973)





`wp-includes/class-wp-error.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_error/#)




```php
function doer_of_stuff() {
       return new WP_Error( 'broke', __( "I've fallen and can't get up", "my_textdomain" ) );
}

$return = doer_of_stuff();
if( is_wp_error( $return ) ) {
       echo $return->get_error_message();
}
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_error%2F%3Freplytocom%3D1973%23feedback-editor-1973)

2. [Skip to note 5 content](https://developer.wordpress.org/reference/classes/wp_error/#comment-content-6583)



Changing an error message.


This example searches for a message from WP Crontrol plugin:





`wp-includes/class-wp-error.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_error/#)




```php
add_action( 'wp_error_added', function ( $code, $message, $data, $wp_error ) {
   	if ( 'crontrol_info' === $code ) {
   		$wp_error->errors['crontrol_info'][0] = 'My custom message';

   		// The following will remove the error
    		// $wp_error->remove( $code );
   	}
}, 10, 4 );
```





The original error is built like this:





`wp-includes/class-wp-error.php`
[Copy](https://developer.wordpress.org/reference/classes/wp_error/#)




```php
new WP_Error( 'crontrol_info', 'WP-Cron spawning is disabled.' );
```







[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_error%2F%3Freplytocom%3D6583%23feedback-editor-6583)

3. [Skip to note 6 content](https://developer.wordpress.org/reference/classes/wp_error/#comment-content-5880)



Checking data on REST if data is empty generate 404 error message





[Log in to add feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_error%2F%3Freplytocom%3D5880%23feedback-editor-5880)


You must [log in](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fdeveloper.wordpress.org%2Freference%2Fclasses%2Fwp_error%2F) before being able to contribute a note or feedback.

Notifications