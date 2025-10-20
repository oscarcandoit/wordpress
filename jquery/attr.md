---
url: https://api.jquery.com/attr/
scraped_at: 2025-10-20T03:17:46.873Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the value of an attribute for the first element in the set of matched elements or set one or more attributes for every matched element.

#### Contents:

- [.attr( attributeName )](https://api.jquery.com/attr/#attr1)  - [.attr( attributeName )](https://api.jquery.com/attr/#attr-attributeName)
- [.attr( attributeName, value )](https://api.jquery.com/attr/#attr2)  - [.attr( attributeName, value )](https://api.jquery.com/attr/#attr-attributeName-value)
  - [.attr( attributes )](https://api.jquery.com/attr/#attr-attributes)
  - [.attr( attributeName, function )](https://api.jquery.com/attr/#attr-attributeName-function)

## .attr( attributeName )Returns: [String](http://api.jquery.com/Types/\#String)

**Description:** Get the value of an attribute for the first element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.attr( attributeName )](https://api.jquery.com/attr/\#attr-attributeName)

  - **attributeName**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the attribute to get.

The `.attr()` method gets the attribute value for only the _first_ element in the matched set. To get the value for each element individually, use a looping construct such as jQuery's `.each()` or `.map()` method.

Using jQuery's `.attr()` method to get the value of an element's attribute has two main benefits:

1. **Convenience**: It can be called directly on a jQuery object and chained to other jQuery methods.
2. **Cross-browser consistency**: The values of some attributes are reported inconsistently across browsers, and even across versions of a single browser. The `.attr()` method reduces such inconsistencies.

**Note:** Attribute values are strings with the exception of a few attributes such as value and tabindex.

As of jQuery 1.6, the `.attr()` method returns `undefined` for attributes that have not been set. **To retrieve and change DOM properties such as the `checked`, `selected`, or `disabled` state of form elements, use the [.prop()](https://api.jquery.com/prop/) method.**

#### Attributes vs. Properties

The difference between _attributes_ and _properties_ can be important in specific situations. **Before jQuery 1.6**, the `.attr()` method sometimes took property values into account when retrieving some attributes, which could cause inconsistent behavior. **As of jQuery 1.6**, the `.prop()` method provides a way to explicitly retrieve property values, while `.attr()` retrieves attributes.

For example, `selectedIndex`, `tagName`, `nodeName`, `nodeType`, `ownerDocument`, `defaultChecked`, and `defaultSelected` should be retrieved and set with the `[.prop()](https://api.jquery.com/prop/)` method. Prior to jQuery 1.6, these properties were retrievable with the `.attr()` method, but this was not within the scope of `attr`. These do not have corresponding attributes and are only properties.

Concerning boolean attributes, consider a DOM element defined by the HTML markup `<input type="checkbox" checked="" />`, and assume it is in a JavaScript variable named `elem`:

| `elem.checked` | `true` (Boolean) Will change with checkbox state |
| `$( elem ).prop( "checked" )` | `true` (Boolean) Will change with checkbox state |
| `elem.getAttribute( "checked" )` | `""` (String) Initial state of the checkbox; does not change |
| `$( elem ).attr( "checked" )` _(4.0+)_ | `""` (String) Initial state of the checkbox; does not change |
| `$( elem ).attr( "checked" )` _(1.6-3.x)_ | `"checked"` (String) Initial state of the checkbox; does not change |
| `$( elem ).attr( "checked" )` _(pre-1.6)_ | `true` (Boolean) Changed with checkbox state |

According to the [W3C forms specification](https://www.w3.org/TR/html401/interact/forms.html#h-17.4), the `checked` attribute is a _[boolean attribute](https://www.w3.org/TR/html4/intro/sgmltut.html#h-3.3.4.2)_, which means the corresponding property is **true** if the attribute is present at all—even if, for example, the attribute has no value or is set to empty string value or even "false". This is true of all boolean attributes.

Nevertheless, the most important concept to remember about the `checked` attribute is that it does not correspond to the `checked` property. The attribute actually corresponds to the `defaultChecked` property and should be used only to set the _initial_ value of the checkbox. The `checked` attribute value does not change with the state of the checkbox, while the `checked` property does. Therefore, the cross-browser-compatible way to determine if a checkbox is checked is to use the property:

- `if ( elem.checked )`
- `if ( $( elem ).prop( "checked" ) )`
- `if ( $( elem ).is( ":checked" ) )`

The same is true for other dynamic attributes, such as `selected` and `value`.

### Additional Notes:

- In Internet Explorer prior to version 9, using `[.prop()](https://api.jquery.com/prop/)` to set a DOM element property to anything other than a simple primitive value (number, string, or boolean) can cause memory leaks if the property is not removed (using [`.removeProp()`](https://api.jquery.com/removeProp/)) before the DOM element is removed from the document. To safely set values on DOM objects without memory leaks, use [`.data()`](https://api.jquery.com/data/).


### Example 1

Display the checked attribute and property of a checkbox as it changes.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo:

### Example 2

Find the title attribute of the first <em> in the page.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo:

## .attr( attributeName, value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set one or more attributes for the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.attr( attributeName, value )](https://api.jquery.com/attr/\#attr-attributeName-value)

  - **attributeName**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the attribute to set.

  - **value**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number) or [Null](http://api.jquery.com/Types/#Null) or [Boolean](http://api.jquery.com/Types/#Boolean)

    A value to set for the attribute. If `null`, the specified attribute will be removed (as in [`.removeAttr()`](https://api.jquery.com/removeAttr/)). Non-ARIA attributes can also be removed by passing `false`.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.attr( attributes )](https://api.jquery.com/attr/\#attr-attributes)

  - **attributes**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object of attribute-value pairs to set.
- #### version added: [1.1](https://api.jquery.com/category/version/1.1/) [.attr( attributeName, function )](https://api.jquery.com/attr/\#attr-attributeName-function)

  - **attributeName**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the attribute to set.

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) attr )
     =>
     [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number)

    A function returning the value to set. `this` is the current element. Receives the index position of the element in the set and the old attribute value as arguments.

The `.attr()` method is a convenient way to set the value of attributes—especially when setting multiple attributes or using values returned by a function. Consider the following image:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

#### Setting a simple attribute

To change the `alt` attribute, simply pass the name of the attribute and its new value to the `.attr()` method:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

_Add_ an attribute the same way:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

#### Setting several attributes at once

To change the `alt` attribute and add the `title` attribute at the same time, pass both sets of names and values into the method at once using a plain JavaScript object. Each key-value pair in the object adds or modifies an attribute:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

When setting multiple attributes, the quotes around attribute names are optional.

#### Removing an attribute

To remove an attribute, either call `.attr( name, null )` or use [`.removeAttr( name )`](https://api.jquery.com/removeAttr/). For non-ARIA attributes, in jQuery 4.0+ you can also call `.attr( name, false )`.

**Note:** Because [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) attributes frequently associate behavior with "false" values that differs from attribute absence, passing `false` as the value for an attribute whose name starts with `"aria-…"` will stringify that value to `"false"` rather than remove the attribute. To guarantee removal of an attribute, use the `.removeAttr()` method or provide `null` as the value to the `.attr()` setter.

**WARNING**: When setting the 'class' attribute, you must always use quotes!

**Note:** Attempting to change the `type` attribute on an `input` or `button` element created via `document.createElement()` will throw an exception on Internet Explorer 8 or older.

#### Computed attribute values

By using a function to set attributes, you can compute the value based on other properties of the element. For example, to concatenate a new value with an existing value:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This use of a function to compute attribute values can be particularly useful when modifying the attributes of multiple elements at once.

**Note:** If nothing is returned in the setter function (ie. `function(index, attr){}`), or if `undefined` is returned, the current value is not changed. This is useful for selectively setting values only when certain criteria are met.

### Example 1

Set some attributes for all <img>s in the page.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo:

### Example 2

Set the id for divs based on the position in the page.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 3

Set the src attribute from title attribute on the image.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

#### Demo: