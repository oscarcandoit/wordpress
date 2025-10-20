---
url: https://api.jquery.com/animated-selector/
scraped_at: 2025-10-20T03:27:41.847Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## animated selector

**Description:** Select all elements that are in the progress of an animation at the time the selector is run.

- #### version added: [1.2](https://api.jquery.com/category/version/1.2/)jQuery( ":animated" )


**Note:** If you use a custom jQuery build _without the effects module_, the `:animated` selector will throw an error.

### Additional Notes:

- Because `:animated` is a jQuery extension and not part of the CSS specification, queries using `:animated` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:animated` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":animated")`](https://api.jquery.com/filter/).


Change the color of any div that is animated.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42 | ```<br>``` |

#### Demo: