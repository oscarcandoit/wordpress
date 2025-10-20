---
url: https://api.jquery.com/data/
scraped_at: 2025-10-20T03:04:02.228Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Store arbitrary data associated with the matched elements or return the value at the named data store for the first element in the set of matched elements.

#### Contents:

- [.data( key, value )](https://api.jquery.com/data/#data1)  - [.data( key, value )](https://api.jquery.com/data/#data-key-value)
  - [.data( obj )](https://api.jquery.com/data/#data-obj)
- [.data( key )](https://api.jquery.com/data/#data2)  - [.data( key )](https://api.jquery.com/data/#data-key)
  - [.data()](https://api.jquery.com/data/#data)

## .data( key, value )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Store arbitrary data associated with the matched elements.

- #### version added: [1.2.3](https://api.jquery.com/category/version/1.2.3/) [.data( key, value )](https://api.jquery.com/data/\#data-key-value)

  - **key**

    Type: [String](http://api.jquery.com/Types/#String)

    A string naming the piece of data to set.

  - **value**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    The new data value; this can be any Javascript type except `undefined`.
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.data( obj )](https://api.jquery.com/data/\#data-obj)

  - **obj**

    Type: [Object](http://api.jquery.com/Types/#Object)

    An object of key-value pairs of data to update.

The `.data()` method allows us to attach data of any type to DOM elements in a way that is safe from circular references and therefore from memory leaks.

We can set several distinct values for a single element and retrieve them later:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Using the `data()` method to update data does not affect attributes in the DOM. To set a `data-*` attribute value, use `[attr](https://api.jquery.com/attr/)`.

Prior to jQuery 1.4.3, `.data( obj )` completely replaced all data. Since jQuery 1.4.3, data is instead extended by shallow merge.

Since **jQuery 3**, every two-character sequence of "-" (U+002D) followed by a lowercase ASCII letter in a key is replaced by the uppercase version of the letter, in alignment with the [HTML dataset API](https://html.spec.whatwg.org/multipage/dom.html#dom-dataset). A statement like `$( "body" ).data( { "my-name": "aValue" } ).data();` will return `{ myName: "aValue" }`.

Due to the way browsers interact with plugins and external code, the `.data()` method cannot be used on `<object>` (unless it's a Flash plugin), `<applet>` or `<embed>` elements.

### Additional Notes:

- Note that this method currently does not provide cross-platform support for setting data on XML documents, as Internet Explorer does not allow data to be attached via expando properties.

- `undefined` is not recognized as a data value. Calls such as `.data( "name", undefined )` will return the jQuery object that it was called on, allowing for chaining.


Store then retrieve a value from the div element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo:

## .data( key )Returns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** Return arbitrary data associated with the first element in the jQuery collection, as set by data() or by an HTML5 `data-*` attribute.

- #### version added: [1.2.3](https://api.jquery.com/category/version/1.2.3/) [.data( key )](https://api.jquery.com/data/\#data-key)

  - **key**

    Type: [String](http://api.jquery.com/Types/#String)

    Name of the data stored.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.data()](https://api.jquery.com/data/\#data)

  - This signature does not accept any arguments.

The `.data()` method allows us to read data previously associated with DOM elements. We can retrieve several distinct values for a single element one at a time, or as a set:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

Calling `.data()` with no parameters returns a JavaScript object containing each stored value as a property. The object can be used directly to get data values (but note that property names originally containing dashes will have been modified as described below).

Since **jQuery 3**, every two-character sequence of "-" (U+002D) followed by a lowercase ASCII letter in a key is replaced by the uppercase version of the letter, in alignment with the [HTML dataset API](https://html.spec.whatwg.org/multipage/dom.html#dom-dataset). A statement like `$( "body" ).data( { "my-name": "aValue" } ).data();` will return `{ myName: "aValue" }`.

#### [HTML5 `data-*` Attributes](https://api.jquery.com/data/\#data-html5)

Since jQuery 1.4.3, [`data-*` attributes](https://html.spec.whatwg.org/multipage/dom.html#embedding-custom-non-visible-data-with-the-data-*-attributes) are used to initialize jQuery data. An element's `data-*` attributes are retrieved the first time the `data()` method is invoked upon it, and then are no longer accessed or mutated (all values are stored internally by jQuery).

Every attempt is made to convert the attribute's string value to a JavaScript value (this includes booleans, numbers, objects, arrays, and null). A string is only converted to a number if doing so doesn't change its representation (for example, the string "100" is converted to the number 100, but "1E02" and "100.000" are left as strings because their numeric value of 100 serializes to "100"). When a string starts with '{' or '\[', then `jQuery.parseJSON` is used to parse it; it must follow [valid JSON syntax](https://en.wikipedia.org/wiki/JSON#Data_types.2C_syntax_and_example) _including quoted property names_. A string not parseable as a JavaScript value is not converted.\
\
To retrieve a `data-*` attribute value as an unconverted string, use the `[attr()](https://api.jquery.com/attr/)` method.\
\
Since jQuery 1.6, dashes in `data-*` attribute names have been processed in alignment with the [HTML dataset API](https://html.spec.whatwg.org/multipage/dom.html#dom-dataset).\
\
For example, given the following HTML:\
\
|     |     |\
| --- | --- |\
| 1 | ```<br>``` |\
\
The following comparisons are all true:\
\
|     |     |\
| --- | --- |\
| 1<br>2<br>3<br>4 | ```<br>``` |\
\
### Additional Notes:\
\
- Note that this method currently does not provide cross-platform support for setting data on XML documents, as Internet Explorer does not allow data to be attached via expando properties.\
\
\
Get the data named "blah" stored at for an element.\
\
|     |     |\
| --- | --- |\
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61 | ```<br>``` |\
\
#### Demo: