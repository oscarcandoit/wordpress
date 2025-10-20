---
url: https://api.jquery.com/jQuery.data/
scraped_at: 2025-10-20T03:04:13.246Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Store arbitrary data associated with the specified element and/or return the value that was set.

#### Contents:

- [jQuery.data( element, key, value )](https://api.jquery.com/jQuery.data/#jQuery-data1)   - [jQuery.data( element, key, value )](https://api.jquery.com/jQuery.data/#jQuery-data-element-key-value)
- [jQuery.data( element, key )](https://api.jquery.com/jQuery.data/#jQuery-data2)  - [jQuery.data( element, key )](https://api.jquery.com/jQuery.data/#jQuery-data-element-key)
  - [jQuery.data( element )](https://api.jquery.com/jQuery.data/#jQuery-data-element)

## jQuery.data( element, key, value )Returns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** Store arbitrary data associated with the specified element. Returns the value that was set.

- #### version added: [1.2.3](https://api.jquery.com/category/version/1.2.3/) [jQuery.data( element, key, value )](https://api.jquery.com/jQuery.data/\#jQuery-data-element-key-value)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    The DOM element to associate with the data.

  - **key**

    Type: [String](http://api.jquery.com/Types/#String)

    A string naming the piece of data to set.

  - **value**

    Type: [Anything](http://api.jquery.com/Types/#Anything)

    The new data value; this can be any Javascript type except `undefined`.

**Note:** This is a low-level method; a more convenient `[.data()](https://api.jquery.com/data/)` is also available.

The `jQuery.data()` method allows us to attach data of any type to DOM elements in a way that is safe from circular references and therefore free from memory leaks. jQuery ensures that the data is removed when DOM elements are removed via jQuery methods, and when the user leaves the page. We can set several distinct values for a single element and retrieve them later:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Additional Notes:

- Note that this method currently does not provide cross-platform support for setting data on XML documents, as Internet Explorer does not allow data to be attached via expando properties.

- `undefined` is not recognized as a data value. Calls such as `jQuery.data( el, "name", undefined )` will return the corresponding data for "name", and is therefore the same as `jQuery.data( el, "name" )`.


Store then retrieve a value from the div element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

## jQuery.data( element, key )Returns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** Returns value at named data store for the element, as set by `jQuery.data(element, name, value)`, or the full data store for the element.

- #### version added: [1.2.3](https://api.jquery.com/category/version/1.2.3/) [jQuery.data( element, key )](https://api.jquery.com/jQuery.data/\#jQuery-data-element-key)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    The DOM element to query for the data.

  - **key**

    Type: [String](http://api.jquery.com/Types/#String)

    Name of the data stored.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [jQuery.data( element )](https://api.jquery.com/jQuery.data/\#jQuery-data-element)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    The DOM element to query for the data.

**Note:** This is a low-level method; a more convenient `[.data()](https://api.jquery.com/data/)` is also available.

**Regarding HTML5 data-\* attributes:** This low-level method does NOT retrieve the `data-*` attributes unless the more convenient `[.data()](https://api.jquery.com/data/)` method has already retrieved them.

The `jQuery.data()` method allows us to attach data of any type to DOM elements in a way that is safe from circular references and therefore from memory leaks. We can retrieve several distinct values for a single element one at a time, or as a set:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

The above lines alert the data values that were set on the `body` element. If nothing was set on that element, an empty string is returned.

Calling `jQuery.data( element )` retrieves all of the element's associated values as a JavaScript object. Note that jQuery itself uses this method to store data for internal use, such as event handlers, so do not assume that it contains only data that your own code has stored.

_Note:_ this method currently does not provide cross-platform support for setting data on XML documents, as Internet Explorer does not allow data to be attached via expando properties.

Get the data named "blah" stored at for an element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60 | ```<br>``` |

#### Demo: