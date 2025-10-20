---
url: https://api.jquery.com/get/
scraped_at: 2025-10-20T03:16:07.284Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Retrieve the DOM elements matched by the jQuery object.

#### Contents:

- [.get( index )](https://api.jquery.com/get/#get1)  - [.get( index )](https://api.jquery.com/get/#get-index)
- [.get()](https://api.jquery.com/get/#get2)  - [.get()](https://api.jquery.com/get/#get)

## .get( index )Returns: [Element](http://api.jquery.com/Types/\#Element)

**Description:** Retrieve one of the elements matched by the jQuery object.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.get( index )](https://api.jquery.com/get/\#get-index)

  - **index**

    Type: [Integer](http://api.jquery.com/Types/#Integer)

    A zero-based integer indicating which element to retrieve.

The `.get()` method grants access to the DOM nodes underlying each jQuery object. If the value of `index` is out of bounds — less than the negative number of elements or equal to or greater than the number of elements — it returns `undefined`. Consider a simple unordered list:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

With an index specified, `.get( index )` retrieves a single element:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Since the index is zero-based, the first list item is returned:

`<li id="foo">`

Each jQuery object also masquerades as an array, so we can use the array dereferencing operator to get at the list item instead:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

However, this syntax lacks some of the additional capabilities of .get(), such as specifying a negative index:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

A negative index is counted from the end of the matched set, so this example returns the last item in the list:

`<li id="bar">`

Display the tag name of the click element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

## .get()Returns: [Array](http://api.jquery.com/Types/\#Array)

**Description:** Retrieve the elements matched by the jQuery object.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.get()](https://api.jquery.com/get/\#get)

  - This method does not accept any arguments.

Consider a simple unordered list:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Without a parameter, `.get()` returns an array of all of the elements:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

All of the matched DOM nodes are returned by this call, contained in a standard array:

\[<li id="foo">, <li id="bar">\]

Select all divs in the document and return the DOM Elements as an Array; then use the built-in reverse() method to reverse that array.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33 | ```<br>``` |

#### Demo: