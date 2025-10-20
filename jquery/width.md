---
url: https://api.jquery.com/width/
scraped_at: 2025-10-20T03:03:54.913Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the current computed width for the first element in the set of matched elements or set the width of every matched element.

#### Contents:

- [.width()](https://api.jquery.com/width/#width1)  - [.width()](https://api.jquery.com/width/#width)
- [.width( value )](https://api.jquery.com/width/#width2)  - [.width( value )](https://api.jquery.com/width/#width-value)
  - [.width( function )](https://api.jquery.com/width/#width-function)

## .width()Returns: [Number](http://api.jquery.com/Types/\#Number)

**Description:** Get the current computed width for the first element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.width()](https://api.jquery.com/width/\#width)

  - This method does not accept any arguments.

The difference between `.css( "width" )` and `.width()` is that the latter returns a unit-less pixel value (for example, `400`) while the former returns a value with units intact (for example, `400px`). The `.width()` method is recommended when an element's width needs to be used in a mathematical calculation.

![](https://api.jquery.com/resources/0042_04_04.png)Figure 1 - Illustration of the measured width

This method is also able to find the width of the window and document.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Note that `.width()` will always return the content width, regardless of the value of the CSS `box-sizing` property. As of jQuery 1.8, this may require retrieving the CSS width plus `box-sizing` property and then subtracting any potential border and padding on each element when the element has `box-sizing: border-box`. To avoid this penalty, use `.css( "width" )` rather than `.width()`.

**Note:** Although `style` and `script` tags will report a value for `.width()` or `height()` when absolutely positioned and given `display:block`, it is strongly discouraged to call those methods on these tags. In addition to being a bad practice, the results may also prove unreliable.

### Additional Notes:

- The number returned by dimensions-related APIs, including `.width()`, may be fractional in some cases. Code should not assume it is an integer. Also, dimensions may be incorrect when the page is zoomed by the user; browsers do not expose an API to detect this condition.

- The value reported by `.width()` is not guaranteed to be accurate when the element or its parent is hidden. To get an accurate value, ensure the element is visible before using `.width()`. jQuery will attempt to temporarily show and then re-hide an element in order to measure its dimensions, but this is unreliable and (even when accurate) can significantly impact page performance. This show-and-rehide measurement feature may be removed in a future version of jQuery.


Show various widths. Note the values are from the iframe so might be smaller than you expected. The yellow highlight shows the iframe body.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51 | ```<br>``` |

#### Demo:

## .width( value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the CSS width of each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.width( value )](https://api.jquery.com/width/\#width-value)

  - **value**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    An integer representing the number of pixels, or an integer along with an optional unit of measure appended (as a string).
- #### version added: [1.4.1](https://api.jquery.com/category/version/1.4.1/) [.width( function )](https://api.jquery.com/width/\#width-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Integer](http://api.jquery.com/Types/#Integer) value )
     =>
     [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A function returning the width to set. Receives the index position of the element in the set and the old width as arguments. Within the function, `this` refers to the current element in the set.

When calling `.width("value")`, the value can be either a string (number and unit) or a number. If only a number is provided for the value, jQuery assumes a pixel unit. If a string is provided, however, any valid CSS measurement may be used for the width (such as `100px`, `50%`, or `auto`). Note that in modern browsers, the CSS width property does not include padding, border, or margin, unless the `box-sizing` CSS property is used.

If no explicit unit is specified (like "em" or "%") then "px" is assumed.

Note that `.width("value")` sets the content width of the box regardless of the value of the CSS `box-sizing` property.

Change the width of each div the first time it is clicked (and change its color).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39 | ```<br>``` |

#### Demo: