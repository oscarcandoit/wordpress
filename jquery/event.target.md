---
url: https://api.jquery.com/event.target/
scraped_at: 2025-10-20T03:12:09.135Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## event.targetReturns: [Element](http://api.jquery.com/Types/\#Element)

**Description:** The DOM element that initiated the event.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)event.target


The `target` property can be the element that registered for the event or a descendant of it. It is often useful to compare `event.target` to `this` in order to determine if the event is being handled due to event bubbling. This property is very useful in event delegation, when events bubble.

### Example 1

Display the tag's name on click

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 2

Implements a simple event delegation: The click handler is added to an unordered list, and the children of its li children are hidden. Clicking one of the li children toggles (see toggle()) their children.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: