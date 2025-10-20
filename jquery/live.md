---
url: https://api.jquery.com/live/
scraped_at: 2025-10-20T03:13:13.298Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .live( events, handler )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [1.7](https://api.jquery.com/category/version/1.7/), removed: [1.9](https://api.jquery.com/category/version/1.9/)

**Description:** Attach an event handler for all elements which match the current selector, now and in the future.

- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [.live( events, handler )](https://api.jquery.com/live/\#live-events-handler)

  - **events**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing a JavaScript event type, such as "click" or "keydown." As of jQuery 1.4 the string can contain multiple, space-separated event types or custom event names.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute at the time the event is triggered.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.live( events \[, data \], handler )](https://api.jquery.com/live/\#live-events-data-handler)

  - **events**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing a JavaScript event type, such as "click" or "keydown." As of jQuery 1.4 the string can contain multiple, space-separated event types or custom event names.

  - **data**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    An object containing data that will be passed to the event handler.

  - **handler**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Event](http://api.jquery.com/Types/#Event) eventObject )

    A function to execute at the time the event is triggered.
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.live( events )](https://api.jquery.com/live/\#live-events)

  - **events**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    A plain object of one or more JavaScript event types and functions to execute for them.

Note: This API has been removed in jQuery 1.9; please use [`on()`](https://api.jquery.com/on/) instead.

This method provides a means to attach delegated event handlers to the `document` element of a page, which simplifies the use of event handlers when content is dynamically added to a page. See the discussion of direct versus delegated events in the [`.on()`](https://api.jquery.com/on/) method for more information.

Rewriting the `.live()` method in terms of its successors is straightforward; these are templates for equivalent calls for all three event attachment methods:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

The `events` argument can either be a space-separated list of event type names and optional namespaces, or an object of event name strings and handlers. The `data` argument is optional and can be omitted. For example, the following three method calls are functionally equivalent (but see below for more effective and performant ways to attach delegated event handlers):

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

Use of the `.live()` method is no longer recommended since later versions of jQuery offer better methods that do not have its drawbacks. In particular, the following issues arise with the use of `.live()`:

- jQuery attempts to retrieve the elements specified by the selector before calling the `.live()` method, which may be time-consuming on large documents.
- Chaining methods is not supported. For example, `$( "a" ).find( ".offsite, .external" ).live( ... ); ` is _not_ valid and does not work as expected.
- Since all `.live()` events are attached at the `document` element, events take the longest and slowest possible path before they are handled.
- On mobile iOS (iPhone, iPad and iPod Touch) the `click` event does not bubble to the document body for most elements and cannot be used with `.live()` without applying one of the following workarounds:

1. Use natively clickable elements such as `a` or `button`, as both of these do bubble to `document`.
2. Use `.on()` or `.delegate()` attached to an element below the level of `document.body`, since mobile iOS does bubble within the body.
3. Apply the CSS style `cursor:pointer` to the element that needs to bubble clicks (or a parent including `document.documentElement`). Note however, this will disable copy\\paste on the element and cause it to be highlighted when touched.
- Calling [`event.stopPropagation()`](https://api.jquery.com/event.stopPropagation/) in the event handler is ineffective in stopping event handlers attached lower in the document; the event has already propagated to `document`.
- The `.live()` method interacts with other event methods in ways that can be surprising, e.g., `$( document ).off( "click" )` removes all click handlers attached by any call to `.live()`!

For pages still using `.live()`, this list of version-specific differences may be helpful:

- Before jQuery 1.7, to stop further handlers from executing after one bound using `.live()`, the handler must return `false`. Calling `.stopPropagation()` will not accomplish this.
- As of **jQuery 1.4** the `.live()` method supports custom events as well as _all JavaScript events that bubble_. It also supports certain events that don't bubble, including `change`, `submit`, `focus` and `blur`.
- In **jQuery 1.3.x** only the following JavaScript events could be bound: `click`, `dblclick`, `keydown`, `keypress`, `keyup`, `mousedown`, `mousemove`, `mouseout`, `mouseover`, and `mouseup`.

### Example 1

Cancel a default action and prevent it from bubbling up by returning false.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 2

Cancel only the default action by using the preventDefault method.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

### Example 3

Bind custom events with .live().

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12 | ```<br>``` |

### Example 4

Use an object to bind multiple live event handlers. Note that .live() calls the click, mouseover, and mouseout event handlers for all paragraphs--even new ones.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11 | ```<br>``` |