---
url: https://api.jquery.com/last-selector/
scraped_at: 2025-10-20T03:29:14.243Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## last selectorversion deprecated: [3.4](https://api.jquery.com/category/version/3.4/)

**Description:** Selects the last matched element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":last" )


**As of jQuery 3.4**, the `:last` pseudo-class is deprecated. Remove it from your selectors and filter the results later using [`.last()`](https://api.jquery.com/last/).

Note that `:last` selects a single element by filtering the current jQuery collection and matching the last element within it.

### Additional Notes:

- Because `:last` is a jQuery extension and not part of the CSS specification, queries using `:last` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:last` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":last")`](https://api.jquery.com/filter/).


Finds the last table row.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21 | ```<br>``` |

#### Demo: