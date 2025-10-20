---
url: https://api.jquery.com/reset-selector/
scraped_at: 2025-10-20T03:29:48.303Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## reset selector

**Description:** Selects all elements of type reset.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/)jQuery( ":reset" )


`:reset` is equivalent to `[type="reset"]`

### Additional Notes:

- Because `:reset` is a jQuery extension and not part of the CSS specification, queries using `:reset` cannot take advantage of the performance boost provided by the native DOM `querySelectorAll()` method. For better performance in modern browsers, use `[type="reset"]` instead.


Finds all reset inputs.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50 | ```<br>``` |

#### Demo: