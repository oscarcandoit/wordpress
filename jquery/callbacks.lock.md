---
url: https://api.jquery.com/callbacks.lock/
scraped_at: 2025-10-20T03:05:30.002Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## callbacks.lock()Returns: [Callbacks](http://api.jquery.com/Types/\#Callbacks)

**Description:** Lock a callback list in its current state.

- #### version added: [1.7](https://api.jquery.com/category/version/1.7/) [callbacks.lock()](https://api.jquery.com/callbacks.lock/\#callbacks-lock)

  - This method does not accept any arguments.

This method returns the Callbacks object onto which it is attached ( `this`).

If the Callbacks object is created with the `"memory"` flag as its argument, additional functions may be added and fired after the callback list is locked.

### Example 1

Use `callbacks.lock()` to lock a callback list to avoid further changes being made to the list state:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22 | ```<br>``` |

### Example 2

Use `callbacks.lock()` to lock a callback list with "memory," and then resume using the list:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60 | ```<br>``` |

#### Demo: