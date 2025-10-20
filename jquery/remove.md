---
url: https://api.jquery.com/remove/
scraped_at: 2025-10-20T03:17:07.544Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .remove( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove the set of matched elements from the DOM.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.remove( \[selector \] )](https://api.jquery.com/remove/\#remove-selector)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector expression that filters the set of matched elements to be removed.

Similar to `[.empty()](https://api.jquery.com/empty/)`, the `.remove()` method takes elements out of the DOM. Use `.remove()` when you want to remove the element itself, as well as everything inside it. In addition to the elements themselves, all bound events and jQuery data associated with the elements are removed. To remove the elements without removing data and events, use `[.detach()](https://api.jquery.com/detach/)` instead.

Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

We can target any element for removal:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This will result in a DOM structure with the `<div>` element deleted:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

If we had any number of nested elements inside `<div class="hello">`, they would be removed, too. Other jQuery constructs such as data or event handlers are erased as well.

We can also include a selector as an optional parameter. For example, we could rewrite the previous DOM removal code as follows:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This would result in the same DOM structure:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 1

Removes all paragraphs from the DOM

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

### Example 2

Removes all paragraphs that contain "Hello" from the DOM. Analogous to doing `$("p").filter(":contains('Hello')").remove()`.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo: