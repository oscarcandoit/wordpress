---
url: https://api.jquery.com/css/
scraped_at: 2025-10-20T03:03:06.291Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the value of a computed style property for the first element in the set of matched elements or set one or more CSS properties for every matched element.

#### Contents:

- [.css( propertyName )](https://api.jquery.com/css/#css1)  - [.css( propertyName )](https://api.jquery.com/css/#css-propertyName)
  - [.css( propertyNames )](https://api.jquery.com/css/#css-propertyNames)
- [.css( propertyName, value )](https://api.jquery.com/css/#css2)  - [.css( propertyName, value )](https://api.jquery.com/css/#css-propertyName-value)
  - [.css( propertyName, function )](https://api.jquery.com/css/#css-propertyName-function)
  - [.css( properties )](https://api.jquery.com/css/#css-properties)

## .css( propertyName )Returns: [String](http://api.jquery.com/Types/\#String)

**Description:** Get the computed style properties for the first element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.css( propertyName )](https://api.jquery.com/css/\#css-propertyName)

  - **propertyName**

    Type: [String](http://api.jquery.com/Types/#String)

    A CSS property.
- #### version added: [1.9](https://api.jquery.com/category/version/1.9/) [.css( propertyNames )](https://api.jquery.com/css/\#css-propertyNames)

  - **propertyNames**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array of one or more CSS properties.

The `.css()` method is a convenient way to get a computed style property from the first matched element, especially in light of the different ways browsers access most of those properties (the `getComputedStyle()` method in standards-based browsers versus the `currentStyle` and `runtimeStyle` properties in Internet Explorer prior to version 9) and the different terms browsers use for certain properties. For example, Internet Explorer's DOM implementation refers to the `float` property as `styleFloat`, while W3C standards-compliant browsers refer to it as `cssFloat`. For consistency, you can simply use `"float"`, and jQuery will translate it to the correct value for each browser.

Also, jQuery can equally interpret the CSS and DOM formatting of multiple-word properties. For example, jQuery understands and returns the correct value for both `.css( "background-color" )` and `.css( "backgroundColor" )`. This means mixed case has a special meaning, `.css( "WiDtH" )` won't do the same as `.css( "width" )`, for example.

Note that the _computed style_ of an element may not be the same as the value specified for that element in a style sheet. For example, computed styles of dimensions are almost always pixels, but they can be specified as em, ex, px or % in a style sheet. Different browsers may return CSS color values that are logically but not textually equal, e.g., #FFF, #ffffff, and rgb(255,255,255).

Retrieval of shorthand CSS properties (e.g., `margin`, `background`, `border`), although functional with some browsers, is not guaranteed. For example, if you want to retrieve the rendered `border-width`, use: `$( elem ).css( "borderTopWidth" )`, `$( elem ).css( "borderBottomWidth" )`, and so on.

An element should be connected to the DOM when calling `.css()` on it. If it isn't, jQuery may throw an error.

**As of jQuery 1.9**, passing an array of style properties to `.css()` will result in an object of property-value pairs. For example, to retrieve all four rendered `border-width` values, you could use `$( elem ).css([ "borderTopWidth", "borderRightWidth", "borderBottomWidth", "borderLeftWidth" ])`.

**As of jQuery 3.2**, [CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) (also called CSS Variables) are supported: `$( "p" ).css( "--custom-property" )`. Note that you need to provide the property name as-is, camelCasing it won't work as it does for regular CSS properties.

### Example 1

Get the background color of a clicked div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo:

### Example 2

Get the width, height, text color, and background color of a clicked div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59 | ```<br>``` |

#### Demo:

## .css( propertyName, value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set one or more CSS properties for the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.css( propertyName, value )](https://api.jquery.com/css/\#css-propertyName-value)

  - **propertyName**

    Type: [String](http://api.jquery.com/Types/#String)

    A CSS property name.

  - **value**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A value to set for the property.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.css( propertyName, function )](https://api.jquery.com/css/\#css-propertyName-function)

  - **propertyName**

    Type: [String](http://api.jquery.com/Types/#String)

    A CSS property name.

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) value )
     =>
     [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A function returning the value to set. `this` is the current element. Receives the index position of the element in the set and the old value as arguments.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.css( properties )](https://api.jquery.com/css/\#css-properties)

  - **properties**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object of property-value pairs to set.

As with the `.prop()` method, the `.css()` method makes setting properties of elements quick and easy. This method can take either a property name and value as separate parameters, or a single object of key-value pairs.

Also, jQuery can equally interpret the CSS and DOM formatting of multiple-word properties. For example, jQuery understands and returns the correct value for both `.css({ "background-color": "#ffe", "border-left": "5px solid #ccc" })` and `.css({backgroundColor: "#ffe", borderLeft: "5px solid #ccc" })`. Notice that with the DOM notation, quotation marks around the property names are optional, but with CSS notation they're required due to the hyphen in the name.

In jQuery 3.x or older, when a number is passed as the value, jQuery will convert it to a string and add `px` to the end of that string. However, there are exceptions. `px` is not added to keys of [`jQuery.cssNumber`](https://api.jquery.com/jQuery.cssNumber/) If the property requires units other than `px`, convert the value to a string and add the appropriate units before calling the method.

In jQuery 4.0 or newer, when a number is passed as the value, jQuery will only convert it to a string and add `px` to the end of that string for a limited set of properties - mostly related to width, height, border, margin & padding; the full list:

- setting the element position: `top`, `right`, `bottom`, `left`
- setting the element dimensions: `width`, `height`, `min-width`, `min-height`, `max-width`, `max-height`
- `padding-related`: `padding`, `padding-top`, `padding-right`, `padding-bottom`, `padding-left`
- `margin`-related: `margin`, `margin-top`, `margin-right`, `margin-bottom`, `margin-left`
- `border`-related: `border`, `border-width`, `border-top`, `border-top-width`, `border-right`, `border-right-width`, `border-bottom`, `border-bottom-width`, `border-left`, `border-left-width`

When using `.css()` as a setter, jQuery modifies the element's `style` property. For example, `$( "#mydiv" ).css( "color", "green" )` is equivalent to `document.getElementById( "mydiv" ).style.color = "green"`. Setting the value of a style property to an empty string — e.g. `$( "#mydiv" ).css( "color", "" )` — removes that property from an element if it has already been directly applied, whether in the HTML style attribute, through jQuery's `.css()` method, or through direct DOM manipulation of the `style` property. As a consequence, the element's style for that property will be restored to whatever value was applied. So, this method can be used to cancel any style modification you have previously performed. It does not, however, remove a style that has been applied with a CSS rule in a stylesheet or `<style>` element. **Warning:** one notable exception is that, for IE 8 and below, removing a shorthand property such as `border` or `background` will remove that style entirely from the element, regardless of what is set in a stylesheet or `<style>` element.

**Note:** `.css()` doesn't support `!important` declarations. So, the statement `$( "p" ).css( "color", "red !important" )` does not turn the color of all paragraphs in the page to red as of jQuery 3.6.0. Do not depend on that _not working_, though, as a future version of jQuery may add support for such declarations. It's strongly advised to use classes instead; otherwise use a jQuery plugin.

As of jQuery 1.8, the `.css()` setter will automatically take care of prefixing the property name. For example, take `.css( "user-select", "none" )` in Chrome/Safari will set it as `-webkit-user-select`, Firefox will use `-moz-user-select`, and IE10 will use `-ms-user-select`.

As of jQuery 1.6, `.css()` accepts relative values similar to `.animate()`. Relative values are a string starting with `+=` or `-=` to increment or decrement the current value. For example, if an element's padding-left was 10px, `.css( "padding-left", "+=15" )` would result in a total padding-left of 25px.

As of jQuery 1.4, `.css()` allows us to pass a function as the property value:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This example sets the widths of the matched elements to incrementally larger values.

**Note:** If nothing is returned in the setter function (ie. `function( index, style ){} )`, or if `undefined` is returned, the current value is not changed. This is useful for selectively setting values only when certain criteria are met.

**As of jQuery 3.2**, [CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*) (also called CSS Variables) are supported: `$( "p" ).css( "--custom-property", "value" )`. Note that you need to provide the property name as-is, camelCasing it won't work as it does for regular CSS properties.

### Example 1

Change the color of any paragraph to red on mouseover event.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 2

Increase the width of #box by 200 pixels the first time it is clicked.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |

#### Demo:

### Example 3

Highlight a clicked word in the paragraph.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo:

### Example 4

Change the font weight and background color on mouseenter and mouseleave.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 5

Increase the size of a div when you click it.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo: