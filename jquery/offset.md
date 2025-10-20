---
url: https://api.jquery.com/offset/
scraped_at: 2025-10-20T03:03:35.284Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the current coordinates of the first element, or set the coordinates of every element, in the set of matched elements, relative to the document.

#### Contents:

- [.offset()](https://api.jquery.com/offset/#offset1)  - [.offset()](https://api.jquery.com/offset/#offset)
- [.offset( coordinates )](https://api.jquery.com/offset/#offset2)  - [.offset( coordinates )](https://api.jquery.com/offset/#offset-coordinates)
  - [.offset( function )](https://api.jquery.com/offset/#offset-function)

## .offset()Returns: [Object](http://api.jquery.com/Types/\#Object)

**Description:** Get the current coordinates of the first element in the set of matched elements, relative to the document.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.offset()](https://api.jquery.com/offset/\#offset)

  - This method does not accept any arguments.

The `.offset()` method allows us to retrieve the current position of an element (specifically its border box, which excludes margins) _relative to the document_. Contrast this with `[.position()](https://api.jquery.com/position/)`, which retrieves the current position _relative to the offset parent_. When positioning a new element on top of an existing one for global manipulation (in particular, for implementing drag-and-drop), `.offset()` is more useful.

`.offset()` returns an object containing the properties `top` and `left`.

**Note:** jQuery does not support getting the offset coordinates of hidden elements or accounting for margins set on the `<html>` document element.

While it is possible to get the coordinates of elements with `visibility:hidden` set, `display:none` is excluded from the rendering tree and thus has a position that is undefined.

### Additional Notes:

- The number returned by dimensions-related APIs, including `.offset()`, may be fractional in some cases. Code should not assume it is an integer. Also, dimensions may be incorrect when the page is zoomed by the user; browsers do not expose an API to detect this condition.


### Example 1

Access the offset of the second paragraph:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24 | ```<br>``` |

#### Demo:

### Example 2

Click to see the offset.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48 | ```<br>``` |

#### Demo:

## .offset( coordinates )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the current coordinates of every element in the set of matched elements, relative to the document.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.offset( coordinates )](https://api.jquery.com/offset/\#offset-coordinates)

  - **coordinates**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object containing the properties `top` and `left`, which are numbers indicating the new top and left coordinates for the elements.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.offset( function )](https://api.jquery.com/offset/\#offset-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [PlainObject](http://api.jquery.com/Types/#PlainObject) coords )
     =>
     [PlainObject](http://api.jquery.com/Types/#PlainObject)

    A function to return the coordinates to set. Receives the index of the element in the collection as the first argument and the current coordinates as the second argument. The function should return an object with the new `top` and `left` properties.

The `.offset()` setter method allows us to reposition an element. The element's border-box position is specified _relative to the document_. If the element's `position` style property is currently `static`, it will be set to `relative` to allow for this repositioning.

Set the offset of the second paragraph:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo: