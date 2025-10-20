---
url: https://api.jquery.com/after/
scraped_at: 2025-10-20T03:16:23.018Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .after( content \[, content \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Insert content, specified by the parameter, after each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.after( content \[, content \] )](https://api.jquery.com/after/\#after-content-content)

  - **content**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Text](http://api.jquery.com/Types/#Text) or [Array](http://api.jquery.com/Types/#Array) or [jQuery](http://api.jquery.com/Types/#jQuery)

    HTML string, DOM element, text node, array of elements and text nodes, or jQuery object to insert after each element in the set of matched elements.

  - **content**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Text](http://api.jquery.com/Types/#Text) or [Array](http://api.jquery.com/Types/#Array) or [jQuery](http://api.jquery.com/Types/#jQuery)

    One or more additional DOM elements, text nodes, arrays of elements and text nodes, HTML strings, or jQuery objects to insert after each element in the set of matched elements.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.after( function )](https://api.jquery.com/after/\#after-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index )
     =>
     [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Text](http://api.jquery.com/Types/#Text) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A function that returns an HTML string, DOM element(s), text node(s), or jQuery object to insert after each element in the set of matched elements. Receives the index position of the element in the set as an argument. Within the function, `this` refers to the current element in the set.
- #### version added: [1.10-and-2.0](https://api.jquery.com/category/version/1.10-and-2.0/) [.after( function-html )](https://api.jquery.com/after/\#after-function-html)

  - **function-html**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) html )
     =>
     [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Text](http://api.jquery.com/Types/#Text) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A function that returns an HTML string, DOM element(s), text node(s), or jQuery object to insert after each element in the set of matched elements. Receives the index position of the element in the set and the old HTML value of the element as arguments. Within the function, `this` refers to the current element in the set.

The `.after()` and `[.insertAfter()](https://api.jquery.com/insertAfter/)` methods perform the same task. The major difference is in the syntax—specifically, in the placement of the content and target. With `.after()`, the content to be inserted comes from the method's argument: `$(target).after(contentToBeInserted)`. With `.insertAfter()`, on the other hand, the content precedes the method and is inserted after the target, which in turn is passed as the `.insertAfter()` method's argument: `$(contentToBeInserted).insertAfter(target)`.

Using the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Content can be created and then inserted after several elements at once:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Each inner `<div>` element gets this new content:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

An element in the DOM can also be selected and inserted after another element:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

If an element selected this way is inserted into a single location elsewhere in the DOM, it will be moved rather than cloned:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

**Important**: If there is more than one target element, however, cloned copies of the inserted element will be created for each target except for the last one.

#### Passing a Function

As of jQuery 1.4, `.after()` supports passing a function that returns the elements to insert.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This example inserts a `<div>` after each paragraph, with each new `<div>` containing the class name(s) of its preceding paragraph.

#### Additional Arguments

Similar to other content-adding methods such as `[.prepend()](https://api.jquery.com/prepend/)` and `[.before()](https://api.jquery.com/before/)`, `.after()` also supports passing in multiple arguments as input. Supported input includes DOM elements, jQuery objects, HTML strings, and arrays of DOM elements.

For example, the following will insert two new `<div>` s and an existing `<div>` after the first paragraph:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Since `.after()` can accept any number of additional arguments, the same result can be achieved by passing in the three `<div>` s as three separate arguments, like so: `$( "p" ).first().after( $newdiv1, newdiv2, existingdiv1 )`. The type and number of arguments will largely depend on the elements that are collected in the code.

### Additional Notes:

- Prior to jQuery 1.9, `.after()` would attempt to add or change nodes in the current jQuery set if the first node in the set was not connected to a document, and in those cases return a new jQuery set rather than the original set. The method might or might not have returned a new result depending on the number or connectedness of its arguments! As of jQuery 1.9, `.after()`, `.before()`, and `.replaceWith()` always return the original unmodified set. Attempting to use these methods on a node without a parent has no effect—that is, neither the set nor the nodes it contains are changed.

- By design, any jQuery constructor or method that accepts an HTML string — [jQuery()](https://api.jquery.com/jQuery/), [.append()](https://api.jquery.com/append/), [.after()](https://api.jquery.com/after/), etc. — can potentially execute code. This can occur by injection of script tags or use of HTML attributes that execute code (for example, `<img onload="">`). Do not use these methods to insert strings obtained from untrusted sources such as URL query parameters, cookies, or form inputs. Doing so can introduce cross-site-scripting (XSS) vulnerabilities. Remove or escape any user input before adding content to the document.


### Example 1

Inserts some HTML after all paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo:

### Example 2

Inserts a DOM element after all paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo:

### Example 3

Inserts a jQuery object (similar to an Array of DOM Elements) after all paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo: