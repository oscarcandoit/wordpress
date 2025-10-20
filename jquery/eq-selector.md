---
url: https://api.jquery.com/eq-selector/
scraped_at: 2025-10-20T03:20:20.903Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## eq selectorversion deprecated: [3.4](https://api.jquery.com/category/version/3.4/)

**Description:** Select the element at index `n` within the matched set.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":eq(index)" )


**index:** Zero-based index of the element to match.

- #### version added: [1.8](https://api.jquery.com/category/version/1.8/)jQuery( ":eq(-index)" )


**indexFromEnd:** Zero-based index of the element to match, counting backwards from the last element.


**As of jQuery 3.4**, the `:eq` pseudo-class is deprecated. Remove it from your selectors and filter the results later using [`.eq()`](https://api.jquery.com/eq/).

The index-related selectors ( `:eq()`, `:lt()`, `:gt()`, `:even`, `:odd`) filter the set of elements that have matched the expressions that precede them. They narrow the set down based on the order of the elements within this matched set. For example, if elements are first selected with a class selector ( `.myclass`) and four elements are returned, these elements are given indices `0` through `3` for the purposes of these selectors.

Note that since JavaScript arrays use _0-based indexing_, these selectors reflect that fact. This is why `$( ".myclass:eq(1)" )` selects the second element in the document with the class myclass, rather than the first. In contrast, `:nth-child(n)` uses _1-based indexing_ to conform to the CSS specification.

Prior to jQuery 1.8, the `:eq(index)` selector did _not_ accept a negative value for `index` (though the [`.eq(index)`](https://api.jquery.com/eq/) method did).

### Additional Notes:

- Because `:eq()` is a jQuery extension and not part of the CSS specification, queries using `:eq()` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `$("your-pure-css-selector").eq(index)` instead.


### Example 1

Find the third td.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21 | ```<br>``` |

#### Demo:

### Example 2

Apply three different styles to list items to demonstrate that `:eq()` is designed to select a single element while `:nth-child()` or `:eq()` within a looping construct such as `.each()` can select multiple elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 3

Add a class to List 2, item 2 by targeting the second to last <li>

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo: