---
url: https://api.jquery.com/parent-selector/
scraped_at: 2025-10-20T03:29:37.246Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## parent selector

**Description:** Select all elements that have at least one child node (either an element or text).

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":parent" )


This is the inverse of `:empty`.

One important thing to note regarding the use of `:parent` (and `:empty`) is that child nodes include text nodes.

The W3C recommends that the `<p>` element have at least one child node, even if that child is merely text (see [https://www.w3.org/TR/html401/struct/text.html#edef-P](https://www.w3.org/TR/html401/struct/text.html#edef-P)). Some other elements, on the other hand, are empty (i.e. have no children) by definition: ` <input>`, `<img>`, `<br>`, and `<hr>`, for example.

To obtain the parents or ancestors of an existing jQuery set, see the `[.parent()](https://api.jquery.com/parent/)` and `[.parents()](https://api.jquery.com/parents/)` methods.

### Additional Notes:

- Because `:parent` is a jQuery extension and not part of the CSS specification, queries using `:parent` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:parent` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":parent")`](https://api.jquery.com/filter/).


Finds all tds with children, including text.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26 | ```<br>``` |

#### Demo: