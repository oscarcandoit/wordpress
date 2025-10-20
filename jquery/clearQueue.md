---
url: https://api.jquery.com/clearQueue/
scraped_at: 2025-10-20T03:07:33.994Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

## .clearQueue( \[queueName \] )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Remove from the queue all items that have not yet been run.

- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.clearQueue( \[queueName \] )](https://api.jquery.com/clearQueue/\#clearQueue-queueName)

  - **queueName**

    Type: [String](http://api.jquery.com/Types/#String)

    A string containing the name of the queue. Defaults to `fx`, the standard effects queue.

When the `.clearQueue()` method is called, all functions on the queue that have not been executed are removed from the queue. When used without an argument, `.clearQueue()` removes the remaining functions from `fx`, the standard effects queue. In this way it is similar to `.stop(true)`. However, while the `.stop()` method is meant to be used only with animations, `.clearQueue()` can also be used to remove any function that has been added to a generic jQuery queue with the `.queue()` method.

Empty the queue.

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>31<br>32<br>33<br>34<br>35<br>36<br>37<br>38<br>39<br>40<br>41<br>42<br>43<br>44<br>45<br>46<br>47<br>48<br>49<br>50<br>51<br>52<br>53<br>54<br>55<br>56<br>57<br>58<br>59<br>60<br>61<br>62 | ```<br>``` |

#### Demo: