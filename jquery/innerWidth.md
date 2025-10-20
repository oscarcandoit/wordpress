---
url: https://api.jquery.com/innerWidth/
scraped_at: 2025-10-20T03:03:31.695Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the current computed inner width (including padding but not border) for the first element in the set of matched elements or set the inner width of every matched element.

#### Contents:

- [.innerWidth()](https://api.jquery.com/innerWidth/#innerWidth1)  - [.innerWidth()](https://api.jquery.com/innerWidth/#innerWidth)
- [.innerWidth( value )](https://api.jquery.com/innerWidth/#innerWidth2)  - [.innerWidth( value )](https://api.jquery.com/innerWidth/#innerWidth-value)
  - [.innerWidth( function )](https://api.jquery.com/innerWidth/#innerWidth-function)

## .innerWidth()Returns: [Number](http://api.jquery.com/Types/\#Number)

**Description:** Get the current computed inner width for the first element in the set of matched elements, including padding but not border.

- #### version added: [1.2.6](https://api.jquery.com/category/version/1.2.6/) [.innerWidth()](https://api.jquery.com/innerWidth/\#innerWidth)

  - This method does not accept any arguments.

This method returns the width of the element, including left and right padding, in pixels. If called on an empty set of elements, returns `undefined` ( `null` before jQuery 3.0).

This method is not applicable to `window` and `document` objects; for these, use `[.width()](https://api.jquery.com/width/)` instead.

![](https://api.jquery.com/resources/0042_04_05.png)Figure 1 - Illustration of the measured width

### Additional Notes:

- The number returned by dimensions-related APIs, including `.innerWidth()`, may be fractional in some cases. Code should not assume it is an integer. Also, dimensions may be incorrect when the page is zoomed by the user; browsers do not expose an API to detect this condition.

- The value reported by `.innerWidth()` is not guaranteed to be accurate when the element or its parent is hidden. To get an accurate value, ensure the element is visible before using `.innerWidth()`. jQuery will attempt to temporarily show and then re-hide an element in order to measure its dimensions, but this is unreliable and (even when accurate) can significantly impact page performance. This show-and-rehide measurement feature may be removed in a future version of jQuery.


Get the innerWidth of a paragraph.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26 | ```<br>``` |

#### Demo:

## .innerWidth( value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the CSS inner width of each element in the set of matched elements.

- #### version added: [1.8](https://api.jquery.com/category/version/1.8/) [.innerWidth( value )](https://api.jquery.com/innerWidth/\#innerWidth-value)

  - **value**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A number representing the number of pixels, or a number along with an optional unit of measure appended (as a string).
- #### version added: [1.8](https://api.jquery.com/category/version/1.8/) [.innerWidth( function )](https://api.jquery.com/innerWidth/\#innerWidth-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Number](http://api.jquery.com/Types/#Number) width )
     =>
     [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A function returning the inner width (including padding but not border) to set. Receives the index position of the element in the set and the old inner width as arguments. Within the function, `this` refers to the current element in the set.

When calling `.innerWidth("value")`, the value can be either a string (number and unit) or a number. If only a number is provided for the value, jQuery assumes a pixel unit. If a string is provided, however, any valid CSS measurement may be used for the width (such as `100px`, `50%`, or `auto`). Note that in modern browsers, the CSS width property does not include padding, border, or margin, unless the `box-sizing` CSS property is used.

If no explicit unit is specified (like "em" or "%") then "px" is assumed.

Change the inner width of each div the first time it is clicked (and change its color).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40 | ```<br>``` |

#### Demo: