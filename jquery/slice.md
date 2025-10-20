---
url: https://api.jquery.com/slice/
scraped_at: 2025-10-20T03:03:01.216Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .slice( start \[, end \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Reduce the set of matched elements to a subset specified by a range of indices.

- #### version added: [1.1.4](https://api.jquery.com/category/version/1.1.4/) [.slice( start \[, end \] )](https://api.jquery.com/slice/\#slice-start-end)

  - **start**

    Type: [Integer](http://api.jquery.com/Types/#Integer)

    An integer indicating the 0-based position at which the elements begin to be selected. If negative, it indicates an offset from the end of the set.

  - **end**

    Type: [Integer](http://api.jquery.com/Types/#Integer)

    An integer indicating the 0-based position at which the elements stop being selected. If negative, it indicates an offset from the end of the set. If omitted, the range continues until the end of the set.

Given a jQuery object that represents a set of DOM elements, the `.slice()` method constructs a new jQuery object containing a subset of the elements specified by the `start` and, optionally, `end` argument. The supplied `start` index identifies the position of one of the elements in the set; if `end` is omitted, all elements after this one will be included in the result.

Consider a page with a simple list on it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

We can apply this method to the set of list items:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The result of this call is a red background for items 3, 4, and 5. Note that the supplied index is zero-based, and refers to the position of elements within the jQuery object, not within the DOM tree.

The end parameter allows us to limit the selected range even further. For example:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

Now only items 3 and 4 are selected. The index is once again zero-based; the range extends up to but not including the specified index.

#### Negative Indices

The jQuery `.slice()` method is patterned after the JavaScript .slice() method for arrays. One of the features that it mimics is the ability for negative numbers to be passed as either the `start` or `end` parameter. If a negative number is provided, this indicates a position starting from the end of the set, rather than the beginning. For example:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

This time only list item 4 is turned red, since it is the only item in the range between two from the end ( `-2`) and one from the end ( `-1`).

### Example 1

Turns divs yellow based on a random slice.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62 | ```<br>``` |

#### Demo:

### Example 2

Selects all paragraphs, then slices the selection to include only the first element.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 3

Selects all paragraphs, then slices the selection to include only the first and second element.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 4

Selects all paragraphs, then slices the selection to include only the second element.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 5

Selects all paragraphs, then slices the selection to include only the second and third element.

|     |     |
| --- | --- |
| 1 | ```<br>``` |

### Example 6

Selects all paragraphs, then slices the selection to include only the third element.

|     |     |
| --- | --- |
| 1 | ```<br>``` |