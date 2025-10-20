---
url: https://api.jquery.com/not-selector/
scraped_at: 2025-10-20T03:22:38.214Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## not selector

**Description:** Selects all elements that do not match the given selector.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":not(selector)" )


**selector:** A selector with which to filter by.


All selectors are accepted inside `:not()`, for example: `:not(div a)` and `:not(div,a)`.

### Additional Notes

The `[.not()](https://api.jquery.com/not/)` method will end up providing you with more readable selections than pushing complex selectors or variables into a `:not()` selector filter. In most cases, it is a better choice.

Finds all inputs that are not checked and highlights the next sibling span. Notice there is no change when clicking the checkboxes since no click events have been linked.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29 | ```<br>``` |

#### Demo: