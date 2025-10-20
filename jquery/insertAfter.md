---
url: https://api.jquery.com/insertAfter/
scraped_at: 2025-10-20T03:16:52.718Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .insertAfter( target )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Insert every element in the set of matched elements after the target.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.insertAfter( target )](https://api.jquery.com/insertAfter/\#insertAfter-target)

  - **target**

    Type: [Selector](http://api.jquery.com/Types/#Selector) or [htmlString](http://api.jquery.com/Types/#htmlString) or [Element](http://api.jquery.com/Types/#Element) or [Array](http://api.jquery.com/Types/#Array) or [jQuery](http://api.jquery.com/Types/#jQuery)

    A selector, element, array of elements, HTML string, or jQuery object; the matched set of elements will be inserted after the element(s) specified by this parameter.

The `[.after()](https://api.jquery.com/after/)` and `.insertAfter()` methods perform the same task. The major difference is in the syntax—specifically, in the placement of the content and target. With `.after()`, the selector expression preceding the method is the container after which the content is inserted. With `.insertAfter()`, on the other hand, the content precedes the method, either as a selector expression or as markup created on the fly, and it is inserted after the target container.

Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

We can create content and insert it after several elements at once:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Each inner `<div>` element gets this new content:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

We can also select an element on the page and insert it after another:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

If an element selected this way is inserted into a single location elsewhere in the DOM, it will be moved after the target (not cloned) and a new set consisting of the inserted element is returned:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

If there is more than one target element, however, cloned copies of the inserted element will be created for each target after the first, and that new set (the original element plus clones) is returned.

**Before jQuery 1.9,** the append-to-single-element case did not create a new set, but instead returned the original set which made it difficult to use the `.end()` method reliably when being used with an unknown number of elements.

### Additional Notes:

- By design, any jQuery constructor or method that accepts an HTML string — [jQuery()](https://api.jquery.com/jQuery/), [.append()](https://api.jquery.com/append/), [.after()](https://api.jquery.com/after/), etc. — can potentially execute code. This can occur by injection of script tags or use of HTML attributes that execute code (for example, `<img onload="">`). Do not use these methods to insert strings obtained from untrusted sources such as URL query parameters, cookies, or form inputs. Doing so can introduce cross-site-scripting (XSS) vulnerabilities. Remove or escape any user input before adding content to the document.

- jQuery doesn't officially support SVG. Using jQuery methods on SVG documents, unless explicitly documented for that method, might cause unexpected behaviors. Examples of methods that support SVG as of jQuery 3.0 are `addClass` and `removeClass`.


Insert all paragraphs after an element with id of "foo". Same as $( "#foo" ).after( "p" )

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo: