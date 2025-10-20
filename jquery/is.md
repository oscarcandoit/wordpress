---
url: https://api.jquery.com/is/
scraped_at: 2025-10-20T03:01:37.249Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .is( selector )Returns: [Boolean](http://api.jquery.com/Types/\#Boolean)

**Description:** Check the current matched set of elements against a selector, element, or jQuery object and return `true` if at least one of these elements matches the given arguments.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.is( selector )](https://api.jquery.com/is/\#is-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.is( function )](https://api.jquery.com/is/\#is-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Element](http://api.jquery.com/Types/#Element) element )
     =>
     [Boolean](http://api.jquery.com/Types/#Boolean)

    A function used as a test for every element in the set. It accepts two arguments, `index`, which is the element's index in the jQuery collection, and `element`, which is the DOM element. Within the function, `this` refers to the current DOM element.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.is( selection )](https://api.jquery.com/is/\#is-selection)

  - **selection**

    Type: [jQuery](http://api.jquery.com/Types/#jQuery)

    An existing jQuery object to match the current set of elements against.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.is( elements )](https://api.jquery.com/is/\#is-elements)

  - **elements**

    Type: [Element](http://api.jquery.com/Types/#Element)

    One or more elements to match the current set of elements against.

Unlike other filtering methods, `.is()` does not create a new jQuery object. Instead, it allows you to test the contents of a jQuery object without modification. This is often useful inside callbacks, such as event handlers.

Suppose you have a list, with two of its items containing a child element:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

You can attach a click handler to the <ul> element, and then limit the code to be triggered only when a list item itself, not one of its children, is clicked:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

Now, when the user clicks on the word "list" in the first item or anywhere in the third item, the clicked list item will be given a red background. However, when the user clicks on item 1 in the first item or anywhere in the second item, nothing will occur, because in those cases the target of the event would be `<strong>` or `<span>`, respectively.

#### Using a Function

The second form of this method evaluates expressions related to elements based on a function rather than a selector. For each element, if the function returns `true`, `.is()` returns `true` as well. For example, given a somewhat more involved HTML snippet:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

You can attach a click handler to every `<li>` that evaluates the number of `<strong>` elements within the clicked `<li>` at that time like so:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |

### Example 1

Shows a few ways is() can be used inside an event handler.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66<br>67<br>68<br>69 | ```<br>``` |

#### Demo:

### Example 2

Returns true, because the parent of the input is a form element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26 | ```<br>``` |

#### Demo:

### Example 3

Returns false, because the parent of the input is a p element.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26 | ```<br>``` |

#### Demo:

### Example 4

Checks against an existing collection of alternating list elements. Blue, alternating list elements slide up while others turn red.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35 | ```<br>``` |

#### Demo:

### Example 5

An alternate way to achieve the above example using an element rather than a jQuery object. Checks against an existing collection of alternating list elements. Blue, alternating list elements slide up while others turn red.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo: