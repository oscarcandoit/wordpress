---
url: https://api.jquery.com/ready/
scraped_at: 2025-10-20T02:58:51.231Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .ready( handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Specify a function to execute when the DOM is fully loaded.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.ready( handler )](https://api.jquery.com/ready/\#ready-handler)

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)()

    A function to execute after the DOM is ready.

The `.ready()` method offers a way to run JavaScript code as soon as the page's Document Object Model (DOM) becomes safe to manipulate. This will often be a good time to perform tasks that are needed before the user views or interacts with the page, for example to add event handlers and initialize plugins. When multiple functions are added via successive calls to this method, they run when the DOM is ready in the order in which they are added. As of jQuery 3.0, jQuery ensures that an exception occuring in one handler does not prevent subsequently added handlers from executing.

Most browsers [provide similar functionality](https://caniuse.com/#search=DOMContentLoaded) in the form of a `DOMContentLoaded` event. However, jQuery's `.ready()` method differs in an important and useful way: If the DOM becomes ready and the browser fires `DOMContentLoaded` before the code calls `.ready( handler )`, the function `handler` will still be executed. In contrast, a `DOMContentLoaded` event listener added after the event fires is never executed.

Browsers also provide the `load` event on the `window` object. When this event fires it indicates that all assets on the page have loaded, including images. This event can be watched in jQuery using `$( window ).on( "load", handler )`. In cases where code relies on loaded assets (for example, if the dimensions of an image are required), the code should be placed in a handler for the `load` event instead.

Note that although the DOM always becomes ready before the page is fully loaded, it is _usually not safe_ to attach a `load` event listener in code executed during a `.ready()` handler. For example, scripts can be loaded dynamically long after the page has loaded using methods such as `$.getScript()`. Although handlers added by `.ready()` will always be executed in a dynamically loaded script, the `window`'s `load` event has already occurred and those listeners will never run.

jQuery offers several ways to attach a function that will run when the DOM is ready. All of the following syntaxes are equivalent:

- `$( handler )`
- `$( document ).ready( handler )`
- `$( "document" ).ready( handler )`
- `$( "img" ).ready( handler )`
- `$().ready( handler )`

As of jQuery 3.0, only the first syntax is recommended; the other syntaxes still work but are deprecated. This is because the selection has no bearing on the behavior of the `.ready()` method, which is inefficient and can lead to incorrect assumptions about the method's behavior. For example, the third syntax works with `"document"` which selects nothing. The fourth syntax waits for the document to be ready but implies (incorrectly) that it waits for images to become ready.

There is also `$(document).on( "ready", handler )`, _deprecated as of jQuery 1.8 and removed in jQuery 3.0_. Note that if the DOM becomes ready before this event is attached, the handler _will not be executed_.

The `.ready()` method is typically used with an anonymous function:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Which is equivalent to the recommended way of calling:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

#### Aliasing the jQuery Object

When `[$.noConflict()](https://api.jquery.com/jQuery.noConflict/)` is used to avoid namespace conflicts, the `$` shortcut is no longer available. However, the `.ready()` handler is passed a reference to the `jQuery` object that called the method. This allows the handler to use a jQuery object, for example as `$`, without knowing its aliased name:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

Display a message when the DOM is loaded.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27 | ```<br>``` |

#### Demo: