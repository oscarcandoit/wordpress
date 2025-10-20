---
url: https://api.jquery.com/jquery/
scraped_at: 2025-10-20T02:58:28.741Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Return a collection of matched elements either found in the DOM based on passed argument(s) or created by passing an HTML string.

#### Contents:

- [jQuery( selector \[, context \] )](https://api.jquery.com/jquery/#jQuery1)  - [jQuery( selector \[, context \] )](https://api.jquery.com/jquery/#jQuery-selector-context)
  - [jQuery( element )](https://api.jquery.com/jquery/#jQuery-element)
  - [jQuery( elementArray )](https://api.jquery.com/jquery/#jQuery-elementArray)
  - [jQuery( object )](https://api.jquery.com/jquery/#jQuery-object)
  - [jQuery( selection )](https://api.jquery.com/jquery/#jQuery-selection)
  - [jQuery()](https://api.jquery.com/jquery/#jQuery)
- [jQuery( html \[, ownerDocument \] )](https://api.jquery.com/jquery/#jQuery2)  - [jQuery( html \[, ownerDocument \] )](https://api.jquery.com/jquery/#jQuery-html-ownerDocument)
  - [jQuery( html, attributes )](https://api.jquery.com/jquery/#jQuery-html-attributes)
- [jQuery( callback )](https://api.jquery.com/jquery/#jQuery3)   - [jQuery( callback )](https://api.jquery.com/jquery/#jQuery-callback)

## jQuery( selector \[, context \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Accepts a string containing a CSS selector which is then used to match a set of elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery( selector \[, context \] )](https://api.jquery.com/jquery/\#jQuery-selector-context)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression

  - **context**

    Type: [Element](http://api.jquery.com/Types/#Element) or [jQuery](http://api.jquery.com/Types/#jQuery) or [Selector](http://api.jquery.com/Types/#Selector)

    A DOM Element, Document, jQuery or selector to use as context
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery( element )](https://api.jquery.com/jquery/\#jQuery-element)

  - **element**

    Type: [Element](http://api.jquery.com/Types/#Element)

    A DOM element to wrap in a jQuery object.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery( elementArray )](https://api.jquery.com/jquery/\#jQuery-elementArray)

  - **elementArray**

    Type: [Array](http://api.jquery.com/Types/#Array)

    An array containing a set of DOM elements to wrap in a jQuery object.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery( object )](https://api.jquery.com/jquery/\#jQuery-object)

  - **object**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    A plain object to wrap in a jQuery object.
- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery( selection )](https://api.jquery.com/jquery/\#jQuery-selection)

  - **selection**

    Type: [jQuery](http://api.jquery.com/Types/#jQuery)

    An existing jQuery object to clone.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [jQuery()](https://api.jquery.com/jquery/\#jQuery)

  - This signature does not accept any arguments.

In the first formulation listed above, `jQuery()` — which can also be written as `$()` — searches through the DOM for any elements that match the provided selector and creates a new jQuery object that references these elements:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

If no elements match the provided selector, the new jQuery object is "empty"; that is, it contains no elements and has `[.length](https://api.jquery.com/length/)` property of 0.

#### Selector Context

By default, selectors perform their searches within the DOM starting at the document root. However, an alternate context can be given for the search by using the optional second parameter to the `$()` function. For example, to do a search within an event handler, the search can be restricted like so:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

When the search for the span selector is restricted to the context of `this`, only spans within the clicked element will get the additional class.

Internally, selector context is implemented with the `.find()` method, so `$( "span", this )` is equivalent to `$( this ).find( "span" )`.

#### Using DOM elements

The second and third formulations of this function create a jQuery object using one or more DOM elements that were already selected in some other way. A jQuery object is created from the array elements in the order they appeared in the array; unlike most other multi-element jQuery operations, the elements are not sorted in DOM order. Elements will be copied from the array as-is and won't be unwrapped if they're already jQuery collections.

Please note that although you can pass text nodes and comment nodes into a jQuery collection this way, most operations don't support them. The few that do will have an explicit note on their API documentation page.

A common use of single-DOM-element construction is to call jQuery methods on an element that has been passed to a callback function through the keyword `this`:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

This example causes elements to be hidden with a sliding animation when clicked. Because the handler receives the clicked item in the `this` keyword as a bare DOM element, the element must be passed to the `$()` function before applying jQuery methods to it.

XML data returned from an Ajax call can be passed to the `$()` function so individual elements of the XML structure can be retrieved using `.find()` and other DOM traversal methods.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

#### Cloning jQuery Objects

When a jQuery object is passed to the `$()` function, a clone of the object is created. This new jQuery object references the same DOM elements as the initial one.

#### Returning an Empty Set

Calling the `jQuery()` method with _no arguments_ returns an empty jQuery set (with a `[.length](https://api.jquery.com/length/)` property of 0). Similarly, if an argument of `null`, `undefined`, an empty array ( `[]`), or an empty string ( `""`) is passed, the set contains no elements.

#### Working With Plain Objects

At present, the only operations supported on plain JavaScript objects wrapped in jQuery are: `.data()`, `.prop()`, `.on()`, `.off()`, `.trigger()` and `.triggerHandler()`. The use of `.data()` (or any method requiring `.data()`) on a plain object will result in a new property on the object called jQuery{randomNumber} (eg. jQuery123456789).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

Should `.trigger( "eventName" )` be used, it will search for an "eventName" property on the object and attempt to execute it after any attached jQuery handlers are executed. It does not check whether the property is a function or not. To avoid this behavior, `.triggerHandler( "eventName" )` should be used instead.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 1

Find all p elements that are children of a div element and apply a border to them.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19 | ```<br>``` |

#### Demo:

### Example 2

Find all inputs of type radio within the first form in the document.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 3

Find all div elements within an XML document from an Ajax response.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

Set the background color of the page to black.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 5

Hide all the input elements within a form.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

## jQuery( html \[, ownerDocument \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Creates DOM elements on the fly from the provided string of raw HTML.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery( html \[, ownerDocument \] )](https://api.jquery.com/jquery/\#jQuery-html-ownerDocument)

  - **html**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString)

    A string of HTML to create on the fly. Note that this parses HTML, **not** XML.

  - **ownerDocument**

    Type: [Document](http://api.jquery.com/Types/#Document)

    A document in which the new elements will be created.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [jQuery( html, attributes )](https://api.jquery.com/jquery/\#jQuery-html-attributes)

  - **html**

    Type: [htmlString](http://api.jquery.com/Types/#htmlString)

    A string defining a single, standalone, HTML element (e.g. <div/> or <div></div>).

  - **attributes**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object of attributes, events, and methods to call on the newly-created element.

#### Creating New Elements

If a string is passed as the parameter to `$()`, jQuery examines the string to see if it looks like HTML (i.e., it starts with `<tag ... >`). If not, the string is interpreted as a selector expression, as explained above. But if the string appears to be an HTML snippet, jQuery attempts to create new DOM elements as described by the HTML. Then a jQuery object is created and returned that refers to these elements. You can perform any of the usual jQuery methods on this object:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

For explicit parsing of a string to HTML, use the [$.parseHTML()](https://api.jquery.com/jQuery.parseHTML/) method.

By default, elements are created with an `.ownerDocument` matching the document into which the jQuery library was loaded. Elements being injected into a different document should be created using that document, e.g., `$("<p>hello iframe</p>", $("#myiframe").prop("contentWindow").document)`.

If the HTML is more complex than a single tag without attributes, as it is in the above example, the actual creation of the elements is handled by the browser's `.innerHTML` mechanism. In most cases, jQuery creates a new `<div>` element and sets the `innerHTML` property of the element to the HTML snippet that was passed in. When the parameter has a single tag (with optional closing tag or quick-closing) — `$( "<img />" )` or `$( "<img>" )`, `$( "<a></a>" )` or `$( "<a>" )` — jQuery creates the element using the native JavaScript `.createElement()` function.

When passing in complex HTML, some browsers may not generate a DOM that exactly replicates the HTML source provided. As mentioned, jQuery uses the browser's `.innerHTML` property to parse the passed HTML and insert it into the current document. During this process, some browsers filter out certain elements such as `<html>`, `<title>`, or `<head>` elements. As a result, the elements inserted may not be representative of the original string passed.

Filtering isn't, however, limited to these tags. For example, Internet Explorer prior to version 8 will also convert all `href` properties on links to absolute URLs, and Internet Explorer prior to version 9 will not correctly handle HTML5 elements without the addition of a separate [compatibility layer](https://github.com/afarkas/html5shiv).

To ensure cross-platform compatibility, the snippet must be well-formed. Tags that can contain other elements should be paired with a closing tag:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Tags that cannot contain elements may be quick-closed or not:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

When passing HTML to `jQuery()`, note that text nodes are not treated as DOM elements. With the exception of a few methods (such as `.content()`), they are generally ignored or removed. E.g:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

This behavior is expected. **As of jQuery 1.9.0** (and unless using the [jQuery Migrate plugin](https://github.com/jquery/jquery-migrate/#readme)), `jQuery()` requires the HTML string to start with a `<` (i.e text nodes cannot appear at the front of the HTML string).

**As of jQuery 1.4**, the second argument to `jQuery()` can accept a plain object consisting of a superset of the properties that can be passed to the [.attr()](https://api.jquery.com/attr/) method.

**Important:** If the second argument is passed, the HTML string in the first argument must represent a simple element with no attributes. **As of jQuery 1.4**, any [event type](https://api.jquery.com/category/events/) can be passed in, and the following jQuery methods can be called: [val](https://api.jquery.com/val/), [css](https://api.jquery.com/css/), [html](https://api.jquery.com/html/), [text](https://api.jquery.com/text/), [data](https://api.jquery.com/data/), [width](https://api.jquery.com/width/), [height](https://api.jquery.com/height/), or [offset](https://api.jquery.com/offset/).

**As of jQuery 1.8**, any jQuery instance method (a method of `jQuery.fn`) can be used as a property of the object passed to the second parameter:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

The name `"class"` must be quoted in the object since it is a JavaScript reserved word, and `"className"` cannot be used since it refers to the DOM property, not the attribute.

While the second argument is convenient, its flexibility can lead to unintended consequences (e.g. `$( "<input>", {size: "4"} )` calling the `.size()` method instead of setting the size attribute). The previous code block could thus be written instead as:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

### Example 1

Create a div element (and all of its contents) dynamically and append it to the body element. Internally, an element is created and its innerHTML property set to the given markup.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 2

Create some DOM elements.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8 | ```<br>``` |

## jQuery( callback )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Binds a function to be executed when the DOM has finished loading.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [jQuery( callback )](https://api.jquery.com/jquery/\#jQuery-callback)

  - **callback**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    The function to execute when the DOM is ready.

This function behaves just like `$( document ).ready()`, in that it should be used to wrap other `$()` operations on your page that depend on the DOM being ready. While this function is, technically, chainable, there really isn't much use for chaining against it.

### Example 1

Execute the function when the DOM is ready to be used.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 2

Use both the shortcut for $(document).ready() and the argument to write failsafe jQuery code using the $ alias, without relying on the global alias.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |