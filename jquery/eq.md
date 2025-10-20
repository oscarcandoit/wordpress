---
url: https://api.jquery.com/eq/
scraped_at: 2025-10-20T03:01:12.664Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .eq( index )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Reduce the set of matched elements to the one at the specified index.

- #### version added: [1.1.2](https://api.jquery.com/category/version/1.1.2/) [.eq( index )](https://api.jquery.com/eq/\#eq-index)

  - **index**

    Type: [Integer](http://api.jquery.com/Types/#Integer)

    An integer indicating the 0-based position of the element.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.eq( indexFromEnd )](https://api.jquery.com/eq/\#eq-indexFromEnd)

  - **indexFromEnd**

    Type: [Integer](http://api.jquery.com/Types/#Integer)

    An integer indicating the position of the element, counting backwards from the last element in the set.

Given a jQuery object that represents a set of DOM elements, the `.eq()` method constructs a new jQuery object from one element within that set. The supplied index identifies the position of this element in the set.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

We can apply this method to the set of list items:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background for item 3. Note that the supplied index is zero-based, and refers to the position of the element within the jQuery object, not within the DOM tree.

Providing a negative number indicates a position starting from the end of the set, rather than the beginning. For example:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This time list item 4 is turned red, since it is two from the end of the set.

If an element cannot be found at the specified zero-based index, the method constructs a new jQuery object with an empty set and a `length` property of 0.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Here, none of the list items is turned red, since `.eq( 5 )` indicates the sixth of five list items.

Turn the div with index 2 blue by adding an appropriate class.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo: