---
url: https://api.jquery.com/Multiple-Selector/
scraped_at: 2025-10-20T03:22:28.182Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## multiple selector

**Description:** Selects the combined results of all the specified selectors.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "selector1, selector2, selectorN" )


**selector1:** Any valid selector.

**selector2:** Another valid selector.

**selectorN:** As many more valid selectors as you like.


You can specify any number of selectors to combine into a single result. This multiple expression combinator is an efficient way to select disparate elements. The order of the DOM elements in the returned jQuery object may not be identical, as they will be in document order. An alternative to this combinator is the . [add()](https://api.jquery.com/add/) method.

### Example 1

Finds the elements that match any of these three selectors.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31 | ```<br>``` |

#### Demo:

### Example 2

Show the order in the jQuery object.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47 | ```<br>``` |

#### Demo: