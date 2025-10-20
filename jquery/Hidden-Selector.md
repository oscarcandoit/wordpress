---
url: https://api.jquery.com/hidden-selector/
scraped_at: 2025-10-20T03:28:38.638Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## hidden selector

**Description:** Selects all elements that are hidden.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":hidden" )


Elements can be considered hidden for several reasons:

- They have a CSS `display` value of `none`.
- They are form elements with `type="hidden"`.
- Their width and height are explicitly set to 0.
- An ancestor element is hidden, so the element is not shown on the page.

Elements with `visibility: hidden` or `opacity: 0` are considered to be visible, since they still consume space in the layout. During animations that hide an element, the element is considered to be visible until the end of the animation.

Elements that are not in a document are not considered to be visible; jQuery does not have a way to know if they will be visible when appended to a document since it depends on the applicable styles.

This selector is the opposite of the [`:visible`](https://api.jquery.com/visible-selector/) selector. So, every element selected by `:hidden` isn't selected by `:visible` and vice versa.

During animations to show an element, the element is considered to be visible at the start of the animation.

How `:hidden` is determined was changed in jQuery 1.3.2. An element is assumed to be hidden if it or any of its parents consumes no space in the document. CSS visibility isn't taken into account (therefore `$( elem ).css( "visibility", "hidden" ).is( ":hidden" ) == false`). The [release notes](https://blog.jquery.com/2009/02/20/jquery-1-3-2-released/) outline the changes in more detail.

jQuery 3 slightly modifies the meaning of `:hidden` (and therefore of [`:visible`](https://api.jquery.com/visible-selector/)). Starting with this version, elements will be considered `:hidden` if they don't have any layout boxes. For example, `br` elements and inline elements with no content will not be selected by the `:hidden` selector.

### Additional Notes:

- Because `:hidden` is a jQuery extension and not part of the CSS specification, queries using `:hidden` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:hidden` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":hidden")`](https://api.jquery.com/filter/).

- Using this selector heavily can have performance implications, as it may force the browser to re-render the page before it can determine visibility. Tracking the visibility of elements via other methods, using a class for example, can provide better performance.


Shows all hidden divs and counts hidden inputs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53 | ```<br>``` |

#### Demo: