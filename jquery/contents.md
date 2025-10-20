---
url: https://api.jquery.com/contents/
scraped_at: 2025-10-20T03:00:54.454Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .contents()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Get the children of each element in the set of matched elements, including text and comment nodes.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.contents()](https://api.jquery.com/contents/\#contents)

  - This method does not accept any arguments.

Given a jQuery object that represents a set of DOM elements, the `.contents()` method allows us to search through the immediate children of these elements in the DOM tree and construct a new jQuery object from the matching elements. The `.contents()` and `.children()` methods are similar, except that the former includes text nodes and comment nodes as well as HTML elements in the resulting jQuery object. Please note that most jQuery operations don't support text nodes and comment nodes. The few that do will have an explicit note on their API documentation page.

The `.contents()` method can also be used to get the content document of an iframe, if the iframe is on the same domain as the main page.

**As of jQuery 3.2**, `.contents()` returns contents of `<template>` elements as well.

Consider a simple `<div>` with a number of text nodes, each of which is separated by two line break elements ( `<br>`):

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

We can employ the `.contents()` method to help convert this blob of text into three well-formed paragraphs:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9 | ```<br>``` |

This code first retrieves the contents of `<div class="container">` and then filters it for text nodes, which are wrapped in paragraph tags. This is accomplished by testing the [`.nodeType` property](https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeType) of the element. This DOM property holds a numeric code indicating the node's type; text nodes use the code 3. The contents are again filtered, this time for `<br />` elements, and these elements are removed.

### Example 1

Find all the text nodes inside a paragraph and wrap them with a bold tag.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

#### Demo:

### Example 2

Change the background color of links inside of an iframe.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

#### Demo: