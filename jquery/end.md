---
url: https://api.jquery.com/end/
scraped_at: 2025-10-20T03:01:09.506Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .end()Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** End the most recent filtering operation in the current chain and return the set of matched elements to its previous state.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.end()](https://api.jquery.com/end/\#end)

  - This method does not accept any arguments.

Most of jQuery's [DOM traversal](https://api.jquery.com/category/traversing/) methods operate on a jQuery object instance and produce a new one, matching a different set of DOM elements. When this happens, it is as if the new set of elements is pushed onto a stack that is maintained inside the object. Each successive filtering method pushes a new element set onto the stack. If we need an older element set, we can use `end()` to pop the sets back off of the stack.

Suppose we have a couple short lists on a page:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10 | ```<br>``` |

The `end()` method is useful primarily when exploiting jQuery's chaining properties. When not using chaining, we can usually just call up a previous object by variable name, so we don't need to manipulate the stack. With `end()`, though, we can string all the method calls together:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

This chain searches for items with the class `foo` within the first list only and turns their backgrounds red. Then `end()` returns the object to its state before the call to `find()`, so the second `find()` looks for '.bar' inside `<ul class="first">`, not just inside that list's `<li class="foo">`, and turns the matching elements' backgrounds green. The net result is that items 1 and 3 of the first list have a colored background, and none of the items from the second list do.

A long jQuery chain can be visualized as a structured code block, with filtering methods providing the openings of nested blocks and `end()` methods closing them:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

The last `end()` is unnecessary, as we are discarding the jQuery object immediately thereafter. However, when the code is written in this form, the `end()` provides visual symmetry and a sense of completion —making the program, at least to the eyes of some developers, more readable, at the cost of a slight hit to performance as it is an additional function call.

### Example 1

Selects all paragraphs, finds span elements inside these, and reverts the selection back to the paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63<br>64<br>65<br>66<br>67<br>68 | ```<br>``` |

#### Demo:

### Example 2

Selects all paragraphs, finds span elements inside these, and reverts the selection back to the paragraphs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26 | ```<br>``` |

#### Demo: