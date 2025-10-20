---
url: https://api.jquery.com/ID-Selector/
scraped_at: 2025-10-20T03:22:00.124Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## id selector

**Description:** Selects a single element with the given id attribute.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "\#id" )


**id:** An ID to search for, specified via the id attribute of an element.


For id selectors, jQuery uses the JavaScript function `document.getElementById()`, which is extremely efficient. When another selector is attached to the id selector, such as `h2#pageTitle`, jQuery performs an additional check before identifying the element as a match.

Calling `jQuery()` (or `$()`) with an id selector as its argument will return a jQuery object containing a collection of either zero or one DOM element.

Each `id` value must be used only once within a document. If more than one element has been assigned the same ID, queries that use that ID will only select the first matched element in the DOM. This behavior should not be relied on, however; a document with more than one element using the same ID is invalid.

If the id contains characters like periods or colons you have to [escape those characters with backslashes](https://learn.jquery.com/using-jquery-core/faq/how-do-i-select-an-element-by-an-id-that-has-characters-used-in-css-notation/).

### Example 1

Select the element with the id "myDiv" and give it a red border.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 2

Select the element with the id "myID.entry\[1\]" and give it a red border. Note how certain characters must be escaped with backslashes.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo: