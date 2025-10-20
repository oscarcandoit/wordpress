---
url: https://api.jquery.com/prependTo/
scraped_at: 2025-10-20T03:17:03.386Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .prependTo( target )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Insert every element in the set of matched elements to the beginning of the target.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.prependTo( target )](https://api.jquery.com/prependTo/\#prependTo-target)

  - **target**

    Type: [Selector](http://api.jquery.com/Types/#Selector) or [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Array](http://api.jquery.com/Types/#Array) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A selector, element, HTML string, array of elements, or jQuery object; the matched set of elements will be inserted at the beginning of the element(s) specified by this parameter.

The `[.prepend()](https://api.jquery.com/prepend/)` and `.prependTo()` methods perform the same task. The major difference is in the syntax-specifically, in the placement of the content and target. With `.prepend()`, the selector expression preceding the method is the container into which the content is inserted. With `.prependTo()`, on the other hand, the content precedes the method, either as a selector expression or as markup created on the fly, and it is inserted into the target container.

Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

We can create content and insert it into several elements at once:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Each inner `<div>` element gets this new content:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |

We can also select an element on the page and insert it into another:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

If an element selected this way is inserted into a single location elsewhere in the DOM, it will be moved into the target (not cloned):

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

If there is more than one target element, however, cloned copies of the inserted element will be created for each target except the last.

### Additional Notes:

- By design, any jQuery constructor or method that accepts an HTML string — [jQuery()](https://api.jquery.com/jQuery/), [.append()](https://api.jquery.com/append/), [.after()](https://api.jquery.com/after/), etc. — can potentially execute code. This can occur by injection of script tags or use of HTML attributes that execute code (for example, `<img onload="">`). Do not use these methods to insert strings obtained from untrusted sources such as URL query parameters, cookies, or form inputs. Doing so can introduce cross-site-scripting (XSS) vulnerabilities. Remove or escape any user input before adding content to the document.

- jQuery doesn't officially support SVG. Using jQuery methods on SVG documents, unless explicitly documented for that method, might cause unexpected behaviors. Examples of methods that support SVG as of jQuery 3.0 are `addClass` and `removeClass`.


Prepend all spans to the element with the ID "foo" (Check .prepend() documentation for more examples)

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo: