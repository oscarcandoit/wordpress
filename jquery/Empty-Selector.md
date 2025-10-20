---
url: https://api.jquery.com/empty-selector/
scraped_at: 2025-10-20T03:27:59.114Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## empty selector

**Description:** Select all elements that have no children (including text nodes).

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":empty" )


This is the inverse of `:parent`.

One important thing to note with :empty (and :parent) is that child elements include text nodes.

The W3C recommends that the `<p>` element have at least one child node, even if that child is merely text (see https://www.w3.org/TR/html401/struct/text.html#edef-P). Some other elements, on the other hand, are empty (i.e. have no children) by definition: <input>, <img>, <br>, and <hr>, for example.

Finds all elements that are empty - they don't have child elements or text.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo: