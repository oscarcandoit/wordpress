---
url: https://api.jquery.com/visible-selector/
scraped_at: 2025-10-20T03:30:11.195Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## visible selector

**Description:** Selects all elements that are visible.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":visible" )


Elements are considered visible if they consume space in the document. Visible elements have a width or height that is greater than zero.

Elements with `visibility: hidden` or `opacity: 0` are considered visible, since they still consume space in the layout.

Elements that are not in a document are considered hidden; jQuery does not have a way to know if they will be visible when appended to a document since it depends on the applicable styles.

This selector is the opposite of the [`:hidden`](https://api.jquery.com/hidden-selector/) selector. So, every element selected by `:visible` isn't selected by `:hidden` and vice versa.

All `option` elements are considered hidden, regardless of their `selected` state.

During animations that hide an element, the element is considered visible until the end of the animation. During animations to show an element, the element is considered visible at the start at the animation.

How `:visible` is calculated was changed in jQuery 1.3.2. The [release notes](https://blog.jquery.com/2009/02/20/jquery-1-3-2-released/) outline the changes in more detail.

jQuery 3 slightly modifies the meaning of `:visible` (and therefore of [`:hidden`](https://api.jquery.com/hidden-selector/)). Starting with this version, elements will be considered `:visible` if they have any layout boxes, including those of zero width and/or height. For example, `br` elements and inline elements with no content will be selected by the `:visible` selector.

### Additional Notes:

- Because `:visible` is a jQuery extension and not part of the CSS specification, queries using `:visible` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:visible` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":visible")`](https://api.jquery.com/filter/).

- Using this selector heavily can have performance implications, as it may force the browser to re-render the page before it can determine visibility. Tracking the visibility of elements via other methods, using a class for example, can provide better performance.


Make all visible divs turn yellow on click.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39 | ```<br>``` |

#### Demo: