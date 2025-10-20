---
url: https://api.jquery.com/jQuery.escapeSelector/
scraped_at: 2025-10-20T03:03:14.338Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## jQuery.escapeSelector( selector )Returns: [Selector](http://api.jquery.com/Types/\#Selector)

**Description:** Escapes any character that has a special meaning in a CSS selector.

- #### version added: [3.0](https://api.jquery.com/category/version/3.0/) [jQuery.escapeSelector( selector )](https://api.jquery.com/jQuery.escapeSelector/\#jQuery-escapeSelector-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to escape.

This method is useful for situations where a class name or an ID contains characters that have a special meaning in CSS, such as the dot or the semicolon.

The method is essentially a shim for the [CSS Working Group's CSS.escape() method](https://drafts.csswg.org/cssom/#the-css.escape()-method). The main difference is that `$.escapeSelector()` can be reliably used in all of jQuery's supported browsers.

### Example 1

Escape an ID containing a hash.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 2

Select all the elements having a class name of `.box` inside a `div`.

|     |     |
| --- | --- |
| 1 | ```<br>``` |