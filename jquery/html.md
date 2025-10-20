---
url: https://api.jquery.com/html/
scraped_at: 2025-10-20T03:16:47.373Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the HTML contents of the first element in the set of matched elements or set the HTML contents of every matched element.

#### Contents:

- [.html()](https://api.jquery.com/html/#html1)  - [.html()](https://api.jquery.com/html/#html)
- [.html( htmlString )](https://api.jquery.com/html/#html2)  - [.html( htmlString )](https://api.jquery.com/html/#html-htmlString)
  - [.html( function )](https://api.jquery.com/html/#html-function)

## .html()Returns: [String](http://api.jquery.com/Types/\#String)

**Description:** Get the HTML contents of the first element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.html()](https://api.jquery.com/html/\#html)

  - This method does not accept any arguments.

This method is not available on XML documents.

In an HTML document, `.html()` can be used to get the contents of any element. If the selector expression matches more than one element, only the first match will have its HTML content returned. Consider this code:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

In order for the following `<div>`'s content to be retrieved, it would have to be the first one with `class="demo-container"` in the document:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

The result would look like this:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This method uses the browser's `innerHTML` property. Some browsers may not return HTML that exactly replicates the HTML source in an original document. For example, Internet Explorer sometimes leaves off the quotes around attribute values if they contain only alphanumeric characters.

### Additional Notes:

- By design, any jQuery constructor or method that accepts an HTML string — [jQuery()](https://api.jquery.com/jQuery/), [.append()](https://api.jquery.com/append/), [.after()](https://api.jquery.com/after/), etc. — can potentially execute code. This can occur by injection of script tags or use of HTML attributes that execute code (for example, `<img onload="">`). Do not use these methods to insert strings obtained from untrusted sources such as URL query parameters, cookies, or form inputs. Doing so can introduce cross-site-scripting (XSS) vulnerabilities. Remove or escape any user input before adding content to the document.


Click a paragraph to convert it from html to text.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42 | ```<br>``` |

#### Demo:

## .html( htmlString )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the HTML contents of each element in the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.html( htmlString )](https://api.jquery.com/html/\#html-htmlString)

  - **htmlString**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString)

    A string of HTML to set as the content of each matched element.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.html( function )](https://api.jquery.com/html/\#html-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [htmlString](http://api.jquery.com/Types/#htmlString) oldhtml )
     =>
     [htmlString](http://api.jquery.com/Types/#htmlString)

    A function returning the HTML content to set. Receives the
     index position of the element in the set and the old HTML value as arguments.
     jQuery empties the element before calling the function;
     use the oldhtml argument to reference the previous content.
     Within the function, `this` refers to the current element in the set.

The `.html()` method is not available in XML documents.

When `.html()` is used to set an element's content,
any content that was in that element is completely replaced by the new content.
Additionally, jQuery removes other constructs such as data and event
handlers from child elements before replacing those elements with the new content.

Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

The content of `<div class="demo-container">` can be set like this:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

That line of code will replace everything inside `<div class="demo-container">`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

As of jQuery 1.4, the `.html()` method allows the HTML content to be set by passing in a function.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Given a document with six paragraphs, this example will set the HTML of `<div class="demo-container">` to `<p>All new content for <em>6 paragraphs!</em></p>`.

This method uses the browser's `innerHTML` property. Some browsers may not generate a DOM that exactly replicates the HTML source provided. For example, Internet Explorer prior to version 8 will convert all `href` properties on links to absolute URLs, and Internet Explorer prior to version 9 will not correctly handle HTML5 elements without the addition of a separate [compatibility layer](https://github.com/afarkas/html5shiv).

To set the content of a `<script>` element, which does not contain HTML, use the [`.text()`](https://api.jquery.com/text/) method and not `.html()`.

**Note:** In Internet Explorer up to and including version 9, setting the text content of an HTML element may corrupt the text nodes of its children that are being removed from the document as a result of the operation. If you are keeping references to these DOM elements and need them to be unchanged, use `.empty().html( string )` instead of `.html(string)` so that the elements are removed from the document before the new string is assigned to the element.

### Example 1

Add some html to each div.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25 | ```<br>``` |

#### Demo:

### Example 2

Add some html to each div then immediately do further manipulations to the inserted html.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo: