---
url: https://api.jquery.com/each/
scraped_at: 2025-10-20T03:01:02.814Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .each( function )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Iterate over a jQuery object, executing a function for each matched element.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.each( function )](https://api.jquery.com/each/\#each-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Element](http://api.jquery.com/Types/#Element) element )

    A function to execute for each matched element.

The `.each()` method is designed to make DOM looping constructs concise and less error-prone. When called it iterates over the DOM elements that are part of the jQuery object. Each time the callback runs, it is passed the current loop iteration, beginning from 0. More importantly, the callback is fired in the context of the current DOM element, so the keyword `this` refers to the element.

Suppose you have a simple unordered list on the page:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4 | ```<br>``` |

You can select the list items and iterate across them:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

A message is thus logged for each item in the list:

`0: foo`

`1: bar`

You can stop the loop from within the callback function by returning `false`.

Note: most jQuery methods that return a jQuery object also loop through the set of elements in the jQuery collection — a process known as _implicit iteration_. When this occurs, it is often unnecessary to _explicitly_ iterate with the `.each()` method:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

### Example 1

Iterate over three divs and sets their color property.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo:

### Example 2

To access a jQuery object instead of the regular DOM element, use `$( this )`. For example:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40 | ```<br>``` |

#### Demo:

### Example 3

Use `return false` to break out of each() loops early.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48 | ```<br>``` |

#### Demo: