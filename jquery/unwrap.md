---
url: https://api.jquery.com/unwrap/
scraped_at: 2025-10-20T03:17:23.250Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .unwrap()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove the parents of the set of matched elements from the DOM, leaving the matched elements in their place.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.unwrap()](https://api.jquery.com/unwrap/\#unwrap)

  - This signature does not accept any arguments.
- #### version added: [3.0](https://api.jquery.com/category/version/3.0/) [.unwrap( \[selector \] )](https://api.jquery.com/unwrap/\#unwrap-selector)

  - **selector**

    Type: [String](http://api.jquery.com/Types/#String)

    A selector to check the parent element against. If an element's parent does not match the selector, the element won't be unwrapped.

The `.unwrap()` method removes the element's parent and returns the unwrapped content. This is effectively the inverse of the `[.wrap()](https://api.jquery.com/wrap/)` method. The matched elements (and their siblings, if any) replace their parents within the DOM structure.

Wrap/unwrap a div around each of the paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34 | ```<br>``` |

#### Demo: