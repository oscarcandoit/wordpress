---
url: https://api.jquery.com/empty/
scraped_at: 2025-10-20T03:16:43.797Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .empty()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove all child nodes of the set of matched elements from the DOM.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.empty()](https://api.jquery.com/empty/\#empty)

  - This method does not accept any arguments.

This method removes not only child (and other descendant) elements, but also any text within the set of matched elements. This is because, according to the DOM specification, any string of text within an element is considered a child node of that element. Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

We can target any element for removal:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This will result in a DOM structure with the `Hello` text deleted:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

If we had any number of nested elements inside `<div class="hello">`, they would be removed, too.

To avoid memory leaks, jQuery removes other constructs such as data and event handlers from the child elements before removing the elements themselves.

If you want to remove elements without destroying their data or event handlers (so they can be re-added later), use [`.detach()`](https://api.jquery.com/detach/) instead.

Removes all child nodes (including text nodes) from all paragraphs

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo: