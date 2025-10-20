---
url: https://api.jquery.com/prop/
scraped_at: 2025-10-20T03:17:59.211Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the value of a property for the first element in the set of matched elements or set one or more properties for every matched element.

#### Contents:

- [.prop( propertyName )](https://api.jquery.com/prop/#prop1)  - [.prop( propertyName )](https://api.jquery.com/prop/#prop-propertyName)
- [.prop( propertyName, value )](https://api.jquery.com/prop/#prop2)  - [.prop( propertyName, value )](https://api.jquery.com/prop/#prop-propertyName-value)
  - [.prop( properties )](https://api.jquery.com/prop/#prop-properties)
  - [.prop( propertyName, function )](https://api.jquery.com/prop/#prop-propertyName-function)

## .prop( propertyName )Returns: [Anything](http://api.jquery.com/Types/\#Anything)

**Description:** Get the value of a property for the first element in the set of matched elements.

- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.prop( propertyName )](https://api.jquery.com/prop/\#prop-propertyName)

  - **propertyName**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the property to get.

The `.prop()` method gets the property value for only the _first_ element in the matched set. It returns `undefined` for the value of a property that has not been set, or if the matched set has no elements. To get the value for each element individually, use a looping construct such as jQuery's `.each()` or `.map()` method.

**Note:** Attempting to change the `type` property (or attribute) of an `input` element created via HTML or already in an HTML document will result in an error being thrown by Internet Explorer 6, 7, or 8.

#### Attributes vs. Properties

The difference between _attributes_ and _properties_ can be important in specific situations. **Before jQuery 1.6**, the `[.attr()](https://api.jquery.com/attr/)` method sometimes took property values into account when retrieving some attributes, which could cause inconsistent behavior. **As of jQuery 1.6**, the `.prop()` method provides a way to explicitly retrieve property values, while `.attr()` retrieves attributes.

For example, `selectedIndex`, `tagName`, `nodeName`, `nodeType`, `ownerDocument`, `defaultChecked`, and `defaultSelected` should be retrieved and set with the `.prop()` method. Prior to jQuery 1.6, these properties were retrievable with the `.attr()` method, but this was not within the scope of `attr`. These do not have corresponding attributes and are only properties.

Concerning boolean attributes, consider a DOM element defined by the HTML markup `<input type="checkbox" checked="checked" />`, and assume it is in a JavaScript variable named `elem`:

| `elem.checked` | `true` (Boolean) Will change with checkbox state |
| `$( elem ).prop( "checked" )` | `true` (Boolean) Will change with checkbox state |
| `elem.getAttribute( "checked" )` | `"checked"` (String) Initial state of the checkbox; does not change |
| `$( elem ).attr( "checked" )` _(1.6+)_ | `"checked"` (String) Initial state of the checkbox; does not change |
| `$( elem ).attr( "checked" )` _(pre-1.6)_ | `true` (Boolean) Changed with checkbox state |

According to the [W3C forms specification](https://www.w3.org/TR/html401/interact/forms.html#h-17.4), the `checked` attribute is a _[boolean attribute](https://www.w3.org/TR/html4/intro/sgmltut.html#h-3.3.4.2)_, which means the corresponding property is **true** if the attribute is present at all—even if, for example, the attribute has no value or is set to empty string value or even "false". This is true of all boolean attributes.

Nevertheless, the most important concept to remember about the `checked` attribute is that it does not correspond to the `checked` property. The attribute actually corresponds to the `defaultChecked` property and should be used only to set the _initial_ value of the checkbox. The `checked` attribute value does not change with the state of the checkbox, while the `checked` property does. Therefore, the cross-browser-compatible way to determine if a checkbox is checked is to use the property:

- `if ( elem.checked )`
- `if ( $( elem ).prop( "checked" ) )`
- `if ( $( elem ).is( ":checked" ) )`

The same is true for other dynamic attributes, such as `selected` and `value`.

### Additional Notes:

- In Internet Explorer prior to version 9, using `[.prop()](https://api.jquery.com/prop/)` to set a DOM element property to anything other than a simple primitive value (number, string, or boolean) can cause memory leaks if the property is not removed (using [`.removeProp()`](https://api.jquery.com/removeProp/)) before the DOM element is removed from the document. To safely set values on DOM objects without memory leaks, use [`.data()`](https://api.jquery.com/data/).


Display the checked property and attribute of a checkbox as it changes.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo:

## .prop( propertyName, value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set one or more properties for the set of matched elements.

- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.prop( propertyName, value )](https://api.jquery.com/prop/\#prop-propertyName-value)

  - **propertyName**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the property to set.

  - **value**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    A value to set for the property.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.prop( properties )](https://api.jquery.com/prop/\#prop-properties)

  - **properties**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object of property-value pairs to set.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.prop( propertyName, function )](https://api.jquery.com/prop/\#prop-propertyName-function)

  - **propertyName**

    Type: [String](http://api.jquery.com/Types/#String)

    The name of the property to set.

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Anything](http://api.jquery.com/Types/#Anything) oldPropertyValue )
     =>
     [Anything](http://api.jquery.com/Types/#Anything)

    A function returning the value to set. Receives the index position of the element in the set and the old property value as arguments. Within the function, the keyword `this` refers to the current element.

The `.prop()` method is a convenient way to set the value of properties—especially when setting multiple properties, using values returned by a function, or setting values on multiple elements at once. It should be used when setting `selectedIndex`, `tagName`, `nodeName`, `nodeType`, `ownerDocument`, `defaultChecked`, or `defaultSelected`. Since jQuery 1.6, these properties can no longer be set with the `.attr()` method. They do not have corresponding attributes and are only properties.

Properties generally affect the dynamic state of a DOM element without changing the serialized HTML attribute. Examples include the `value` property of input elements, the `disabled` property of inputs and buttons, or the `checked` property of a checkbox. The `.prop()` method should be used to set disabled and checked instead of the `[.attr()](https://api.jquery.com/attr/)` method. The `[.val()](https://api.jquery.com/val/)` method should be used for getting and setting value.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

**Important:** the `[.removeProp()](https://api.jquery.com/removeProp/)` method should not be used to remove native properties. This will lead to unexpected behavior. See `[.removeProp()](https://api.jquery.com/removeProp/)` for more information.

#### Computed property values

By using a function to set properties, you can compute the value based on other properties of the element. For example, to toggle all checkboxes based off their individual values:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

**Note:** If nothing is returned in the setter function (ie. `function( index, prop ){})`, or if `undefined` is returned, the current value is not changed. This is useful for selectively setting values only when certain criteria are met.

### Additional Notes:

- In Internet Explorer prior to version 9, using `[.prop()](https://api.jquery.com/prop/)` to set a DOM element property to anything other than a simple primitive value (number, string, or boolean) can cause memory leaks if the property is not removed (using [`.removeProp()`](https://api.jquery.com/removeProp/)) before the DOM element is removed from the document. To safely set values on DOM objects without memory leaks, use [`.data()`](https://api.jquery.com/data/).


Disable all checkboxes on the page.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo: