---
url: https://api.jquery.com/append/
scraped_at: 2025-10-20T03:16:26.381Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .append( content \[, content \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Insert content, specified by the parameter, to the end of each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.append( content \[, content \] )](https://api.jquery.com/append/\#append-content-content)

  - **content**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Text](http://api.jquery.com/Types/#Text) or [Array](http://api.jquery.com/Types/#Array) or [jQuery](http://api.jquery.com/Types/#jQuery)

    DOM element, text node, array of elements and text nodes, HTML string, or jQuery object to insert at the end of each element in the set of matched elements.

  - **content**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Text](http://api.jquery.com/Types/#Text) or [Array](http://api.jquery.com/Types/#Array) or [jQuery](http://api.jquery.com/Types/#jQuery)

    One or more additional DOM elements, text nodes, arrays of elements and text nodes, HTML strings, or jQuery objects to insert at the end of each element in the set of matched elements.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.append( function )](https://api.jquery.com/append/\#append-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) html )
     =>
     [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Text](http://api.jquery.com/Types/#Text) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A function that returns an HTML string, DOM element(s), text node(s), or jQuery object to insert at the end of each element in the set of matched elements. Receives the index position of the element in the set and the old HTML value of the element as arguments. Within the function, `this` refers to the current element in the set.

The `.append()` method inserts the specified content as the last child of each element in the jQuery collection (To insert it as the _first_ child, use [`.prepend()`](https://api.jquery.com/prepend/)).

The `.append()` and `[.appendTo()](https://api.jquery.com/appendTo/)` methods perform the same task. The major difference is in the syntax-specifically, in the placement of the content and target. With `.append()`, the selector expression preceding the method is the container into which the content is inserted. With `.appendTo()`, on the other hand, the content precedes the method, either as a selector expression or as markup created on the fly, and it is inserted into the target container.

Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

You can create content and insert it into several elements at once:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Each inner `<div>` element gets this new content:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |

You can also select an element on the page and insert it into another:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

If an element selected this way is inserted into a single location elsewhere in the DOM, it will be moved into the target (not cloned):

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

**Important**: If there is more than one target element, however, cloned copies of the inserted element will be created for each target except for the last one.

#### Additional Arguments

Similar to other content-adding methods such as `[.prepend()](https://api.jquery.com/prepend/)` and `[.before()](https://api.jquery.com/before/)`, `.append()` also supports passing in multiple arguments as input. Supported input includes DOM elements, jQuery objects, HTML strings, and arrays of DOM elements.

For example, the following will insert two new `<div>` s and an existing `<div>` as the last three child nodes of the body:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Since `.append()` can accept any number of additional arguments, the same result can be achieved by passing in the three `<div>` s as three separate arguments, like so: `$('body').append( $newdiv1, newdiv2, existingdiv1 )`. The type and number of arguments will largely depend on how you collect the elements in your code.

### Additional Notes:

- By design, any jQuery constructor or method that accepts an HTML string — [jQuery()](https://api.jquery.com/jQuery/), [.append()](https://api.jquery.com/append/), [.after()](https://api.jquery.com/after/), etc. — can potentially execute code. This can occur by injection of script tags or use of HTML attributes that execute code (for example, `<img onload="">`). Do not use these methods to insert strings obtained from untrusted sources such as URL query parameters, cookies, or form inputs. Doing so can introduce cross-site-scripting (XSS) vulnerabilities. Remove or escape any user input before adding content to the document.

- jQuery doesn't officially support SVG. Using jQuery methods on SVG documents, unless explicitly documented for that method, might cause unexpected behaviors. Examples of methods that support SVG as of jQuery 3.0 are `addClass` and `removeClass`.


### Example 1

Appends some HTML to all paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo:

### Example 2

Appends an Element to all paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo:

### Example 3

Appends a jQuery object (similar to an Array of DOM Elements) to all paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo: