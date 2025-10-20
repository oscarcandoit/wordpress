---
url: https://api.jquery.com/lt-selector/
scraped_at: 2025-10-20T03:22:21.208Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## lt selectorversion deprecated: [3.4](https://api.jquery.com/category/version/3.4/)

**Description:** Select all elements at an index less than `index` within the matched set.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":lt(index)" )


**index:** Zero-based index.

- #### version added: [1.8](https://api.jquery.com/category/version/1.8/)jQuery( ":lt(-index)" )


**indexFromEnd:** Zero-based index, counting backwards from the last element.


**As of jQuery 3.4**, the `:lt` pseudo-class is deprecated. Remove it from your selectors and filter the results later using [`.slice()`](https://api.jquery.com/slice/). For example, `:lt(3)` can be replaced with a call to `.slice( 0, 3 )`.

**index-related selectors**

The index-related selectors (including this "less than" selector) filter the set of elements that have matched the expressions that precede them. They narrow the set down based on the order of the elements within this matched set. For example, if elements are first selected with a class selector ( `.myclass`) and four elements are returned, these elements are given indices 0 through 3 for the purposes of these selectors.

Note that since JavaScript arrays use _0-based indexing_, these selectors reflect that fact. This is why `$( ".myclass:lt(1)" )` selects the first element in the document with the class `myclass`, rather than selecting no elements. In contrast, `:nth-child(n)` uses _1-based indexing_ to conform to the CSS specification.

Prior to jQuery 1.8, the `:lt(index)` selector did _not_ accept a negative value for `index`

### Additional Notes:

- Because `:lt()` is a jQuery extension and not part of the CSS specification, queries using `:lt()` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `$("your-pure-css-selector").slice(0, index)` instead.


Give TDs less than the one with the 4th index (TD#4) a yellow background and TDs less than the one with -2nd index a red text color.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo: