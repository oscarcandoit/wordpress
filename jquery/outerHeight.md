---
url: https://api.jquery.com/outerHeight/
scraped_at: 2025-10-20T03:03:38.451Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the current computed outer height (including padding, border, and optionally margin) for the first element in the set of matched elements or set the outer height of every matched element.

#### Contents:

- [.outerHeight( \[includeMargin \] )](https://api.jquery.com/outerHeight/#outerHeight1)  - [.outerHeight( \[includeMargin \] )](https://api.jquery.com/outerHeight/#outerHeight-includeMargin)
- [.outerHeight( value \[, includeMargin \] )](https://api.jquery.com/outerHeight/#outerHeight2)  - [.outerHeight( value \[, includeMargin \] )](https://api.jquery.com/outerHeight/#outerHeight-value-includeMargin)
  - [.outerHeight( function )](https://api.jquery.com/outerHeight/#outerHeight-function)

## .outerHeight( \[includeMargin \] )Returns: [Number](http://api.jquery.com/Types/\#Number)

**Description:** Get the current computed outer height (including padding, border, and optionally margin) for the first element in the set of matched elements.

- #### version added: [1.2.6](https://api.jquery.com/category/version/1.2.6/) [.outerHeight( \[includeMargin \] )](https://api.jquery.com/outerHeight/\#outerHeight-includeMargin)

  - **includeMargin** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether to include the element's margin in the calculation.

Returns the height of the element, including top and bottom padding, border, and optionally margin, in pixels. If called on an empty set of elements, returns `undefined` ( `null` before jQuery 3.0).

This method is not applicable to `window` and `document` objects; for these, use `[.height()](https://api.jquery.com/height/)` instead. Although `.outerHeight()` can be used on table elements, it may give unexpected results on tables using the `border-collapse: collapse` CSS property.

![](https://api.jquery.com/resources/0042_04_03.png)Figure 1 - Illustration of the measured height

### Additional Notes:

- The number returned by dimensions-related APIs, including `.outerHeight()`, may be fractional in some cases. Code should not assume it is an integer. Also, dimensions may be incorrect when the page is zoomed by the user; browsers do not expose an API to detect this condition.

- The value reported by `.outerHeight()` is not guaranteed to be accurate when the element or its parent is hidden. To get an accurate value, ensure the element is visible before using `.outerHeight()`. jQuery will attempt to temporarily show and then re-hide an element in order to measure its dimensions, but this is unreliable and (even when accurate) can significantly impact page performance. This show-and-rehide measurement feature may be removed in a future version of jQuery.


Get the outerHeight of a paragraph.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |

#### Demo:

## .outerHeight( value \[, includeMargin \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the CSS outer height of each element in the set of matched elements.

- #### version added: [1.8](https://api.jquery.com/category/version/1.8/) [.outerHeight( value \[, includeMargin \] )](https://api.jquery.com/outerHeight/\#outerHeight-value-includeMargin)

  - **value**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A number representing the number of pixels, or a number along with an optional unit of measure appended (as a string).

  - **includeMargin** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether to new value should account for the element's margin.
- #### version added: [1.8](https://api.jquery.com/category/version/1.8/) [.outerHeight( function )](https://api.jquery.com/outerHeight/\#outerHeight-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Number](http://api.jquery.com/Types/#Number) height )
     =>
     [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A function returning the outer height to set. Receives the index position of the element in the set and the old outer height as arguments. Within the function, `this` refers to the current element in the set.

When calling `.outerHeight(value)`, the value can be either a string (number and unit) or a number. If only a number is provided for the value, jQuery assumes a pixel unit. If a string is provided, however, any valid CSS measurement may be used (such as `100px`, `50%`, or `auto`).

Change the outer height of each div the first time it is clicked (and change its color).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40 | ```<br>``` |

#### Demo: