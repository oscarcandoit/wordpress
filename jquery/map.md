---
url: https://api.jquery.com/map/
scraped_at: 2025-10-20T03:01:44.072Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .map( callback )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Pass each element in the current matched set through a function, producing a new jQuery object containing the return values.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/) [.map( callback )](https://api.jquery.com/map/\#map-callback)

  - **callback**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [Element](http://api.jquery.com/Types/#Element) domElement )
     =>
     [Object](http://api.jquery.com/Types/#Object)

    A function object that will be invoked for each element in the current set.

If you wish to process a plain array or object, use the [jQuery.map()](https://api.jquery.com/jQuery.map/) instead.

As the return value is a jQuery object, which contains an array, it's very common to call `.get()` on the result to work with a basic array.

The `.map()` method is particularly useful for getting or setting the value of a collection of elements. Consider a form with a set of checkboxes in it:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20 | ```<br>``` |

To get a comma-separated list of checkbox `ID` s:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6 | ```<br>``` |

The result of this call is the string, `"two,four,six,eight"`.

Within the callback function, `this` refers to the current DOM element for each iteration. The function can return an individual data item or an array of data items to be inserted into the resulting set. If an array is returned, the elements inside the array are inserted into the set. If the function returns `null` or `undefined`, no element will be inserted.

### Example 1

Build a list of all the values within a form.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo:

### Example 2

A contrived example to show some functionality.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60 | ```<br>``` |

#### Demo:

### Example 3

Equalize the heights of the divs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38 | ```<br>``` |

#### Demo: