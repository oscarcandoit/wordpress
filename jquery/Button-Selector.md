---
url: https://api.jquery.com/button-selector/
scraped_at: 2025-10-20T03:27:45.219Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## button selector

**Description:** Selects all button elements and elements of type button.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":button" )


An equivalent selector to `$( ":button" )` using valid CSS is `$( "button, input[type='button']" )`.

### Additional Notes:

- Because `:button` is a jQuery extension and not part of the CSS specification, queries using `:button` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. To achieve the best performance when using `:button` to select elements, first select the elements using a pure CSS selector, then use [`.filter(":button")`](https://api.jquery.com/filter/).


Find all button inputs and mark them.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62<br>63 | ```<br>``` |

#### Demo: