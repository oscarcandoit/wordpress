---
url: https://api.jquery.com/file-selector/
scraped_at: 2025-10-20T03:28:09.598Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## file selector

**Description:** Selects all elements of type file.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":file" )


`:file` is equivalent to `[type="file"]`. As with other pseudo-class selectors (those that begin with a ":") it is recommended to precede it with a tag name or some other selector; otherwise, the universal selector ("\*") is implied. In other words, the bare `$( ":file" )` is equivalent to `$("*:file" )`, so `$( "input:file" )` should be used instead.

### Additional Notes:

- Because `:file` is a jQuery extension and not part of the CSS specification, queries using `:file` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `[type="file"]` instead.


Finds all file inputs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46 | ```<br>``` |

#### Demo: