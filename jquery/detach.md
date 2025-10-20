---
url: https://api.jquery.com/detach/
scraped_at: 2025-10-20T03:16:40.991Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .detach( \[selector \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove the set of matched elements from the DOM.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.detach( \[selector \] )](https://api.jquery.com/detach/\#detach-selector)

  - **selector**

    Type: [Selector](http://api.jquery.com/Types/#Selector)

    A selector expression that filters the set of matched elements to be removed.

The `.detach()` method is the same as `[.remove()](https://api.jquery.com/remove/)`, except that `.detach()` keeps all jQuery data associated with the removed elements. This method is useful when removed elements are to be reinserted into the DOM at a later time.

Detach all paragraphs from the DOM

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40 | ```<br>``` |

#### Demo: