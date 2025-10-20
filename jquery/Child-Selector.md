---
url: https://api.jquery.com/child-selector/
scraped_at: 2025-10-20T03:27:28.753Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## child selector

**Description:** Selects all direct child elements specified by "child" of elements specified by "parent".

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( "parent > child" )


**parent:** Any valid selector.

**child:** A selector to filter the child elements.


The child combinator (E **>** F) can be thought of as a more specific form of the descendant combinator (E F) in that it selects only first-level descendants.

Places a border around all list items that are children of <ul class="topnav"> .

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32 | ```<br>``` |

#### Demo: