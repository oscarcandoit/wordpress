---
url: https://api.jquery.com/Odd-Selector/
scraped_at: 2025-10-20T03:23:23.688Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## odd selectorversion deprecated: [3.4](https://api.jquery.com/category/version/3.4/)

**Description:** Selects odd elements, zero-indexed. See also [`:even`](https://api.jquery.com/even-selector/).

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":odd" )


**As of jQuery 3.4**, the `:odd` pseudo-class is deprecated. Remove it from your selectors and filter the results later using [`.odd()`](https://api.jquery.com/odd/) (available in jQuery 3.5.0 or newer).

In particular, note that the _0-based indexing_ means that, counter-intuitively, `:odd` selects the second element, fourth element, and so on within the matched set.

### Additional Notes:

- Because `:odd` is a jQuery extension and not part of the CSS specification, queries using `:odd` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:odd` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":odd")`](https://api.jquery.com/filter/).

- Selected elements are in the order of their appearance in the document.


Finds odd table rows, matching the second, fourth and so on (index 1, 3, 5 etc.).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |

#### Demo: