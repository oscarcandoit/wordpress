---
url: https://api.jquery.com/addBack/
scraped_at: 2025-10-20T02:59:59.055Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .addBack( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Add the previous set of elements on the stack to the current set, optionally filtered by a selector.

- #### version added: [1.8](https://api.jquery.com/category/version/1.8/) [.addBack( \[selector \] )](https://api.jquery.com/addBack/\#addBack-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A string containing a selector expression to match the current set of elements against.

As described in the discussion for `[.end()](https://api.jquery.com/end/)`, jQuery objects maintain an internal stack that keeps track of changes to the matched set of elements. When one of the DOM traversal methods is called, the new set of elements is pushed onto the stack. If the previous set of elements is desired as well, `.addBack()` can help.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

The result of the following code is a red background behind items 3, 4 and 5:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

First, the initial selector locates item 3, initializing the stack with the set containing just this item. The call to `.nextAll()` then pushes the set of items 4 and 5 onto the stack. Finally, the `.addBack()` invocation merges these two sets together, creating a jQuery object that points to all three items in document order: `{[<li.third-item>,<li>,<li> ]}`.

The `.addBack()` method causes the previous set of DOM elements in the traversal stack to be added to the current set. In the first example, the top stack contains the set resulting from `.find("p")`. In the second example, `.addBack()` adds the previous set of elements on the stack — in this case `$("div.after-addback")` — to the current set, selecting both the div and its enclosed paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55 | ```<br>``` |

#### Demo: