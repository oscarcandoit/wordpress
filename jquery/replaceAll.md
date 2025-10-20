---
url: https://api.jquery.com/replaceAll/
scraped_at: 2025-10-20T03:17:11.148Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .replaceAll( target )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Replace each target element with the set of matched elements.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.replaceAll( target )](https://api.jquery.com/replaceAll/\#replaceAll-target)

  - **target**

    Type: [Selector](http://api.jquery.com/Types/#Selector) or [jQuery](http://api.jquery.com/Types/#jQuery) or [Array](http://api.jquery.com/Types/#Array) or [Element](http://api.jquery.com/Types/#Element)

    A selector string, jQuery object, DOM element, or array of elements indicating which element(s) to replace.

The `.replaceAll()` method is similar to `[.replaceWith()](https://api.jquery.com/replaceWith/)`, but with the source and target reversed. Consider this DOM structure:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

We can create an element, then replace other elements with it:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This causes all of them to be replaced:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Or, we could select an element to use as the replacement:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This results in the DOM structure:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

From this example, we can see that the selected element replaces the target by being moved from its old location, not by being cloned.

### Additional Notes:

- The `.replaceAll()` method removes all data and event handlers associated with the removed nodes.


Replace all the paragraphs with bold words.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

#### Demo: