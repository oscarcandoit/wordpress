---
url: https://api.jquery.com/focus-selector/
scraped_at: 2025-10-20T03:28:30.919Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## focus selector

**Description:** Selects element if it is currently focused.

- #### version added: [1.6](https://api.jquery.com/category/version/1.6/)jQuery( ":focus" )


As with other pseudo-class selectors (those that begin with a ":"), it is recommended to precede `:focus` with a tag name or some other selector; otherwise, the universal selector ( "\*" ) is implied. In other words, the bare `$( ":focus" )` is equivalent to `$( "*:focus" )`. If you are looking for the currently focused element, `$( document.activeElement )` will retrieve it without having to search the whole DOM tree.

Adds the focused class to whatever element has focus

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36 | ```<br>``` |

#### Demo: