---
url: https://api.jquery.com/die/
scraped_at: 2025-10-20T03:09:54.361Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .die()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)version deprecated: [1.7](https://api.jquery.com/category/version/1.7/), removed: [1.9](https://api.jquery.com/category/version/1.9/)

**Description:** Remove event handlers previously attached using `.live()` from the elements.

- #### version added: [1.4.1](https://api.jquery.com/category/version/1.4.1/) [.die()](https://api.jquery.com/die/\#die)

  - This signature does not accept any arguments.
- #### version added: [1.3](https://api.jquery.com/category/version/1.3/) [.die( eventType \[, handler \] )](https://api.jquery.com/die/\#die-eventType-handler)

  - **eventType**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing a JavaScript event type, such as `click` or `keydown`.

  - **handler**

    Type: [String](http://api.jquery.com/Types/#String)

    The function that is no longer to be executed.
- #### version added: [1.4.3](https://api.jquery.com/category/version/1.4.3/) [.die( events )](https://api.jquery.com/die/\#die-events)

  - **events**

    Type: [PlainObject](http://api.jquery.com/Types/#PlainObject)

    A plain object of one or more event types, such as `click` or `keydown` and their corresponding functions that are no longer to be executed.

Note: This API has been removed in jQuery 1.9; please use [`on()`](https://api.jquery.com/on/) instead.

Any handler that has been attached with `.live()` can be removed with `.die()`. This method is analogous to calling `.off()` with no arguments, which is used to remove all handlers attached with `.on()`.
See the discussions of `.live()` and `.off()` for further details.

If used without an argument, .die() removes _all_ event handlers previously attached using `.live()` from the elements.

**As of jQuery 1.7**, use of `.die()` (and its complementary method, `.live()`) is not recommended. Instead, use [`.off()`](https://api.jquery.com/off/) to remove event handlers bound with [`.on()`](https://api.jquery.com/on/)

**Note:** In order for .die() to function correctly, the selector used with it must match exactly the selector initially used with .live().

### Example 1

To unbind all live events from all paragraphs, write:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 2

To unbind all live click events from all paragraphs, write:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 3

To unbind just one previously bound handler, pass the function in as the second argument:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |