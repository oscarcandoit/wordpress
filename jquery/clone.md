---
url: https://api.jquery.com/clone/
scraped_at: 2025-10-20T03:16:37.150Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .clone( \[withDataAndEvents \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Create a deep copy of the set of matched elements.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.clone( \[withDataAndEvents \] )](https://api.jquery.com/clone/\#clone-withDataAndEvents)

  - **withDataAndEvents** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether event handlers should be copied along with the elements. As of jQuery 1.4, element data will be copied as well.
- #### version added: [1.5](https://api.jquery.com/category/version/1.5/) [.clone( \[withDataAndEvents \] \[, deepWithDataAndEvents \] )](https://api.jquery.com/clone/\#clone-withDataAndEvents-deepWithDataAndEvents)

  - **withDataAndEvents** (default: `false`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether event handlers and data should be copied along with the elements. The default value is `false`. _\*In jQuery 1.5.0 the default value was incorrectly `true`; it was changed back to `false` in 1.5.1 and up._

  - **deepWithDataAndEvents** (default: `value of withDataAndEvents`)

    Type: [Boolean](http://api.jquery.com/Types/#Boolean)

    A Boolean indicating whether event handlers and data for all children of the cloned element should be copied. By default its value matches the first argument's value (which defaults to `false`).

The `.clone()` method performs a _deep_ copy of the set of matched elements, meaning that it copies the matched elements as well as all of their descendant elements and text nodes.

**Note:** For performance reasons, the dynamic state of certain form elements (e.g., user data typed into `textarea` and user selections made to a `select`) is not copied to the cloned elements. When cloning `input` elements, the dynamic state of the element (e.g., user data typed into text inputs and user selections made to a checkbox) is retained in the cloned elements.

When used in conjunction with one of the insertion methods, `.clone()` is a convenient way to duplicate elements on a page. Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

As shown in the discussion for `[.append()](https://api.jquery.com/append/)`, normally when an element is inserted somewhere in the DOM, it is moved from its old location. So, given the code:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The resulting DOM structure would be:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

To prevent this and instead create a copy of the element, you could write the following:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This would produce:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

**Note:** When using the `.clone()` method, you can modify the cloned elements or their contents before (re-)inserting them into the document.

Normally, any event handlers bound to the original element are _not_ copied to the clone. The optional `withDataAndEvents` parameter allows us to change this behavior, and to instead make copies of all of the event handlers as well, bound to the new copy of the element. As of jQuery 1.4, all element data (attached by the `.data()` method) is also copied to the new copy.

However, objects and arrays within element data are not copied and will continue to be shared between the cloned element and the original element. To deep copy all data, copy each one manually:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

As of jQuery 1.5, `withDataAndEvents` can be optionally enhanced with `deepWithDataAndEvents ` to copy the events and data for all children of the cloned element.

**Note:** Using `.clone()` has the side-effect of producing elements with duplicate `id` attributes, which are supposed to be unique. Where possible, it is recommended to avoid cloning elements with this attribute or using `class` attributes as identifiers instead.

Clones all b elements (and selects the clones) and prepends them to all paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17 | ```<br>``` |

#### Demo: