---
url: https://api.jquery.com/find/
scraped_at: 2025-10-20T03:01:19.943Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .find( selector )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the descendants of each element in the current set of matched elements, filtered by a selector, jQuery object, or element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.find( selector )](https://api.jquery.com/find/\#find-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match elements against.
- #### version added: [1.6](https://api.jquery.com/category/version/1.6/) [.find( element )](https://api.jquery.com/find/\#find-element)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element) or [jQuery](http://api.jquery.com/Types/#jQuery)

    An element or a jQuery object to match elements against.

Given a jQuery object that represents a set of DOM elements, the `.find()` method allows us to search through the descendants of these elements in the DOM tree and construct a new jQuery object from the matching elements. The `.find()` and `.children()` methods are similar, except that the latter only travels a single level down the DOM tree.

The first signature for the `.find()` method accepts a selector expression of the same type that we can pass to the `$()` function. The elements will be filtered by testing whether they match this selector; all parts of the selector must lie inside of an element on which .find() is called. The expressions allowed include selectors like `> p` which will find all the paragraphs that are children of the elements in the jQuery object.

Consider a page with a basic nested list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

If we begin at item II, we can find list items within it:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background on items A, B, 1, 2, 3, and C. Even though item II matches the selector expression, it is not included in the results; only descendants are considered candidates for the match.

Unlike most of the tree traversal methods, the selector expression is required in a call to `.find()`. If we need to retrieve all of the descendant elements, we can pass in the universal selector `'*'` to accomplish this.

[Selector context](https://api.jquery.com/jquery/#selector-context) is implemented with the `.find()` `method;` therefore, `$( "li.item-ii" ).find( "li" )` is equivalent to `$( "li", "li.item-ii" )`.

**As of jQuery 1.6**, we can also filter the selection with a given jQuery collection or element. With the same nested list as above, if we start with:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

And then pass this jQuery object to find:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This will return a jQuery collection which contains only the list elements that are descendants of item II.

Similarly, an element may also be passed to find:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

The result of this call would be a red background on item 1.

### Example 1

Starts with all paragraphs and searches for descendant span elements, same as `$( "p span" )`

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18 | ```<br>``` |

#### Demo:

### Example 2

A selection using a jQuery collection of all span tags. Only spans within p tags are changed to red while others are left blue.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo:

### Example 3

Add spans around each word then add a hover and italicize words with the letter **t**.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49 | ```<br>``` |

#### Demo: