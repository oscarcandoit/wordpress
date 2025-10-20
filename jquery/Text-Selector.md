---
url: https://api.jquery.com/text-selector/
scraped_at: 2025-10-20T03:30:08.171Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## text selector

**Description:** Selects all input elements of type text.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":text" )


`$( ":text" )` allows us to select all `<input type="text">` elements. As with other pseudo-class selectors (those that begin with a ":") it is recommended to precede it with a tag name or some other selector; otherwise, the universal selector ( "\*" ) is implied. In other words, the bare `$( ":text" )` is equivalent to `$( "*:text" )`, so `$( "input:text" )` should be used instead.

**Note:** As of jQuery 1.5.2, `:text` selects `input` elements that have no specified `type` attribute (in which case `type="text"` is implied).

This difference in behavior between `$( ":text" )` and `$( "[type=text]" )`, can be seen below:

|     |     |
| --- | --- |
| 1<br>2 | ```<br>``` |

### Additional Notes:

- Because `:text` is a jQuery extension and not part of the CSS specification, queries using `:text` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `[type="text"]` instead.


Finds all text inputs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51 | ```<br>``` |

#### Demo: