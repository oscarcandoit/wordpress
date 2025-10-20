---
url: https://developer.wordpress.org/plugins/javascript/jquery
scraped_at: 2025-10-20T03:14:20.649Z
---

[Skip to content](https://developer.wordpress.org/plugins/javascript/jquery/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

jQuery


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[JavaScript](https://developer.wordpress.org/plugins/javascript/)jQuery

Search

# jQuery

## In this article

Table of Contents

- [Using jQuery](https://developer.wordpress.org/plugins/javascript/jquery/#using-jquery)

[↑ Back to top](https://developer.wordpress.org/plugins/javascript/jquery/#wp--skip-link--target)

## [Using jQuery](https://developer.wordpress.org/plugins/javascript/jquery/\#using-jquery)

Your jQuery script runs on the user’s browser after your WordPress webpage is received. A basic jQuery statement has two parts: a selector that determines which HTML elements the code applies to, and an action or event, which determines what the code does or what it reacts to. The basic event statement looks like this:

``
[Copy](https://developer.wordpress.org/plugins/javascript/jquery/#)

```javascript
jQuery.(selector).event(function);
```

When an event, such as a mouse click, occurs in an HTML element selected by the selector, the function that is defined inside the final set of parentheses is executed.

All the following code examples are based on this HTML page content. Assume it appears on your plugin’s admin settings screen, defined by the file `myplugin_settings.php`. It is a simple table with radio buttons next to each title.

``
[Expand code](https://developer.wordpress.org/plugins/javascript/jquery/#)

[Copy](https://developer.wordpress.org/plugins/javascript/jquery/#)

```markup
<form id="radioform">
	<table>
		<tbody>
		<tr>
			<td><input class="pref" checked="checked" name="book" type="radio" value="Sycamore Row" />Sycamore Row</td>
			<td>John Grisham</td>
		</tr>
		<tr>
			<td><input class="pref" name="book" type="radio" value="Dark Witch" />Dark Witch</td>
			<td>Nora Roberts</td>
		</tr>
		</tbody>
	</table>
</form>
```

The output could look something like this on your settings page.

![sample table](https://i0.wp.com/make.wordpress.org/docs/files/2013/11/pdh-ajax-example.png?ssl=1)

In the [article on AJAX](https://developer.wordpress.org/plugin/javascript/ajax/ "AJAX"), we will build an AJAX exchange that saves the user selection in usermeta and adds the number of posts tagged with the selected title. Not a very practical application, but it illustrates all the important steps. jQuery code can either reside in an external file or be output to the page inside a `<script>` block. We will focus on the external file variation because passing values from PHP requires special attention. The same code can be output to the page if that seems more expedient to you.

#### [Selector and Event](https://developer.wordpress.org/plugins/javascript/jquery/\#selector-and-event)

The selector is the same form as CSS selectors: `".class"` or `"#id"`. There’s many [more forms](http://api.jquery.com/category/selectors/ "jQuery Reference"), but these are the two you will frequently use. In our example, we will use class `".pref"`. There’s also a slew of possible [events](http://api.jquery.com/category/events/ "jQuery Reference"), one you will likely use a lot is _‘click’_. In our example we will use _‘change’_ to capture a radio button selection. Be aware that jQuery events are often named somewhat differently than those with JavaScript. So far, after we add in an empty anonymous function, our example statement looks like this:

``
[Copy](https://developer.wordpress.org/plugins/javascript/jquery/#)

```javascript
$.(".pref").change(function(){
	/*do stuff*/
});
```

This code will “do stuff” when any element of the “pref” class changes.

**Note:** This code snippet, and all examples on this page, are for illustrating the use of AJAX. The code is not suitable for production environments because related operations such as [sanitization](https://developer.wordpress.org/plugins/plugin-security/securing-input/ "Handbook Chapter"), [security](https://developer.wordpress.org/plugins/plugin-security/user-capabilities-nonces/#nonces "Handbook Chapter"), [error handling](http://www.sitepoint.com/error-handling-in-php/ "External Site"), and [internationalization](https://developer.wordpress.org/plugins/javascript/internationalization/ "Handbook Chapter") have been intentionally omitted. Be sure to always address these important operations in your production code.

First published

October 28, 2014

Last updated

November 17, 2022

[PreviousHeartbeat APIPrevious: Heartbeat API](https://developer.wordpress.org/plugins/javascript/heartbeat-api/)

[NextAJAXNext: AJAX](https://developer.wordpress.org/plugins/javascript/ajax/)

Notifications