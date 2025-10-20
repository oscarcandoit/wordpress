---
url: https://api.jquery.com/first-selector/
scraped_at: 2025-10-20T03:28:27.194Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## first selectorversion deprecated: [3.4](https://api.jquery.com/category/version/3.4/)

**Description:** Selects the first matched DOM element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":first" )


**As of jQuery 3.4**, the `:first` pseudo-class is deprecated. Remove it from your selectors and filter the results later using [`.first()`](https://api.jquery.com/first/).

The `:first` pseudo-class is equivalent to `:eq( 0 )`. It could also be written as `:lt( 1 )`. While this matches only a single element, [:first-child](https://api.jquery.com/first-child-selector/) can match more than one: One for each parent.

### Additional Notes:

- Because `:first` is a jQuery extension and not part of the CSS specification, queries using `:first` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:first` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":first")`](https://api.jquery.com/filter/).

- Selected elements are in the order of their appearance in the document.


Finds the first table row.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |

#### Demo: